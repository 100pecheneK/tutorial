# Introducción a la interfaz de línea de comandos

> Para los lectores en casa: este capítulo puede verse en el vídeo [Tu nuevo amigo: Línea de Comandos](https://www.youtube.com/watch?v=jvZLWhkzX-8).

Es emocionante, ¿verdad? ¡Vas a escribir tu primera línea de código en pocos minutos! :)

**Permítenos presentarte a tu primer amigo nuevo: ¡la línea de comandos!**

Los siguientes pasos te mostrarán cómo usar aquella ventana negra que todos los hackers usan. Puede parecer un poco aterrador al principio pero es solo un mensaje en pantalla que espera a que le des órdenes.

> **Nota** Ten en cuenta que a lo largo de este libro usamos los términos 'directorio' y 'carpeta' indistintamente pero son la misma cosa.

## ¿Qué es la línea de comandos?

La ventana, que generalmente es llamada **línea de comandos** ó **interfaz de línea de comandos**, es una aplicación basada en texto para ver, manejar y manipular archivos en tu ordenador. Similar a Windows Explorer o Finder en Mac, pero sin la interfaz gráfica. Otros nombres para la línea de comandos son: *cmd*, *CLI*, *prompt* -símbolo de sistema-, *console* -consola- o *terminal*.

## Abrir la interfaz de línea de comandos

Para empezar con algunos experimentos necesitarás abrir nuestra interfaz de línea de comandos en primer lugar.

{% incluye "/intro_to_command_line/open_instructions.md" %}

## Símbolo del Sistema (Prompt)

Ahora deberías ver una pantalla blanca o negra que espera a que introduzcas tus comandos.

<!--sec data-title="Prompt: OS X and Linux" data-id="OSX_Linux_prompt" data-collapse=true ces-->

Si estás en Mac o Linux, probablemente veas una `$`, como ésta:

{% filename %}command-line{% endfilename %}

    $
    

<!--endsec-->

<!--sec data-title="Prompt: Windows" data-id="windows_prompt2" data-collapse=true ces-->

En Windows, probablemente veas un `>`, como éste:

{% filename %}command-line{% endfilename %}

    >
    

Echa un vistazo a la sección anterior sobre Linux -- podrás consultar más cuando llegues a PythonAnywhere más adelante en este tutorial.

<!--endsec-->

Cada comando vendrá precedido por un `$` o un `>` y un espacio, pero no debes escribirlos tú mismo. El ordenador lo hará por ti. :)

> Solo una pequeña anotación: en tu caso puede que haya algo como `C:\Users\ola>` o `Olas-MacBook-Air:~ ola$` antes del símbolo de introducción, lo cual es 100% NORMAL.

La parte superior incluye el `$` o el `>` que es llamado en la *línea de comandos*, o mas corto *prompt*. Introduce algo allí.

En el tutorial, cuando queramos introducir un comando, incluye el `$` o `>`, y ocasionalmente más a la izquierda. Ignora la parte izquierda solamente escribiendo el comando, el cuál inicia después de el prompt.

## Tu primer comando (¡BIEN!)

Iniciemos por teclear este comando:

<!--sec data-title="Your first command: OS X and Linux" data-id="OSX_Linux_whoami" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ whoami
    

<!--endsec-->

<!--sec data-title="Your first command: Windows" data-id="windows_whoami" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > whoami
    

<!--endsec-->

Y luego presiona `enter`. Esto será nuestro resultado:

{% filename %}command-line{% endfilename %}

    $ whoami olasitarska
    

Como puedes ver, el computador ha solo impreso tu nombre de usuario. Ordenado, ¿ah? :)

> Intenta escribir cada comando; no copies y pegues. ¡De ésta manera lo recordarás!

## Fundamentos

Cada sistema operativo tiene un poco diferente la configuración de los comandos para la consola, así que asegurate de seguir las instrucciones para tu sistema operativo. Intentemos esto, ¿Verdad?

### Directorio actual

Sería bueno saber dónde estamos ahora, ¿Correcto? Veamos. Escribe éste comando y presiona `enter`:

<!--sec data-title="Current directory: OS X and Linux" data-id="OSX_Linux_pwd" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ pwd
    /Users/olasitarska
    

