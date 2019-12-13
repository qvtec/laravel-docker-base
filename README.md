# 環境構築

## 1. クローン

`git clone [プロジェクト]`


## 2. Docker起動

### 2-1. docker設定ファイルの作成

```
cd docker/
cp env-example .env
```

### 2-2. ビルドと起動

`docker-compose up -d --build`

### 2-3. コンテナ接続

`docker-compose exec work bash`


## 3. プロジェクト設定

workコンテナで実行する

### 3-0. Laravel初期プロジェクト

`laravel new`

### 3-1. Laravel設定ファイル

`cp .env.example .env`

```
DB_HOST=mysql
DB_USSERNAME=root
DB_PASSWORD=root

CACHE_DRIVER=redis
REDIS_HOST=redis

MAIL_DRIVER=log
```

### 3-2. composer install

```
composer dump-autoload
composer install
```

### 3-3. マイグレーション

```
php artisan migrate
```

## 4. hosts設定と表示

```
127.0.0.1 local.admin.com
```

https://local.admin.com/


## その他

* 次回からの起動(ビルド不要)
`docker-compose up -d`

* 起動確認
`docker-compose ps`

* ログ
`docker-compose logs --f`
