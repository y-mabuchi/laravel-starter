# Laravel Starter

Laravel Starterは、以下で構成されたDockerコンテナです。

- Nginx
- PHP
- MySQL
- Laravel7

参照 : [Laravelの環境をDockerで構築するチュートリアル](https://tech.windii.jp/backend/laravel/laravel-with-docker-compose).

# 必要なもの

* Docker 2.3.0
* docker-compose 1.26.2

# インストール 

## リポジトリをクローン
```bash
git clone git@github.com:y-mabuchi/laravel-starter.git
```

## Dockerを起動
```bash
cd laravel-starter
docker-compose up -d
```

## Dockerコンテナに入る
```bash
docker-compose exec app bash
```

## Composerインストール
```bash
composer install
```

## .envを編集
- データベース部分を編集する

```bash
cp .env.example .env
vim .env
```

```.env
DB_HOST=mysql
DB_DATABASE=laravel
DB_USERNAME=user
DB_PASSWORD=password
```

## App Keyを生成
```bash
docker-compose exec app php artisan key:generate
```

## マイグレーション実行
```
docker-compose exec app php artisan migrate
```

## ブラウザで確認
[http://localhost](http://localhost)

## リモートリポジトリを変更
```
git remote set-url origin {YOUR-NEW-REPOSITORY-URL}
```

# Author

* Yusuke Mabuchi
* mabu.you@gmail.com
