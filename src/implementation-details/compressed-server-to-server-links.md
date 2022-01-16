# 5.3.1.1 圧縮されたサーバ間リンク

サーバが相手と圧縮リンクを確立したい場合は、PASS メッセージのオプションパラメータに "Z" フラグを設定する必要があります。両方のサーバが圧縮を要求し、両方のサーバが2つの圧縮されたストリームを初期化できる場合、残りの通信は圧縮されることになります。いずれかのサーバがストリームの初期化に失敗した場合、そのサーバは圧縮されていない ERROR メッセージを相手側に送信し、接続を終了します。

圧縮に使用するデータ形式は、[RFC1950 [ZLIB]](https://datatracker.ietf.org/doc/html/rfc1950)、[RFC1951 [DEFLATE]](https://datatracker.ietf.org/doc/html/rfc1951)、[RFC1952 [GZIP]](https://datatracker.ietf.org/doc/html/rfc1952) で記述されています。
