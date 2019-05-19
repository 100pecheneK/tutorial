# Implementazione!

> **Nota** Il seguente capitolo è abbastanza difficile da capire fino in fondo. Non mollare e cerca di portarlo a termine; l'implementazione è una parte importante nel processo di costruzione di un sito web. Questo capitolo è inserito a metà del tutorial per far sì che il tuo tutor possa aiutarti con il processo leggermente più complesso di messa online del sito. Questo significa che puoi ancora finire il tutorial da sola se sei a corto di tempo.

Fino ad ora, il tuo sito web era presente solo sul tuo computer. Adesso imparerai come fare il deploy! Il deploy è il processo di pubblicazione online del tuo progetto in modo tale che sia visibile anche da altre persone. :)

Come abbiamo imparato, un sito Web deve trovarsi su un server. Ci sono molti server provider disponibili su Internet, noi useremo [PythonAnywhere](https://www.pythonanywhere.com/). PythonAnywhere è gratuito per le piccole applicazioni che non hanno troppi visitatori, sarà quindi perfetto per te al momento.

L'altro servizio esterno che useremo è [GitHub](https://www.github.com), che è un servizio di hosting di codice. Ne esistono altri, ma di questi tempi quasi tutti i programmatori hanno un account GitHub e ora lo avrai anche tu!

Questi tre servizi saranno importantissimi per te. Il tuo computer in locale sarà il posto in cui svilupperai e farai test. Quando sei soddisfatto delle modifiche, caricherai una copia del programma su GitHub. Il tuo sito Web sarà su PythonAnywhere e lo aggiornerai con una nuova copia del codice da GitHub.

# Git

> **Nota** Se hai giá eseguito i passagi di installazione, non é necessario eseguire nuovamente questa operazione - puoi andare alla sezione successiva e iniziare a creare il tuo repository Git.

{% include "/deploy/install_git.md" %}

## Inizializzare un repository Git

Git tiene traccia delle modifiche a un particolare insieme di file in quello che è chiamato repository di codice (o "repo" in breve). Iniziamone uno per il nostro progetto. Apri la console ed esegui questi comandi nella directory `djangogirls`:

> **Nota** Controlla la tua cartella di lavoro corrente con a`pwd`(Mac OS X/Linux) o`cd` (Windows) comando prima di inizziare il repository. Dovresti essere nella cartella `djangogirls`.

{% filename %}comando-linea{% endfilename %}

    $ git init
    Initialized empty Git repository in ~/djangogirls/.git/
    $ git config --global user.name "Your Name"
    $ git config --global user.email you@example.com
    

L'inizializzazione del repository git é qualcosa che dobbiamo fare una sola volta per progetto (e non dovrai piú reinserire il nome utente e l'indirizzo email).

Git memorizzerà le modifiche a tutti i file e le cartelle in questa directory, ma ci sono alcuni file che vogliamo ignorare. Si fa creando un file chiamato `.gitignore` nella directory di base. Apri il tuo editor e crea un nuovo file con questo contenuto:

{% filename %}.gitignore{% endfilename %}

    *.pyc
    *~
    __pycache__
    myvenv
    db.sqlite3
    /statica
    .DS_Negozio
    

E salvalo come `.gitignore` all'interno della cartella "djangogirls".

> **Nota** Il punto all'inizio del nome del file è importante! Se hai difficoltá a crearlo (per esempio, Mac non piacere creare file che iniziano con un punto attraverso il Finder), usa la funzione "salva con nome" nell'editor, é a prova di proiettile. E assicurati di non aggiungere `.txt`, `.py`, o qualsiasi altra estensione al nome del file -- sarà riconosciuto da Git solo se il nome è `.gitignore`.
> 
> **Nota** Uno dei file che hai specificato nel tuo`.ginignore`il file é`db.sqlite3`. That file is your local database, where all of your users and posts are stored. We'll follow standard web programming practice, meaning that we'll use separate databases for your local testing site and your live website on PythonAnywhere. The PythonAnywhere database could be SQLite, like your development machine, but usually you will use one called MySQL which can deal with a lot more site visitors than SQLite. Either way, by ignoring your SQLite database for the GitHub copy, it means that all of the posts and superuser you created so far are going to only be available locally, and you'll have to create new ones on production. Dovresti pensare al database locale come un parco giochi dove si possono provare cose diverse e senza avere paura di eliminare i tuoi messaggi reali dal tuo blog.