> Nota: 'pwd' es para imprimir el directorio de trabajo (print working directory).

<!--endsec-->

<!--sec data-title="Current directory: Windows" data-id="windows_cd" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd 
    C:\Users\olasitarska
    

> Nota: 'cd' es para cambiar de directorio (change directory). Con la consola tu puedes usar pwd solo con Linux o Mac OS X.

<!--endsec-->

Probablemente veremos algo similar en tu computador. Una vez que abres la consola o la línea de comandos, usualmente inicias en tu directorio principal.

* * *

### Aprende más sobre un comando

¡Muchos comandos pueden escribirse en el prompt que tiene construído una ayuda que puedes leer! Por ejemplo, aprende más acerca de el comando del directorio actual:

<!--sec data-title="Command help: OS X and Linux" data-id="OSX_Linux_man" data-collapse=true ces-->

OS X y Linux tienen un comando `man`, el cuál te da una ayuda en comandos. Try `man pwd` and see what it says, or put `man` before other commands to see their help. The output of `man` is normally paged. Use the space bar to move to the next page, and `q` to quit looking at the help.

<!--endsec-->

<!--sec data-title="Current directory: Windows" data-id="windows_help" data-collapse=true ces-->

Adding a `/?` suffix to most commands will print the help page. You may need to scroll your command window up to see it all. Try `cd /?`.

<!--endsec-->

### Listar ficheros y directorios

So what's in it? It'd be cool to find out. Let's see:

<!--sec data-title="List files and directories: OS X and Linux" data-id="OSX_Linux_ls" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ ls
    Applications
    Desktop
    Downloads
    Music
    ...
    

<!--endsec-->

<!--sec data-title="List files and directories: Windows" data-id="windows_dir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > dir
    Directory of C:\Users\olasitarska
    05/08/2014 07:28 PM <DIR> Applications
    05/08/2014 07:28 PM <DIR> Desktop
    05/08/2014 07:28 PM <DIR> Downloads
    05/08/2014 07:28 PM <DIR> Music
    ...
    

> Note: In powershell you can also use 'ls' like on Linux and Mac OS X. <!--endsec-->

* * *

### Cambiar el directorio actual

Now, let's go to our Desktop directory:

<!--sec data-title="Change current directory: OS X" data-id="OSX_move_to" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ cd Desktop
    

<!--endsec-->

<!--sec data-title="Change current directory: Linux" data-id="Linux_move_to" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ cd Desktop
    

Note that the directory name "Desktop" might be translated to the language of your Linux account. If that's the case, you'll need to replace `Desktop` with the translated name; for example, `Schreibtisch` for German.

<!--endsec-->

<!--sec data-title="Change current directory: Windows" data-id="windows_move_to" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd Desktop
    

<!--endsec-->

Check if it's really changed:

<!--sec data-title="Check if changed: OS X and Linux" data-id="OSX_Linux_pwd2" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ pwd
    /Users/olasitarska/Desktop
    

<!--endsec-->

<!--sec data-title="Check if changed: Windows" data-id="windows_cd2" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd
    C:\Users\olasitarska\Desktop
    

<!--endsec-->

Here it is!

> PRO tip: if you type `cd D` and then hit `tab` on your keyboard, the command line will automatically fill in the rest of the name so you can navigate faster. If there is more than one folder starting with "D", hit the `tab` key twice to get a list of options.

* * *

### Crear un directorio

How about creating a practice directory on your desktop? You can do it this way:

<!--sec data-title="Create directory: OS X and Linux" data-id="OSX_Linux_mkdir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ mkdir practice
    

<!--endsec-->

<!--sec data-title="Create directory: Windows" data-id="windows_mkdir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > mkdir practice
    

<!--endsec-->

This little command will create a folder with the name `practice` on your desktop. You can check if it's there by looking on your Desktop or by running a `ls` or `dir` command! Try it. :)

> PRO tip: If you don't want to type the same commands over and over, try pressing the `up arrow` and `down arrow` on your keyboard to cycle through recently used commands.

* * *

### ¡Ejercicio!

