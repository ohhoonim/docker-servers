# 사용자 생성

```sql
-- 데이터베이스 생성
show databases;
create database testdb;
-- 사용자 생성 
create user 'matthew'@'%' IDENTIFIED BY 'wngudehs';
-- 사용자 권한 부여
grant all PRIVILEGES on testdb.* to 'matthew'@'%';
-- 새로고침
flush PRIVILEGES;
```