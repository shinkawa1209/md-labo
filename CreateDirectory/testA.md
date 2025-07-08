---
marp: true
paginate: true
---
# Git王道シナリオ（編集中）

**編集開始前**
```mermaid
flowchart LR
    A[エクスプローラーで<br>対象フォルダをCodeで開く] --> B[ターミナルはpowershell]
    B --> C[いる場所の確認<br>（フォルダ、branch）]
    C -->|フォルダ：pwd<br>branch：git branch| D[mainに移動し<br>最新のmainを取得]
    D -->|git checkout main<br>git pull origin main|E[作業用branchの作成と移動]
    E -->|git checkout -b xxx<br>（xxx:作業branch名）|F[編集開始]
```

**編集後のマージ提案**
```mermaid
flowchart LR
    A[ステージングとコミット] -->|git add .| B[ステージ]
    B -->|git commit| C[履歴に保存]
    C -->|git push| D[リモートリポジトリに反映]
    D --> E[GitHubで確認]
    E -->|GitHubで操作| F[Pull Request作成]
　
```

**作業後の処理手順**
```mermaid
flowchart LR
　　A[main branchに戻る] -->|git caeckout main|B[ローカルの<br>作業ブランチ削除]
　　B -->|git branch -d xxx<br>（作業branch名）| C[完了]
```

## 作業開始前手順

- エクスプローラーで対象フォルダを開く。
  フォルダ内で右クリック → 「Code で開く」
- VSコード内、ターミナルをpowershellで開く。

```
初回のみ gitリポジトリかの確認（「今いるディレクトリがGitで管理されているかどうか」を確認するコマンド）
　git status

管理されていなかった場合、以下コマンドの実行（2回目以降は不要）
現在のディレクトリに .git フォルダが作成され、Gitの管理が始まる
　git init
```

- 現在のフォルダの確認

```
pwd
```

```
pwd実行後▼
path
C:\Users\KTC\develop\md-labo
※ これはmd-laboにいる状態
```

- フォルダを移動したい場合

```
cd .\md-labo
※ cd m～tab押下で変換される
```
```
いるフォルダを間違えて、Pull/Fetch/Clone実行すると・・
ホーム直下に大量のファイルが作られる。（ぶちまけ状態。）
⇒ 修正方法
隠しフォルダを表示して、半透明の.gitを削除、誤マージファイル/フォルダを削除する。
◎今いる場所を把握しつつ何を実行するかが重要なポイント！
```

- 現在のbranchの確認

```
git branch または　git status
```

```
実行後▼
* feat-addflow
  main
※ 2つのbranchが存在し、* の場所にいる状態
```

- mainに移動し最新のmainを取得

```
　git checkout main
　git pull origin main
```
```
もし 他のmain以外のブランチにいる状態で git pull origin main を実行すると
main の内容が 現在のブランチにマージされてしまう。
```

- 最新のmainをベースに作業用branchの作成と移動

```
　git checkout -b xxx（xxx:作業branch名）
```

## 編集後のマージ提案

- 編集内容をadd .してcommitする
```
git add .
git commit -m "接頭辞：作業内容の説明"
```
- GitHub上にpushして反映させる
```
git psh origin xxx
```
- GitHub上でPull Request（PR）を作成
⇒ GitHub上の画面で「Compare & pull request」でマージ提案

## 作業完了後の処理
- main branchに戻る
```
git checkout main
```

- ローカルの作業ブランチ削除
```
git branch -d xxx(作業branch名)
```


