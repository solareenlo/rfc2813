# 5.6 ニックネーム変更の追跡

すべての IRC サーバは最近のニックネームの変更履歴を保持することが要求されます。これはニックネームを操作するコマンドでニックネーム変更の競合状態が発生したときに、サーバが状況を把握する機会を持つために重要です。ニックネームの変更を追跡しなければならないメッセージは以下の通りです。

* KILL （切断されるニックネーム）

* MODE （チャネル上の `+`/`-` `o`,`v`）

* KICK （チャネルから外されるニックネーム）

他のコマンドでニックの変更を確認する必要はありません。

上記の場合、サーバはまずニックネームの存在を確認し、次にそのニックネームが今誰のものなのか（もし誰かいれば！）履歴を確認する必要があります。これはレースコンディションの可能性を減らしますが、サーバが間違ったクライアントに影響を及ぼしてしまうということはまだ起こり得ます。上記のコマンドで変更履歴を調べるときは、時間範囲を指定し、古すぎるエントリは無視することをお勧めします。

合理的な履歴のために、サーバは、彼らがすべて変更することを決めた場合、それが知っているすべてのクライアントのために前のニックネームを保持することができるはずです。このサイズは他の要因（例えばメモリなど）によって制限されます。