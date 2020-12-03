# laravel-in-docker
Full functional latest Laravel dev enironment in docker

## Customization

#### In `docker-compose.yml` :

Change the file change the `user` and `uid` according to your host machine's current username and user id.
you may issue `echo $UID` in your console to see the uid and `whoami` to see the user.

`docker-compose` will read the DB credentials from your Laravel's `.env` file. So make sure that your Laravel project files with `.env` file is already there.

## Build and Up
Build the `app` image with the following command:

`docker-compose build app`

When the build is finished, you can run the environment in background mode with:

`docker-compose up -d
`

We'll now run composer install to install the application dependencies:

`docker-compose exec app composer install`

The last thing we need to do before testing the application is to generate a unique application key with the artisan Laravel command-line tool. 

`docker-compose exec app php artisan key:generate`

Now go to your browser and access your server’s domain name or IP address on port 8000:

`http://localhost:8000`
