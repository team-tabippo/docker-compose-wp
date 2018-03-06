FROM wordpress:latest

# 必要なツール郡をインストール
RUN apt-get update
RUN apt-get -y install wget unzip

# WP プラグイン (zip) ダウンロード
WORKDIR /tmp/wp-plugins
RUN wget https://downloads.wordpress.org/plugin/contact-form-7.4.6.zip
RUN wget https://downloads.wordpress.org/plugin/syntaxhighlighter.zip
RUN wget https://downloads.wordpress.org/plugin/advanced-custom-fields.4.4.12.zip
RUN wget https://downloads.wordpress.org/plugin/wp-emmet.zip
RUN wget https://downloads.wordpress.org/plugin/all-in-one-seo-pack.2.4.5.1.zip
RUN wget https://downloads.wordpress.org/plugin/any-mobile-theme-switcher.2.1.zip
RUN wget https://downloads.wordpress.org/plugin/backwpup.3.4.4.zip
RUN wget https://downloads.wordpress.org/plugin/db-cache-reloaded-fix.zip
RUN wget https://downloads.wordpress.org/plugin/google-sitemap-generator.4.0.9.zip
RUN wget https://downloads.wordpress.org/plugin/query-monitor.2.17.0.zip
RUN wget https://downloads.wordpress.org/plugin/regenerate-thumbnails.zip
RUN wget https://downloads.wordpress.org/plugin/simple-301-redirects.1.07.zip
RUN wget https://downloads.wordpress.org/plugin/wp-mail-smtp.zip
RUN wget https://downloads.wordpress.org/plugin/wp-user-avatar.zip

https://wordpress.org/plugins/advanced-custom-fields/
# Zip ファイルを解凍してインストール
RUN unzip './*.zip' -d /usr/src/wordpress/wp-content/plugins

# 不要になった一時ファイルを削除
RUN apt-get clean
RUN rm -rf /tmp/*

# 不必要なファイルを削除
RUN rm -rf /usr/src/wordpress/wp-content/themes/twentysixteen
RUN rm -rf /usr/src/wordpress/wp-content/themes/twentyfifteen
RUN rm -rf /usr/src/wordpress/wp-content/themes/index.php
RUN rm -f /usr/src/wordpress/wp-content/plugins/hello.php
RUN rm -f /usr/src/wordpress/wp-content/plugins/index.php

# サーバが読めるように wp-content 以下の所有者を変更
RUN chown -R www-data:www-data /usr/src/wordpress/wp-content

WORKDIR /var/www/html
