---
title: Connect an app to Attio through OAuth - Attio Docs
url: https://docs.attio.com/rest-api/tutorials/connect-an-app-through-oauth
crawled_at: unknown
depth: 2
parent_url: https://docs.attio.com/rest-api/overview
---

# Connect an app to Attio through OAuth - Attio Docs

**Source:** [https://docs.attio.com/rest-api/tutorials/connect-an-app-through-oauth](https://docs.attio.com/rest-api/tutorials/connect-an-app-through-oauth)

[Attio Docs home page![light logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/light.svg)![dark logo](https://mintlify.s3.us-west-1.amazonaws.com/attio/logo/dark.svg)](https://docs.attio.com/)
Search...
⌘KAsk AI
Search...
Navigation
Tutorials
Connect an app to Attio through OAuth
[Overview](https://docs.attio.com/docs/overview)[App SDK](https://docs.attio.com/sdk/introduction)[REST API](https://docs.attio.com/rest-api/overview)
* [](https://build.attio.com/)
* [](https://attio.com/help)
##### Introduction
  * [Overview](https://docs.attio.com/rest-api/overview)


##### How-to guides
  * [How to authenticate requests](https://docs.attio.com/rest-api/how-to/authentication)
  * [How to handle rate limits](https://docs.attio.com/rest-api/how-to/rate-limiting)
  * [How to apply filters and sorts](https://docs.attio.com/rest-api/how-to/filtering-and-sorting)
  * [How to paginate API results](https://docs.attio.com/rest-api/how-to/pagination)
  * [How to configure webhooks](https://docs.attio.com/rest-api/how-to/webhooks)


##### Tutorials
  * [Connect an app to Attio through OAuth](https://docs.attio.com/rest-api/tutorials/connect-an-app-through-oauth)


##### Endpoint reference
  * [OpenAPI](https://docs.attio.com/rest-api/endpoint-reference/openapi)
  * Core endpoints
  * Standard objects
  * OAuth 2.0


##### Webhook reference
  * Webhook events


Tutorials
# Connect an app to Attio through OAuth
Learn how to create an OAuth 2.0 app to access Attio’s REST API
If you’re building an app that needs to make requests to Attio’s REST API on behalf of many users, you should use OAuth 2.0 to authenticate your app.
This tutorial will walk you through the process of modifying an example Node.js app to connect to Attio through OAuth. We’ll start with a boilerplate app and modify it step-by-step to support generating an OAuth token for each user and then use that token to display a list of tasks they have in Attio.
If you would prefer to jump straight ahead to reference information for each endpoint in our OAuth flow, you can find documentation [here](https://docs.attio.com/rest-api/endpoint-reference/oauth/oauth-20/authorize-endpoint).
1
Create a new app in the developer dashboard
Head over to our [Developer dashboard](https://build.attio.com) and sign in with your Attio account.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/build-attio-screenshot.png)![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/build-attio-screenshot-dark.png)
Then, create a developer account. You should set the name of your account to the name of your company or organization.
![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/developer-account-creation.png)![](https://mintlify.s3.us-west-1.amazonaws.com/attio/images/developer-account-creation-dark.png)
Once you’ve created a developer account, you’ll be able to create an app. Give it a unique name and hit create.
2
Configure OAuth
Our next job is to enable OAuth 2.0 for the app. Head to the OAuth tab in your app’s settings and enable OAuth 2.0 via the toggle at the top of the page.
Next, configure the redirect URIs for your app. For our tutorial, we’ll use the following URL:
Copy
```
http://localhost:3050/integrations/attio/callback
```

Of course, for a real app, you’d also include a publicly available URL such as `https://my-app.com/integrations/attio/callback`.
Lastly, we need to configure the app’s scopes. Heads to the scopes tab to enable these. For our demonstration app, we’ll set tasks, user management, object configuration and records to “read” so we can fetch a list of tasks and which users they are assigned to.
3
Setup the Node.js project
Make a new directory and setup your new Node.js project inside it:
Copy
```
mkdir my-app
cd my-app
npm init -y
npm install express dotenv sqlite3 bcrypt express-session
```

Create a new file called `server.js` and add the following code:
Copy
```
require("dotenv").config()
const express = require("express")
const session = require("express-session")
const sqlite3 = require("sqlite3").verbose()
const bcrypt = require("bcrypt")
const app = express()
const PORT = 3050
// NOTE: The following code is heavily simplified for educational purposes and should not be copied
// for production use without careful consideration of security implications.
// 1) Setup a database
// Use ":memory:" for a temporary database in RAM. A real app should use a persistent database.
const db = new sqlite3.Database(":memory:")
// Seed a "users" table if it doesn't exist
db.run(`
  CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    username TEXT UNIQUE NOT NULL,
    passwordHash TEXT NOT NULL
  )
`)
// 2) Middleware
// Enable parsing of form data
app.use(express.urlencoded({extended: false}))
// Setup session middleware
app.use(
    session({
        secret: "mysecret", // Replace with a strong secret in production
        resave: false,
        saveUninitialized: false,
    })
)
// 3) Page routes
app.get("/", (req, res) => {
    if (req.session.userId) {
        return res.send(`
      <h1>Welcome to Taskr!</h1>
      <p>You are logged in as <strong>${req.session.username}</strong>.</p>
      <p><a href="/logout">Logout</a></p>
    `)
    } else {
        return res.send(`
      <h1>You are not logged in</h1>
      <p><a href="/signup">Sign Up</a></p>
    `)
    }
})
app.get("/signup", (req, res) => {
    if (req.session.userId) {
        return res.redirect("/")
    }
    res.send(`
    <h1>Sign Up</h1>
    <form method="POST" action="/signup">
      <label>Username:
        <input type="text" name="username" required>
      </label>
      <br><br>
      <label>Password:
        <input type="password" name="password" required>
      </label>
      <br><br>
      <button type="submit">Sign Up</button>
    </form>
  `)
})
// 4) Endpoint routes
app.post("/signup", async (req, res) => {
    const {username, password} = req.body
    try {
        const passwordHash = await bcrypt.hash(password, 10) // Hash the password for secure storage
        // Create a new user in the database
        db.run(
            `INSERT INTO users (username, passwordHash) VALUES (?, ?)`,
            [username, passwordHash],
            function (err) {
                if (err) {
                    // If username is taken, sqlite typically throws a UNIQUE constraint error
                    if (err.message.includes("UNIQUE constraint failed")) {
                        return res.send(`
              <h1>Username already taken</h1>
              <p><a href="/signup">Try another username</a></p>
            `)
                    }
                    return res.send("An error occurred. Please try again.")
                }
                // If insert succeeds, log the user in
                req.session.userId = this.lastID // ID of the newly created user
                req.session.username = username
                // Show the home page
                return res.redirect("/")
            }
        )
    } catch (error) {
        console.error("Error hashing password:", error)
        res.send("An error occurred. Please try again.")
    }
})
app.get("/logout", (req, res) => {
    req.session.destroy(() => {
        res.redirect("/")
    })
})
// 4) Start the server
app.listen(PORT, () => {
    console.log(`App running at http://localhost:${PORT}`)
})
```

You should now be able to run your app from the command line and visit it in your browser at `http://localhost:3050`:
Copy
```
node server.js
```

Run through the signup flow to ensure everything works as expected.
4
Add support for OAuth
To add support for OAuth, we need to ensure that our Node.js code has access to the OAuth client ID and client secret.
Create a new file called `.env` and add your app’s client ID and client secret. You can find these in the OAuth tab in your app’s settings.
Copy
```
ATTIO_CLIENT_ID=your-client-id
ATTIO_CLIENT_SECRET=your-client-secret
```

When we complete the OAuth flow, we’ll need a place to store the OAuth access token for each user. Modify the code that creates the `users` table as follows:
Copy
```
db.run(`
  CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    username TEXT UNIQUE NOT NULL,
    passwordHash TEXT NOT NULL,
    attio_access_token TEXT
  )
`)
```

In a real app, you should encrypt these values before storing them. Access tokens are highly sensitive data and should be stored securely.
Next, we need to implement the OAuth flow itself. An OAuth flow consists of the following steps:
  1. Redirect to Attio’s OAuth authorization page when prompted by the user
  2. Handle the redirect back from Attio
  3. Exchange the authorization code for an access token
  4. Persist the access token
  5. Make API requests using the access token


AttioYour AppUserAttioYour AppUserClick "Connect to Attio"Redirect to OAuth authorization pageRedirect to app with authorization codeExchange authorization code for access token securelyReturn access tokenStore access tokenMake API request with access token
We’ll start by adding a new route to our app that redirects the user to the OAuth authorization page.
Copy
```
const crypto = require("crypto")
app.get("/integrations/attio/connect", (req, res) => {
    if (!req.session.userId) {
        return res.redirect("/signup") // Must be logged in
    }
    // Generate a secure random state parameter and store it in the user's session
    const state = crypto.randomBytes(16).toString("hex")
    req.session.oauthState = state
    const authUrl = `https://app.attio.com/authorize?response_type=code&client_id=${process.env.ATTIO_CLIENT_ID}&redirect_uri=http://localhost:3050/integrations/attio/callback&state=${state}`
    res.redirect(authUrl)
})
```

A second route will handle the redirect back from Attio.
Copy
```
const ATTIO_TOKEN_URL = "https://app.attio.com/oauth/token"
app.get("/integrations/attio/callback", async (req, res) => {
    if (!req.session.userId) {
        return res.redirect("/signup")
    }
    const {code, state} = req.query
    // Verify the state parameter
    if (!state || state !== req.session.oauthState) {
        return res.status(403).send("Invalid state parameter. Possible CSRF attack detected.")
    }
    if (!code) {
        return res.status(400).send("Missing authorization code from Attio")
    }
    try {
        // Exchange authorization code for an access token using fetch
        const tokenResponse = await fetch(ATTIO_TOKEN_URL, {
            method: "POST",
            headers: {"Content-Type": "application/x-www-form-urlencoded"},
            body: new URLSearchParams({
                grant_type: "authorization_code",
                code: code,
                redirect_uri: "http://localhost:3050/integrations/attio/callback",
                client_id: process.env.ATTIO_CLIENT_ID,
                client_secret: process.env.ATTIO_CLIENT_SECRET,
            }),
        })
        if (!tokenResponse.ok) {
            console.error("Attio token exchange failed with status:", tokenResponse.status)
            return res.status(500).send("Error exchanging code for token")
        }
        const tokenData = await tokenResponse.json()
        const attioAccessToken = tokenData.access_token
        // Update the user's record with the access token
        db.run(
            `UPDATE users SET attio_access_token = ? WHERE id = ?`,
            [attioAccessToken, req.session.userId],
            (err) => {
                if (err) {
                    console.error("Failed to store Attio token in DB:", err)
                    return res.status(500).send("Database error storing Attio token")
                }
                // Redirect back to home
                res.redirect("/")
            }
        )
    } catch (err) {
        console.error("Error fetching token from Attio:", err)
        res.status(500).send("Internal error")
    }
})
```

Last, we need to ensure the user can navigate to the start of this flow. Let’s add a button to the home page that redirects to the `/integrations/attio/connect` route.
Copy
```
app.get("/", async (req, res) => {
    if (req.session.userId) {
        await db.get(
            "SELECT * FROM users WHERE id = ?",
            [req.session.userId],
            async (err, user) => {
                if (err) {
                    console.error("Error fetching users:", err)
                    return res.status(500).send("Error fetching users")
                }
                const hasAttioConnection = user !== null && user.attio_access_token !== null
                return res.send(`
          <h1>Welcome to Taskr!</h1>
          <p>You are logged in as <strong>${req.session.username}</strong>.</p>
          <p><a href="/logout">Logout</a></p>
          ${
              hasAttioConnection
                  ? `<p>Todo: render tasks</p>`
                  : `<p><a href="/integrations/attio/connect">Connect Attio</a></p>`
          }
        `)
            }
        )
    } else {
        // ...
    }
})
```

Please note, the example above stores a raw access token in the database. The access tokens that we grant to your app are highly sensitive data and should be stored securely. Please ensure any production apps you build encrypt the token before storing it.
5
Make a request to the Attio API and render the results
Now we have a token, all that remains is to make a request to the Attio API and render the results.
To make a request to the Attio API, we need to call the right endpoint and pass in our new oauth token in the `Authorization` header like so.
Copy
```
app.get("/", async (req, res) => {
    if (req.session.userId) {
        await db.get(
            "SELECT * FROM users WHERE id = ?",
            [req.session.userId],
            async (err, user) => {
                if (err) {
                    console.error("Error fetching users:", err)
                    return res.status(500).send("Error fetching users")
                }
                const hasAttioConnection = user !== null && user.attio_access_token !== null
                if (hasAttioConnection) {
                    const fetchResult = await fetch(`https://api.attio.com/v2/tasks?limit=10`, {
                        headers: {
                            Authorization: `Bearer ${user.attio_access_token}`, // Pass in the token here
                        },
                    })
                    const data = await fetchResult.json()
                    const taskItems = data.data.map((task) => {
                        return `<li>${task.content_plaintext}</li>`
                    })
                    const taskList = `<ul>${taskItems.join("")}</ul>`
                    return res.send(`
            <h1>Welcome to Taskr!</h1>
            <p>You are logged in as <strong>${req.session.username}</strong>.</p>
            <p><a href="/logout">Logout</a></p>
            ${taskList}
          `)
                }
                return res.send(`
      <h1>Welcome to Taskr!</h1>
      <p>You are logged in as <strong>${req.session.username}</strong>.</p>
      <p><a href="/logout">Logout</a></p>
      <p><a href="/integrations/attio/connect">Connect Attio</a></p>
    `)
            }
        )
    } else {
        return res.send(`
      <h1>You are not logged in</h1>
      <p><a href="/signup">Sign Up</a></p>
    `)
    }
})
```

6
Test your app
All that remains is to spin up your app and test it out!
Run your app from the command line and visit it in your browser at `http://localhost:3050`.
Copy
```
node server.js
```

Was this page helpful?
YesNo
[How to configure webhooks](https://docs.attio.com/rest-api/how-to/webhooks)[OpenAPI](https://docs.attio.com/rest-api/endpoint-reference/openapi)
[x](https://x.com/Attio)[website](https://attio.com)
[Powered by Mintlify](https://mintlify.com/preview-request?utm_campaign=poweredBy&utm_medium=referral&utm_source=docs.attio.com)
Assistant
Responses are generated using AI and may contain mistakes.
