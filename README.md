# PHP+nginx+MySQL+PHPMyAdmin for Laravel on Docker (2024)
In this guide, we’ll use Docker Compose to containerize a Laravel application for development. When you’re finished, you’ll have a demo Laravel application running on three separate service containers:

* An app service running PHP7.4-FPM;
* A db service running MySQL 8.0;
* An nginx service that uses the app service to parse PHP code before serving the Laravel application to the final user.

## How to use

- Clone this repo
- Rename sample.env to .env file and make the necessary changes 
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
- For testing purpose an index file is added to src/public folder which can be viewed at http://localhost
- nginx settings can be added under nginx/default.conf
- PhpMyAdmin can be accessed under http://localhost:8081
