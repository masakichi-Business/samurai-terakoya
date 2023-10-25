- GitHubとは何かを知ろう
  GitHubとは無償で利用することができ、特にエンジニアやデザイナーなど技術職の方が多く活用しているツールになります。<br>
  GitHubの特徴と開発現場での使われ方、似ているgitというツールとの違いについて順に説明していきたいと思います。
  - GitHubの特徴
    GitHubとはインターネット上で自身や協業メンバーが制作した資材を管理するためのツールです。
    自身のローカル(お手元のPC)で作成したものをGitHub上へアップロード(資材の添付)したり、GitHub上にある資材を自身のローカル環境にダウンロードしたりが可能です。
  - GitHubの開発現場での利用シーン
    実際の現場では
  - Gitとは
- GitHubの用語を理解しよう
  GitHubとGitで登場する用語や作業の流れを把握していきます。<br>
  - GitHubでの作業の流れ
  - 用語の理解
    - ローカルリポジトリ
    - リモートリポジトリ
    - commit
    - push
    - pull
    - fetch
    - marge
    - index
    - pull request
    - clone
    - master
    - devlop
    - branch
- GitHubへアクセスしよう
  まずはGoogle Chromeを使用し、GitHub(https://github.co.jp/)にアクセスしてみましょう。<br>
- GitHubの基本的な使い方をマスターしよう#1
  - ファイルの追加方法
  - ファイルの編集方法
  - ファイルの削除方法
  - ファイルのアップロード
  - ファイルのダウンロード
  - ディレクトリの作成
  - 作成したディレクトリにファイルのアップロード
  - ブランチの作成
- GitHubの基本的な使い方をマスターしよう#2
  - 差分の比較方法
  - タグ付け方法
  - 任意のブランチやタグのファイルやフォルダをダウンロードする方法
- Git・GitHubの関係について理解しよう
  Gitとはファイルなどの資材を「誰が、いつ、どのように」修正したか記録しておくためのツールです。  開発現場では複数のメンバーが共同で開発を行いますが、Gitを使用しなければ、ファイルの修正履歴を辿ったり、現在のファイルの状態を確認することが困難になります。
Gitを使用することで開発をより効率的に実施することが可能となるのです。
  - GitとGitHubの関係
    Gitとはローカル環境で作業したファイルなどを共有サーバーを使用したリモートリポジトリに挙げることでメンバー内で共同で作業するツールです。
    一方でGitHubは共有サーバを自前で用意する必要がなく、無償でリモートリポジトリを作成し、共同開発する場を作ることができます。
  - Gitの概要図
    Gitでは主にローカルリポジトリとリモートリポジトリというものが存在します。
    ローカルリポジトリとは自前のPCなどの環境のことです。共同で開発を行う際にいきなりリモートリポジトリで作業するのではなく、ローカル環境で動作を確認した上で変更箇所をリモートリポジトリへ反映させます。
    ローカルリポジトリの変更をリモートリポジトリに反映させるためにGitコマンドというものを使用します。
    Gitコマンドを使用し、まずはローカルリポジトリの変更を「index(貯蔵庫のようなもの)」にcommitします。一度にリモートリポジトリに反映させるのではなく、indexにcommitし、差分を確認し、続いてリモートリポジトリへpushします。
- Gitをインストールしよう
  https://gitforwindows.org/
  gitバージョン確認コマンド
  git --version
- Gitの初期設定をしよう
  Gitの設定を行うことでファイルを操作したユーザが誰でいつ、どのように操作したかがわかるようになります。
  - Gitの設定ファイル3種類
    - system
      システム全体
    - global
      ユーザ全体
    - local
      対象リポジトリのみ
  - とりあえず、変更しておきたい初期設定
    - ユーザ名
    ```
    git config --[設定ファイルの種類] [設定項目] [設定する値]
    ```
    ```
    git config --global user.name "あなたのGitHubユーザー名"
    ※命名規則に則ったユーザ名にする
    ```
    - メールアドレス
    ```
    git config --global user.email "あなたのGitHubメールアドレス"
    ```
    - 設定した内容の確認
    ```
    git config --global user.name
    git config --global user.email
    ```
    設定の一覧表示
    ```
    git config --global --list
    ```
    - デフォルトブランチの確認と変更
    ```
    git config init.defaultBranch
    // もし、デフォルトがメインではなかったら
    git config --global init.defaultBranch main
    ```
- Gitでファイルを管理しよう
  開発する際にファイルなどの資材を置いておく場所をリポジトリと呼びました。その中で動作確認が終わっていない作業途中のものはローカルリポジトリという場所で管理をします。まずはGitコマンドを使ってローカルリポジトリで作業する環境を整えていきましょう。
  - ローカルリポジトリを配置するためのディレクトリを作成します。
    自身のPCに作業用のディレクトリを作成します。コマンドは「mkdir」です。
    mkdir git_tutorial
    // 作成したディレクトリに移動します。
    cd git_tutlrial
    // カレントディレクトリにローカルリポジトリを新規作成します。
    git init
    フォルダを確認し.gitフォルダが作成されていれば、カレントディレクトリがgit管理下になっていることを示しています。
    // 修正した素材をindexに登録します。
    # 1つのファイルをインデックスに登録する
    git add [ファイルパス]

    # ディレクトリごとインデックスに登録する
    git add [ディレクトリパス]

    # ワークツリーの変更をすべてインデックスに登録する
    git add .
    // ローカルリポジトリへの登録
    git commit -m "ここにコミットメッセージを入力"
    // 登録内容の確認
    git status
    // 差分の確認
    # インデックスとローカルリポジトリの変更差分を確認する
    git diff --staged
    // 過去の修正内容の確認
    git log
    // 1行で表示
    git log --oneline
    // ファイル削除
    git rm 【ファイルパス】
    // ファイル移動
    git mv [旧ファイルパス] [新ディレクトリパス]
- リモートリポジトリの使い方を理解しよう
  リモートリポジトリのGitHubにローカルリポジトリの内容をアップロードする方法を理解します。
  流れとしては、
　① GitHubにSSH接続するための設定を行う。
　② ローカルリポジトリとリモートリポジトリを接続する。
  ③ リモートリポジトリへアップロードする。
  - SSH方式で接続するためのステップ
    - 秘密鍵と公開鍵の作成
      ssh-keygen -t rsa -C [GitHubに登録したメールアドレス]
    - 保存ファイル名の設定(デフォルトでOK)
      Generating public/private rsa key pair.
      Enter file in which to save the key ([ユーザーフォルダパス]/.ssh/id_rsa):
    - パスフレーズを決められます。セキュリティの観点から設定しましょう。
      Enter passphrase (empty for no passphrase):
    - 以下のような成功メッセージが表示されます。id_rsa.pubが公開鍵、id_rsaが秘密鍵です。
      Your identification has been saved in ■■■.ssh/id_rsa.
Your public key has been saved in ■■■.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:■■■■■■■■■■■■■■■■■ mail@sample.jp
The key's randomart image is:
+---[RSA 2048]----+
|   xxxx          |
|xxxxxxxxxxx      |
| x x x xxx  xxx  |
|        xx  x    |
|     xx x        |
|       x x       |
|        x x      |
|         x       |
|          x      |
+----[SHA256]-----+
     - 鍵の内容をGitHubに登録します。成功したメッセージに表示されているパスを使います。
       cat ■■■.ssh/id_rsa.pub.
     - 表示された内容を丸ごとコピーします。
       ssh-rsa ■■■■■■■■■■■■■■■■■■■■■■■■■■■■■
■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■■
■■■■■■■■■■■■■■■■■■■■■■■■ mail@sample.jp
     - GitHubの画面を開きSettingにさきほどのキーを登録します。
     - SSH接続の確認
       ssh -T git@github.com
       // 以下のメッセージにYesと回答します
       The authenticity of host 'github.com (13.114.40.48)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
RSA key fingerprint is MD5:16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)? 
       // パスフレーズを求められます
       Warning: Permanently added 'github.com,13.114.40.48' (RSA) to the list of known hosts.
