# docker コマンド実行

```

docker-compose run api rails new . --force --no-deps --database=postgresql --api

```

```

docker-compose build

```

```

docker-compose run --rm front sh -c "yarn create react-app frontend"

```

# database.yml の変更

config/database.yml 　の default: &default 欄に username, password を追記

```
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password: password
  pool: 5

```

# docker-compose で起動

```
docker-compose up -d
docker-compose run api rails db:create

```
