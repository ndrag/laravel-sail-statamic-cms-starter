# Laraval Sail starter with Statamic CMS

Laravel is a modern full-stack PHP development environment that offers back-end rendered HTML templates or integration with a front-end framework like Vue JS (not included in this starter - see my [Laravel + Vue stater here](https://github.com/ndrag/laravel-vue-inertia-tailwind-starter)).

Statamic is a simple CMS that allows you to build your Laravel application with content generated via a user-accessible front-end. It uses flat files rather than a database to provide super speedy performance for small-scale, text-heavy websites. 

This application is almost entirely self-contained: It doesn't require PHP, Laravel, or any other global installs except Docker Desktop. 

## Stack
- PHP 8
- Laravel 8
- Statamic CMS
- TailwindCSS 2
- Docker via Laravel Sail

## Requirements
- Windows with WSL2 and Docker Desktop.
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
- Configure a global bash alias to enable the 'sail' command shortcut `alias sail='[ -f sail ] && bash sail || bash vendor/bin/sail'`
- Run `artisan key:generate` to generate an application key.

## Local Developmnet
- Run `sail up` to launch the Docker container and serve the site at `localhost`.
- Run `sail down` to spin down the Docker container. 