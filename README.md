## Use Docker

#### Target
- Nodejs@8.11.0 Dev Platform
- Mysql
- phpMyAdmin


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