# VS CodeにおけるGitの操作方法、VS CodeとGitHubの連携方法

1. VSCodeのterminalでgit initし、ローカルリポジトリを作成
   
2. ファイルを作成し、「＋」で、ローカルリポジトリにステージング(git add)する。これにより U→A と変化
   
3. ステージングしたファイルをコミットする
   1. 「Message」と書かれた部分にコメントを記入
   2. 「Commit」を押す
4. GitHubにログインして、リモートリポジトリを作る
   1. GitHub画面左上の『New』ボタンを押す
   2. リポジトリの名前を入力して『Create Repository』を押す
5. リモートリポジトリに結びつける
   1. PC上に作成したローカルリポジトリとGitHubで作成したリモートリポジトリの紐づけ
   ```
   $ git remote add origin https://github.com/{ユーザー名}/{リポジトリ名}.git
   ```
   2. 確認
   ```
   $ git remote -v
   ```
   ```
   # 以下が出ればOK
   $ origin  https://github.com/{ユーザー名}/{リポジトリ名}.git # fetch
   $ origin  https://github.com/{ユーザー名}/{リポジトリ名}.git # push
   ```

6. リモートリポジトリにプッシュする※
   ```
   $ git branch -M main
   $ git push -u origin main
   ```
   ※ ここでエラーが生じる場合は https://miya-system-works.com/blog/detail/vscode-github/ を参照
   PAT: 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

7. Githubに反映されたかを確認する。github上でファイルが表示されていればOK
8. （変更があった時）変更をコミット・プッシュする
   1. VSCode上でファイルを編集・追加する
   2. 変更のステージング・コミットする
   3. 変更をリモートリポジトリにプッシュする