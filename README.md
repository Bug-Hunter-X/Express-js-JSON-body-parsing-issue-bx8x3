# Express.js JSON Body Parsing Issue

This repository demonstrates a common issue encountered when working with JSON request bodies in Express.js applications.  The problem arises when the client omits or sends an incorrect `Content-Type` header, causing the application to fail to parse the JSON data.

## Bug Description

The provided Express.js application is designed to handle POST requests to the `/data` endpoint.  It's expected to parse the JSON data from the request body and log it to the console.  However, if the client doesn't set the `Content-Type` header to `application/json` (or sets it to something incorrect), Express.js will not automatically parse the request body, resulting in `req.body` being empty.

## Solution

The solution involves explicitly configuring Express.js to parse JSON regardless of the presence or value of the `Content-Type` header.  This is achieved by setting `express.json()` options to allow any content type.