Branch 命名規則
==================

* http://keijinsonyaban.blogspot.jp/2010/10/successful-git-branching-model.html に従う

リリース方法
====================

* developブランチからreleaseブランチを作成 (例: git checkout -b release-20130401 develop)
* style/tutorial.sty 中の講習会名(author), 講習会日時(date)を修正しcommit (例: git commit -a -m 'Bumped version number to 20130401')
* make_dist.sh を実行し, できあがったPDFファイルの中身を確認 (文字が途中で切れているところはないか? リンクは正しく動作するか? 等)
* commitが完了したら, masterにマージしtagを付ける (例: git checkout master; git merge --no-ff release-20130401; git tag -a 20130401)
* developにマージした後, リリースブランチを削除 (例: git checkout develop; git merge --no-ff release-20130401; git branch -d release-20130401)
