# 4.1.3 Nick

```
   Command: NICK
Parameters: <nickname> <hopcount> <username> <host> <servertoken>
            <umode> <realname>
```

この形式の NICK メッセージは、ユーザ接続から許可されてはいけません。しかし、IRC ネットワークに新しいユーザが参加したことを他のサーバに通知するために、NICK/USER ペアの代わりに使用する必要があります。

このメッセージは、実際には3つの異なるメッセージが組み合わされたものです。NICK、USER、MODE [[IRC-CLIENT]](https://solareenlo.com/rfc2812) です。

`<hopcount>` パラメータは、ユーザがホームサーバからどのくらい離れているかを示すためにサーバが使用します。ローカル接続の場合、ホップカウントは `0` です。ホップカウントの値は、渡されたサーバごとに増加されます。

`<servertoken>` パラメータは USER の `<servername>` パラメータを置き換えます（サーバートークンの詳細については [4.1.2 節](./server-message.md) を参照してください）。

例：

```
NICK syrk 5 kalt millennium.stealth.net 34 +i :Christophe Kalt
    ; ニックネーム "syrk"、ユーザ名 "kalt" の新規ユーザが、
      ホスト "millennium.stealth.net" からサーバ "34" （前の例では "csd.bu.edu"）に接続した場合。

:krys NICK syrk
    ; "IRC クライアントプロトコル" [IRC-CLIENT] で定義され、サーバ間で使用される NICK メッセージのもう一つの形式：
      krys はニックネームを syrk に変更しました。
```
