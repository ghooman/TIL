## ๐ HTTPS ์ฌ์ค์ธ์ฆ์ ๋ฐ๊ธ
MacOS ์ฌ์ฉ์ ๊ธฐ์ค   
ํ๋ธ๋ฅ ํตํด ์ค์น ๊ฐ๋ฅ

### 1. mkcert ์ค์น
$ brew install mkcert   

---
### 2. $ mkcert -install
---
### 3. ๋ก์ปฌํธ์คํธ
$ mkcert -key-file key.pem -cert-file cert.pem localhost 127.0.0.1 ::1   

์ด์  ๊ทธ๋ผ ๋๊ฐ์ ํค๋ค ์์ฑ๋๋ค.   

cert.pem <-๊ณต๊ฐํค
key.pem <-๊ฐ์ธํค   

key.pem์ ๊ฐ์ธํค ์ด๊ธฐ ๋๋ฌธ์ ์ ๋ ๊น์ ์ฌ๋ผ๊ฐ์ง ์์์ผ ํ๋ค.
cert.pem์ ๊ณต๊ฐํค๋ก ๊ณต๊ฐ๋์ด๋ ์๊ด์๋ค.   

ํค๋ฅผ ๋ฐ๊ธ๋ฐ์ผ๋ฉด ๊ณ์ ์ฐ๊ธฐ ๋๋ฌธ์ ๋ค์ ์ค์น ๋ฐ์ํ์ ์์ด ์ด ํค๋ฅผ ํ์ํ๊ณณ์ ์ ๋ณต์ฌ ๋ถํ๋ฃ๊ธฐ ํ๋ฉด ๋๋ค.   

---
### 4. HTTPS ์๋ฒ์์ฑ
ํค๋ฅผ ๋ฐ๊ธ ๋ฐ์์ผ๋ฉด ์๋ฒ์ ์ ์ฉํ๋ ์์์ด ํ์ํ๋ค.   

**1) Node.js https ๋ชจ๋ ์ด์ฉ**
```javascript
const https = require('https');
const fs = require('fs');

https
  .createServer(
    {
      key: fs.readFileSync(__dirname + '/key.pem', 'utf-8'),
      cert: fs.readFileSync(__dirname + '/cert.pem', 'utf-8'),
    },
    function (req, res) {
      res.write('Congrats! You made https server now :)');
      res.end();
    }
  )
  .listen(3001);
```

์ ์ํ๋ฉด URI์ฐฝ ์ผ์ชฝ์ ์ข๋ฌผ์ ๊ฐ ๋ณด์ธ๋ค.   

**2) express.js ์ด์ฉ**
```javascript
const https = require('https');
const fs = require('fs');
const express = require('express');

const app = express();

https
  .createServer(
    {
      key: fs.readFileSync(__dirname + '/key.pem', 'utf-8'),
      cert: fs.readFileSync(__dirname + '/cert.pem', 'utf-8'),
    },
    app.use('/', (req, res) => {
      res.send('Congrats! You made https server now :)');
    })
  )
  .listen(3001);
```
