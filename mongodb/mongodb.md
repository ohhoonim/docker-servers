# MongoDB

## docker-componse.yml

```yaml
version: '3.7'
services:
  mongodb:
    image: mongo:4.4
    container_name: mongodb
    restart: always
    ports:
      - 27017:27017
    volumes:
      - ./mongodb:/data/db
    environment:
      - MONGO_INITDB_ROOT_USERNAME=root
      - MONGO_INITDB_ROOT_PASSWORD=1234 
volumes:
  mongodb_datas:
```

<aside>
๐ก mongodb 5 ๋ฒ์ ์ด์์ ARMv8.2-A์ด์๋ง ์ง์ํจ.

</aside>

## Collection ์์ฑ/์กฐํ

```json
// database ๋ณ๊ฒฝ
use('testdb')
// collection ์์ฑ
db.createCollection('book')
// ๋ฐ์ดํฐ ์๋ ฅ
db.book.insertOne({name:"hello mongo", author:"choi"})
db.book.insertMany([{name:"hello java", author:"kim"}, {name:"hello docker", author:"lee"}])
// ๋ฐ์ดํฐ ์กฐํ
db.book.find().pretty()
// ๋ฐ์ดํฐ ์๋ฐ์ดํธ
db.book.updateOne( { _id: ObjectId("61e374779cbbcefe0d6d744d") }, { $set: { author: "lee docker" } } )
// ์๋ฐ์ดํธ ๋ฐ์ดํฐ ์กฐํ
db.book.find({name:"hello docker"})
// ๋ฐ์ดํฐ ์ญ์ 
db.book.deleteOne({name:"hello docker"})
```

## ์ฐธ๊ณ ๋ฌธํ

[๋์ปค(Docker)๋ก MongoDB ์๋ฒ ๊ตฌ์ถํ๊ธฐ](https://wooiljeong.github.io/server/docker-mongo/)