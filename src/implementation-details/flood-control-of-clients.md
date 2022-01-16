# 5.8 クライアントの大量リクエスト対策

IRC サーバが相互に接続された大規模なネットワークでは、ネットワークに接続している任意の1つのクライアントが、ネットワークをフラッディングさせるだけでなく、他のクライアントに提供するサービスのレベルを低下させる結果となるメッセージの連続ストリームを供給することは非常に簡単です。すべての "犠牲者" が独自の保護を提供することを要求するのではなく、フラッド保護がサーバに書き込まれ、サービス以外のすべてのクライアントに適用されます。現在のアルゴリズムは以下の通りです。

* クライアントの "メッセージタイマー" が現在の時刻より小さいかどうか調べます（小さい場合は等しくなるように設定します）。

* クライアントから存在するあらゆるデータを読み取ります。

* タイマーが現在時刻より10秒以上進んでいない間、現在のメッセージをすべて解析し、メッセージごとにクライアントに2秒のペナルティを課します。

* ネットワーク上で多くのトラフィックを発生させる特定のコマンドに対して、追加のペナルティを使用することができます。

これは要するに、クライアントが悪影響を受けることなく、2秒に1回メッセージを送信できることを意味します。サービスにもこの仕組みが適用される場合があります。