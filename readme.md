<span align="right"><img src="https://laravel.com/assets/img/components/logo-laravel.svg"></span>
<p align="center"></p>

### Get ready:
- make sure ports 8181 and 3306 are clear.
- in your .env file, define:
   - DB_HOST=database
   - DB_DATABASE=docker_db
- run the database container:  
    `docker container run -d --name database -p 3306:3306
     -e MYSQL_ROOT_PASSWORD=secret
      -e MYSQL_DATABASE=docker_db 
      -v :/var/lib/mysql mysql`

### Grab my image:
- to pull the existing image
  run `docker pull efrat19/laravel`
  #### OR
  
- to build from the local Dockerfile: 
  - copy my Dockerfile to your root directory
  -  run `docker build -t <whatever> .`
  
### Show Time:
- run `docker container run -d -p 8181:8181 --name laravel_1 efrat19/laravel`
- open your browser at localhost:8181 to see the result


###### when you're done:
### Cleanup the mess :
`docker container rm -f database laravel_1`
