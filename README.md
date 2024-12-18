# Git Lesson

## リモートリポジトリとローカルリポジトリとはそれぞれ何でしょうか？
・リモートリポジトリはネット上に配置して複数人で共有するためのリポジトリ。
・ローカルリポジトリは開発者一人ひとりが使用するために自分のPC上に配置するためのリポジトリ。
・システム開発は基本的にチームでの作業になるため、複数人でソースコードを共有したり、編集履歴や編集内容を都度取得するために必要。
・リポジトリとは、コードやファイルを保存する場所を指す。


## プッシュとマージの違いは何でしょうか？
・プッシュはローカルリポジトリで行った作業内容(変更履歴)をリモートリポジトリに反映させるコマンド。
・マージは各ブランチで行った作業内容(変更履歴)を指定したブランチに反映させるコマンド。
・ローカルで行った作業内容を他のメンバーと共有するため、プッシュでリモートに反映させる必要がある。


## コミットとプッシュの違い
・コミットはローカルリポジトリに対し行った作業内容(変更履歴)を保存するコマンド。
・プッシュはローカルリポジトリで行った作業内容(変更履歴)リモートリポジトリに反映させるコマンド。
・変更内容ごとにコミットするのが良い。手間はかかるが、コミットしないまま作業を終了してしまった場合やブランチを移動した時などには作業内容が保存されないため、できるだけ細かい単位でコミットするのが理想。


## コミットのメッセージはどのように書いてあげるのが最適でしょうか？
・変更内容を簡潔にわかりやすく記載するのが適切。
・複数記載することも可能であり、変更内容と変更理由を記載するなどの使い方も可能。
・「どんな指摘に対して何を修正したか」や「何をコミットしたか」が不明確なメッセージの場合、変更内容のコードを読んで理解する手間が発生するため、「どのような変更を行なったのか」がわかりやすいメッセージにする必要がある。

## ローカルでマージするフローと、プルリクエストでマージするフローの違いは何でしょうか？
・ローカルでマージする場合、現在作業を行ったブランチにいることを確認し、git merge <ブランチ名>で指定したブランチに対して変更を反映させる。その後リモートリポジトリのブランチへプッシュする。
・プルリクエストを使ってマージする場合、ローカルのBブランチからリモートのBブランチへプッシュする。その後プルリクエストを送り承認されることで、リモートのBブランチの内容がAブランチへマージされる。
・それぞれマージする際のリポジトリの場所、他者の承認が必要かどうかが異なる。
・また、プルリクエストを使ってマージする場合、リモートリポジトリ上のブランチの内容がローカルリポジトリのブランチには反映されないため、反映させるためにあらためてプルする必要がある。
・ローカルでマージする場合コードレビューがないため、最終的に誤った内容を誰も気づかないまま本番環境にアップロードしてしまう可能性があり、危険である。そのため、他者のレビューが必要なプルリクエストでマージするフローが安全。

## コンフリクトを起こしてしまった場合、どう対処すべきですか？
・ソースコードを確認し、マージされた複数の内容からどれを反映させるかを決めて修正し、修正内容をコミットし保存する。
・どれを反映させるか自分一人では判断がつかない場合、チームリーダーやPMに指示を仰ぐ。