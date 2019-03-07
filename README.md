# Quick start guide

## Clone repositories

```bash
git clone --recursive https://github.com/rezonanc/devilbox-symfony-example.git
```

*Note*: This will clone out all linked git sub-modules as well:

* `devilbox` - development environment
* `symfony-hello-app` - simple hello world Symfony application

## Start docker

* Make sure docker is running
* Make sure there are no conflicting services already binded for localhost on ports:
  * `80`
  * `1053`
  * `3306`
  * `5432`
  * `6379`
  * `11211`
  * `27017`

```bash
cd devilbox-symfony-example
docker-compose up -d
```

## Install project

```bash
docker-compose exec --user devilbox php bash -c "cd /shared/httpd/symfony-hello-app/project/ && composer install -n"
```

## Check development environment dashboard

* Visit http://127.0.0.1

## Manage virtual hosts

* Visit http://127.0.0.1/vhosts.php to see which entries are necessary to be added to `/etc/hosts` (*Linux/macOS*)

## Profit

Visit http://symfony-hello-app.loc/

## Help

For more details on how to manage the development environment please see: https://devilbox.readthedocs.io/en/latest/
