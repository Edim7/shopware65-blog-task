Before we start, a bit about the project / set up...
Even though I named the repo shopware 65 its actually using shopware 6.4

For this to run you need PHP, Docker, Composer and Symfony CLI
We are going to use Symfonys webserver and Docker for almost everything else since this makes the workflow much easier to setup and less resource intensive



## Short info on the install and how this project was created


This project was created with composer and the shopware production:dev-flex project command below: (this gets shopware 6.4, even though I expeted 6.5)

```bash
> composer create-project shopware/production:dev-flex project
```

Application template for the Shopware Platform is in the directory `project`, which we can cd inot to start up our project
```bash
> cd project
```

Now we start our service containers:

```bash
> docker compose up -d
```

Install deps

```bash
> composer install
```

You need to install it through symfony CLI

```bash
symfony console system:install --basic-setup --drop-database --create-database -f
```

Start the webserver with Symfony CLI:

```bash
symfony server:start -d
```

PS you should use Symfony CLI instead of ./bin/console or ./psh.phar

```bash
symfony console plugin:refresh
```

To be sure that the installation succeeded, just open the following URL in your favorite browser: [127.0.0.1:8000](http://127.0.0.1:8000/)
