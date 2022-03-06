# userApp
このアプリケーションは、ユーザー登録することにより使用できます。

# Description
会員登録、ログインします。  
その後、ユーザー情報を閲覧・編集が可能になります。

# Installation
①ローカルリポジトリを作成し、クローンする。  
任意のローカルリポジトリを作成し、下記コマンドを実行  
$git clone https://github.com/masanob0213/Connect.inc.git.

②.envファイルを作成  
・ローカルリポジトリに移動  
$cd ローカルリポジトリ  
・DockerPracticeディレクトリに移動  
$ cd DockerPractice  
・appコンテナに入る。  
$ winpty docker-compose exec app bash  
・プロジェクトに移動  
$cd userapp  
env.sampleから.envを作成  
$ cp .env.sample .env

③.envファイルの編集  
・上記で作成した.envファイルの11行目あたりを下記に編集。  
DB_CONNECTION=mysql  
DB_HOST=laravel_db  
DB_PORT=3306  
DB_DATABASE=laravel_db  
DB_USERNAME=laravel_user  
DB_PASSWORD=laravel_pass  

④マイグレーションの実行  
・上記で作成したリモートリポジトリに移動  
$ cd リモートリポジトリ  
・appコンテナに入る。  
$ winpty docker-compose exec app bash  
・laravelプロジェクトに移動  
$ cd userapp/  
・マイグレーション実行  
$ php artisan migrate  
・phpMyAdminにアクセスし、データベース作成されていることを確認  
http://127.0.0.1:8080/

⑤コンテナの立ち上げ  
・上記で作成したリモートリポジトリに移動  
$ cd リモートリポジトリ  
・DockerPracticeディレクトリに移動  
$ cd DockerPractice  
・イメージ作成  
$ docker-compose build  
・コンテナを起動  
$ docker-compose up -d  

⑥動作確認  
http://localhost/  
にアクセスし、ログイン画面が表示されること

# Requirement
Laravel 8.83.3  
Docker Desktop 4.5.1  
MySQL 5.7.37  
PHPMyAdmin：5  
gitbash 2.35

# DEMO
【初めて利用する方】  
名前、電話番号、メールアドレス、パスワードを入力し、会員登録する。  
![register](https://user-images.githubusercontent.com/90172942/156915134-343e86ed-4914-4ab3-ac7e-067f1f20af70.png)


【会員登録済の方】  
メールアドレス、パスワードを入力しログインする。
![login](https://user-images.githubusercontent.com/90172942/156915193-db78d1f0-5bc5-44db-8681-49e8ee7c96e3.png)

・会員情報の表示  
![index](https://user-images.githubusercontent.com/90172942/156907822-ed002b9f-a9df-4bb4-9a8a-de609e1afb5a.png)

・会員情報の変更  
![edit](https://user-images.githubusercontent.com/90172942/156907796-3b8f89d9-9699-4dbc-863e-54fc47ae45a5.png)

# Author
【NAME】 M.Ohmori  

# License  
https://choosealicense.com/no-permission/

