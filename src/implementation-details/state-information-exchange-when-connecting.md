# 5.3.2 接続時の状態情報の交換

サーバ間で交換される状態情報の順序が重要です。必要な順序は以下の通りです。

* 既知の全サーバ

* すべての既知のクライアント情報

* すべての既知のチャネル情報

サーバに関する情報は SERVER メッセージ、クライアント情報は NICK メッセージと SERVICE メッセージ、チャネルは NJOIN/MODE メッセージで追加送信されます。

NOTE：TOPIC コマンドは古いトピック情報を上書きするため、せいぜい接続の両側でトピックを交換する程度なので、ここでチャネルのトピックを交換するべきではありません。

サーバの状態情報を先に渡すことで、すでに存在するサーバとの衝突は、第二サーバが特定のニックネームを導入することによるニックネームの衝突よりも先に発生します。IRC ネットワークは非周期的なグラフとしてしか存在できないため、ネットワークがすでに別の場所で再接続されている可能性があります。この場合、サーバの衝突が発生した場所は、ネットが分割される必要がある場所を示しています。
