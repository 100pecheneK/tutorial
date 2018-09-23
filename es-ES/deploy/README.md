# ¡Despliega!

> **Nota** El siguiente capítulo puede ser, a veces, un poco difícil de seguir. Se persistente y acábalo. El despliegue es una parte importante del proceso en el desarrollo web. Este capítulo está a mitad del tutorial para que tu mentor pueda ayudarte a conseguir que tu sitio web esté online, algo que puede ser un poco complicado. Esto significa que podrás acabar el tutorial por tu cuenta si se te acaba el tiempo.

Hasta ahora, tu sitio sólo está disponible en tu ordenador. ¡Ahora aprenderás como desplegarlo! El despliegue es el proceso de publicar tu aplicación en internet para que la gente pueda acceder y ver tu aplicación. :)

Como ya has aprendido, un sitio web tiene que estar en un servidor. Hay muchos proveedores de servidores disponibles en internet, nosotros vamos a usar [PythonAnywhere](https://www.pythonanywhere.com/). PythonAnywhere es gratuito para aplicaciones pequeñas que no tienen muchos visitantes, y con eso tendrás más que suficiente por ahora.

El otro servicio externo que vamos a utilizar es [GitHub](https://www.github.com), un servicio de almacenamiento de código. Hay otras opciones por ahí, pero hoy en día casi todas las programadoras y programadores tenemos una cuenta de GitHub, ¡y ahora tú también la vas a tener!

Estos tres lugares serán importantes para ti. Tu ordenador local será el lugar donde desarrollas y pruebas. Cuando estés contento con los cambios, subirás una versión de tu programa a GitHub. Tu sitio web estará en PythonAnywhere y para actualizarlo descargarás la última versión de tu código desde GitHub.

# Git

> **Nota** Si ya has realizado los pasos de instalación, no los tienes que repetir, puedes avanzar a la siguiente sección y empezar a crear tu repositorio de Git.

{% include "deploy/install_git.md" %}

## Crear nuestro repositorio Git

Git sigue los cambios realizados a un grupo determinado de archivos en lo que llamamos un repositorio de código (abreviado "repo"). Vamos a crear uno para nuestro proyecto. Abre la consola y ejecuta los siguientes comandos en el directorio de `djangogirls`:

> **Nota** Comprueba en qué directorio estás ahora mismo (es decir, el directorio de trabajo actual) con el comando `pwd` (OSX/Linux) o `cd` (Windows) antes de inicializar el repositorio. Deberías estar en la carpeta `djangogirls`.

{% filename %}command-line{% endfilename %}

    $ git init
    Initialized empty Git repository in ~/djangogirls/.git/
    $ git config --global user.name "Tu nombre"
    $ git config --global user.email tu@ejemplo.com
    

Inicializar el repositorio de git es algo que sólo tenemos que hacer una vez por proyecto (y no tendrás que volver a teclear tu nombre de usuario y correo electrónico nunca más).

Git llevará un seguimiento de los cambios realizados en todos los archivos y carpetas en este directorio, pero hay algunos archivos que queremos que ignore. Esto lo hacemos creando un archivo llamado `.gitignore` en el directorio base. Abre tu editor y crea un nuevo archivo con el siguiente contenido:

{% filename %}.gitignore{% endfilename %}

    *.pyc
    *~
    __pycache__
    myvenv
    db.sqlite3
    /static
    .DS_Store
    

Y guárdalo como `.gitignore` en la carpeta "djangogirls".

> **Nota** ¡El punto al principio del nombre del archivo es importante! Si tienes problemas para crearlo (a los Mac no les gusta que crees ficheros con un punto al principio del nombre usando el Finder por ejemplo), entonces usa la opción "Save As" o "Guardar como" de tu editor, esto funcionará seguro.
> 
> **Nota** Uno de los archivos especificados en tu `.gitignore` es `db.sqlite3`. Este archivo es tu base de datos local, donde se almacenan todas tus publicaciones. No querrás añadir esto a tu repositorio por que tu pagina en PythonAnywhere va a usar una base de datos distinta. Esa base de datos podría ser SQLite, como tu maquina de desarrollo, pero usualmente usarás una llamada MySQL que puede manejar muchos mas visitantes que SQLite. De todos modos, al ignorar tu base de datos SQLite en la copia de GitHub todas las publicaciones que has creado hasta el momento solo van a estar disponibles localmente y se van a quedar así, pero vas a tener que añadirlas de nuevo en producción. Deberías imaginar que tu base de datos local es un buen campo de pruebas donde puedes probar diferentes cosas sin miedo a borrar tus publicaciones reales de tu blog.

Es una buena idea utilizar el comando `git status` antes de `git add` o en cualquier momento en que no estés seguro de lo que ha cambiado. Esto te ayudará a prevenir cualquier sorpresa, como archivos incorrectos siendo añadidos o consignados (commit). El comando `git status` muestra información sobre cualquier archivo no seguido("untracked"), modificado ("modified"), preparado ("staged"), el estado de la rama y mucho más. La salida debería ser similar a lo siguiente:

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
    

Y finalmente guardamos nuestros cambios. Ve a tu consola y ejecuta estos comandos:

{% filename %}command-line{% endfilename %}

    $ git add --all .
    $ git commit -m "Mi aplicación Django Girls, primer commit"
     [...]
     13 files changed, 200 insertions(+)
     create mode 100644 .gitignore
     [...]
     create mode 100644 mysite/wsgi.py
    

## Colocando tu código en Github

Ve a [GitHub.com](https://www.github.com) y registrate para una nueva cuenta gratuita. (Si ya hiciste esto en la preparación del taller, ¡esta genial!)

Entonces, crea un nuevo repositorio dándole el nombre "my-first-blog". Deja el cuadro de chequeo "initialize with a README" sin validar, deja la opción de .gitignore vacía (ya lo hemos hecho manualmente) y deja la licencia como None.

![](images/new_github_repo.png)

> **Note** El nombre `my-first-blog` es importante - tu puedes escoger algo mas, pero va a ocurrir muchas veces en las instrucciones, y vas a tener que sustituirlo cada vez. It's probably easier to stick with the name `my-first-blog`.

On the next screen, you'll be shown your repo's clone URL, which you will use in some of the commands that follow:

![](images/github_get_repo_url_screenshot.png)

Ahora necesitas enlazar el repositorio de Git en tu computador al repositorio de github.

Type the following into your console (replace `<your-github-username>` with the username you entered when you created your GitHub account, but without the angle-brackets -- the URL should match the clone URL you just saw):

{% filename %}command-line{% endfilename %}

    $ git remote add origin https://github.com/<your-github-username>/my-first-blog.git
    $ git push -u origin master
    

Ingresa tu nombre de usuario y contraseña de GitHub y deberías ver algo como:

{% filename %}command-line{% endfilename %}

    Username for 'https://github.com': ola
    Password for 'https://ola@github.com':
    Counting objects: 6, done.
    Writing objects: 100% (6/6), 200 bytes | 0 bytes/s, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To https://github.com/ola/my-first-blog.git
    
     * [new branch]      master -> master
    Branch master set up to track remote branch master from origin.
    

<!--TODO: maybe do ssh keys installs in install party, and point ppl who dont have it to an extension -->

Tu código ahora está en GitHub. ¡Ve y verificalo! Encontrarás que algunas compañias como - [Django](https://github.com/django/django)[Django Girst Tutorial](https://github.com/DjangoGirls/tutorial), y muchas otros proyectos grandes de software libre están alojados en GitHub. :)

# Configurar nuestro blog en PythonAnywhere

## Regístrese para crear una cuenta en PythonAnywhere

> **Nota** Puede que ya hayas creado una cuenta en PythonAnywhere durante los paso de instalación. Si es así, no necesitas hacerlo de nuevo.

{% include "/deploy/signup_pythonanywhere.md" %}

## Configurar nuestra página en PythonAnywhere

Vuelve al [panel principal de PythonAnywhere](https://www.pythonanywhere.com/) al hacer click en el logo, y escoge la opción iniciar la consola "Bash" – esa es la versión de una línea de comando de PythonAnywhere, tal como la de tu computador.

![La sección 'Nueva Consola' en la interfaz de PythonAnywhere con un botón para 'bash'](images/pythonanywhere_bash_console.png)

> **Nota** PythonAnywhere está basado en Linux, entonces si estás en Windows, la consola tendrá una apariencia diferente a la de tu computador.

Desplegar una aplicación web en PythonAnywhere involucra jalar tu codigo de GitHub y entonces configurar PythonAnywhere para reconocerlo y empezar a servirlo como una aplicación web. Hay maneras manuales de hacerlo, pero PythonAnywhere provee una herramienta de asistencia que lo hará todo por tí. Instalemos la herramienta primero:

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ pip3.6 install --user pythonanywhere
    

Eso debería imprimir en pantalla algunas cadenas de texto como `Collecting pythonanywhere`, and eventually end with a line saying `Successfully installed (...) pythonanywhere- (...)`.

Ahora ejecutamos el asistente para configurar automáticamente nuestra aplicación desde GitHub. Type the following into the console on PythonAnywhere (don't forget to use your GitHub username in place of `<your-github-username>`, so that the URL matches the clone URL from GitHub):

{% filename %}PythonAnywhere command-line{% endfilename %}

    $ pa_autoconfigure_django.py https://github.com/<your-github-username>/my-first-blog.git
    

A medida que ves ejecutar, podrás ver lo que hace:

- Descarga tu código de GitHub
- Crea un virtualenv en PythonAnywhere, tal como el de tu PC
- Actualiza tus configuraciones con algunas configuraciones de despliegue
- Configura la base de datos en PythonAnywhere usando el comando `manage.py migrate`
- Configura tus archivos estáticos (aprenderemos acerca de estos luego)
- Y configura PythonAnywhere para publicar tu aplicación web por medio de su API

En PythonAnywhere todos esos pasos están automatizados, pero son los mismos pasos que tendrías que haber seguido en cualquier otro proveedor de servidor. Lo principal a notar ahora es que tu base de datos en PythonAnywhere está, en realidad, totalmente separada de la base de datos en tu propio PC—eso significa que puedes tener distintas publicaciones y cuentas de administración.

Como resultado, tal como hicimos en tu computador, necesitamos inicializar la cuenta de administrador con `createsuperuser`. PythonAnywhere ha activado automáticamente tu virtualenv, entonces todo lo que debes hacer es ejecutar:

{% filename %}PythonAnywhere command-line{% endfilename %}

    (ola.pythonanywhere.com) $ python manage.py createsuperuser
    

Inserta las credenciales para tu usuario admin. Mejor si usas las mismas que usas en tu computador, para evitar confusiones; a menos que quieras que la contraseña en PythonAnywhere sea más segura.

Ahora, si lo deseas, tambien puedes mirar tu código en PythonAnywhere usando `ls`:

{% filename %}PythonAnywhere command-line{% endfilename %}

    (ola.pythonanywhere.com) $ ls
    blog  db.sqlite3  manage.py  mysite requirements.txt static
    (ola.pythonanywhere.com) $ ls blog/
    __init__.py  __pycache__  admin.py  forms.py  migrations  models.py  static
    templates  tests.py  urls.py  views.py
    

You can also go to the "Files" page and navigate around using PythonAnywhere's built-in file browser. (From the Console page, you can get to other PythonAnywhere pages from the menu button in the upper right corner. Once you're on one of the pages, there are links to the other ones near the top.)

## Ahora estás en línea!

Your site should now be live on the public Internet! Click through to the PythonAnywhere "Web" page to get a link to it. You can share this with anyone you want :)

> **Nota** Este es un tutorial para principiantes, y al desplegar esta página hemos tomado algunos atajos que no son ideales desde una perspectiva de seguridad. Si y cuando decida construir sobre este proyecto, o comenzar uno nuevo, debería revisar el [Checklist de despliegue de Django](https://docs.djangoproject.com/en/2.0/howto/deployment/checklist/) para obtener algunos tips de cómo asegurar tu página.

## Tips de Depuración

Si ves un error al ejecutar el script `pa_autconfigure_django.py`, aqui hay algunas causas comunes:

- Olvidar crear el token de API de PythonAnywhere.
- Cometer un error en la URL de GitHub
- Si ves un error diciendo *"Could not find your settings.py*, es probable que no añadieras todos tus archivos a Git, y/o no los subiste a GitHub satisfactoriamente. Dale otro vistazo a la sección Git arriba

Si ves un error cuando tratas de visitar tu página, el primer lugar para ver alguna información de depuración es en tu **log de errores**. You'll find a link to this on the PythonAnywhere ["Web" page](https://www.pythonanywhere.com/web_app_setup/). Mira si hay algún mensaje de error allí; los más recientes están en la parte inferior.

Hay también alguns [ tips generales de depuración en la página de ayuda de PythonAywhere](http://help.pythonanywhere.com/pages/DebuggingImportError).

Y recuerda, tu mentor está aquí para ayudar!

# Checa tu página!

La página por defecto debería decir "It worked!", tal como lo dice en tu computador. Intenta añadir `/admin/` al final de la URL y te llevará a la página de administración. Ingresa con el usuario y contraseña y verás que puedes agregar nuevas publicaciones al servidor.

Una vez que hayas creado algunas publicaciones, puedes volver a tu instalación local (no PythonAnywhere). Desde allí, deberías trabajar en tu instalación local para hacer cambios. Este es un flujo de trabajo común en el desarrollo web – haz cambios localmente, sube esos cambios a GitHub, y jala tus cambios al servidor de publicación. Esto te permite trabajar y experimentar sin romper tu página publicada. Genial, ¿ah?

¡Date una *GRAN* palmada en la espalda! El despliegue a servidor es una de las partes más complicadas de desarrollo web y con frecuencia requiere a las personas múltiples días antes de lograr que funcione. But you've got your site live, on the real Internet!