## プラグインのインストール
- VSCodeのExtensionから`Dev Containers`をインストール

## コンテナへアタッチ
- 左下の`><マーク`をクリック
- Remote接続するメニューが表示される
- `実行中のコンテナーにアタッチ`を選択

## コンテナ内でLaravelのインストール
`composer create-project laravel/laravel .`

## DBの設定
#### .envの修正
変更前
```
DB_CONNECTION=sqlite
# DB_HOST=127.0.0.1
# DB_PORT=3306
# DB_DATABASE=laravel
# DB_USERNAME=root
# DB_PASSWORD=
```

変更後
```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE={「laravel-wp」リポジトリ直下にある「.env」の「DB_DATABASE」の値}
DB_USERNAME={「laravel-wp」リポジトリ直下にある「.env」の「DB_USERNAME」の値}
DB_PASSWORD={「laravel-wp」リポジトリ直下にある「.env」の「DB_PASSWORD」の値}
```

#### マイグレーションコマンドの実行
`php artisan migrate`

## Laravelにアクセス
#### `Failed to open stream: Permission denied`が表示される場合
コマンドの実行`chmod -R 777 /var/www/html/storage`
