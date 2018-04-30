## Run A Node Project With Docker

- build a image
  ```bash
  $ docker build --tag node1 .
  ```

- run a container
  ```bash
  $ docker run -d -p 9994:9994 --rm --link local-mysql:db --name node1 node1
  ```

- check logs
  ```bash
  $ docker logs node1
  ```

- rm All containers
`$ docker rm $(docker stop $(docker ps -aq))`