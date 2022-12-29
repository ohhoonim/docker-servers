# PostgreSQL

## docker-compose.yml

```yaml
version: '3.7'

services:
  postgres:
    image: postgres:latest
    container_name: postgres
    restart: always
    ports:
      - "5432:5432"
    environment:
      POSTGRES_USER: "${DB_USER_ID}"
      POSTGRES_PASSWORD: "${DB_USER_PASSWORD}"
    volumes:
      - postgres_datas:/var/lib/postgresql/data
volumes:
    postgres_datas:
```

## .env

```
DB_USER_ID=postgres
DB_USER_PASSWORD=12345678
```

<aside>
💡 docker-compose config 라고 명령어를 입력하면 .env 파일의 설정정보가 매핑된 것을 미리볼수 있다.

</aside>

## 참고문헌

[Docker Compose를 이용한 PostgreSQL 세팅! 근데 이제 Swarm Mode를 곁들인... - 인하대학교 인트아이](https://int-i.github.io/sql/2021-08-21/postgres-docker-compose/)

[[Docker] SpringBoot와 PostgreSQL 이미지 docker-compose로 한 번에 관리하기](https://earth-95.tistory.com/135)