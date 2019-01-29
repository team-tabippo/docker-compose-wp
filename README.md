# WordPress開発環境 with Docker Compose

![](https://www.upcloud.com/support/wp-content/uploads/2016/03/wordpress-docker-compose.png)

※ MacでDocker composeを使ったWordPress開発環境  
  
  
## Dockerのインストール
- Docker for Macを落とす  
[https://docs.docker.com/docker-for-mac/install/](https://docs.docker.com/docker-for-mac/install/)
  
- アカウントを作成する(右上の"Create Docker ID"から作成できます)  
[https://www.docker.com/docker-mac](https://www.docker.com/docker-mac)  


## How to start 

```
git clone https://github.com/hiroki-tkg/docker-compose-wp.git [任意の開発用ディレクトリ名]
cd [任意の開発用ディレクトリ名]

# 環境git関連削除
rm -rf .git .gitignore

# ホストPCで編集できるように、wp-contentを作成
mkdir wp-content

# Docker Compose をデタッチで起動
docker-compose up -d 

# [おまけ] 編集まで1行でいけるコマンド
git clone https://github.com/hiroki-tkg/docker-compose-wp.git [任意の開発用ディレクトリ名] && cd [任意の開発用ディレクトリ名] && rm -rf .git .gitignore && mkdir wp-content && subl ../[任意の開発用ディレクトリ名]

```
※ Docker for Macをインストールすると、Docker Composeもセットでついてきます。

dockerがちゃんと動けば、以下ですぐにWordPressにアクセスできます。  
[http://localhost:9000](http://localhost:9000)

一瞬でできるし、環境がコードベースなので、差異がありません。

作成 : `<tkg.japan@gmail.com>` 


## 課題
wp cliを使って、テーマやpluginをいじりたいけど、wordpress coreがないとwp cliが動かない。  
そこで、wordpressコンテナで、volumeを ./:/var/www/html/　のようにして、  
wordpress coreがローカルにもくるように設定して試すも、wordpress coreの本体は、  
dockerのwordpressコンテナにあるので、wp cliがエラーで使えない。
  
  
何が一番やりやすいのか現状検討中です。
 