È una buona idea usare il comando `git status` prima di `git add` oppure ogni volta che non sei sicuro di cosa sia cambiato. This will help prevent any surprises from happening, such as wrong files being added or committed. The `git status` command returns information about any untracked/modified/staged files, the branch status, and much more. L'output dovrebbe essere simile a quanto segue:

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
    

E finalmente salviamo le nostre modifiche. vai alla tua console ed esegui questi comandi:

{% filename %}command-line{% endfilename %}

    $ git add --all .
    $ git commit -m "My Django Girls app, first commit"
     [...]
     13 files changed, 200 insertions(+)
     create mode 100644 .gitignore
     [...]
     create mode 100644 mysite/wsgi.py
    

## Pubblica il tuo codice su GitHub

Vai su [GitHub.com](https://www.github.com) e crea un nuovo account gratuito. (Se lo hai già fatto nella preparazione al workshop, benissimo!) Assicurati di ricordare la tua password (aggiungila al tuo password manager, se ne usi uno).

Then, create a new repository, giving it the name "my-first-blog". Leave the "initialize with a README" checkbox unchecked, leave the .gitignore option blank (we've done that manually) and leave the License as None.

![](images/new_github_repo.png)

> **Note** The name `my-first-blog` is important – you could choose something else, but it's going to occur lots of times in the instructions below, and you'd have to substitute it each time. It's probably easier to stick with the name `my-first-blog`.

On the next screen, you'll be shown your repo's clone URL, which you will use in some of the commands that follow:

![](images/github_get_repo_url_screenshot.png)

Now we need to hook up the Git repository on your computer to the one up on GitHub.

Type the following into your console (replace `<your-github-username>` with the username you entered when you created your GitHub account, but without the angle-brackets -- the URL should match the clone URL you just saw):

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

Adesso Il tuo codice è su GitHub. Go and check it out! You'll find it's in fine company – [Django](https://github.com/django/django), the [Django Girls Tutorial](https://github.com/DjangoGirls/tutorial), and many other great open source software projects also host their code on GitHub. :)

# Configurare il nostro blog su PythonAnywhere

## Crea un account PythonAnywhere

> **Nota** Potresti aver già creato un account PythonAnywhere prima, durante la fase di istallazione - in questo caso, non c'è bisogno di crearlo di nuovo.

{% include "/deploy/signup_pythonanywhere.md" %}

## Configurare il nostro sito su PythonAnywhere

Go back to the main [PythonAnywhere Dashboard](https://www.pythonanywhere.com/) by clicking on the logo, and choose the option to start a "Bash" console – that's the PythonAnywhere version of a command line, just like the one on your computer.

![The 'New Console' section on the PythonAnywhere web interface, with a button for 'bash'](images/pythonanywhere_bash_console.png)

> **Note** PythonAnywhere is based on Linux, so if you're on Windows, the console will look a little different from the one on your computer.

Deploying a web app on PythonAnywhere involves pulling down your code from GitHub, and then configuring PythonAnywhere to recognise it and start serving it as a web application. There are manual ways of doing it, but PythonAnywhere provides a helper tool that will do it all for you. Let's install it first:

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ pip3.6 install --user pythonanywhere
    

That should print out some things like `Collecting pythonanywhere`, and eventually end with a line saying `Successfully installed (...) pythonanywhere- (...)`.

Now we run the helper to automatically configure our app from GitHub. Type the following into the console on PythonAnywhere (don't forget to use your GitHub username in place of `<your-github-username>`, so that the URL matches the clone URL from GitHub):

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ pa_autoconfigure_django.py https://github.com/<your-github-username>/my-first-blog.git
    

As you watch that running, you'll be able to see what it's doing:

- Downloading your code from GitHub
- Creating a virtualenv on PythonAnywhere, just like the one on your own computer
- Updating your settings file with some deployment settings
- Setting up a database on PythonAnywhere using the `manage.py migrate` command
- Setting up your static files (we'll learn about these later)
- And configuring PythonAnywhere to serve your web app via its API

On PythonAnywhere all those steps are automated, but they're the same steps you would have to go through with any other server provider.

The main thing to notice right now is that your database on PythonAnywhere is actually totally separate from your database on your own computer, so it can have different posts and admin accounts. As a result, just as we did on your own computer, we need to initialize the admin account with `createsuperuser`. PythonAnywhere has automatically activated your virtualenv for you, so all you need to do is run:

{% filename %}PythonAnywhere command-line{% endfilename %}

    (ola.pythonanywhere.com) $ python manage.py createsuperuser
    

Type in the details for your admin user. Best to use the same ones as you're using on your own computer to avoid any confusion, unless you want to make the password on PythonAnywhere more secure.

Now, if you like, you can also take a look at your code on PythonAnywhere using `ls`:

{% filename %}PythonAnywhere command-line{% endfilename %}

    (ola.pythonanywhere.com) $ ls 
    blog db.sqlite3 manage.py mysite requirements.txt static 
    (ola.pythonanywhere.com) $ ls blog/ 
    __init__.py __pycache__ admin.py apps.py migrations models.py 
    tests.py views.py
    

You can also go to the "Files" page and navigate around using PythonAnywhere's built-in file browser. (From the Console page, you can get to other PythonAnywhere pages from the menu button in the upper right corner. Once you're on one of the pages, there are links to the other ones near the top.)

## You are now live!

Your site should now be live on the public Internet! Click through to the PythonAnywhere "Web" page to get a link to it. You can share this with anyone you want :)

> **Nota** Questo è un tutorial per principianti, e nel distribuire questo sito abbiamo preso alcune scorciatoie che non sono ideali dal punto di vista della sicurezza. If and when you decide to build on this project, or start a new project, you should review the [Django deployment checklist](https://docs.djangoproject.com/en/2.0/howto/deployment/checklist/) for some tips on securing your site.

## Suggerimenti per il debug

If you see an error while running the `pa_autoconfigure_django.py` script, here are a few common causes:

- Forgetting to create your PythonAnywhere API token.
- Making a mistake in your GitHub URL
- If you see an error saying *"Could not find your settings.py"*, it's probably because you didn't manage to add all your files to Git, and/or you didn't push them up to GitHub successfully. Have another look at the Git section above

If you see an error when you try to visit your site, the first place to look for some debugging info is in your **error log**. You'll find a link to this on the PythonAnywhere ["Web" page](https://www.pythonanywhere.com/web_app_setup/). See if there are any error messages in there; the most recent ones are at the bottom.

There are also some [general debugging tips on the PythonAnywhere help site](http://help.pythonanywhere.com/pages/DebuggingImportError).

E ricorda, il tuo coach è qui per aiutarti!

# Check out your site!

The default page for your site should say "It worked!", just like it does on your local computer. Try adding `/admin/` to the end of the URL, and you'll be taken to the admin site. Log in with the username and password, and you'll see you can add new Posts on the server -- remember, the posts from your local test database were not sent to your live blog.

Once you have a few posts created, you can go back to your local setup (not PythonAnywhere). From here you should work on your local setup to make changes. This is a common workflow in web development – make changes locally, push those changes to GitHub, and pull your changes down to your live Web server. This allows you to work and experiment without breaking your live Web site. Pretty cool, huh?

Give yourself a *HUGE* pat on the back! Server deployments are one of the trickiest parts of web development and it often takes people several days before they get them working. But you've got your site live, on the real Internet!