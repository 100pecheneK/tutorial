# HTML简介

什么是模板，你可能会问？

A template is a file that we can re-use to present different information in a consistent format – for example, you could use a template to help you write a letter, because although each letter might contain a different message and be addressed to a different person, they will share the same format.

A Django template's format is described in a language called HTML (that's the HTML we mentioned in the first chapter, **How the Internet works**).

## HTML 是什么？

HTML is a code that is interpreted by your web browser – such as Chrome, Firefox or Safari – to display a web page for the user.

HTML代表“HyperText Markup Language（超文本标记语言）”。 **超文本** 是指它是一种支持网页之间的超链接的文本。 **标记** 是指我们将一份文件用代码标记组织起来，然后告诉某个东西（在这种情况下，浏览器中） 如何解释网页。 HTML 代码是由 **标记**构成的，每一个都是由 `<` 开始，由结束 `>`. 这些标签表示标记 **元素**.

## 你的第一个模板 ！

创建一个模板是指创建一个模板文件。一切都是文件，对吧？你可能已经注意到这点了。

模板保存在 `blog/templates/blog` 目录中。 因此，首先在您的 blog 目录内创建一个称为 `templates` 的目录。 然后创建另一个称为 `blog` 的目录到你的 templates 目录：

    blog
    └───templates
        └───blog
    

(You might wonder why we need two directories both called `blog` – as you will discover later, this is simply a useful naming convention that makes life easier when things start to get more complicated.)

现在创建一个叫做 `post_list.html` 的文件 （现在是空的，别管它）到 `blog/templates/blog` 目录下。

看看你的网站现在是什么样子： http://127.0.0.1:8000/ /

> If you still have an error `TemplateDoesNotExist`, try to restart your server. Go into command line, stop the server by pressing Ctrl+C (Control and C keys together) and start it again by running a `python manage.py runserver` command.

![图 11.1](images/step1.png)

再也没有错误了 ！祝贺:)然而，您的网站实际上并没有展现任何东西出了一个空白页，因为您的模板也是空。我们需要解决这个问题。

在您的模板文件中添加以下内容：

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<html>
    <p>Hi there!</p>
    <p>It works!</p>
</html>
```

So how does your website look now? Visit it to find out: http://127.0.0.1:8000/

![图 11.2](images/step3.png)

它工作了 ！很好地完成了:)

* The most basic tag, `<html>`, is always the beginning of any web page and `</html>` is always the end. 正如你所看到的，整个网站的内容是在 `<html>` 开始标记和结束标记之间 `</html>`的
* `<p>` 一种用于段落元素标记 ；`</p>` 关闭每个段落

## Head and body

每个 HTML 页面也分为两个元素： **head** 和 **body**.

* **head** 是一个包含有关文档且未显示在屏幕上的信息元素。

* **body** 是包含 web 页中所有显示的元素。

我们使用 `<head>` 告诉浏览器这个页面的配置，以及 `<body>` 来告诉它什么实际上是在页面上。

For example, you can put a web page title element inside the `<head>`, like this:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<html>
    <head>
        <title>Ola's blog</title>
    </head>
    <body>
        <p>Hi there!</p>
        <p>It works!</p>
    </body>
</html>
```

保存该文件并刷新您的网页。

![图 11.3](images/step4.png)

注意浏览器怎么理解"Ola's blog"是你的网页的标题的呢？ 它解释了 `<title> Ola's blog </title>` 并将其放置到您的浏览器 （它也用于书签，等等） 的标题栏中。

可能你也注意到每个开始标记匹配的 *结束标记*，用 `/`） 和元素是 *嵌套* （即只有您不能关闭特定标记，直到在里面的所有标记都关闭了）。

这就像把东西放进盒子里。 你有一个大箱子里，`<html></html>` ；在它里面还有 `<body></body>`，并包含更小盒： `<p></p>`.

You need to follow these rules of *closing* tags, and of *nesting* elements – if you don't, the browser may not be able to interpret them properly and your page will display incorrectly.

## 自定义您的模板

现在，你可以找点乐子，尝试自定义您的模板 ！为此这里有几个有用的标签：

