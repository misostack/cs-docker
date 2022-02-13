# DOCKER

## REFS

- [Docker Cheat Sheet](https://gist.github.com/misostack/162ff602ada455a078bfa496a3cb20ea)

1. Docker là cái quái gì và tại sao nên ( không nhất phải ) sử dụng

> Câu chuyện xa xưa từ thuở chưa có Docker. Câu chuyện mỗi lần triển khai 1 dự án phần mềm lên web là khá rối rắm. 
> Code + Configurations (nghĩa là số nhiều) + Vagrant(ảo hóa) + Jenkins(1 công cụ CI/CD) + Chef( 1 công cụ giúp tự động hóa việc config cho server( cài đặt các package cần thiết), cho phép lưu lại thiết lập như 1 recipes/cookbooks, monitor, undo), vân vân và mây mây. Trải qua 1 qúa trình như vậy với các thứ khủng khiếp đã liệt kê, chúng ta có thể triển khai các môi trường riêng biệt cho dev, test, production một cách tự động hóa
> Vậy DOCKER làm được chuyện gì ? Khá đơn giản nó nhận input (configuration) và làm phần việc của toàn bộ các tool liên quan kia và đóng gói lại 1 container duy nhất

2. Các khái niệm chính trong Docker

**Images** : tương tự với các image trong khi ảo hóa, nó là 1 tập hợp các filesystem và một số metadata, là cái nền của các container

**Containers**: là khởi tạo của các image

**Layers**: là những sự thay đổi lên các tập tin

## Practice

1. Chạy 1 container mysql

- https://hub.docker.com/_/mysql
- https://docs.docker.com/engine/reference/commandline/ps/

```bash
docker container ls -a

docker container run --name mysql -p 3360:3306 -e MYSQL_ROOT_PASSWORD=123456 -d mysql:8.0

docker container kill mysql
docker container start mysql
docker container stop mysql
docker container rm -f mysql
```

**Execute command on docker container**

```bash
docker container exec -it mysql /bin/bash
docker container exec -it mysql /bin/sh
```

**Sử dụng Dockerfile để thiết lập các configuration cần thiết cũng như thay đổi configuration**

**Persist data**

```bash

```


**KẾT NỐI PHPMYADMIN CONTAINER VỚI HOST NGOÀI**
```bash
docker run --name phpmyadmin -d -e PMA_HOST=172.17.0.1 -e PMA_ARBITRARY=1 -p 8080:80 phpmyadmin
```

## Docker Compose

**remove all container name start with "rest-api"**
```bash
docker ps --filter name=rest-api -aq | xargs docker stop | xargs docker rm
---




2. Tạo 1 docker image của phpmyadmin kết nối được với mysql container
  
3. Tạo 1 docker image của phpyadmin kết nối được với mysql của host

- https://stackoverflow.com/questions/28056522/access-host-database-from-a-docker-container
- https://docs.docker.com/docker-for-mac/networking/#httphttps-proxy-support
- https://nickjanetakis.com/blog/docker-tip-35-connect-to-a-database-running-on-your-docker-host

