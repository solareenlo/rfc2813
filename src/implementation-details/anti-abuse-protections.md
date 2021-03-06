# 5.3.1.2 不正使用防止対策

ほとんどのサーバは、信頼できない当事者（通常はユーザ）から起こりうる悪用行為に対して、さまざまな種類の保護機能を実装しています。ネットワークによっては、このような保護が必要不可欠な場合もあれば、不必要な場合もあります。特定のネットワークにおいて、すべてのサーバがそのような機能を実装し、有効にすることを要求するために、2つのサーバが接続するときに "P" フラグが使用されます。このフラグがある場合、サーバの保護機能が有効であることを意味し、サーバはすべてのサーバリンクに対して同様に保護機能を有効にすることを要求します。

一般的に見られる保護機能は、[5.7 最近使ったニックネームの追跡](./tracking-recently-used-nicknames.md) と [5.8 クライアントの大量リクエスト対策](./flood-control-of-clients.md) で説明されています。
