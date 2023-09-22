## Quickstart / Installation

A full installation guide covering different dev environments is available in the [docs](https://developer.shopware.com/docs/guides/installation).

*For the impatient reader, here is a tl;dr using docker and symfony cli.*

Let's start by creating a new project:

```bash
> composer create-project shopware/production:dev-flex project
```

You now have the application template for the Shopware Platform in the directory `project`, we now change into it:

```bash
> cd project
```

Now we start our service containers:

```bash
> docker compose up -d
```

And install Shopware with the following command:

```bash
symfony console system:install --basic-setup --drop-database --create-database -f
```

Start the webserver:

```bash
symfony server:start -d
```

PS you should use Symfony CLI instead of ./bin/console or ./psh.phar

```bash
symfony console plugin:refresh
```

To be sure that the installation succeeded, just open the following URL in your favorite browser: [localhost:8000](http://localhost:8000/)