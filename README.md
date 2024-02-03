- laravelをインストール

```bash
$ docker compose build
$ docker compose run --rm app composer create-project laravel/laravel:^10.0 .
```

```
www
├── README.md
├── app
├── artisan
├── bootstrap
├── composer.json
├── composer.lock
├── config
├── database
├── package.json
├── phpunit.xml
├── public
├── resources
├── routes
├── storage
├── tests
├── vendor
└── vite.config.js
```

- .envを更新

```
...
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=test_db_name
DB_USERNAME=test_user
DB_PASSWORD=test_pass
...
```

- (Optional) タイムゾーン、ロケール変更

```php
'timezone' => 'Asia/Tokyo'

'local' => 'ja'
```

- ドキュメントルートのリネーム

```bash
$ mv www/public  www/html
```

- public_path() の上書き

```php
// www/bootstrap/app.php

...
$app->usePublicPath(base_path('html'));

return $app;
```

- 初期セットアップ

```bash
$ docker compose up -d
$ docker compose exec app bash

# php artisan key:generate
# php artisan storage:link
# chmod -R 777 storage bootstrap/cache
```

- ページの表示確認
  - http://localhost
  - http://localhost:8080/phpmyadmin
