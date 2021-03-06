# π HTTP νΈλμ­μ ν΄λΆ
[HTTP νΈλμ­μ ν΄λΆ](https://nodejs.org/ko/docs/guides/anatomy-of-an-http-transaction/) μ°Έκ³ .

---
### 1. μλ² μμ±
λͺ¨λ  node μΉ μλ² μ νλ¦¬μΌμ΄μμ μΉ μλ² κ°μ²΄λ₯Ό λ§λ€μ΄μΌ νλ€. μ΄ λ createServerλ₯Ό μ΄μ©νλ€.   
```javascript
const http = require('http');

const server = http.createServer((request, response) => {
  // μ¬κΈ°μ μμμ΄ μ§νλ©λλ€!
});
```
μ΄ μλ²λ‘ μ€λ `HTTP` μμ²­λ§λ€ `createServer`μ μ λ¬λ ν¨μκ° ν λ²μ© νΈμΆλλ€. `HTTP` μμ²­μ΄ μλ²μ μ€λ©΄ `node`κ° νΈλμ­μμ λ€λ£¨λ €κ³  `request`μ `response` κ°μ²΄λ₯Ό μ λ¬νλ©° μμ²­ νΈλ€λ¬ ν¨μλ₯Ό νΈμΆνλ€. μμ²­μ μ€μ λ‘ μ²λ¦¬νλ €λ©΄ `listen` λ©μλκ° `server` κ°μ²΄μμ νΈμΆλμ΄μΌ νλ€. λλΆλΆμ μλ²κ° μ¬μ©νκ³ μ νλ ν¬νΈ λ²νΈλ₯Ό `listen`μ μ λ¬νκΈ°λ§ νλ©΄ λλ€.   

---
### 2. λ©μλ, URL, ν€λ
μμ²­μ μ²λ¦¬ν  λ, μ°μ  λ©μλμ `URL`μ νμΈν ν μ΄μ κ΄λ ¨λ μ μ ν μμμ μ€νν΄μΌνλ€. `node`λ `request` κ°μ²΄μ κ° νλ‘νΌν°λ₯Ό λ£μ΄λμμΌλ―λ‘ μ½κ² μμ κ°λ₯νλ€.
```javascript
const { method, url } = request;

const { headers } = request;
const userAgent = headers['user-agent'];
```
μ¬κΈ°μ `method`λ μΌλ°μ μΈ `HTTP` λ©μλ/λμ¬κ° λ  κ²μ΄κ³ , `url`μ μ μ²΄ `URL`μμ μλ², νλ‘ν μ½, ν¬νΈλ₯Ό μ μΈν κ²μΌλ‘, μΈ λ²μ§Έ μ¬λμ μ΄νμ λλ¨Έμ§ μ λΆμ΄λ€.   

`request`μ `headers`λΌλ μ μ© κ°μ²΄κ° μκ³ , ν΄λΌμ΄μΈνΈκ° μ΄λ»κ² ν€λλ₯Ό μ€μ νλμ§μ κ΄κ³μμ΄ λͺ¨λ  ν€λλ μλ¬Έμλ‘λ§ ννλλ€λ κ²μ κΈ°μ΅νμ. μ΄λ μ΄λ€ λͺ©μ μ΄λ  ν€λλ₯Ό νμ±νλ μμμ κ°νΈνκ² ν΄μ€λ€.

---
### 3. μμ²­ λ°λ
`POST`λ `PUT` μμ²­μ λ°μ λ μ νλ¦¬μΌμ΄μμ μμ²­ λ°λλ μ€μν  κ²μ΄λ€. νΈλ€λ¬μ μ λ¬λ `request` κ°μ²΄λ `ReadableStream` μΈν°νμ΄μ€λ₯Ό κ΅¬ννκ³  μλλ°, μ΄ μ€νΈλ¦Όμ `'data'`μ `'end'` μ΄λ²€νΈμ μ΄λ²€νΈ λ¦¬μ€λλ₯Ό λ±λ‘ν΄μ λ°μ΄ν°λ₯Ό λ°μ μ μλ€.   

κ° `'data'` μ΄λ²€νΈμμ λ°μμν¨ μ²­ν¬λ `Buffer`μ΄λ€. μ΄ μ²­ν¬λ λ¬Έμμ΄ λ°μ΄ν°μ΄λ―λ‘ μ΄ λ°μ΄ν°λ₯Ό λ°°μ΄μ λ΄κ³ , `'end'` μ΄λ²€νΈμμ μ΄μ΄ λΆμΈ λ€μ λ¬Έμμ΄λ‘ λ§λλ κ²μ΄ κ°μ₯ μ’λ€.
```javascript
let body = [];
request.on('data', (chunk) => {
  body.push(chunk);
}).on('end', () => {
  body = Buffer.concat(body).toString();
  // μ¬κΈ°μ `body`μ μ μ²΄ μμ²­ λ°λκ° λ¬Έμμ΄λ‘ λ΄κ²¨μμ΅λλ€.
});
```

# π Mini Node Server
μ΄λ²μ λ§λ€μ΄μΌν  μΉ μλ²μ κΈ°λ₯μ λ§€μ° λ¨μνλ€. λ²νΌμ ν΄λ¦­ν¨μ λ°λΌ κ°κΈ° λ€λ₯Έ μμ²­μ λ³΄λ΄λ©°, κ°κ° λ³΄λΈ λ¨μ΄λ₯Ό μλ¬Έμ λλ λλ¬Έμλ‘ λ°κΎΈλ©΄ λλ κ²μ΄μλ€.   
![mini-node-server](https://user-images.githubusercontent.com/85857465/160459136-2fb9be64-0aa7-4952-bcfa-1dc21febb2fa.gif)   

### Sprint κ΅¬ννκΈ°
<img width="424" alt="αα³αα³αα΅α«αα£αΊ 2022-03-29 αα©αα₯α« 3 03 32" src="https://user-images.githubusercontent.com/85857465/160459326-9a452994-b691-4426-befd-965c3b60a25a.png">   

`URL`μ΄ `/lower`μ΄κ³ , `POST` μμ²­μ΄ μλ€λ©΄ μλ²λ λ¬Έμμ΄μ μλ¬Έμλ‘ λ§λ€μ΄ μλ΅ν΄μΌ νκ³ , `URL`μ΄ `/upper`μΈ `POST` μμ²­μλ λ¬Έμμ΄μ λλ¬Έμλ‘ λ§λ€μ΄ μλ΅ν΄μΌ νλ€. λν, `CORS` κ΄λ ¨ ν€λλ₯Ό `OPTIONS` μλ΅μ μ μ©ν΄μΌ νλ€.   

λ°λΌμ, λ¨Όμ  `Method`κ° `POST`μΈμ§ `OPTIONS`μΈμ§ λΆκΈ°νκ³ , `POST` μμ²­μ΄ μλ€λ©΄ `URL`μ νμΈνκ³  μλ§μ μμ²­μ λ³΄λ΄μ£Όλ μμΌλ‘ κ΅¬ννλ€.
```javascript
const http = require('http');
const PORT = 5000;
const ip = 'localhost';

const server = http.createServer((request, response) => {
  if (request.method === 'OPTIONS') {
    // ν΄λΌμ΄μΈνΈμ preflight requestμ λν μλ΅μ λλ €μ€λ€
    response.writeHead(200, defaultCorsHeader);
    response.end();
  }
  if (request.method === 'POST') {
    let body = [];
    request
      .on('data', (chunk) => {
        // μμ HTTP νΈλμ­μ ν΄λΆ λ¬Έμμμ κ³΅λΆνλ κ²μ²λΌ,
        // body λ°°μ΄μ chunkλ₯Ό λ΄κ³ 
        body.push(chunk);
      })
      .on('end', () => {
        // end μ΄λ²€νΈμμ μ΄μ΄ λΆμ΄κ³  λ¬Έμμ΄λ‘ λ§λ λ€
        body = Buffer.concat(body).toString();
        response.writeHead(201, defaultCorsHeader);
        if (request.url === '/lower') {
          response.end(body.toLowerCase());
        } else if (request.url === '/upper') {
          response.end(body.toUpperCase());
        } else {
          response.writeHead(404, defaultCorsHeader);
          response.end();
        }
      });
  }
});

server.listen(PORT, ip, () => {
  console.log(`http server listen on ${ip}:${PORT}`);
});

// μλ΅ ν€λ
const defaultCorsHeader = {
  'Access-Control-Allow-Origin': '*',
  'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE, OPTIONS',
  'Access-Control-Allow-Headers': 'Content-Type, Accept',
  'Access-Control-Max-Age': 10,
};
```

**reference code**   
μ΄ μ½λλ μ μ΄μ λ¬Έμμ΄ λ³μ `data`λ₯Ό μ μΈνμ¬ `'data'` μ΄λ²€νΈμμ `chunk`λ₯Ό λν΄μ£Όκ³ , `'end'` μ΄λ²€νΈμμ κ·Έ `data`λ₯Ό μλ¬Έμ νΉμ λλ¬Έμλ‘ λ°κΎΈμ΄ μλ΅νλ ννμ μ½λμ΄λ€. ν¨μ¬ κ°λ¨νκ² κ΅¬νν λͺ¨μ΅μ΄λ€.
```javascript
const http = require('http');
const PORT = 5000;
const ip = 'localhost';

const server = http.createServer((req, res) => {
  if (req.method === 'POST') {
    if (req.url === '/lower') {
      let data = '';
      req.on('data', chunk => {
        data = data + chunk;
      });
      req.on('end', () => {
        data = data.toLowerCase();
        res.writeHead(201, defaultCorsHeader);
        res.end(data);
      });
    } else if (req.url === '/upper') {
      let data = '';
      req.on('data', chunk => {
        data = data + chunk;
      });
      req.on('end', () => {
        data = data.toUpperCase();
        res.writeHead(201, defaultCorsHeader);
        res.end(data);
      });
    } else {
      res.writeHead(404, defaultCorsHeader);
      res.end();
    }
  }
  if (req.method === 'OPTIONS') {
    res.writeHead(200, defaultCorsHeader);
    res.end();
  }
});

server.listen(PORT, ip, () => {
  console.log(`http server listen on ${ip}:${PORT}`);
});

const defaultCorsHeader = {
  'Access-Control-Allow-Origin': '*',
  'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE, OPTIONS',
  'Access-Control-Allow-Headers': 'Content-Type, Accept',
  'Access-Control-Max-Age': 10
};
```
