# 3.4 数値返信

サーバに送信されたメッセージのほとんどは、何らかの応答を生成します。最も一般的な返信は数値による返信で、エラーと正常な返信の両方に使用されます。数値返信は、送信者接頭辞、3桁の数値、リプライのターゲットからなる1つのメッセージとして送信する必要があります。サーバがこのようなメッセージを受信すると、静かに削除されます。キーワードが文字列ではなく3桁の数字で構成されていることを除けば、他のすべての点で、数値による返信は通常のメッセージと同じです。異なる返信のリストは ["IRC クライアントプロトコル" [IRC-CLIENT]](https://solareenlo.com/rfc2812) で提供されています。
