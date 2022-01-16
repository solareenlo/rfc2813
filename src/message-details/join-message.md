# 4.2.1 Join メッセージ

```
   Command: JOIN
Parameters: <channel>[ %x7 <modes> ]
            *( "," <channel>[ %x7 <modes> ] )
```

JOIN コマンドは、クライアントが特定のチャネルのリスニングを開始するために使用されます。クライアントがチャネルに参加できるかどうかは、クライアントが接続しているローカルサーバのみが確認します。他のサーバは、他のサーバからコマンドを受信すると、自動的にユーザをチャネルに追加します。

オプションとして、制御 G（`^G` または ASCII 7）をセパレータとして、チャネルのユーザステータス（チャネルモード `O`, `o`, `v`）をチャネル名に付加することができます。このようなデータは、メッセージがサーバから受信されていない場合は無視されなければなりません。このフォーマットはクライアントに送信してはならず、サーバ間でのみ使用可能であり、避けるべきです。

JOIN コマンドは全サーバにブロードキャストされ、各サーバがチャネルに参加しているユーザの居場所を知ることができるようにする必要があります。これにより、PRIVMSG と NOTICE メッセージがチャネルに最適に配信されます。

数値返信：

```
        ERR_NEEDMOREPARAMS              ERR_BANNEDFROMCHAN
        ERR_INVITEONLYCHAN              ERR_BADCHANNELKEY
        ERR_CHANNELISFULL               ERR_BADCHANMASK
        ERR_NOSUCHCHANNEL               ERR_TOOMANYCHANNELS
        ERR_TOOMANYTARGETS              ERR_UNAVAILRESOURCE
        RPL_TOPIC
```

例：

```
:WiZ JOIN #Twilight_zone
    ; WiZ からの JOIN メッセージ
```
