# 5.5 サーバ-サーバの接続終了

サーバとサーバの接続が、SQUIT コマンドまたは "自然な" 原因によって閉じられた場合、接続されている残りの IRC ネットワークは、閉鎖を検出したサーバによってその情報が更新されなければなりません。終了するサーバは次に SQUIT のリスト（その接続の背後にある各サーバに対して1つ)を送信する。(セクション4.1.6(SQUIT)参照)。

サーバとサーバの接続が、SQUIT コマンドまたは "自然な" 原因によって閉じられた場合、接続されている残りの IRC ネットワークは、閉鎖を検出したサーバによってその情報が更新されなければなりません。終了するサーバは次に SQUIT のリスト（その接続の背後にある各サーバに対して1つ）を送信します。（[4.1.6 SQUIT](../message-details/server-quit-message.md) 参照）。