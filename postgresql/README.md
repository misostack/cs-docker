# DOCKER WITH POSTGRES

```bash
docker pull postgres:13.3

docker run --name postgres13 -p 5432:5432 -d --env-file=./.env -v postgres:/var/lib/postgresql/data postgres:13.3
```

1. ENV?

```bash
-e MYVAR1
--env MYVAR2=abc
--env-file ./.env
```

2. Volume Docker?

- **--volume** vs **--mount**

```bash
docker volume create postgres
docker volume inspect posgres
```

3. Create a container

```bash
docker run --name postgres13 -e POSTGRES_PASSWORD=mysecretpassword -v postgres:/var/lib/postgresql/data -p 5432:5432 -d postgres:13.3

docker run --name postgres13 --env-file ./.env -v "pg13data:/var/lib/postgresql/data" -p "5432:5432" -d "postgres:13.3"
```

PGDATA = /var/lib/postgresql/data
