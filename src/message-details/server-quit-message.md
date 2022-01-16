# 4.1.6 Server quit メッセージ

```
   Command: SQUIT
Parameters: <server> <comment>
```

SQUITメッセージには、2つの明確な使い方があります。

最初のもの（["Internet Relay Chat: クライアントプロトコル" [IRC-CLIENT]](https://solareenlo.com/rfc2812) で説明）は、オペレータがローカルまたはリモートサーバのリンクを切断することを可能にします。この形式のメッセージは、最終的にはサーバがリモートサーバのリンクを切断するためにも使用されます。

このメッセージの2つ目の用途は、"ネットワークスプリット"（"ネットスプリット"とも呼ばれる）が発生したとき、言い換えれば、終了したサーバや死んだサーバを他のサーバに知らせるために必要です。あるサーバが他のサーバとの接続を切断したい場合、他のサーバに SQUIT メッセージを送信する必要があります。このとき、サーバパラメータとして他のサーバの名前を使用し、サーバは終了するサーバとの接続を切断します。

`<comment>` は、エラーメッセージや同様のメッセージをここに置くべきサーバによって埋められます。

コネクションを閉じた側のサーバは、そのリンクの背後にあると考えられる他のすべてのサーバのコネクションに対して、SQUIT メッセージを送信する必要があります。

同様に、QUIT メッセージは、その終了するリンクの背後にあるすべてのクライアントに代わって、まだ接続している他のサーバに送信されるかもしれません。これに加えて、"分割" によってメンバを失ったチャネルの全メンバに QUIT メッセージを送らなければなりません。チャネルメンバへのメッセージは、各クライアントのローカルサーバで生成されます。

サーバ接続が早期に切断された場合（リンクの反対側のサーバが死んだなど）、この切断を検出したサーバは、ネットワークの残りの部分に接続が終了したことを通知し、コメントフィールドに適切な内容を記入することが要求されます。

SQUIT メッセージの結果としてクライアントが削除されたとき、サーバは将来のニックネームの衝突を防ぐために、一時的に利用できないニックネームのリストにニックネームを追加すべきです。この手順の詳細については [5.7 最近使ったニックネームの追跡](../implementation-details/tracking-recently-used-nicknames.md) を参照してください。

When a client is removed as the result of a SQUIT message, the server should add the nickname to the list of temporarily unavailable nicknames in an attempt to prevent future nickname collisions. See section 5.7 (Tracking recently used nicknames) for more information on this procedure.

数値返信：

```
        ERR_NOPRIVILEGES                ERR_NOSUCHSERVER
        ERR_NEEDMOREPARAMS
```

例：

```
SQUIT tolsun.oulu.fi :Bad Link ?
    ; tolson.oulu.fi のサーバリンクは "Bad Link" のため、終了しました。

:Trillian SQUIT cm22.eng.umd.edu :Server out of control
    ; Trillian からの "Server out of control" のため
      "cm22.eng.umd.edu" をネットから切断するというメッセージ。
```
