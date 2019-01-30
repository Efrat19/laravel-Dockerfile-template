<span align="right"><img src="https://laravel.com/assets/img/components/logo-laravel.svg"></span>
<p align="center"></p>

### Get ready:
- make sure ports 8181 and 3306 are clear.
- in the .env file, define:
   - DB_HOST=database
   - DB_DATABASE=docker_db
   - DB_HOST=database
   - DB_PASSWORD=secret
- run the database container:  
    `docker container run -d --name database -p 3306:3306 -e MYSQL_ROOT_PASSWORD=secret MYSQL_DATABASE=docker_db -v :/var/lib/mysql`

### Grab my image:
- to pull the existing image
  run `docker pull efrat19/laravel`
  #### OR
  
- to build from the local Dockerfile:
  - make sure you're inside the project directory
  -  run `docker build -t <whatever> .`
  
### Show Time:
- run `docker container run -d -p 8181:8181 --name laravel_1 efrat19/laravel`
- open your browser at localhost:8181 to see the result

### Cleanup the mess:
`docker rm -f database laravel_1`
