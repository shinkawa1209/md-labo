# md-labo
### はじめに
- ここは、Markdown記法で文書を作成・管理することを目指す道場です。
- 今はまだ発展途上でこれからコンテンツを充実させていきます。
---
### ルール
- Mainブランチは直接編集禁止です。
  - 更新する際は、Branchを作成して更新し、PullRequestを発行してApproveを受けて下さい。
---
### 使い方
1. まずはこのリポジトリをローカルにCloneします。
   **※必ずコマンドラインでCloneしたい場所に移動してから実行してください。**
    ```
    git clone git@github.com:shinkawa1209/md-labo.git
    ```
2. CloneされたディレクトリをVSCodeで開きます。
3. ターミナルを開き、以下のコマンドでブランチを作成します。
    ```
    git checkout -b [英語の自分の名前]edit
    ```
4. ブランチが移動出来ているか確認します。
   ```
   git branch
   ```
    手順３で作ったブランチ名に＊が付いていれば移動出来ています。
    出来ていなかったら、以下のコマンドを実施してください。
    ```
    git checkout [手順３のブランチ名]
    ```
5. 移動したブランチで編集を行います。終わったら、以下のコマンドで編集内容をステージングします。
    ```
    git add .
    ```
6. ステージング内容にメッセージを付けてCommitします。
    ```
    git commit -m "この編集の目的を書く"
    ```
7. Commitした内容をRemoteにPushします。
   ```
   git push origin [手順３で作ったブランチ名]
   ```
8. Githubサイト上で反映を確認し、Compare&PullRequastボタンから、変更内容の承認申請を行います。 

### このリポジトリのディレクトリ構成
**工事中**
検討中↓<br>
・Markdown記法のトレーニングコンテンツ<br>
・GitとGithub（もしくはAzureRepos）のトレーニングコンテンツ<br>
### Github_windowsでの注意点
- SSH　Keygen　して、Githubに公開鍵の登録が必要（ed25519で作った方が良い）
- 秘密鍵は、自分のユーザーDir直下に、「.ssh」フォルダが必要
- 鍵は、Git Bashを使って、以下のコマンドでPermissionを変更する
    ```
    chmod 600 ~/.ssh/id_ed25519
    ```
- sshAgentを起動し、鍵を登録しておくこと
  - PowerShell
  ``` 
    Get-Service ssh-agent | Set-Service -StartupType Automatic
    Start-Service ssh-agent
  ```
  - ssh-Agentが起動したら鍵を登録
  ```
    ssh-add /c/Users/あなたのユーザー名/.ssh/id_ed25519
  ```
  - 登録出来ているか、確認
  ```
    ssh-add -l
  ```
- .sshにConfigファイルを作成し、Git利用時の鍵を指定しておく。
  - Configファイルの内容（~/.ssh/configに作成）
  ```
    Host github github.com
    HostName github.com
    IdentityFile ~/.ssh/id_ed25519
    User あなたのGithubユーザー名
  ```
