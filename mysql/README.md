# MYSQL Docker Usage

```bash
docker run --name=mysql -d mysql/mysql-server # lastest
docker run --name=mysql --restart on-failure -d mysql/mysql-server:8.0

docker ps
## regex
docker ps --filter "name=(.*)l$"
```
