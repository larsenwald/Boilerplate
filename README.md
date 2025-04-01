# Boilerplate

A repository where I store boilerplate code for the tools, frameworks, and languages I use most often.

## Table of Contents
- [Node.js](#nodejs)
  - [Basic Express Server Startup](#basic-express-server-startup)
  - [Axios](#axios)

## Node.js

### Basic Express Server Startup

```javascript
// Start the server
import express from "express";
const app = express();
const port = 3000;

app.listen(port, () => {
    console.log(`Server's up! Listening on port ${port}...`);
});

// For retrieving info from submitted forms
import bodyParser from "body-parser";
app.use(bodyParser.urlencoded({ extended: true }));

// So EJS files can have access to the images and styles we placed in "public"
app.use(express.static("public"));
```
### Axios
```javascript
// Import axios
import axios from "axios";

// GET request to a REST endpoint
try {
    const response = await axios.get("https://api.example.com/data");
    console.log(response.data);
} catch (error) {
    res.status(500).json({ error: "Something went wrong" });
}

// POST request
try {
    const response = await axios.post(
        "https://api.example.com/data",
        { key1: "value1", key2: "value2" }, // Data to be passed
        {
            headers: {
                "Content-Type": "application/json",
                Authorization: "Bearer YOUR_ACCESS_TOKEN",
            },
        }
    );

    console.log(response.data);
} catch (error) {
    res.status(500).json({ error: "Something went wrong" });
}
```
### PostgreSQL
```javascript
import pg from "pg";
const db = new pg.Client({
  user: "myusername", //default username is "postgres"
  host: "localhost",
  database: "mydatabase",
  password: "mypassword123",
  port: 5432,
});
db.connect();
```
