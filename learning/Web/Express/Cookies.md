Cookies are simple, small files/data that are sent to client with a server request and stored on the client side. Every time the user loads the website back, this cookie is sent with the request. This helps us keep track of the user’s actions.

The following are the numerous uses of the HTTP Cookies −

- Session management
- Personalization(Recommendation systems)
- User tracking

To use cookies with Express, we need the `cookie-parser` middleware
```bash
npm i cookie-parser
```

```javascript
var express = require('express')
var cookieParser = require('cookie-parser')

var app = express()
app.use(cookieParser())

app.get('/', function(req, res){
   res.cookie('name', 'express',{expire: 360000 + Date.now()}).send('cookie set'); 
});

app.listen(3000);
```
