## ๐ ์คํค๋ง(schema)
schema๋ ๋ฐ์ดํฐ๋ฒ ์ด์ค์์ ๋ฐ์ดํฐ๊ฐ ๊ตฌ์ฑ๋๋ ๋ฐฉ์๊ณผ ์๋ก ๋ค๋ฅธ ์ํฐํฐ ๊ฐ์ ๊ด๊ณ์ ๋ํ ์ค๋ช์ด๋ค.   
์ฆ, `"๋ฐ์ดํฐ๋ฒ ์ด์ค์ ์ฒญ์ฌ์ง"`๊ณผ ๊ฐ๋ค.
***
**โ๏ธ instagram schema design**
![instagram schema design](https://user-images.githubusercontent.com/85857465/146780258-0e7d00c1-470f-434c-8e9e-128c6968e84b.png)   

```mysql
Table users {
  id int [pk, increment]
  username varchar(50)
  password varchar(50)
}

Table posts {
  id int [pk, increment]
  image blob
  message text
  created_at timestamp
  total_likes int
  total_comments int
  user_id int
}

Table hashtags {
  id int [pk, increment]
  name char(50)
}

Table post_comments {
  id int [pk, increment]
  comment varchar(255
  user_id int
  post_id int
  created_at timestamp
}

Table post_likes {
  id int [pk, increment]
  created_at timestamp
  user_id int
  post_id int
}

Table follow_follower {
  id int [pk, increment]
  follower_id int
  user_id int
}

Table posts_hashtags {
  id int [pk, increment]
  hashtag_id int
  post_id int
}


ref: users.id < follow_follower.follower_id
ref: users.id < follow_follower.user_id
ref: users.id < post_comments.user_id
ref: users.id < posts.user_id
ref: users.id < post_likes.user_id
ref: posts_hashtags.post_id > posts.id
ref: posts_hashtags.hashtag_id > hashtags.id
ref: posts.id < post_comments.post_id
ref: posts.id < post_likes.post_id
```
