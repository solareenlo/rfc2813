```
Network Working Group                                           C. Kalt
Request for Comments: 2813                                   April 2000
Updates: 1459
Category: Informational
```

<h1 align="center">
Internet Relay Chat: サーバプロトコル
</h1>

## IRC
- [RFC 1459](https://solareenlo.com/rfc1459) (Internet Relay Chat Protocol)
- [RFC 2810](https://solareenlo.com/rfc2810) (Internet Relay Chat: Architecture)
- [RFC 2811](https://solareenlo.com/rfc2811) (Internet Relay Chat: Channel Management)
- [RFC 2812](https://solareenlo.com/rfc2812) (Internet Relay Chat: Client Protocol)
- [RFC 2813](https://solareenlo.com/rfc2813) (Internet Relay Chat: Server Protocol)
- [RFC 7194](https://solareenlo.com/rfc7194) (Default Port for Internet Relay Chat (IRC) via TLS/SSL)


## このメモの位置付け

このメモは、インターネットコミュニティーのための情報を提供するものです。このメモは、いかなる種類のインターネット標準も規定するものではありません。このメモの配布は無制限です。

## 著作権について

Copyright (C) The Internet Society (2000).  All Rights Reserved.

## 概要

IRC（Internet Relay Chat）プロトコルは、クライアント・サーバモデルをベースとしながらも、サーバ同士が効果的にネットワークを形成することを可能にしています。

この文書では、サーバが相互に通信するために使用するプロトコルを定義しています。元々はクライアントプロトコルのスーパーセットでしたが、異なる進化を遂げました。

1993年5月に [RFC 1459 [IRC]](https://solareenlo.com/rfc1459) の一部として初めて正式に文書化され、それ以降にもたらされた変更のほとんどは、プロトコルの拡張性に重点を置いて開発されたため、ほとんどの変更点はこのドキュメントに記載されています。スケーラビリティの向上により、既存のワールドワイドなネットワークは成長を続け、旧来の仕様では考えられなかった規模に到達することができるようになりました。
