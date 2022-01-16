# 4.1.2 Server メッセージ

```
   Command: SERVER
Parameters: <servername> <hopcount> <token> <info>
```

SERVER コマンドは、新しいサーバを登録するために使用されます。新しい接続は、その相手に対して自分自身をサーバとして紹介します。このメッセージは、サーバのデータをネット全体に渡すためにも使われます。新しいサーバがネットに接続されると、そのサーバに関する情報はネットワーク全体にブロードキャストされなければなりません。

`<info>` パラメータには空白文字が含まれることがあります。

`<hopcount>`は、各サーバがどの程度離れているかという内部情報を全サーバに与えるために使用されます。ローカルピアの値は `0` で、渡されたサーバごとに値が増加します。完全なサーバリストがあれば、サーバツリー全体のマップを作成することが可能ですが、ホストマスクがこれを阻んでいます。

`<token>` パラメータは、サーバが識別子として使用する符号なし数字です。この識別子は、その後サーバ間で送信される NICK および SERVICE メッセージでサーバを参照するために使用されます。サーバトークンは、使用されるポイントツーポイントピアリングでのみ意味を持ち、その接続で一意でなければなりません。これらはグローバルではありません。

SERVER メッセージは、(a) まだ登録されておらず、サーバとして登録しようとしている接続、または (b) 他のサーバへの既存の接続、この場合、SERVER メッセージはそのサーバの後ろに新しいサーバを紹介している、のいずれかからのみ受け入れられなければなりません。

SERVER コマンドを受信した際に発生するエラーの多くは、宛先ホスト（ターゲットサーバ）によって接続が切断されることになります。このような事象は重大であるため、エラーの返答は通常、数値ではなく "ERROR" コマンドを使用して送信されます。

SERVER メッセージが解析され、それが受信サーバにすでに知られているサーバを紹介しようとした場合、サーバへの重複したルートが形成され、IRC ツリーの非周期性が壊れるため、そのメッセージが到着した接続は（正しい手順で）閉じられなければなりません。条件によっては、すでに知られているサーバが登録されている接続を代わりに閉じてもかまいません。この種のエラーは、2番目に稼働しているサーバの問題である可能性もあり、プロトコル内で修正することはできず、通常は人間の介入を必要とすることに注意する必要があります。この種の問題は、IRC ネットワークの一部が簡単に孤立してしまい、それぞれのパーティションに接続されている2台のサーバのうち1台が、2つのパーティションを結合することができなくなるため、特に陰湿なものとなっています。

数値返信：

```
        ERR_ALREADYREGISTRED
```

例：

```
SERVER test.oulu.fi 1 1 :Experimental server
    ; 新しいサーバ test.oulu.fi が自己紹介し、登録を試みています。

:tolsun.oulu.fi SERVER csd.bu.edu 5 34 :BU Central Server
    ; サーバ tolsun.oulu.fi は、5ホップ離れている csd.bu.edu へのアップリンクです。
      トークン "34" は、csd.bu.edu に接続する新しいユーザやサービスを紹介する際に、tolsun.ulu.fi によって使用されます。
```