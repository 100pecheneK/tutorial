Puedes [saltarte esta sección](http://tutorial.djangogirls.org/en/installation/#install-python) en caso de que no estés usando un Chromebook. Si lo usas, tu experiencia de instalación será algo diferente. Puedes ignorar el resto de las instrucciones de instalación.

### IDE en la nube (PaizaCloud Cloud IDE, AWS Cloud9)

Nube de IDE es una herramienta que te ofrece un editor de código y el acceso por medio de internet a una computadora donde puedes instalar, escribir y ejecutar el software. Durante este tutorial, el IDE en la nube te servirá como tu *máquina local*. Seguirás ejecutando comandos en una terminal igual que tus compañeros de clase en OS X, Ubuntu, o Windows, pero tu terminal en realidad estará conectada a una computadora trabajando en algún otro lugar, que el IDE en la nube configura para ti. Aquí están las instrucciones para IDEs en la nube (PaizaCloud Cloud IDE, AWS Cloud9). Puedes elegir uno de los IDEs en la nube, y seguir sus instrucciones.

#### PaizaCloud Cloud IDE

1. Ve a [PaizaCloud Cloud IDE](https://paiza.cloud/)
2. Crea una cuenta
3. Haz click en *New Server*
4. Haz click en el botón Terminal (en el lado izquierdo de la ventana)

Ahora deberías ver una interfaz con una barra y botones en la izquierda. Haz click en al botón "Terminal" para abrir la ventana de la terminal con un símbolo de sistema como este:

{% filename %}Terminal{% endfilename %}

    $
    

La terminal en el IDE en la nube PaizaCloud, está preparada para ejecutar tus instrucciones. Puedes redimensionar o maximar la ventana para hacerla un poco mas grande.

#### AWS Cloud9

1. Ve a [AWS Cloud9](https://aws.amazon.com/cloud9/)
2. Crea una cuenta
3. Haz click en *Create Environment*

Deberías ver un interfaz con una barra lateral, una ventana principal grande con texto y una ventana pequeña abajo del todo parecida a esto:

{% filename %}bash{% endfilename %}

    yourusername:~/workspace $
    

El área de abajo es tu terminal. Puedes usar el terminal para enviar instrucciones al ordenador remoto en Clod 9. Puedes redimensionar o maximar la ventana para hacerla un poco mas grande.

### Entorno Virtual

Un entorno virtual (también llamado virtualenv) es como una caja privada donde podemos guardar código útil para el proyecto en el que estamos trabajando. Lo usamos para guardar por separado los trozos de código de distintos proyectos, y que así, las cosas no se mezclen entre proyectos.

En la terminal de la parte inferior de Cloud 9, ejecuta lo siguiente:

{% filename %}Cloud 9{% endfilename %}

    sudo apt update
    sudo apt install python3.6-venv
    

Si aun así, no te funciona, pide ayuda a tu mentor.

A continuación, ejecuta:

{% filename %}Cloud 9{% endfilename %}

    mkdir djangogirls
    cd djangogirls
    python3.6 -mvenv myvenv
    source myvenv/bin/activate
    pip install django~={{ book.django_version }}
    

(nota que en la ultima linea usamos una virgulilla (~) seguido de un signo igual `~=`).

### GitHub

Hazte una cuenta de [GitHub](https://github.com).

### PythonAnywhere

El tutorial de Django Girls tiene una sección que se llama "Despliegue", que es el proceso de coger el código de tu nueva aplicación web y ponerlo en un ordenador públicamente accesible (un servidor) para que todo el mundo pueda ver tu trabajo.

Esta parte del tutorial es algo extraña usando un Chromebook, pues ya estamos usando un computador conectado a internet (contrario a, por ejemplo, una laptop). Sin embargo, aún es útil, ya que podemos pensar que nuestro espacio de trabajo en Cloud 9 como un repositorio para nuestro trabajo "en progreso" y Python Anywhere como un lugar donde mostrar nuestro trabajo más completo.

Así que créate una cuenta de PythonAnywhere en [www.pythonanywhere.com](https://www.pythonanywhere.com).