docker-rails-sample
=====

起動
-----

```
$ docker-compose run web rails new . --force --database=mysql --skip-bundle

$ vim ./rails/config/database.yml
default: &default
  adapter: mysql2
  encoding: utf8
  pool: 5
  username: root
  password: password
  host: db

$ vim ./rails/Gemfile
gem 'mysql2', '~> 0.3.20'

$ docker-compose build
$ docker-compose run web rake db:create
$ docker-compose up
```

参考
-----

https://docs.docker.com/compose/rails/
