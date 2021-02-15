# Laravel LEMP Stack
A clean and simple LEMP stack built for a Laravel app. Uses docker and WSL2. 

### Directory Structure
```
docker
 ┣ logs
 ┃ ┗ nginx
 ┃ ┃ ┗ error.log  <--- NGINX errors are logged here
 ┣ nginx
 ┃ ┣ logrotate
 ┃ ┃ ┗ nginx
 ┃ ┣ sites
 ┃ ┃ ┗ default.conf  <--- NGINX site configs are mapped to the container
 ┃ ┣ ssl  <--- SSL Cert store for NGINX
 ┃ ┃ ┣ default.crt
 ┃ ┃ ┣ default.csr
 ┃ ┃ ┗ default.key
 ┃ ┣ Dockerfile <--- Specific config for the NGINX container
 ┃ ┣ nginx.conf <--- Main NGINX config file is copied to the container at build
 ┃ ┗ startup.sh <--- Generates self signed certificate for https
 ┣ php-fpm
 ┃ ┣ Dockerfile <--- Specific config for the php container
 ┃ ┗ php.ini <--- PHP.ini is mapped to the container at startup
 ┣ .env
 ┗ docker-compose.yml
 ```

### How to Use
- Copy the docker folder into the root directory of your app.
- Set your project name in the .env file.
- Change the container_name's in the docker-compose.yml to match your project's name.
- In the SQL container config, change 'portal' to your project's name. This folder will persist your SQL data.

```
cd docker
docker-compose up -d
```
