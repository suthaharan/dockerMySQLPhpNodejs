# PHP+nginx+MySQL+PHPMyAdmin for Laravel on Docker (2024)
In this guide, we’ll use Docker Compose to containerize a Laravel application for development. When you’re finished, you’ll have a demo Laravel application running:

* An app service running PHP8.0-FPM; (use PHP8.2-FPM for Laravel 10 deployment)
* A db service running MySQL 8.0;
* An nginx service that uses the app service to parse PHP code before serving the Laravel application to the final user.

## How to use

- Clone this repo
- Make the necessary changes to .env file
- Put the laravel web application inside src/ folder
- Useful docker commands to build and navigate docker containers
```
- $ docker-compose build app
- $ docker-compose up -d
- $ docker-compose ps
- $ docker-compose exec app ls -l
- $ docker-compose exec app rm -rf vendor composer.lock
- $ docker-compose exec app composer install
- $ docker-compose exec app php artisan key:generate
- $ docker-compose logs nginx
- $ docker-compose down
```
- For testing purpose, an index file is added to src/public folder which can be viewed at http://localhost:8000
- nginx settings can be added under nginx/default.conf
- The .env file in the root folder is used for docker-compose set up
- PhpMyAdmin can be accessed under http://localhost:8081
- To set up Laravel inside the container, create the application inside the src/ folder. The .env file of the Laravel application will make use of the database name/hostname from the docker-compose container settings.
