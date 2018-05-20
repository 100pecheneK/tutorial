> このチャプターの一部はGeek Girls Carrots (http://django.carrots.pl/)のチュートリアルに基づいています。
> 
> このチャプターの一部はCreative Commons Attribution-ShareAlike 4.0 International License のライセンスによるdjango-marcador tutorialに基づいています. このdjango-marcador tutorialはMarkus Zapke-Gründemann らが著作権を保有しています。 

## 仮想環境

Django をインストールする前に、あなたのコーディング環境を、きれいにしておく便利な道具をインストールしてもらいます。 このステップをとばすこともできますが、しかし、このステップをとばすことは全くお勧めしまません。 可能な限りベストなセットアップで始めることは将来のたくさんのトラブルからあなたを救うはずですから！

さあ、**仮想環境（virtual environment )**(*virtualenv*とも呼ばれています）を作成してみましょう。 仮想環境（virtual environment）ではプロジェクト単位であなたのPython/Djangoのセットアップを他から隔離します。 これは、あなたがひとつのウェブサイトにおこなったどんな変更も、あなたが開発している他のサイトに影響を及ぼさないということです。 便利でしょ？

あなたがしなければならないのは、あなたが`仮想環境（virtual environment）`を作成したいディレクトリを見つけることです（たとえばホームディレクトリなどです）。 Windowsでは、ホームディレクトリは、`C:\Users\Name`と書かれているかもしれません (`Name`はあなたのログインネームです)。

> **補足：**　Windowsの方は、ディレクトリ名に特殊文字やアクセント記号を含まないよう気をつけてください。もし、ユーザー名が特殊文字を含む場合は、`C:\djangogirls` のようなディレクトリを作成してください。

このチュートリアルのために、ホームディレクトリに新しいディレクトリ`djangogirls`を作成します。

{% filename %}command-line{% endfilename %}

    $ mkdir djangogirls
    $ cd djangogirls
    

`myvenv`という仮想環境（virtual environment）を作成します。一般的なコマンドは以下のようになります：

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

<!--sec data-title="Virtual environment: Windows" data-id="virtualenv_installation_windows"
data-collapse=true ces-->

新しい`virtualenv`を作成するために、コマンドプロンプトを開き（コマンドプロンプトについては何章か前にお話ししましたね。覚えてますか？）、`python -m venv myvenv`を実行して下さい。たとえばこのように入力します：

{% filename %}command-line{% endfilename %}

    C:\Users\Name\djangogirls> python -m venv myvenv
    

`myvenv` というところが、あなたの`virtualenv（仮想環境）` の名前です。 どんな名前でも使うことができますが、必ず小文字で表記し、スペース・アクセント記号・特殊文字は入れないでください。 短い名前にしておくのもいいアイデアですーあなたはこの名前を何度も参照しますから！

<!--endsec-->

<!--sec data-title="Virtual environment: Linux and OS X" data-id="virtualenv_installation_linuxosx"
data-collapse=true ces-->

LnuxやOX Xで`virtualenv`を作るときは、`python3 -m venv myvenv`と実行するだけです。 たとえばこんな感じです：

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

`myvenv` は、あなたの `仮想環境(virtualenvironment)` の名前です。 どんな名前でも使うことができますが、必ず小文字で表記し、スペースは入れないでください。 短い名前にしておくのもいいアイデアですーあなたはこの名前を何度も参照しますから！

> **NOTE:** On some versions of Debian/Ubuntu you may receive the following error:
> 
> {% filename %}command-line{% endfilename %}
> 
>     The virtual environment was not created successfully because ensurepip is not available.  On Debian/Ubuntu systems, you need to install the python3-venv package using the following command.
>        apt install python3-venv
>     You may need to use sudo with that command.  After installing the python3-venv package, recreate your virtual environment.
>     
> 
> In this case, follow the instructions above and install the `python3-venv` package: {% filename %}command-line{% endfilename %}
> 
>     $ sudo apt install python3-venv
>     
> 
> **NOTE:** On some versions of Debian/Ubuntu initiating the virtual environment like this currently gives the following error:
> 
> {% filename %}command-line{% endfilename %}
> 
>     Error: Command '['/home/eddie/Slask/tmp/venv/bin/python3', '-Im', 'ensurepip', '--upgrade', '--default-pip']' returned non-zero exit status 1
>     
>     
> 
> このエラーを回避するために、代わりに`仮想環境(virtualenvironment)`コマンドを使います。
> 
> {% filename %}command-line{% endfilename %}
> 
>     $ sudo apt install python-virtualenv
>     $ virtualenv --python=python3.6 myvenv
>     
> 
> **NOTE:** If you get an error like
> 
> {% filename %}command-line{% endfilename %}
> 
>     E: Unable to locate package python3-venv
>     
> 
> then instead run:
> 
> {% filename %}command-line{% endfilename %}
> 
>     sudo apt install python3.6-venv
>     

<!--endsec-->

## 仮想環境の操作

上に示したコマンドは仮想環境（基本的には一連のディレクトリとファイル）を含む`myvenv` という名前（あるいはあなたが選んだ名前）のディレクトリを生成します。次に我々がしたいのは、これを実行し、開始することです。

<!--sec data-title="Working with virtualenv: Windows" data-id="virtualenv_windows"
data-collapse=true ces-->

実行して、仮想環境を起動します。

{% filename %}command-line{% endfilename %}

    C:\Users\Name\djangogirls > myvenv\Scripts\activate
    

> **NOTE:** on Windows 10 you might get an error in the Windows PowerShell that says `execution of scripts is disabled on this system`. In this case, open another Windows PowerShell with the "Run as Administrator" option. Then try typing the following command before starting your virtual environment:
> 
> {% filename %}command-line{% endfilename %}
> 
>     C:\WINDOWS\system32> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
>         Execution Policy Change
>         The execution policy helps protect you from scripts that you do not trust. Changing the execution policy might expose you to the security risks described in the about_Execution_Policies help topic at http://go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy? [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): A
>     

<!--endsec-->

<!--sec data-title="Working with virtualenv: Linux and OS X" data-id="virtualenv_linuxosx"
data-collapse=true ces-->

実行して、仮想環境を起動します。

{% filename %}command-line{% endfilename %}

    $ source myvenv/bin/activate
    

`myvenv`のところをあながた選んだ`仮想環境(virtualenvironment)`名に置き換えることを忘れないで下さいね！

> **備考:** `source` ではできない場合もあります。その場合は、代わりに以下のように入力してみてください：
> 
> {% filename %}command-line{% endfilename %}
> 
>     $ . myvenv/bin/activate
>     

<!--endsec-->

You will know that you have `virtualenv` started when you see that the prompt in your console is prefixed with `(myvenv)`.

virtual environment(仮想環境)の中で作業しているとき、`python`は自動的に正しいバージョンの`Python`を参照しますので、`python3`の代わりに<0>python</0>を使うことができます.

OK,これでDjangoのインストール前に入れておきたい依存関係の準備がすべて整いました。いよいよDjangoのインストールです！

## Djangoのインストール

今度はあなたの`virtualenv`を起動したので、Djangoをインストールすることができます。

これを行う前に、Djangoのインストールに使用する最新バージョンの`pip`がインストールされていることを確認する必要があります。

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ pip install --upgrade pip
    

コンソールで、`pip install django~=1.11.0` を実行してDjangoをインストールします。（この時、チルダとイコール`~=`を使います。）

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ pip install django~=1.11.0
    Collecting django~=1.11.0
      Downloading Django-1.11.3-py2.py3-none-any.whl (6.8MB)
    Installing collected packages: django
    Successfully installed django-1.11.3
    

<!--sec data-title="Installing Django: Windows" data-id="django_err_windows"
data-collapse=true ces-->

> Windowsでpipを呼んだときにエラーが起きた場合は、あなたのプロジェクトのパス名がスペース・アクセント・特殊文字を含んでいないか確認してみて下さい （例 `C:\Users\User Name\djangogirls`）。 もし含まれている場合は、そのディレクトリを他のスペース・アクセント・特殊文字が含まれていない場所（`C:\djangogirls`など）に移動することを検討してみてください。 Create a new virtualenv in the new directory, then delete the old one and try the above command again. (Moving the virtualenv directory won't work since virtualenv uses absolute paths.)

<!--endsec-->

<!--sec data-title="Installing Django: Windows 8 and Windows 10" data-id="django_err_windows8and10"
data-collapse=true ces-->

> Djangoをインストールしようとしてコマンドラインがフリーズして動かなくなってしまうことがあります。その時は、以下のコマンドを代わりに入力してみてください。
> 
> {% filename %}command-line{% endfilename %}
> 
>     C:\Users\Name\djangogirls> python -m pip install django~=1.11.0
>     

<!--endsec-->

<!--sec data-title="Installing Django: Linux" data-id="django_err_linux"
data-collapse=true ces-->

> Ubuntu 12.04でpipを呼んだときにエラーが起きた場合は、仮想環境(virtualenvironment)内でpipインストールをフィックスするために`python -m pip install -U --force-reinstall pip` を実行して下さい。

<!--endsec-->

以上です！あなたは（ついに）Djangoアプリケーションを作成する準備が整いました！