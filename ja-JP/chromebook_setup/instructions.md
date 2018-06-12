Chromebookをお持ちでない場合は、[このセクションをスキップ](http://tutorial.djangogirls.org/en/installation/#install-python) できます。 もしもっていなければ、普通のインストールの作業とは少し異なります。 インストール手順の残りの部分は無視できます。

### Cloud 9

クラウド 9 は、インストール、書き込み、およびソフトウェアを実行することができますインターネット上で実行しているコンピューターにコード エディター、アクセスを与えるツールです。 チュートリアルをやっている間、Cloud 9はあなたの*ローカルマシーン*のように動きます。 あなたはMacもしくはUbuntu、またはWindowsを使用しています。ターミナルや、コマンドプロンプトは自分の端末の実行中のコンピュータに接続されます。クラウド9は他の場所に接続する設定をおこないます。

1. [Chrome ウェブストア](https://chrome.google.com/webstore/detail/cloud9/nbdmccoknlfggadpfkmcpnamfnbkmkcp)から Cloud 9 を インストールする
2. [C9.io](https://c9.io) に行く
3. アカウントにサインアップします
4. *作成新しいワークスペース*をクリック
5. 名前はdjango-girlsとします
6. (オレンジ色のロゴの下の行の右側) から 2 番目 *Blank*を選択

サイドバーとインターフェイス、大きなメインウィンドウ テキスト、下部に小さなウィンドウがあり、次のようになります。

{% filename %}Cloud 9{% endfilename %}

    yourusername:~/workspace $
    

この下部は *ターミナル*コンピューターを与えるがクラウド 9 があなたの指示を準備しています。それを少し大きくするウィンドウのサイズを変更できます。

### Virtual Environment

A virtual environment (仮想環境とも呼ばれます) に取り組んでいるプロジェクトのために有用なコンピューター コードを詰めることができる専用ボックスのようです。 我々 は様々 なプロジェクトのため独立したように、必要もの混ざってはいけないプロジェクト間コードの様々 なビットを保つためにそれらを使用します。

クラウド 9 インターフェイスの下部に端末で次を実行します。

{% filename %}Cloud 9{% endfilename %}

    sudo apt update
    sudo apt install python3.6-venv
    

それでも問題が解決しない場合は、コーチに相談してください。

次の実行

{% filename %}Cloud 9{% endfilename %}

    mkdir djangogirls
    cd djangogirls
    python3.6 -mvenv myvenv
    source myvenv/bin/activate
    pip install django~=1.11.0
    

(note that on the last line we use a tilde followed by an equal sign: ~=).

### Github

Githubのアカウントを作ります。

### PythonAnywhere

Django Girlsチュートリアルには、Deploymentと呼ばれるものに関するセクションが含まれています。 新しいWebアプリケーションを強化するコードを実行するプロセスです。 それを公開アクセス可能なコンピュータ（サーバーと呼ばれる）に移動して インターネット上で、あなたが作ったものを全ての人が見られるようにできます。

この部分は、Chromebookでチュートリアルを行うときに、インターネットに接続されているコンピュータ（ラップトップとは対照的に）を既に使用しているので少し奇妙です。 However, it's still useful, as we can think of our Cloud 9 workspace as a place for our "in progress" work and Python Anywhere as a place to show off our stuff as it becomes more complete.

Thus, sign up for a new Python Anywhere account at [www.pythonanywhere.com](https://www.pythonanywhere.com).