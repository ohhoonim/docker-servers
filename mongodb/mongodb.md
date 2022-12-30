# MongoDB

## docker-componse.yml

```yaml
version: '3.8'
services:
  mongodb:
    image: mongo
    container_name: mongodb
    restart: always
    ports:
      - 27017:27017
    volumes:
      - ./mongodb:/data/db
    environment:
      - MONGO_INITDB_ROOT_USERNAME=root
      - MONGO_INITDB_ROOT_PASSWORD=1234 
      - MONGO_INITDB_DATABASE=testdb
volumes:
  mongodb_datas:
```

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

[Docker - 도커로 MongoDB 컨테이너 설치하는 방법을 알아보자](https://7942yongdae.tistory.com/131)

[몽고디비(MongoDB) docker-compose 설치 및 데이터 CRUD 예제](https://youngwonhan-family.tistory.com/entry/Docker-mongodb-docker-compose-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EB%8D%B0%EC%9D%B4%ED%84%B0-CRUD-%EC%98%88%EC%A0%9C)