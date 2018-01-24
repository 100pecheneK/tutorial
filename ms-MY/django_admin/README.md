# Django admin

Untuk menambah, edit dan padamkan siaran kami baru saja dimodelkan, kita akan menggunakan Django admin.

Let's open the `blog/admin.py` file and replace its contents with this:

{% filename %}blog/admin.py{% endfilename %}

```python
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

Seperti yang anda boleh lihat, kita import (termasuk) Pos model didefinisikan dalam bab sebelumnya. To make our model visible on the admin page, we need to register the model with `admin.site.register(Post)`.

OK, masa untuk melihat model Pos kami. Remember to run `python manage.py runserver` in the console to run the web server. Go to your browser and type the address http://127.0.0.1:8000/admin/. Anda akan melihat halaman login seperti ini:

![Halaman log masuk](images/login_page2.png)

To log in, you need to create a *superuser* - a user account that has control over everything on the site. Go back to the command line, type `python manage.py createsuperuser`, and press enter.

> Ingat, untuk tulis arahan baru ketika pelayan web adalah berjalan, buka terminal baru jendela dan mengaktifkan anda virtualenv. We reviewed how to write new commands in the **Your first Django project!** chapter, in the **Starting the web server** section.

{% filename %}Mac OS X or Linux:{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py createsuperuser
    

{% filename %}Windows:{% endfilename %}

    (myvenv) C:\Users\Name\djangogirls> python manage.py createsuperuser
    

When prompted, type your username (lowercase, no spaces), email address, and password. **Don't worry that you can't see the password you're typing in – that's how it's supposed to be.** Just type it in and press `enter` to continue. The output should look like this (where the username and email should be your own ones):

    Username: admin
    Email address: admin@admin.com
    Password:
    Password (again):
    Superuser created successfully.
    

Return to your browser. Log in with the superuser's credentials you chose; you should see the Django admin dashboard.

![Django admin](images/django_admin3.png)

Go to Posts and experiment a little bit with it. Add five or six blog posts. Don't worry about the content – you can simply copy-paste some text from this tutorial to save time. :)

Make sure that at least two or three posts (but not all) have the publish date set. It will be helpful later.

![Django admin](images/edit_post3.png)

If you want to know more about Django admin, you should check Django's documentation: https://docs.djangoproject.com/en/1.11/ref/contrib/admin/

This is probably a good moment to grab a coffee (or tea) or something to eat to re-energize yourself. You created your first Django model – you deserve a little break!