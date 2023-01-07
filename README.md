### 1.  Gitとはファイルの変更を細かい単位で管理することができる「バージョン管理システム」である。
 　プログラムに新機能を搭載するためにプログラムファイルの追記を行うことがある。
 しかし、ファイルにエラーやバグがあった際に変更前のファイルに戻したいという場面が発生する。Gitで変更履歴を管理することができるため、変更前のファイルに戻すことが容易である。
 プログラムの開発には複数人が携わることがある。複数人での開発では誰がいつどこを変更したのかを共有することが必要である。変更したファイルを一括管理することができるため、どこまで変更されているか確認することができる。さらに、複数人で修正したものを一つに統合させることができる。
Gitを使用することで修正や変更したファイルを管理することができる。開発には複数人が携わることもあるが、人数が多いほど管理が難しくなる。プログラムの修正や変更の履歴を残すことができ、開発作業やデバック作業を効率的に行うことができるシステムである。

### 2. GitHubとはGitを用いてバージョン管理をすることができ、Gitにはない機能を持った
　世界中の開発環境で利用されているサービスである。
　Git同様にプログラムのバージョンを管理することができるサービスであるが、Gitにはない機能がある。それはプルリクエストと呼ばれる機能である。これは自分が変更したコードを他の人にレビューしてもらい、承認が通ったものを反映させるというものである。この機能は複数人で共同作成する際に有効である。
　また、ソースコードをGithubの全利用者に公開することができる。この機能を用いることで他者からの評価、自分の技術力のアピールをすることができるため、最近では就活の際にGitHubのアカウントを聞いてくる企業もある。
　バージョン管理は共同で作業する人数が増えていくことで誰がどこを変更したのかを把握することが難しくなり、複雑になっていく。Githubにあるプルリクエストという機能を用いることで他者にレビューしもらい、承認が通らなければ反映されないため、誰がどこをの部分を確認することができる。


### 3. Markdownとは、文章を記述するためのマークアップ言語である。
　マークアップ言語の有名所にHTMLがある。この言語は文章を書く際に様々なタグを使いこなすことで文章を記述していく。そのため、使いこなすにはある程度スキルを要する。しかし、Markdownもタグを使用するものの、記述したまま表示されるため、直感的に記述することができ、スキルの高さを求められづらい。
　複数人で開発する際に仕様などを共有しながら進めていく必要がある。そのため、簡単に文書を記述できるMarkdownを使用したテキストファイルを共有フォルダや開発データベースに「README.md」という名前で保存されることがある。
　Markdownとは、プレーンテキストをHTML文書へ変換するために開発されてマークアップ言語である。HTMLよりも簡単な構造になっており、直感的に文書を作成することができる。そのため、メモなどのように手軽に記述したい時に用いられる。

### Gitインストール(Mac)
* ターミナルで`brew install git` を入力すると、インストールが始まるが、そこそこ時間かかった
* `git --version`を入力し、バージョンがで出力されることを確認

