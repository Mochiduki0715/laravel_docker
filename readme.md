## セットアップ
cp docker-compose.yml.sample docker-compose.yml
docker-compose up -d --build

## docker起動後
http://localhost/

## DB接続設定
cd src
cp .env.example .env
dokcer-compose.ymlのDB方法に合わせてlaravelの.envも変更
.env内でDB情報の設定が必要
