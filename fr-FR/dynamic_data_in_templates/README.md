# Données dynamiques dans les templates

Nous avons différents morceaux en place : le modèle `Post` qui est définit dans le fichier `models.py`, la vue `post_list` dans `views.py` et nous venons de créer notre template. Mais comment allons-nous faire pour faire apparaître nos posts dans notre template HTML ? Car au final, n'est-ce pas le but que nous souhaiterions atteindre ? Nous aimerions prendre du contenu, en l’occurrence notre modèle sauvegardé dans notre base de données, et réussir à joliment l'afficher dans notre template.

C'est à ça que servent les *vues* : connecter les modèles et les templates. Dans notre *vue* `post_list`, nous allons avoir besoin de prendre les modèles dont nous avons besoin et de les passer au template. C'est dans la *vue* que nous allons décider ce qui va s'afficher (quel modèle) dans un template.

Ok, et sinon, on fait comment ?

Nous allons avoir besoin d'ouvrir le fichier `blog/views.py` dans l'éditeur de code. Pour l'instant, la *vue* `post_list` ressemble à ceci :

{% filename %}blog/views.py{% endfilename %}

```python
from django.shortcuts import render

def post_list(request):
    return render(request, 'blog/post_list.html', {})
```

Est-ce que vous vous souvenez de comment rajouter des morceaux de code écris dans d'autres fichiers ? Nous en avons parlé dans un chapitre précédent. Now is the moment when we have to include the model we have written in `models.py`. We will add the line `from .models import Post` like this:

{% filename %}blog/views.py{% endfilename %}

```python
from django.shortcuts import render
from .models import Post
```

The dot before `models` means *current directory* or *current application*. Both `views.py` and `models.py` are in the same directory. This means we can use `.` and the name of the file (without `.py`). Ensuite, nous importons le modèle (`Post`).

But what's next? To take actual blog posts from the `Post` model we need something called `QuerySet`.

## QuerySet

You should already be familiar with how QuerySets work. We talked about them in [Django ORM (QuerySets) chapter](../django_orm/README.md).

So now we want published blog posts sorted by `published_date`, right? We already did that in QuerySets chapter!

{% filename %}blog/views.py{% endfilename %}

```python
Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
```

So, let's open the `blog/views.py` file in the code editor, and add this piece of code to the function `def post_list(request)` -- but don't forget to first add `from django.utils import timezone`:

{% filename %}blog/views.py{% endfilename %}

```python
from django.shortcuts import render
from django.utils import timezone
from .models import Post

def post_list(request):
    posts = Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
    return render(request, 'blog/post_list.html', {})
```

The last missing part is passing the `posts` QuerySet to the template context. Don't worry – we will cover how to display it in a later chapter.

Veuillez noter que nous créons une *variable* pour notre QuerySet : `posts`. Considérez que c'est le nom de notre QuerySet. À partir de maintenant, nous allons pouvoir faire référence à notre QuerySet en utilisant ce nom.

In the `render` function we have one parameter `request` (everything we receive from the user via the Internet) and another giving the template file (`'blog/post_list.html'`). The last parameter, `{}`, is a place in which we can add some things for the template to use. Nous avons par exemple de lui donner des noms : nous allons rester sur `'posts'` pour le moment). :) Ça va ressembler à ça : `{'posts': posts}`. Please note that the part before `:` is a string; you need to wrap it with quotes: `''`.

Au final, notre fichier `blog/views.py` doit ressembler à ceci maintenant :

{% filename %}blog/views.py{% endfilename %}

```python
from django.shortcuts import render
from django.utils import timezone
from .models import Post

def post_list(request):
    posts = Post.objects.filter(published_date__lte=timezone.now()).order_by('published_date')
    return render(request, 'blog/post_list.html', {'posts': posts})
```

Et voilà, c'est bon ! Nous allons retourner du côté de notre template pour que notre QuerySet puisse s'afficher correctement !

Want to read a little bit more about QuerySets in Django? You should look here: https://docs.djangoproject.com/en/2.0/ref/models/querysets/