# docker コマンド実行

```
cd .\rails-react-docker\
docker-compose build

```

# front/fontend ディレクトにて npm のインストール

```
cd .\front\frontend\
npm install
cd ../../

```

# docker-compose で起動

```
docker-compose up -d
docker-compose run api rails db:create

```
