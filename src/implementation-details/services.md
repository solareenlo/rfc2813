# 5.2.2 サービス

新しいサービス接続の登録に成功すると、サーバにはユーザと同じ種類の要件が適用されます。サービスは多少異なるため、以下の応答のみが送信されます。rpl_youreservice, rpl_yourhost, rpl_myinfo。

これを処理した後、サーバは新しいサービスのニックネームとサービスから提供されたその他の情報（SERVICE メッセージ）およびサーバが DNS サーバから発見できた情報を他のサーバに SERVICE メッセージで送信しなければなりません。