そもそもこのインストール方法はHomebrewがインストールされている必要があるらしい
一応インストール方法も記載
` /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
`brew list`
`brew update`


* `git config --global user,name "ユーザー名" `を入力し、returnするとユーザー名が登録される
* `git config --global user.email "メールアドレス" ` を入力し、returnするとメールアドレスが登録される
* 登録がうまくいっていれば `git config user.name`と`git config user.email`を入力すると登録したユーザー名とアドレスが出力される


### Gitの使い方
* 新しいリポジトリを作成するために`git init`を入力する
* 入力すると、`Initialized empty Git repository in パス`というメッセージが表示され、リポジトリが作成される

#### リポジトリというのは、ファイルとかディレクトリの変更履歴を管理する場所のこと
* 作成したリポジトリにファイルを追加するには`git add 追加したいファイルのパス`
* 追加したファイルを登録するには`git commit`を行う
  * commitを行う際に`git commit -m メッセージ`で行うと、メッセージ部を残すことができ、履歴として管理しやすくなる
※ コミット時に発生したエラー
    `Untracked files:<br>
 　  (use "git add <file>..." to include in what will be committed)
	 .README.md.swp`
これはおそらくgit addが成功していないために発生している。
意図しないファイルが存在しているという意味だと思うので、一度そのファイルを削除することで対応できた。
削除コマンド`git clean -n`
* ローカルリポジトリからリモートリポジトリ(オリジナル)にアップロードするには、`git push　origin master`を行う
  ※ push時に発生したエラー`Everything up-to-date`　
  これは全てが最新版で、差分が無いという意味。原因は、コミットできていないこと

### GitHubのアカウント作成
* 公式サイトにアクセス https://github.com/
* 「Sign up fot Github」をクリックするとアカウント作成画面になる
* メールアドレス、パスワード、ユーザー名、githubににアップデートが入った際の通知を受け取るかどうかのyes,no(いらないからnoにした)、ロボットではない証明をする
* 登録したアドレスに数字のキーが届くので、それを入力する
* 色々質問されるので、適当に答える
* プランの選択を聞かれるので、"Free"を選択する

### GitHubへのREADME.mdの公開方法
* 画面の右上にある`+🔻`をクリックし、"New repository"を選択する(リポジトリっていうのはファイルの保管場所みたいなもの)
* `Repository name`に"mau-j2n"という名前をいれ、publicを選択し、`Create repository`をクリックする
* githubのリポジトリと自PCのGitと連携できるようにSSHキーというのを作成するために、
  `ssh-keygen -t ed25519 -C "githubに登録したメールアドレス`をターミナルで打ち込んで、成功していたら下のログが出てくるはず
```
  tannohidaka@hidaka mau-j2n % ssh-keygen -t ed25519 -C "メールアドレス"
Generating public/private ed25519 key pair.
Enter file in which to save the key (/Users/.ssh/id_ed25519):
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in パスワード
Your public key has been saved in パスワード.pub
The key fingerprint is:
SHA256:xxxxxxxxxxxxxxxxx
メールアドレス
The key's randomart image is:
+--[ED25519 256]--+
|o oB==BBo..      |
|o.oo+=#*+ ..     |
|o . o@ @o..      |
| . .  %.o.       |
| E.    *S        |
|  .   o          |
| .   .           |
|  . .            |
|   .             |
+----[SHA256]-----+
```
* `ls ~/.ssh`でキーが作成できていたら、
  `config		id_ed25519	id_ed25519.pub`が出てくる
* githubの画面の右上にあるプロフィールの画像をクリックして`Settings`を選択する
* 左側に出てくる`SSH and GPG keys`をクリックする
* `New SSH key`を、クリックする
* "title"は適当につけて、"key"の欄に次のコマンドをターミナルで入力し、ペーストする`pbcopy < ~/.ssh/id_ed25519.pub`
* `Add SSH key`をクリックする
* SSH接続ができるか確認のため、`ssh -T git@github.com`とターミナルで入力するとパスワードを聞かれるので、パスワードを入力してリターンを押す
```
Hi hidaka-mau! You've successfully authenticated, but GitHub does not provide shell access.
```
とログが返ってきたら成功

* ディレクトリを作成する`mkdir フォルダ名`
* 作成したディレクトリに移動する`cd フォルダ名`
* そのフォルダをgitで管理できるように`git init`を行う
* githubのリポジトリ画面で"HTTPS/SSH"と書かれたボタンの"SSH"をクリックし、コピーボタンをクリックする`git remote add origin <URL>`
* ターミナルで`git remote add origin <ペースト>`を入力するとプッシュ先のリポジトリを登録できる
* 登録が成功したか`git remote -v`で確認できる(成功していたら以下になる)
```
origin	git@github.com:hidaka-mau/mau-j2n.git (fetch)
origin	git@github.com:hidaka-mau/mau-j2n.git (push)
```
* gitに入れたいファイルを作成したら、`git add ファイル名`を入力する
* `git commit -m "Create メッセージ`
* `git push origin master`
  これで完了


  参考文献：
  * 『Web制作者のためのGitHubの教科書　チームの効率を最大化する共同開発ツール』
　　　塩谷　哲、柴竹　佑騎、平木　聡　インプレス
  * 『わかばちゃんと学ぶ　Git使い方入門』　湊川 愛 著、DQNEO 監修　C&R研究所
  * https://prog-8.com/docs/git-env
  　　　　　