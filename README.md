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



#### Docker Commands

- docker exec -it demo1 /bin/bash


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