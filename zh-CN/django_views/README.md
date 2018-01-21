# Django views – time to create!

是是候去解决我们在上一章所制造的Bug了! :)

*view*是存放应用逻辑的地方。 它将从你之前创建的 `模型`中获取数据，并将它传递给 `模板`。 我们将在下一章创建 tempalte 模板。 Views are just Python functions that are a little bit more complicated than the ones we wrote in the **Introduction to Python** chapter.

视图都被置放在`views.py`文件中。我们将加入我们自己的*views*到`blog/views.py`文件。

## blog/views.py

好，让我们打开这个文件，看看里面有什么：

{% filename %}blog/views.py{% endfilename %}

```python
from django.shortcuts import render

# Create your views here.
```

Not too much stuff here yet.

Remember that lines starting with `#` are comments – this means that those lines won't be run by Python.

Let's create a *view* as the comment suggests. Add the following minimal view below it:

{% filename %}blog/views.py{% endfilename %}

```python
def post_list(request):
    return render(request, 'blog/post_list.html', {})
```

As you can see, we created a function (`def`) called `post_list` that takes `request` and `return` a function `render` that will render (put together) our template `blog/post_list.html`.

Save the file, go to http://127.0.0.1:8000/ and see what we've got.

另一个错误！读读现在发生了什么：

![错误](images/error.png)

This shows that the server is running again, at least, but it still doesn't look right, does it? Don't worry, it's just an error page, nothing to be scared of! Just like the error messages in the console, these are actually pretty useful. You can read that the *TemplateDoesNotExist*. Let's fix this bug and create a template in the next chapter!

> 阅读更多关于Django views的内容请参阅官方文档：https://docs.djangoproject.com/en/1.11/topics/http/views/