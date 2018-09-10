# Laradock Wooter

Checkout official documentation here:
https://github.com/laradock/laradock

## Setup for Wooter
Download & install Docker:
https://www.docker.com/products/docker-desktop

Checkout this repo and and put it possibly beside the wooter-project
/projects/laradock-wooter
/projects/wooter <= root folder of main wooter project

In case your path is different, edit the ```APP_CODE_PATH_HOST``` in .env

Create your .env file

```cp env-example .env```

For making the app work, we have to map a few host-name:
Add in /etc/hosts

```
127.0.0.1       mariadb
127.0.0.1       wooter.test
```

Install the docker-sync for having the best performance of docker:
```sudo ./sync.sh install```


Now you can start the server with our start script:

```./sync.sh up nginx mariadb redis```

It will need a while if you are running this the first time!
Now the containers should be ready to use (try out the http://localhost)

Make sure you don't have a mariadb/mysql running that the default port is not occupied. If you want to use a different port you have to adjust the value MARIADB_PORT in /laradock-wooter/.env 

Or you connect with a sql-client eg. Sequel Pro to

```
Host:   127.0.0.1
User:   default
Pw:     secret
```

Last but not least, edit your DB-Host in Laravels .env

```
DB_HOST=mariadb
```

To connect to containers, you have to be in the laradock-wooter folder, then execute for connecting to the nginx server:

```docker-compose exec workspace bash```

```docker-compose exec mariadb bash```


If something is not working, contact Stefan :-)
