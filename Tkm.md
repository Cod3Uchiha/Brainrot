```html
<!-- index.html -->

<!DOCTYPE html>
<html>
<head>
  <title>Brainrot</title>
</head>
<body>
  <h1>Brainrot</h1>
  <p>Welcome to Brainrot, the website where you can post all your brainrot and forget about it.</p>
  <form action="/post" method="POST">
    <textarea name="post"></textarea>
    <input type="submit" value="Post">
  </form>
</body>
</html>

```

```javascript
// server.js

const express = require('express');
const app = express();

app.use(express.urlencoded({ extended: true }));

app.get('/', (req, res) => {
  res.sendFile(__dirname + '/index.html');
});

app.post('/post', (req, res) => {
  console.log(req.body.post);
  res.redirect('/');
});

app.listen(3000);

```