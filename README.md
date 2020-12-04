# laravel-in-docker
Turn any existing laravel project into docker project.

- **Persistent database**
- **Persistent codebase** lets you use your favourite IDE/Editor.
- **No file permission issue** inherits user and permission from the host machine.
- **PhpMyAdmin** Out of the box

## Installation
[Download](https://github.com/nahidacm/laravel-in-docker/archive/main.zip) and extract the Zip file. 

Copy the `docker-compose.yml`,`DockerFile` and `docker-compose` in your existing Laravel project root directory.

**Initial SQL:**  `docker-compose/mysql/init_db.sql`

## Customization

#### In `docker-compose.yml` :

Change the `user` and `uid` according to your host machine's current username and user id.

You may issue `echo $UID` in your console to see the uid and `whoami` to see the user.

`docker-compose` will read the DB credentials from your Laravel's `.env` file. 

So make sure your Laravel project files with `.env` file is already there.

## Build and Up
Build the `app` image with the following command:

`docker-compose build app`

When the build is finished, you can run the environment in background mode with:

`docker-compose up -d`

Run any command inside the app, use `docker-composer exec app`  

Example: 

`docker-compose exec app composer install`

`docker-compose exec app php artisan key:generate`

Now go to your browser and access your server’s domain name or IP address on port 8000:

http://localhost:8000

To access phpMyAdmin:

http://localhost:3030