Enter passphrase for key '/home/ec2-user/.ssh/id_rsa': 
       // エンターを押すと以下の成功メッセージが表示されます
       Hi tarou-samurai! You've successfully authenticated, but GitHub does not provide shell access.
  - ローカルリポジトリとリモートリポジトリの接続
    - 新しく接続する場合、
      git remote add [リモートリポジトリの簡易名] [リモートリポジトリのURL]
      // originはGitのデフォルト、リモートリポジトリのURLはGitHubから取得できます
      git remote add origin
    - 接続確認
      git remote -v
  - リモートリポジトリに反映させよう
    ローカルリポジトリの内容をリモートリポジトリにプッシュします
    git push -u [接続先のリモートリポジトリ] [ローカルリポジトリのブランチ名]
    // 今回はブランチを分けていないためmain、-uで紐づけ先のリモートリポジトリを設定可能にしています
    git push -u origin main
    // GitHub側でサインインを求められます
    // 成功メッセージが表示されます
  - 次回以降はgit pushだけでindexからリモートリポジトリへpushできます。
- 変更を取り消す方法を理解しよう
  作成したファイルに対して取り消す操作を学びます
  - git checkout
  echo "ファイルに入れたい文字列" >> 作成したいファイル名
  git add README.md
  git commit -m "READMEファイル追加"
  // ファイルの内容を変更
  echo "侍エンジニア" >> README.md
  // ファイルの変更を取り消す
  git checkout -- README.md
  - git reset
  echo "インデックスの変更取消しを確認" >> README.md
  git add README.md
  git status
  git reset HEAD README.md
  git status
