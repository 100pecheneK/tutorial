# デプロイ！

> **補足** このチャプターはちょっと難しいことが沢山書かれています。 頑張って最後までやりきってください。デプロイはウェブサイトを開発するプロセスの上で、とても重要な部分ですが、つまずきやすいポイントも多く含まれています。 チュートリアルの途中にこのチャプターを入れています。そういったつまずきやすい箇所はメンターに質問して、あなたが作っているウェブサイトをオンラインでみれるようにしてください。 言い換えれば、もし時間切れでワークショップ内でチュートリアルを終わらせることができなかったとしても、この後のチュートリアルはきっと自分で終わらせることができるでしょう。

今のところ、あなたが作ったサイトは、あなたのコンピューターでしかみることができません。 ここでは、デプロイの方法を学びましょう！ デプロイとは、あなたが作っているアプリケーションをインターネットで公開することです。あなた以外の人もウェブサイトを見ることができるようになりますよ. :)

これまでに学んだとおり、ウェブサイトはサーバーに置かれています。 インターネットで利用できる多くのサーバー プロバイダーがありますが、私達は [PythonAnywhere](https://www.pythonanywhere.com/) を使用します。 PythonAnywhere は、多くの人がアクセスするものではない小さいアプリケーションを無料で公開できますので今のあなたには最適でしょう。

使用するその他の外部サービスは [GitHub](https://www.github.com)、コードのホスティング サービスです。 他にも色々ありますが、ほとんどのプログラマはGitHubのアカウントを持っています。そしてあなたも今そうなります。

これら3つの場所が重要になります。 ローカルコンピューターは、開発およびテストを行う場所になります。 変更に満足したら、GitHub上にプログラムのコピーを配置します。 あなたのウェブサイトはPythonAnywhereで公開され、GitHub からコードの新しいコピーを取得することによって更新されます。

# Git

> **注：**もし、すでにインストールしていた場合は再度行う必要はありません。次のセクションに進んであなたのGitリポジトリを作り始められます。

{% include "/deploy/install_git.md" %}

## Gitリポジトリを始める

Gitはコードリポジトリ（または略して「リポジトリ」）というものの中に置かれる特定のファイルへの変更を追跡します。 私たちのプロジェクトを開始しましょう。 あなたのコンソールを開き、`djangogirls` ディレクトリでこれらのコマンドを実行します。

> **備考：**リポジトリを初期化する前に `pwd` (OSX/Linux) または `cd` (Windows) コマンドで現在の作業ディレクトリを確認してください。 `djangogirls` フォルダー内にいる必要があります。

{% filename %}command-line{% endfilename %}

    $ git init
    Initialized empty Git repository in ~/djangogirls/.git/
    $ git config --global user.name "Your Name"
    $ git config --global user.email you@example.com
    

gitリポジトリを初期化することは、プロジェクトごとに1回だけ行う必要があります（ユーザー名と電子メールをもう一度入力する必要はありません）。

Git はこのディレクトリ内のすべてのファイルとフォルダの変更を追跡しますが、無視してほしいいくつかのファイルがあります。 ベースディレクトリ内で `.gitignore` という名前のファイルを作成することによってこれを行います。 あなたのエディターを開き、次の内容で新しいファイルを作成します。

{% filename %}.gitignore{% endfilename %}

    *.pyc
    *~
    __pycache__
    myvenv
    db.sqlite3
    /static
    .DS_Store
    

これを "djangogirls" フォルダ内に `.gitignore` という名前で保存します。

> **備考：**ファイル名の先頭のドットは重要です! もしそのファイルを作るのが難しいなら、（Macをお使いの方はFinderからドット（ . ）で始まるファイルを作れません。）そういう時はエディタでSave Asから作成すれば問題ありません。 `.txt`や `.py`などの拡張子をファイル名に入れないように気をつけてください。 ファイル名が`.gitignore`でないとGitに認識されません。
> 
> **備考：** `.gitignore`ファイルで指定したファイルの1つが`db.sqlite3`です。 そのファイルはローカルデータベースで、すべてのユーザーと投稿が保存されます。 私達は標準的なウェブプログラミングの慣習に従います。つまり、ローカルのテストサイトとPythonAnywhere上の本番のウェブサイトでデータベースを分けるということです。 The PythonAnywhere database could be SQLite, like your development machine, but usually you will use one called MySQL which can deal with a lot more site visitors than SQLite. Either way, by ignoring your SQLite database for the GitHub copy, it means that all of the posts and superuser you created so far are going to only be available locally, and you'll have to create new ones on production. ローカルデータベースは本当のブログ投稿をブログから削除してしまうことを心配せずに、さまざまなことをテストできるよい遊び場として考えるといいでしょう。

`git add` コマンドを実行する前や、どのような変更を加えたか定かでない時は、 `git status` コマンドを使用する事をおすすめします。 これは間違ったファイルを追加またはコミットなど思いもかけない事を止めるために役立ちます。 `git status` コマンドは、あらゆる追跡されていない/変更されている/ステージされている（untracked/modifed/staged）ファイルや、ブランチの状態などさまざまな情報を返します。 出力は次のようになります。

{% filename %}command-line{% endfilename %}

    $ git status
    On branch master
    
    Initial commit
    
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
    
            .gitignore
            blog/
            manage.py
            mysite/
            requirements.txt
    
    nothing added to commit but untracked files present (use "git add" to track)
    

最後に、変更内容を保存します。コンソールに移動し、これらのコマンドを実行します。

{% filename %}command-line{% endfilename %}

    $ git add --all .
    $ git commit -m "My Django Girls app, first commit"
     [...]
     13 files changed, 200 insertions(+)
     create mode 100644 .gitignore
     [...]
     create mode 100644 mysite/wsgi.py
    

## GitHubにコードをプッシュする

Go to [GitHub.com](https://www.github.com) and sign up for a new, free user account. (If you already did that in the workshop prep, that is great!) Be sure to remember your password (add it to your password manager, if you use one).

そして、新しいリポジトリに "my-first-blog"の名前で新しいリポジトリを作成します。 "READMEで初期化する"チェックボックスをオフのままにし、.gitignoreオプションを空白にして（手動で行っています）、ライセンスをNoneのままにしておきます。

![](images/new_github_repo.png)

> **注** `my-first-blog`という名前は重要です。何か他のものを選択することもできますが、以下の手順では何度も繰り返す必要があります。他の名前を選択した場合は、 毎回それを置き換えてください。 できれば、`my-first-blog` の名前にしておきましょう。

次の画面では、リポジトリをクローンするためのURLが表示されます。これはこの後のコマンドで利用します。

![](images/github_get_repo_url_screenshot.png)

そして自分のコンピューター上のGitリポジトリをGitHub上のGitリポジトリに結びつけてあげる必要があります。

コンソールに次のように入力します（`<your-github-username>`をGitHubアカウントの作成時に入力したユーザー名に置き換えます。山カッコ&lt;&gt;を残さないでください。このURLはさっき見たクローンURLと一致する必要があります）。

{% filename %}command-line{% endfilename %}

    $ git remote add origin https://github.com/<your-github-username>/my-first-blog.git
    $ git push -u origin master
    

When you push to GitHub, you'll be asked for your GitHub username and password (either right there in the command-line window or in a pop-up window), and after entering credentials you should see something like this:

{% filename %}command-line{% endfilename %}

    Counting objects: 6, done.
    Writing objects: 100% (6/6), 200 bytes | 0 bytes/s, done.
    Total 3 (delta 0), reused 0 (delta 0)
    
    To https://github.com/ola/my-first-blog.git
     * [new branch]      master -> master
    Branch master set up to track remote branch master from origin.
    

<!--TODO: maybe do ssh keys installs in install party, and point ppl who dont have it to an extension -->

あなたのコードは今GitHub上にあります。 見に行きましょう！ [ Django ](https://github.com/django/django)や[ Django Girls Tutorial ](https://github.com/DjangoGirls/tutorial)、その他たくさんの素晴らしいオープンソースソフトウェアプロジェクトもGitHubでコードをホストしています。 :)

# PythonAnywhereでブログを設定する

## PythonAnywhere アカウントにサインアップする

> **備考：**あなたがすでにPythonAnywhereのアカウントを以前に作成しインストールの手順をふんでいたら、再びそれを行う必要はありません。

{% include "/deploy/signup_pythonanywhere.md" %}

## PythonAnywhere でサイトを設定する

ロゴをクリックしてメインの[PythonAnywhere Dashboard](https://www.pythonanywhere.com/)に戻り、「Bash」コンソールを起動するボタンをクリックします。これはPythonAnywhereバージョンのコマンドラインで、ちょうどあなたのコンピューターのコマンドラインと同じようなものです。

![PythonAnywhereのウェブインターフェースの「New Console」、「bash」ボタン](images/pythonanywhere_bash_console.png)

> **備考：**PythonAnywhere は Linuxベースなので、Windowsを使っている場合は、コンソールがあなたのものと少し違って見えるでしょう。

PythonAnywhereにWebアプリケーションをデプロイするには、コードをGitHubからプルし、PythonAnywhereがそれを認識してWebアプリケーションのサーバを動かし始めるように設定する必要があります。 それを手動で行う方法もありますが、PythonAnywhereはそれをすべて行うヘルパーツールを提供しています。 まず、インストールしてみましょう。

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ pip3.6 install --user pythonanywhere
    

`Collecting pythonanywhere` のようなメッセージがいくつか出力され、最終的に`Successfully installed (...) pythonanywhere- (...)`という行で終わると思います。

GitHub からアプリを自動的に構成するためのヘルパーを実行します。 PythonAnywhereのコンソールに次のように入力します（GitHubからクローンしたときのURLと一致するように、`<your-github-username>`の代わりにGitHubユーザー名を使用することを忘れないでください）：

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ pa_autoconfigure_django.py --python=3.6 https://github.com/<your-github-username>/my-first-blog.git
    

実行しているところを見れば、何をしているのかわかるでしょう。

- GitHubからコードをダウンロードする
- Creating a virtualenv on PythonAnywhere, just like the one on your own computer
- 一部のデプロイメント設定で設定ファイルを更新する
- `manage.py migrate`コマンドを使ってPythonAnywhere上のデータベースをセットアップする
- 静的ファイルの設定（これについては後で学習します）
- APIを通じてPythonAnywhereがあなたのWebアプリケーションを提供するように設定する

On PythonAnywhere all those steps are automated, but they're the same steps you would have to go through with any other server provider.

The main thing to notice right now is that your database on PythonAnywhere is actually totally separate from your database on your own computer, so it can have different posts and admin accounts. As a result, just as we did on your own computer, we need to initialize the admin account with `createsuperuser`. PythonAnywhere has automatically activated your virtualenv for you, so all you need to do is run:

{% filename %}PythonAnywhere command-line{% endfilename %}

    (ola.pythonanywhere.com) $ python manage.py createsuperuser
    

管理者の詳細を入力します。 PythonAnywhere上のパスワードをより安全にしたい場合を除き、混乱を避けるために自分のコンピュータで使用しているのと同じものを使用することをお勧めします。

PythonAnywhereのコードを`ls`を使って見てみることもできます：

{% filename %}PythonAnywhere command-line{% endfilename %}

    (ola.pythonanywhere.com) $ ls
    blog  db.sqlite3  manage.py  mysite requirements.txt static
    (ola.pythonanywhere.com) $ ls blog/
    __init__.py  __pycache__  admin.py  apps.py  migrations  models.py
    tests.py  views.py
    

また、「ファイル」ページに移動し、PythonAnywhereに組み込まれているファイルブラウザを使用して閲覧することもできます。 (Consoleページから他のPythonAnywhereページには右上のメニューボタンからいけます。 一度いずれかのページに移動したら、他ページへのリンクはトップのあたりにあります。)

## 動いています！

あなたのサイトは現在、インターネット上で動作しているはずです！ PythonAnywhereの「Web」ページをクリックしてリンクを取得します。 あなたはあなたが望む誰とでもこれを共有することができます:)

> **注** これは初心者向けのチュートリアルです。このサイトをデプロイする際にはセキュリティの観点からは理想的ではない、いくつかのショートカットをしました。 If and when you decide to build on this project, or start a new project, you should review the [Django deployment checklist](https://docs.djangoproject.com/en/2.2/howto/deployment/checklist/) for some tips on securing your site.

## デバッギングのヒント

`pa_autoconfigure_django.py`スクリプトの実行中にエラーが表示された場合は、次のような原因が考えられます。

- PythonAnywhere APIトークンの作成を忘れている
- あなたのGitHubのURLを間違えている
- *Could not find your settings.py*というエラーが表示された場合は、おそらくGitにすべてのファイルを追加できていなかったか、 GitHubにうまくプッシュできていなかった。 この場合はGitセクションをもう一度見てください
- If you previously signed up for a PythonAnywhere account and had an error with collectstatic, you probably have an older version of SQLite (eg 3.8.2) for your account. In that case, sign up for a new account and try the commands in the PythonAnywhere section above.

サイトにアクセスしようとするとエラーが表示された場合、最初にデバッグ情報を探す場所は**エラーログ**です。 PythonAnywhereの[ Webページ](https://www.pythonanywhere.com/web_app_setup/)には、このリンクがあります。 そこにエラーメッセージがあるかどうかを確認してください。 最新のものは一番下にあります。

[ PythonAnywhereヘルプサイトの一般的なデバッグのヒント](http://help.pythonanywhere.com/pages/DebuggingImportError)もあります。

つまづいた時は、コーチに助けを求めましょう。

# あなたのサイトをチェック！

サイトのデフォルトページでは、ローカルコンピュータと同じように「It worked！」と表示されます。 URLの最後に`/admin/`を追加すると、管理サイトに移動します。 Log in with the username and password, and you'll see you can add new Posts on the server -- remember, the posts from your local test database were not sent to your live blog.

いくつかの投稿を作成したら、ローカル環境（PythonAnywhereではなく）に戻ることができます。 ここから、変更を加えるためにはあなたのローカル環境で作業する必要があります。 これがWeb開発の一般的なワークフローです。ローカルで変更し、それらの変更をGitHubにプッシュし、それからその変更を公開しているWebサーバーにプルしてきます。 これにより、公開しているWebサイトを壊すことなく作業したり試したりできます。 とってもクールでしょ？

自分を*すっごく*褒めてあげてください！ サーバーのデプロイはWeb開発の最も難しい部分の1つで、ちゃんと動くようになるまで数日かかることもよくあります。 しかし、あなたは実際のインターネット上で、あなたのサイトを動かす事ができました！