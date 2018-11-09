# Διαχείριση μέσω Django admin

Για να προσθέσουμε, επεξεργαστούμε και να διαγράψουμε τις δημοσιεύσεις που έχουμε αναρτήσει, θα χρησιμοποιήσουμε την εφαρμογή Django admin.

Ας ανοίξουμε το αρχείο `blog/admin.py` μέσα σε έναν code editor και ας αντικαταστήσουμε τα περιεχόμενα του με τα ακόλουθα:

{% filename %}blog/admin.py{% endfilename %}

```python
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

Με τον παραπάνω κώδικα, εισάγουμε το μοντέλο Post (δηλαδή τον πίνακα της βάσης δεδομένων με το όνομα Post) όπως ορίστηκε από το προηγούμενο κεφάλαιο. Για να κάνουμε το μοντέλο μας ορατό στην σελίδα διαχείρισης θα πρέπει να το "εγγράψουμε" (να το κάνουμε register) με την συνάρτηση `admin.site.register(Post)`.

Εντάξει λοιπόν, ας ρίξουμε μια ματιά στο Post μοντέλο μας. Θυμηθείτε ότι πρέπει πρώτα να πληκτρολογήσουμε `python manage.py runserver` στην κονσόλα μας ώστε να ξεκινήσει ο development server. Πηγαίνετε στον browser και πληκτρολογήστε http://127.0.0.1:8000/admin/. Θα δείτε μία σελίδα σύνδεσης όπως αυτή:

![Login page](images/login_page2.png)

Για να συνδεθείτε, χρειάζεται να δημιουργήσετε έναν *superuser*, δηλαδή έναν χρήστη ο οποίος θα έχει δικαιώματα σε οτιδήποτε σε αυτή την σελίδα. Πηγαίνετε πίσω στην γραμμή εντολών, πατήστε Ctrl + c για να σταματήσετε τον development server Που ήδη τρέχει, πληκτρολογήστε `python manage.py createsuperuser` και πατήστε enter.

> Θυμηθείτε, για να γράψετε νέες εντολές ενώ ο server εκτελείται, ανοίξτε μια νέα κονσόλα και ενεργοποιήστε το virtualenv. We reviewed how to write new commands in the **Your first Django project!** chapter, in the **Starting the web server** section.

{% filename %}Mac OS X or Linux:{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py createsuperuser
    

{% filename %}Windows:{% endfilename %}

    (myvenv) C:\Users\Name\djangogirls> python manage.py createsuperuser
    

When prompted, type your username (lowercase, no spaces), email address, and password. **Don't worry that you can't see the password you're typing in – that's how it's supposed to be.** Type it in and press `enter` to continue. The output should look like this (where the username and email should be your own ones):

    Username: ola
    Email address: ola@example.com
    Password:
    Password (again):
    Superuser created successfully.
    

Return to your browser. Log in with the superuser's credentials you chose; you should see the Django admin dashboard.

![Django admin](images/django_admin3.png)

Go to Posts and experiment a little bit with it. Add five or six blog posts. Don't worry about the content –- it's only visible to you on your local computer -- you can copy-paste some text from this tutorial to save time. :)

Make sure that at least two or three posts (but not all) have the publish date set. It will be helpful later.

![Django admin](images/edit_post3.png)

If you want to know more about Django admin, you should check Django's documentation: https://docs.djangoproject.com/en/2.0/ref/contrib/admin/

This is probably a good moment to grab a coffee (or tea) or something to eat to re-energize yourself. You created your first Django model – you deserve a little break!