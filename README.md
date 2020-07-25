# Docker Compose NGINX/PHP/MYSQL 
This is a basic quick start docker compose project bundled with NGINX:LATEST, MYSQL:5.6 and
PHP 7.4 . Can be used to easily boot up a quick PHP 7.4 application with a MySQL backend using docker.

## Getting Started

1. Set your app name within the **site.conf** NGINX config file by updating the **server_name** directive
    ``server_name myapp.local;``

2. Install **Docker** together with **Docker Compose** on your machine.

3. Set you MySQL root password with the **MYSQL_ROOT_PASSWORD** environmental variable within the MySQL block. Last line in the docker-compose.yml

4. Run docker compose
    ``docker-compose up -d``
5. Copy all your PHP development files into the **html** directory. The html is the host path mounted to the NGINX and PHP containers.

6. Create your database using the below commands:
    ````
    docker exec -it mysql  /bin/bash
    mysql -u root -p
    CREATE DATABASE <database_name>
    ````
   
7. Update your host file on your OS with the value you set as your server name

    ```127.0.0.1	myapp.local```
    
    In Linux the **hosts** file is located within **/etc/hosts** and on Windows the **hosts** file can be found within the 
    **C:\Windows\System32\drivers\etc** directory.