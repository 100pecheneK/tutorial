# Djangoテンプレート

何かデータを表示しましょう！Djangoはそれをビルトインの **テンプレートタグ** で実現できます。

## テンプレートタグとは？

HTML中で本当はPythonのコードを書くことはできません。なぜならブラウザが理解できないからです。ブラウザはHTMLだけ分かります。HTMLはどちらかというと静的で、それに対してPythonはもっとずっと動的なことを私たちは知っています。

**Djangoテンプレートタグ** はHTMLにPyhtonのようなコードを埋め込むことができて、動的なウェブサイトがより早く簡単に作れます!

## ブログ一覧テンプレートの表示

前の章で、`posts` 変数でテンプレートに記事のリストを渡しました。今からHTMLで表示をしてみましょう。

Djangoテンプレートで変数を表示するためには、次のように変数の名前を二重中括弧で括ります。

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{{ posts }}
```

これを `blog/templates/blog/post_list.html` テンプレートでやってみましょう。 エディタでこのファイルを開き、２つめと３つめの `<div></div>` タグをまるごと `{{posts}}` に置き換えて下さい。 ファイルを保存してページをリロードしますと：

![図 13.1](images/step1.png)

見たとおり、このようになります。

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<QuerySet [<Post: My second post>, <Post: My first post>]>
```

Djangoはposts変数をオブジェクトのリストと認識します。 **Python入門**でどうやってリストを表示できたか覚えていますか？ ループを使ってリストを表示しましたよね。 Djangoテンプレートではこう書きます：

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% for post in posts %}
    {{ post }}
{% endfor %}
```

これをブログのテンプレートで使ってみましょう。

![図 13.2](images/step2.png)

動きましたね。 しかし、本当は**HTML入門**で作った静的な記事のように表示してほしいところです。 そこで、HTMLとテンプレートタグを混ぜてみましょう。 `body` タグの中を次のように書いてください：

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<div>
    <h1><a href="/">Django Girls Blog</a></h1>
</div>

{% for post in posts %}
    <div>
        <p>published: {{ post.published_date }}</p>
        <h2><a href="">{{ post.title }}</a></h2>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endfor %}
```

{% raw %}`{% for %}` と `{% endfor %}` の間に書いたものはリスト中の各オブジェクトの分だけ繰り返されます。ページをリロードしてみましょう。{% endraw %}

![図 13.3](images/step3.png)

post変数がさっきと違って、`{{ post.title }}` や `{{ post.text }}` になっていることに気づきましたか？ `Post` モデルで定義したそれぞれのフィールドにアクセスしています。 `|linebreaksbr` はpostのテキスト中の改行を段落に変換するフィルタに通すという意味です。

## もう一つ...

今の時点でのウェブサイトを公開して見てみませんか？もう一度PythonAnywhereでデプロイしてみましょう。デプロイのステップをおさらいします。

* まず、GithubにあなたのコードをPushしましょう

{% filename %}command-line{% endfilename %}

    $ git status
    [...]
    $ git add --all .
    $ git status
    [...]
    $ git commit -m "Modified templates to display posts from database."
    [...]
    $ git push
    

* そしたら、[PythonAnywhere](https://www.pythonanywhere.com/consoles/)に戻って、**Bashコンソール**（か、新しいコンソール）に入って、次のようにコマンドを打ちましょう：

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ cd <your-pythonanywhere-domain>.pythonanywhere.com
    $ git pull
    [...]
    

(Remember to substitute `<your-pythonanywhere-domain>` with your actual PythonAnywhere subdomain, without the angle-brackets.)

* 最後に[「Web」ページ](https://www.pythonanywhere.com/web_app_setup/)を開いてアプリを**リロード**します。 (To reach other PythonAnywhere pages from the console, use the menu button in the upper right corner.) Your update should be live on https://subdomain.pythonanywhere.com -- check it out in the browser! PythonAnywhereサイトで表示されるブログの記事が、あなたのパソコンの中のローカルサーバーのものと違っていても大丈夫です。 ローカルコンピュータにあるデータベースと、PythonAnywhere上のデータベースは同期していません。

Congrats! Now go ahead and try adding a new post in your Django admin (remember to add published_date!) Make sure you are in the Django admin for your pythonanywhere site, https://subdomain.pythonanywhere.com/admin. Then refresh your page to see if the post appears there.

Works like a charm? We're proud! Step away from your computer for a bit – you have earned a break. :)

![Figure 13.4](images/donut.png)