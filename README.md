# Rails Tutorial
Rails Tutorial on docker

## How to use
### Run an existing project
Please execute the following command.

```bash
$ docker-compose build
```

### Initialize Database

```bash
$ docker-compose run web rails db:migrate
```

### Run test

```bash 
$ docker-compose run web rails test
````

