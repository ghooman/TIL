## ๐MySQL ๋ฌธ๋ฒ ์ ๋ฆฌ

**<๋ฐ์ดํฐ์กฐํํ๊ธฐ (SELECT)>**
```mysql
# ๋ชจ๋  ์ปฌ๋ผ์ ์ ํํ  ๋
SELECT * FROM ํ์ด๋ธ๋ช;

# ํน์  ์ปฌ๋ผ์ ์ ํํ  ๋
SELECT column1, column2
FROM ํ์ด๋ธ๋ช;
```

**<๊ฒ์ ์กฐ๊ฑด ์ง์ ํ๊ธฐ (WHERE)>**
```mysql
SELECT column1, column2 FROM ํ์ด๋ธ๋ช WHERE ์กฐ๊ฑด์;

# WHERE๋ฌธ ์์ 
SELECT * FROM ํ์ด๋ธ๋ช WHERE price = 200; 
// price ๊ฐ์ด 200์ธ ๊ฒฝ์ฐ๋ง ์กฐํ

SELECT * FROM ํ์ด๋ธ๋ช WHERE price <> 200; 
// price ๊ฐ์ด 200์ด ์๋ ๊ฒฝ์ฐ๋ง ์กฐํ

SELECT * FROM ํ์ด๋ธ๋ช WHERE name = 'ํ๊ธธ๋';
// name์ด ํ๊ธธ๋์ธ ๊ฒฝ์ฐ๋ง ์กฐํ
// ์ซ์๊ฐ ์๋ ๋ฌธ์์ด์ ๊ฒฝ์ฐ ''๋ฅผ ๋ถ์ธ๋ค.

SELECT * FROM ํ์ด๋ธ๋ช WHERE name IS NULL;
// name์ด NULL์ธ ๊ฒฝ์ฐ๋ง ์กฐํ
```
