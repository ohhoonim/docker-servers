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
💡 mongodb 5 버전이상은 ARMv8.2-A이상만 지원함.

</aside>

## Collection 생성/조회

```json
// database 변경
use('testdb')
// collection 생성
db.createCollection('book')
// 데이터 입력
db.book.insertOne({name:"hello mongo", author:"choi"})
db.book.insertMany([{name:"hello java", author:"kim"}, {name:"hello docker", author:"lee"}])
// 데이터 조회
db.book.find().pretty()
// 데이터 업데이트
db.book.updateOne( { _id: ObjectId("61e374779cbbcefe0d6d744d") }, { $set: { author: "lee docker" } } )
// 업데이트 데이터 조회
db.book.find({name:"hello docker"})
// 데이터 삭제
db.book.deleteOne({name:"hello docker"})
```

## 참고문헌

[도커(Docker)로 MongoDB 서버 구축하기](https://wooiljeong.github.io/server/docker-mongo/)