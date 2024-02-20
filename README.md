# 素のlaravelファイル
phpmyadminの設定は完了済

## git clone後に行う作業
1 mkdir -p storage/framework/cache/data/
 　mkdir -p storage/framework/app/cache
 　mkdir -p storage/framework/sessions
 　mkdir -p storage/framework/views
 2 docker run --rm
 　-u ""$(id -u):$(id -g)""
 　-v $(pwd):/var/www/html
 　-w /var/www/html
 　laravelsail/php82-composer:latest
 　composer install --ignore-platform-reqs
 3 cp .env.example .env
 4 DB_CONNECTION=mysql
 　DB_HOST=mysql
 　DB_PORT=3306
 　DB_DATABASE=ファイル名で
 　DB_USERNAME=自分で決める
 　DB_PASSWORD=自分で決める
 5 "権限変更（必要な人のみ）
 　sail root-shell
 　chown sail:sail -R .
 　exit
 6 sail up
 7 npm install
 8 npm run build
 9 sail artisan key:generate
 10 sail artisan migrate
 11 localhost と localhost:8080 を表示できるか確認
