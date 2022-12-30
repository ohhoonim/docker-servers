# Redis

## docker-compose.yml

```yaml
version: '3.7'
services:
  redis:
    image: redis:7.0.4
    command: redis-server --port 6379
    container_name: redis_standalone
    hostname: redis_standalone
    labels:
      - "name=redis"
      - "mode=standalone"
    ports:
      - 6379:6379
```

## redis-cli

```bash
>> docker exec -it redis_boot redis-cli
127.0.0.1:6379> PING
PONG
127.0.0.1:6379> keys *
(empty array)
127.0.0.1:6379> SET abc 123
OK
127.0.0.1:6379> GET abc
"123"
127.0.0.1:6379>
```

## 참고문헌

[Redis 컨테이너 환경 실행 with Docker-compose](https://box0830.tistory.com/404)

[docker로 redis 설치 및 redis 기본적인 명령어를 알아보자](https://msyu1207.tistory.com/entry/Redis-PubSub)