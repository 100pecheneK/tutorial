Pots [saltar fins aquesta secció](http://tutorial.djangogirls.org/en/installation/#install-python) si no fas servir un Chromebook. Si el fas servir, la teva experiència d'instal·lació serà una mica diferent. Pots ignorar la resta d'instruccions d'instal·lació.

### Cloud IDE (PaizaCloud Cloud IDE, AWS Cloud9)

L'entorn de desenvolupament integrat (IDE) Cloud 9 és una eina que t'ofereix un editor de codi i accés a un ordinador funcionant a Internet, on pots instal·lar, escriure i executar el programari. Durant la resta del tutorial, Cloud 9 actuarà com la teva *màquina local*. Permet executar comandes des d'una interficíe de terminal com uan màquina OS, Ubuntu o Windows, però aquesta estarà conectada a un ordinador executatnt en algun altre lloc, que IDE al n`vol posa a la nostra disposició. Here is the instructions for cloud IDEs (PaizaCloud Cloud IDE, AWS Cloud9). You can choose one of the cloud IDEs, and follow the instruction of the cloud IDE.

#### PaizaCloud Cloud IDE

1. Go to [PaizaCloud Cloud IDE](https://paiza.cloud/)
2. Sign up for an account
3. Click *New Server*
4. Click Terminal button(on the left side of the window)

Now you should see an interface with a sidebar, buttons at the left. Click "Terminal" button to open terminal window with prompt like this:

{% filename %}Terminal{% endfilename %}

    $
    

The terminal on the PaizaCloud Cloud IDE is prepared for your instructions. You can resize or maximize that window to make it a bit bigger.

#### AWS Cloud9

1. Go to [AWS Cloud9](https://aws.amazon.com/cloud9/)
2. Sign up for an account
3. Click *Create Environment*

Now you should see an interface with a sidebar, a big main window with some text, and a small window at the bottom that looks something like this:

{% filename %}bash{% endfilename %}

    yourusername:~/workspace $
    

This bottom area is your terminal. You can use the terminal to send instructions to the remote Cloud 9 computer. You can resize that window to make it a bit bigger.

### Entorn Virtual

A virtual environment (also called a virtualenv) is like a private box we can stuff useful computer code into for a project we're working on. We use them to keep the various bits of code we want for our various projects separate so things don't get mixed up between projects.

In your terminal at the bottom of the Cloud 9 interface, run the following:

{% filename %}Cloud 9{% endfilename %}

    sudo apt update
    sudo apt install python3.6-venv
    

If this still doesn't work, ask your coach for some help.

Next, run:

{% filename %}Cloud 9{% endfilename %}

    mkdir djangogirls
    cd djangogirls
    python3.6 -mvenv myvenv
    source myvenv/bin/activate
    pip install django~={{ book.django_version }}
    

(note that on the last line we use a tilde followed by an equal sign: `~=`).

### GitHub

Make a [GitHub](https://github.com) account.

### PythonAnywhere

El tutorial de Django Girls inclou un apartat anomenat Desplegament, que és el procés d' agafar el codi que fa funcionar la teva nova aplicació web i posar-lo a un ordinador accessible públicament (anomenat un servidor) així altres persones poden veure el teu treball.

This part is a little odd when doing the tutorial on a Chromebook since we're already using a computer that is on the Internet (as opposed to, say, a laptop). However, it's still useful, as we can think of our Cloud 9 workspace as a place for our "in progress" work and Python Anywhere as a place to show off our stuff as it becomes more complete.

Thus, sign up for a new Python Anywhere account at [www.pythonanywhere.com](https://www.pythonanywhere.com).