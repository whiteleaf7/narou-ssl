# narou-ssl

Chrome81 から mixed-content がブロックされるようになり、「DLボタン設置」ブック
マークレットが https://syosetu.com/ などで動かなくなってしまったので、動かせる
様にします。

# 必要なもの

- docker
- docker-compose

# セットアップ＆起動

```sh
$ git clone https://github.com/whiteleaf7/narou-ssl.git
$ cp .env.sample .env
$ vim .env
$ docker-compose up
```

初回立ち上げには時間がかかるのでしばらく待つと、.env の SERVER_SSL_PORT で設定
したポート、例えば https://localhost:8443 にアクセスできる様になります。

https://localhost:8443/help にアクセスして「DLボタン設置」のブックマークレット
を取得してください。

websocket が https 環境では動かないので、あくまで「DLボタン設置」のブックマー
クレットを動かすため専用だと思ってください。「Narou.rbでダウンロード」すら動き
ません。基本的には WEB UI は http 環境で使用してください。

chrome://flags/#allow-insecure-localhost を有効にしておくと localhost で自己証
明書の警告を表示されないようになります。
