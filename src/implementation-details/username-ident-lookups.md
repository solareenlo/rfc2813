# 5.9.2 ユーザ名 (Ident) ルックアップ

他のプログラムに組み込んで使用するための ident ライブラリ（"Ident Protocol" [IDENT] を実装）は数多く存在するが、これらは同期的に動作するため、頻繁に遅延が生じるという問題がありました。この場合も、サーバの他の部分と協調し、ノンブロッキング IO で動作するルーチン群を書くことが解決策となりました。