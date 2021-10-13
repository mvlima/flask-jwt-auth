# Flask JWT Auth

Utilizado como referência o [post](https://realpython.com/blog/python/token-based-authentication-with-flask/) do blog Real Python e o código utilizados nele.

As instruções de teste seguem abaixo:

### Início

1. Fork/Clone
1. Ative um virtualenv
1. Instalar os requirements

### Configurar Variáveis de Ambiente

Atualize *project/server/config.py*, e depois rode:

```sh
$ export APP_SETTINGS="project.server.config.DevelopmentConfig"
```

ou

```sh
$ export APP_SETTINGS="project.server.config.ProductionConfig"
```

Defina uma SECRET_KEY:

```sh
$ export SECRET_KEY="change_me"
```

### Crie a DB

Cria a base de dados em `psql`:

```sh
$ psql
# create database flask_jwt_auth
# create database flask_jwt_auth_test
# \q
```

Crie as tabelas e depois rode as migrações:

```sh
$ python manage.py create_db
$ python manage.py db init
$ python manage.py db migrate
```

### Rode a Aplicação

```sh
$ python manage.py runserver
```

Acesse a aplicação no [http://localhost:5000/](http://localhost:5000/)

> Quer especificar uma porta diferente?

> ```sh
> $ python manage.py runserver -h 0.0.0.0 -p 8080
> ```

### Teste

Sem coverage:

```sh
$ python manage.py test
```

Com coverage:

```sh
$ python manage.py cov
```