- 直前のコミットを修正
  echo "コミットメッセージの修正を確認" >> README.md
  git add README.md
  git commit -m "コミットメッセージを習性"
  git commit --amend -m "コミットメッセージを修正"
  git log --oneline
- リモートリポジトリへ反映済みの内容を修正
  git revert ［コミットID］

- リモートリポジトリから必要な情報を取得しよう
  リモートリポジトリから必要な情報を取得するには以下の2パターンがあります。
  - git fetch→git merge
    git fetch origin main
    git merge origin/main
  - git pull
    git pull origin main
- ブランチを使いこなせるようになろう
  ブランチとは開発を行う際にベースとなるmainブランチから枝分かれしたものです。
  - git branch
    // ブランチ名を指定する
    git branch feature
    // ブランチ一覧表示
    git branch
    //  ブランチ切り替え
    git checkout feature
    // ブランチ作成＆切り替え
    git checkout -b feature
    // ブランチの変更をプッシュ
    git push -u origin feature
　- mainブランチにマージ
    git checkout main
    git merge feature
    // mainブランチへのマージ確認
    git ls-tree --name-only main
  - コンフリクト
- Gitでの作業を退避する方法
  gitで作業中のファイルなどを退避させたい場合について学習します。
  - git stash
    // indexとローカルの変更を退避します
    git stash push -u -m "わかりやすいメッセージ"
    // 退避したリスト一覧表示
    git stash list
    // 直前のstashだけ復元
    git stash
    // indexも含めて復元
    git stash apply --index
    // 指定して復元
    git stash apply stash@{1}
    // 退避データの削除
    git stash drop
    // すべての退避データの削除
    git stash clear
- プルリクエストを実行しよう
  プルリクエストとはレビュワーに修正した内容を確認し、mainブランチに取り込んでもらうための依頼のことです。
  - プルリクまでのステップ
    ①mainブランチの内容をpullし最新にする
    ②ブランチを作成する。
    ③ブランチ内で資材を修正する。
    ④修正内容をGitHubに反映する。
    ⑤プルリクエストを依頼する。
