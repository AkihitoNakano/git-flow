# git-flow

git flow のテストです

1. リポジトリを作成する
2. ローカルにクローンする
3. git flow の初期化をする
   1. git flow init -d
4. develop ブランチと main ブランチができていることを確認
5. リモートに develop ブランチを作成するため push
   1. git push -u origin develop
6. 確認
   1. git branch -a

## Git Flow を疑似体験

### feature branch を作成する

add-user というブランチを作成する

develop ブランチからスタート

1. git pull をして最新の状態にする
2. feature branch の作成
   1. git flow feature start add-user
3. 作成できたか確認
   1. git branch
