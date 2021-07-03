# Redis Docker

```bash
docker pull redis
# fixed version
docker run --name=redis --restart on-failure -d redis
```

## Use Dockerfile

```bash
docker build -t 2base/redis .
docker run --name=redis --restart on-failure -p "6379:6379" -d 2base/redis
```
