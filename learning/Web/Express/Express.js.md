 -  It is a node.js framework.
- While _Express_ itself is fairly minimalist, developers have created compatible middleware packages to address almost any web development problem.

It provides mechanisms to:
- Write handlers for requests with different HTTP verbs at different URL paths (routes).
- Integrate with "view" rendering engines in order to generate responses by inserting data into templates.
- Set common web application settings like the port to use for connecting, and the location of templates that are used for rendering the response.
- Add additional request processing "middleware" at any point within the request handling pipeline.

installation
```bash
npm i express
```

Hello World program
```JavaScript
const express = require("express");
const app = express();
const port = 3000;

app.get("/", function (req, res) {
  res.send("Hello World!");
});

app.listen(port, function () {
  console.log(`Example app listening on port ${port}!`);
});
```


[[Request]]
[[Response]]
[[Middleware]]
[[Routing]]
[[Cookies]]