## Use Docker

#### Target
- Nodejs@8.11.0 Dev Platform
  It Will Not Run Any Deamon Process, We Cant Run The Container Without Node Script
- Mysql
  Run without save data
  ```bash
  $ docker run --name local-mysql --rm -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -d mysql:5.6
  ```
  Run With Save Data
  ```bash
  $ docker run --name local-mysql --rm -p 3306:3306 -v $PWD/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root -d mysql:5.6
  ```
- phpMyAdmin
  ```bash
  $ docker run --name local-phpmyadmin --rm -d --link local-mysql:db -p 88:80 phpmyadmin/phpmyadmin
  ```
  - Open `http://localhost:88`
  - root/root

#### Docker Compose

Questions:
- Network
- Links

#### Docker Commands

- 通过Dockerfile创建一个镜像

  `$ docker build --tag node1 .`
- 执行容器的终端

  `$ docker exec -it demo1 /bin/bash`
- 查看容器的控制台日志

  `$ docker logs node1`
- 运行一个容器，并且链接本地的其他容器

  `$ docker run -d -p 9994:9994 --rm --link local-mysql:db --name node1 node1`


#### Example

- Edit The Dockerfile
- Build An Image
  ```bash
  $ docker build -t demo1 .
  ```
- Run An Container
  ```bash
  $ docker run -d -p 80:80 -v $PWD:/app --name demo1 demo1
  ```
- Check It Out