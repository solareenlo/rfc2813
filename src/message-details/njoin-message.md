# 4.2.2 Njoin メッセージ

```
   Command: NJOIN
Parameters: <channel> [ "@@" / "@" ] [ "+" ] <nickname>
                      *( "," [ "@@" / "@" ] [ "+" ] <nickname> )
```

NJOIN メッセージは、サーバ間でのみ使用されます。クライアントからこのようなメッセージを受信した場合、無視しなければなりません。2台のサーバが接続し、各チャネルのチャネルメンバー一覧を交換するときに使用されます。

JOIN を連続させることで同じ機能を実現することができますが、より効率的であるため、このメッセージを代わりに使用することが望まれます。接頭辞 `@@` は "チャネル作成者"、`@` のみは "チャネルオペレータ"、`+`は "音声権限者" であることを示します。

数値返信：

```
        ERR_NEEDMOREPARAMS              ERR_NOSUCHCHANNEL
        ERR_ALREADYREGISTRED
```

例：

```
:ircd.stealth.net NJOIN #Twilight_zone :@WiZ,+syrk,avalon
    ; ircd.stealth.net からの NJOIN メッセージで、#Twilight_zone チャネルに参加するユーザをお知らせしています。
      WiZ はチャネルオペレータ、syrk は音声権限、avalon は権限なし。
```