* `<h1>A heading</h1>` for your most important heading
* `<h2>A sub-heading</h2>` 为下一层级的标题！
* `<h3>A sub-sub-heading</h3>` …and so on, up to `<h6>`
* `<p>A paragraph of text</p>`
* `<em>text</em>` 强调您的文本
* `<strong>text</strong>` 强烈强调您的文本
* `<br>` goes to another line (you can't put anything inside br and there's no closing tag)
* `<a href="https://djangogirls.org">link</a>` 创建一个链接
* `<ul><li>first item</li><li>second item</li></ul>` 产生一个列表，就像这样！
* `<div></div>` 定义页面上的一个段

Here's an example of a full template, copy and paste it into `blog/templates/blog/post_list.html`:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<html>
    <head>
        <title>Django Girls blog</title>
    </head>
    <body>
        <div>
            <h1><a href="/">Django Girls Blog</a></h1>
        </div>

        <div>
            <p>published: 14.06.2014, 12:14</p>
            <h2><a href="">My first post</a></h2>
            <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</p>
        </div>

        <div>
            <p>published: 14.06.2014, 12:14</p>
            <h2><a href="">My second post</a></h2>
            <p>Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum. Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut f.</p>
        </div>
    </body>
</html>
```

我们已经创建了三个不同的 `div` 部分。

* The first `div` element contains the title of our blog – it's a heading and a link
* 另两个 `div` 元素包含我们博客文章发表的日期，`h2` 是可点击文章标题和两个 `p` （段落） 的文本、 日期和我们的博客。

它给了我们这种效果：

![图 11.4](images/step6.png)

耶！ But so far, our template only ever displays exactly **the same information** – whereas earlier we were talking about templates as allowing us to display **different** information in the **same format**.

What we really want to do is display real posts added in our Django admin – and that's where we're going next.

## 还有一件事：部署！

我们把这些成果放到网上一定很棒，对吧？让我们再来一次 PythonAnywhere 部署：

### 提交并推送代码到Github

首先，让我们看看上次部署之后什么文件改变了（运行这些本地命令，不是在 PythonAnywhere 上）：

{% filename %}command-line{% endfilename %}

    $ git status
    

请确保你在 `djangogirls` 目录中，让我们告诉 `git` 包括此目录内的所有更改：

{% filename %}command-line{% endfilename %}

    $ git add --all .
    

> **Note** `--all` means that `git` will also recognize if you've deleted files (by default, it only recognizes new/modified files). 此外记得 （在第 3 章）`.` 意味着当前目录。

在我们上传的所有文件之前，让我们检查`git` 将上传什么（所有`git` 将上传的文件现在应以绿色显示）：

{% filename %}command-line{% endfilename %}

    $ git status
    

我们已经差不多完成了，现在是时候告诉它要在它的历史记录中保存此更改。 我们将要给它附上一条"提交消息"用来描述我们做了什么改动。 您可以在这个阶段键入任何您想要的东西，但写一些描述性的东西更有用，因为它能在将来使你记起你做了什么。

{% filename %}command-line{% endfilename %}

    $ git commit -m "Changed the HTML for the site."
    

> **注意** 请确保您使用双引号括提交消息。

Once we've done that, we upload (push) our changes up to GitHub:

{% filename %}command-line{% endfilename %}

    $ git push
    

### Pull 把你的新代码拉到 PythonAnywhere，然后重新加载你的 web 应用程序

* 打开 [PythonAnywhere consoles page](https://www.pythonanywhere.com/consoles/) 并转到你的 **Bash console**（或启动一个新的）。然后，运行：

{% filename %}command-line{% endfilename %}

    $ cd ~/my-first-blog
    $ git pull
    [...]
    

然后观察你的代码被下载下来。如果你想要检查他是否正确下载，你可以跳转到**Files Tab** 并在PythonAnywhere上查看代码。

* 最后，跳到 [Web tab](https://www.pythonanywhere.com/web_app_setup/) 并点击对应你的 Web 应用程序的 **Reload** 。

你的更新应已上线！刷新你的浏览器，看到更新了吧. :)