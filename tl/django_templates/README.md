# Mga template ng Django

Oras na para magpakita ng mga datos! Ang Django ay nagbibigay sa atin ng mga nakakatulong na mga built-it na mga **template na tags** para dito.

## Ano ang mga template tags?

Makita mo, sa HTML, hindi ka maaring magsulat ng code na Python, dahil hindi ito maiintindihan ng mga browser. Alam lang nila ang HTML. Alam natin na ang HTML ay hindi nababago, habang ang Python ay pabago-bago.

**Django template tags** allow us to transfer Python-like things into HTML, so you can build dynamic websites faster. Cool!

## Magdisplay ng Post List na Template

Sa nakaraang kabanata, binigyan natin ang ating template ng lista ng mga posts sa ating `posts` na variable. Ngayon, maari na natin itong ilagay sa HTML.

Para magprint ng variable sa templates ng Django, gagamit tayo ng dobleng pamukod na may pangalan ng variable sa loob, gaya nito:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{{ posts }}
```

Subukan mo ito sa loob ng iyong `blog/templates/blog/post_list.html` na template. Palitan ang lahat mula sa pangalawa `<div>`hanggang sa pangatlong `</div>` ng `{{ posts }}`. I-save ang file, at i-refresh ang pahina para makita ang mga resulta:

![Tambilang 13.1](images/step1.png)

Gaya nang makikita mo, ang lahat ng nakuha natin ay ito lang:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<QuerySet [<Post: My second post>, <Post: My first post>]>
```

Ibig sabihin nito ay naintindihan ni Django na ito ay isang lista ng mga object. Natandaan mo mula sa **Introduksyon sa Python** kung paano nati mapakita ang mga lista? Oo, gamit ang for loops! Sa Django template gagawin natin ito gaya nito:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
{% for post in posts %}
    {{ post }}
{% endfor %}
```

Subukan ito sa iyong template.

![Tambilang 13.2](images/step2.png)

Gumana ito! Pero gusto nating i-display ang mga post gaya ng mga static na post na ginawa natin kanina sa **Introduksyon sa HTML** na kabanata. Maari mong ihalo ang HTML at ang mga template tags. Ang ating `body` ay magmukhang ganito:

{% filename %}blog/templates/blog/post_list.html{% endfilename %}

```html
<div>
    <h1><a href="/">Blog ng Django Girls</a></h1>
</div>

{% for post in posts %}
    <div>
        <p>published: {{ post.published_date }}</p>
        <h1><a href="">{{ post.title }}</a></h1>
        <p>{{ post.text|linebreaksbr }}</p>
    </div>
{% endfor %}
```

{% raw %}Lahat ng nilagay mo sa pagitan ng `{% for %}` at `{% endfor %}` ay uulitin sa bawat object na nasa list. I-refresh ang iyong pahina:{% endraw %}

![Tambilang 13.3](images/step3.png)

Napansin mo ba na gumagamit tayo ng kakaibang notasyon ngayon (`{{ post.title }}` or `{{ post.text }})`? Tayo ay kukuha ng mga datos sa bawat field na nakalarawan sa ating `Post` na model. At, ang `|linebreaksbr` ay nagpipe nga mga teskto ng post sa filter para i-convert ang mga line-break sa mga talata.

## Isa pang bagay

Magandang tingnan kung ang website ay gumagana pa rin sa publikong Internet, di ba? Subukan nating mag-deploy sa PythonAnywhere ulit. Eto ay pagbibigay buod sa mga hakbang…

* Una, itulak ang iyong code sa Github

{% filename %}command-line{% endfilename %}

    $ git status
    [...]
    $ git add --all .
    $ git status
    [...]
    $ git commit -m "Binago ang mga template para magdisplay ng mga post galing sa database."
    [...]
    $ git push
    

* Pagkatapos, maglog ulit sa [PythonAnywhere](https://www.pythonanywhere.com/consoles/) at pumunta sa iyong **Bash na console** (o magpatakbo ng isa pa), at patakbuhin ang:

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ cd my-first-blog
    $ git pull
    [...]
    

* Sa katapusan, puntahahan ang [Web tab](https://www.pythonanywhere.com/web_app_setup/) at pindutin ang **Reload** sa iyong web app. Ang iyong update ay dapat naka-live! Kung ang mga blog post sa ating PythonAnywhere na site ay hindi tugma sa mga post na makikita sa blog na nakahost sa ating local na serva, okay lang yan. Ang database sa ating local na kompyuter at sa Python Anywhere ay hindi nakasync gaya ng iba nating mga file.

Maligayang bati! Ngayon dumiretso ka na at subukan mong magdagdag ng bagong post sa iyong Django admin (tandaan magdagdag ng published_date!) Siguraduhin na nasa Django admin ka ng iyong pythonanywhere na site, https://yourname.pythonanywhere.com/admin. Pagkatapos i-refresh ang iyong pahina at tingnan kung makita mo ang post mo doon.

Parang anting-anting di ba? Ipinagmamalaki ka namin! Lumayo muna ng saglit sa iyong kompyuter - dapat kang magpahinga. :)

![Tambilang 13.4](images/donut.png)