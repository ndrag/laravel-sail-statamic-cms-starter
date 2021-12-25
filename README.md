# Laraval Sail starter with Statamic CMS

## Stack
- PHP 8
- Laravel 8
- Statamic CMS
- TailwindCSS 2
- Docker via Laravel Sail

## Requirements
- A linux distro with Docker installed or Windows with WSL2 and Docker for Desktop (ideally). 
## Setup
- Clone the repo with `git clone https://github.com/ndrag/laravel-sail-statamic-cms-starter.git`
- First run only: Run the following command to spin up a docker instance with php 8 & composer and then automatically execute the `composer install` command.
``` bash
docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v $(pwd):/var/www/html \
    -w /var/www/html \
    laravelsail/php80-composer:latest \
    composer install --ignore-platform-reqs
```
- You now have access to a fully self-contained PHP 8, Statamic, Laravel Sail application!
- Copy `.env.example` to `.env` and configure appropriately.
- Run `artisan key:generate` to generate an application key.

## Local Developmnet
- Run `sail up` to launch the Docker container and serve the site at `localhost`.
- Run `sail down` to spin down the Docker container. 