# 1. 序説

この文書は、IRC サーバの実装に取り組んでいる人々を対象としていますが、IRC サービスを実装している人にも役に立つでしょう。

サーバは、"Internet Relay Chat: アーキテクチャ" [[IRC-ARCH](https://solareenlo.com/rfc2810)] で定義されたリアルタイム会議に必要な3つの基本サービスを提供します。クライアントプロトコルによるクライアントロケータ [[IRC-CLIENT](https://solareenlo.com/rfc2812)]、この文書で定義されたサーバプロトコルによるメッセージ中継、特定の規則に従ったチャネルのホストと管理 [[IRC-CHAN](https://solareenlo.com/rfc2811)] です。
