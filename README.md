# 素のlaravelファイル
2024年2月20日時点の素のlaravelファイル<br>
phpmyadminの設定は完了済

## git clone後に行う作業
1 下記のコマンドを実行<br>
mkdir -p storage/framework/cache/data/<br>
mkdir -p storage/framework/app/cache<br>
mkdir -p storage/framework/sessions<br>
mkdir -p storage/framework/views<br>
 2 下記のコマンドを実行<br>
docker run --rm \ <br>
    -u "$(id -u):$(id -g)" \ <br>
    -v $(pwd):/var/www/html \ <br>
    -w /var/www/html \ <br>
    laravelsail/php82-composer:latest \ <br>
    composer install --ignore-platform-reqs <br>
 3 cp .env.example .env <br>
 4 DB_CONNECTION=mysql <br>
 　DB_HOST=mysql <br>
 　DB_PORT=3306 <br>
 　DB_DATABASE=ファイル名で <br>
 　DB_USERNAME=自分で決める <br>
 　DB_PASSWORD=自分で決める <br>
 5 sail up <br>
 6 "権限変更（必要な人のみ） <br>
 　sail root-shell <br>
 　chown sail:sail -R . <br>
 　exit <br>
 7 npm install <br>
 8 npm run build <br>
 9 sail artisan key:generate <br>
 10 sail artisan migrate <br>
 11 localhost と localhost:8080 を表示できるか確認 <br>
