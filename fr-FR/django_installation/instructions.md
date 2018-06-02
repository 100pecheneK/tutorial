> Part of this section is based on tutorials by Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).
> 
> Part of this section is based on the [django-marcador tutorial](http://django-marcador.keimlink.de/) licensed under the Creative Commons Attribution-ShareAlike 4.0 International License. Le tutoriel django-marcador a été créé par Markus Zapke-Gründemann et al.

## L'environnement virtuel

Avant d'installer Django, nous allons vous faire installer un outil extrêmement utile qui vous aidera à maintenir votre environnement de développement propre. Nous vous recommandons fortement de ne pas sauter cette étape, même si elle n'est pas indispensable. En commençant avec la meilleure configuration possible vous éviterez beaucoup de problèmes par la suite !

Donc, commençons par créer un **environnement virtuel de programmation** (ou *virtualenv*). Chaque projet aura sa propre configuration en Python/Django grâce à virtualenv. Ce qui veut dire que si vous modifiez un site web, ça n'affectera pas les autres sites sur lesquels vous travaillez. Plutôt cool, non ?

Tout ce dont vous avez besoin, c'est de trouver un dossier où vous voulez créer votre `virtualenv` ; vous pouvez choisir votre home par exemple. On Windows, it might look like `C:\Users\Name` (where `Name` is the name of your login).

> **NOTE:** On Windows, make sure that this directory does not contain accented or special characters; if your username contains accented characters, use a different directory, for example, `C:\djangogirls`.

Dans ce tutoriel, nous allons utiliser un nouveau dossier `djangogirls` que vous allez créer dans votre dossier home :

{% filename %}command-line{% endfilename %}

    $ mkdir djangogirls
    $ cd djangogirls
    

Nous allons créer un virtualenv appelé `myvenv`. Pour cela, nous taperons une commande qui ressemblera à :

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

<!--sec data-title="Virtual environment: Windows" data-id="virtualenv_installation_windows"
data-collapse=true ces-->

To create a new `virtualenv`, you need to open the command prompt and run `python -m venv myvenv`. It will look like this:

{% filename %}command-line{% endfilename %}

    C:\Users\Name\djangogirls> python -m venv myvenv
    

Where `myvenv` is the name of your `virtualenv`. Vous pouvez choisir un autre nom mais attention : il doit être en minuscules, sans espaces et sans accents ou caractères spéciaux. It is also good idea to keep the name short – you'll be referencing it a lot!

<!--endsec-->

<!--sec data-title="Virtual environment: Linux and OS X" data-id="virtualenv_installation_linuxosx"
data-collapse=true ces-->

We can create a `virtualenv` on both Linux and OS X by running `python3 -m venv myvenv`. It will look like this:

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

`myvenv` est le nom de votre `virtualenv`. Vous pouvez choisir un autre nom, mais veillez à n'utiliser que des minuscules et à n'insérer ni espaces, ni caractères spéciaux. It is also a good idea to keep the name short as you'll be referencing it a lot!

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
> Pour résoudre ce problème, utilisez plutôt la commande `virtualenv`.
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

## Travailler avec virtualenv

Les commandes listées ci-dessus permettent de créer un dossier appelé `myvenv` (ou le nom que vous avez choisi) qui contient notre environnement virtuel. Pour faire simple, c'est un dossier composé lui-même d'autres dossiers et de fichiers.

<!--sec data-title="Working with virtualenv: Windows" data-id="virtualenv_windows"
data-collapse=true ces-->

Démarrez votre environnement virtuel en exécutant :

{% filename %}command-line{% endfilename %}

    C:\Utilisateurs\Nom\djangogirls> myvenv\Scripts\activate
    

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

Démarrez votre environnement virtuel en exécutant :

{% filename %}command-line{% endfilename %}

    $ source myvenv/bin/activate
    

N'oubliez pas de remplacer `myvenv` par le nom que vous avez choisi pour votre `virtualenv` (le cas échéant) !

> **NOTE :** il arrive parfois que `source` ne soit pas disponible. Dans ce cas, vous pouvez essayer ceci :
> 
> {% filename %}command-line{% endfilename %}
> 
>     $ . myvenv/bin/activate
>     

<!--endsec-->

You will know that you have `virtualenv` started when you see that the prompt in your console is prefixed with `(myvenv)`.

Quand vous travaillez dans un environnement virtuel, la commande `python` fera automatiquement référence à la bonne version de Python. Vous pouvez donc utiliser `python` plutôt que `python3`.

Ok, nous avons installé toutes les dépendances dont nous avions besoin. Nous allons enfin pouvoir installer Django !

## Installation de Django

Now that you have your `virtualenv` started, you can install Django.

Before we do that, we should make sure we have the latest version of `pip`, the software that we use to install Django:

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ python3 -m pip install --upgrade pip
    

Then run `pip install django~=1.11.0` (note that we use a tilde followed by an equal sign: `~=`) to install Django.

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ pip install django~=1.11.0
    Collecting django~=1.11.0
      Downloading Django-1.11.3-py2.py3-none-any.whl (6.8MB)
    Installing collected packages: django
    Successfully installed django-1.11.3
    

<!--sec data-title="Installing Django: Windows" data-id="django_err_windows"
data-collapse=true ces-->

> If you get an error when calling pip on Windows platform, please check if your project pathname contains spaces, accents or special characters (for example, `C:\Users\User Name\djangogirls`). If it does, please consider using another place without spaces, accents or special characters (suggestion: `C:\djangogirls`). Create a new virtualenv in the new directory, then delete the old one and try the above command again. (Moving the virtualenv directory won't work since virtualenv uses absolute paths.)

<!--endsec-->

<!--sec data-title="Installing Django: Windows 8 and Windows 10" data-id="django_err_windows8and10"
data-collapse=true ces-->

> Your command line might freeze after when you try to install Django. If this happens, instead of the above command use:
> 
> {% filename %}command-line{% endfilename %}
> 
>     C:\Users\Name\djangogirls> python -m pip install django~=1.11.0
>     

<!--endsec-->

<!--sec data-title="Installing Django: Linux" data-id="django_err_linux"
data-collapse=true ces-->

> Si vous obtenez une erreur lorsque vous utilisez pip sous Ubuntu 12.04, tapez la commande `python -m pip install -U --force-reinstall pip` pour réparer l'installation de pip dans votre virtualenv.

<!--endsec-->

Et voilà ! Vous êtes (enfin) prête pour créer votre première application Django !