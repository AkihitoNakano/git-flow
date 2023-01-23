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

- add-user というブランチを作成する

- develop ブランチからスタート

1. git pull をして最新の状態にする
2. feature branch の作成
   1. git flow feature start add-user
3. 作成できたか確認
   1. git branch

- develop ブランチが更新されれば常に feature ブランチに merge する
- develop 更新　 → develop/ git pull -> feature/ git merge develop

### リリースブランチを作成する

最新の develop ブランチからバージョン 1.0.0 の release 作業をします

1. git checkout develop
2. git pull
3. git flow release start '1.0.0'
   1. 基本的にバージョン番号変更のようなコミットだけを行う
4. git flow release finish '1.0.0'
   1. release ブランチが main ブランチにマージされる
5. バージョンのタグを確認する
   1. git tag
6. リモートリポジトリへの反映
   1. develop ブランチに push
   2. main ブランチにタグ情報を push
      1. git push --tags

### hotfix ブランチを作成する

- このバグを対応したバージョンを 1.0.1 とする

1. git fetch origin
2. git flow hotfix start '1.0.1' '1.0.0'
3. git push origin hotfix/1.0.1

- Github で新しいタグを作成する

1. hotfix から develop へ PR を送りマージする
2. hotfix を finish し main へマージする