A small challenge for you: in your newly created `practice` directory, create a directory called `test`. (Use the `cd` and `mkdir` commands.)

#### Solución:

<!--sec data-title="Exercise solution: OS X and Linux" data-id="OSX_Linux_test_dir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ cd practice
    $ mkdir test
    $ ls
    test
    

<!--endsec-->

<!--sec data-title="Exercise solution: Windows" data-id="windows_test_dir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd practice
    > mkdir test
    > dir
    05/08/2014 07:28 PM <DIR>      test
    

<!--endsec-->

Congrats! :)

* * *

### Clean up

We don't want to leave a mess, so let's remove everything we did until that point.

First, we need to get back to Desktop:

<!--sec data-title="Clean up: OS X and Linux" data-id="OSX_Linux_back" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ cd ..
    

<!--endsec-->

<!--sec data-title="Clean up: Windows" data-id="windows_back" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd ..
    

<!--endsec-->

Using `..` with the `cd` command will change your current directory to the parent directory (that is, the directory that contains your current directory).

Check where you are:

<!--sec data-title="Check location: OS X and Linux" data-id="OSX_Linux_pwd3" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ pwd
    /Users/olasitarska/Desktop
    

<!--endsec-->

<!--sec data-title="Check location: Windows" data-id="windows_cd3" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > cd
    C:\Users\olasitarska\Desktop
    

<!--endsec-->

Now time to delete the `practice` directory:

> **Attention**: Deleting files using `del`, `rmdir` or `rm` is irrecoverable, meaning *the deleted files will be gone forever*! So be very careful with this command.

<!--sec data-title="Delete directory: Windows Powershell, OS X and Linux" data-id="OSX_Linux_rm" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ rm -r practice
    

<!--endsec-->

<!--sec data-title="Delete directory: Windows Command Prompt" data-id="windows_rmdir" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > rmdir /S practice
    practice, Are you sure <Y/N>? Y
    

<!--endsec-->

Done! To be sure it's actually deleted, let's check it:

<!--sec data-title="Check deletion: OS X and Linux" data-id="OSX_Linux_ls2" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ ls
    

<!--endsec-->

<!--sec data-title="Check deletion: Windows" data-id="windows_dir2" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > dir
    

<!--endsec-->

### Salir

That's it for now! You can safely close the command line now. Let's do it the hacker way, alright? :)

<!--sec data-title="Exit: OS X and Linux" data-id="OSX_Linux_exit" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    $ exit
    

<!--endsec-->

<!--sec data-title="Exit: Windows" data-id="windows_exit" data-collapse=true ces-->

{% filename %}command-line{% endfilename %}

    > exit
    

<!--endsec-->

Genial, ¿no? :)

## Resumen

Here is a summary of some useful commands:

| Comando (Windows) | Comando (Mac OS / Linux) | Descripción                   | Ejemplo                                            |
| ----------------- | ------------------------ | ----------------------------- | -------------------------------------------------- |
| exit              | exit                     | Cierra la ventana             | **exit**                                           |
| cd                | cd                       | Cambia el directorio          | **cd test**                                        |
| cd                | pwd                      | Mostrar el directorio actual  | **cd** (Windows) o **pwd** (Mac OS / Linux)        |
| dir               | ls                       | Lista directorios/archivos    | **dir**                                            |
| copy              | cp                       | Copia de archivos             | **copy c:\test\test.txt c:\windows\test.txt**  |
| move              | mv                       | Mueve archivos                | **move c:\test\test.txt c:\windows\test.txt**  |
| mkdir             | mkdir                    | Crea un nuevo directorio      | **mkdir testdirectory**                            |
| rmdir (o del)     | rm                       | Eliminar un archivo           | **del c:\test\test.txt**                         |
| rmdir /S          | rm -r                    | Eliminar un Directorio        | **rm -r testdirectory**                            |
| [CMD] /?          | man [CMD]                | Obtener ayuda para un comando | **cd /?** (Windows) or **man cd** (Mac OS / Linux) |

These are just a very few of the commands you can run in your command line, but you're not going to use anything more than that today.

If you're curious, [ss64.com](http://ss64.com) contains a complete reference of commands for all operating systems.

## ¿Listo?

Let's dive into Python!