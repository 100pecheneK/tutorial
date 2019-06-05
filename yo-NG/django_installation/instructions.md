> Apá kan lára abala yìí dá lórí àwọn àlàyé ti Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).
> 
> Apá kan lára abala yìí dá lórí [àlàyé django-marcador](http://django-marcador.keimlink.de/) náà tó ní ìwé-àṣẹ lábẹ́ Creative Commons Attribution-ShareAlike 4.0 International License. Àlàyé django-marcador náà ni ẹ̀tọ́ rẹ̀ jẹ́ ti Markus Zapke-Gründemann et al.

## Àyíká àìrí

Ṣáájú kí a tó ṣàgbékalẹ̀ Django, a ó mú ọ ṣàgbékalẹ̀ irinṣẹ́ kan tó wúlò púpọ̀ láti ṣe ìrànlọ́wọ́ mímú kí àyíká kóòdù kíkọ rẹ wà létòlétò lórí kọ̀mpútà rẹ. Ó ṣeéṣe láti fo ìgbésẹ̀ yìí, ṣùgbọ́n òhun ló dáa jù. Bíbẹ̀rẹ̀ pẹ̀lú àgbékalẹ̀-ètò tó dára jù lọ yíò gbà ọ́ sílẹ̀ lọ́wọ́ ọ̀pọ̀lọpọ̀ wàhálà lọ́jọ́ iwájú!

Nítorí náà, jẹ́ ká ṣẹ̀dá **àyíká àìrí** kan (tí a tún pè ní *virtualenv* kan). Virtualenv will isolate your Python/Django setup on a per-project basis. This means that any changes you make to one website won't affect any others you're also developing. Neat, right?

All you need to do is find a directory in which you want to create the `virtualenv`; your home directory, for example. On Windows, it might look like `C:\Users\Name` (where `Name` is the name of your login).

> **NOTE:** On Windows, make sure that this directory does not contain accented or special characters; if your username contains accented characters, use a different directory, for example, `C:\djangogirls`.

Fún àlàyé yìí, a ó máa lo àkójọpọ̀ fáìlì `djangogirls` tuntun kan láti àkójọpọ̀ fáìlì ìpìlẹ̀ rẹ:

{% filename %}command-line{% endfilename %}

    $ mkdir djangogirls
    $ cd djangogirls
    

A ó ṣẹ̀dá virtualenv kan tí a n pè ní `myvenv`. Àṣẹ tí a sábà náà yíò rí báyìí:

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

<!--sec data-title="Virtual environment: Windows" data-id="virtualenv_installation_windows"
data-collapse=true ces-->

Láti ṣẹ̀dá `virtualenv` tuntun kan, o nílò láti ṣí command prompt náà kí o sì ṣe `python -m venv myvenv`. Yíò rí báyìí:

{% filename %}command-line{% endfilename %}

    C:\Users\Name\djangogirls> python -m venv myvenv
    

Níbi tí `myvenv` jẹ́ orúkọ `virtualenv` rẹ. O lè lo èyíkéyìí orúkọ mìíràn, ṣùgbọ́n dúró lórí lílo lẹ́tà kékeré láìsí àwọn àlàfo, àmì ohùn tàbí àkànṣe ẹyọ ọ̀rọ̀. Ó tún jẹ́ èrò tó dára kan láti mú kí orúkọ náà kéré – ìwọ yíò ma tọ́ka rẹ̀ lọ́pọ̀ ìgbà!

<!--endsec-->

<!--sec data-title="Virtual environment: Linux and OS X" data-id="virtualenv_installation_linuxosx"
data-collapse=true ces-->

A lè ṣẹ̀dá `virtualenv` kan lórí Linux àti OS X nípasẹ̀ lílo `python3 -m venv myvenv`. Yíò rí báyìí:

{% filename %}command-line{% endfilename %}

    $ python3 -m venv myvenv
    

`myvenv` ni orúkọ `virtualenv` rẹ. O lè lo èyíkéyìí orúkọ mìíràn, ṣùgbọ́n dúró lórí lílo lẹ́tà kékeré láìsí àwọn àlàfo. Ó tún jẹ́ èrò tó dára kan láti mú kí orúkọ náà kéré nítorí pé ìwọ yíò ma tọ́ka rẹ̀ lọ́pọ̀ ìgbà!

> **ÀKÍYÈSÍ:** Lórí àwọn ẹyà Debian/Ubuntu kan, o lè rí àṣìṣe tó tẹ̀lé yìí:
> 
> {% filename %}command-line{% endfilename %}
> 
>     The virtual environment was not created successfully because ensurepip is not available.  On Debian/Ubuntu systems, you need to install the python3-venv package using the following command.
>        apt install python3-venv
>     You may need to use sudo with that command.  After installing the python3-venv package, recreate your virtual environment.
>     
> 
> Ní irú ìṣẹ̀lẹ̀ yìí, tẹ̀lé àwọn ìtọ́sọ́nà tó wà lókè kí o sì ṣàgbékalẹ̀ ètò `python3-venv` náà: {% filename %}command-line{% endfilename %}
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
> Láti borí àṣìṣe yìí, lo àṣẹ `virtualenv` náà dípò.
> 
> {% filename %}command-line{% endfilename %}
> 
>     $ sudo apt install python-virtualenv
>     $ virtualenv --python=python3.6 myvenv
>     
> 
> **ÀKÍYÈSÍ:** Tí o bá rí àṣìṣe kan bíi
> 
> {% filename %}command-line{% endfilename %}
> 
>     E: Unable to locate package python3-venv
>     
> 
> ṣe èyí dípò:
> 
> {% filename %}command-line{% endfilename %}
> 
>     sudo apt install python3.6-venv
>     

<!--endsec-->

## Ìṣiṣẹ́ pẹ̀lú virtualenv

Àṣẹ tó wà lókè náà yíò ṣẹ̀dá àkójọpọ̀ fáìlì kan tí a n pè ní `myvenv` (tàbí orúkọ yòówù tí o yàn) tí yíò kó àyíká àìrí wa sínú (ní pàtàkì àpapọ̀ àkójọpọ̀ fáìlì àti àwọn fáìlì kan).

<!--sec data-title="Working with virtualenv: Windows" data-id="virtualenv_windows"
data-collapse=true ces-->

Bẹ̀rẹ̀ àyíká àìrí rẹ nípasẹ̀ ṣíṣe:

{% filename %}command-line{% endfilename %}

    C:\Users\Name\djangogirls> myvenv\Scripts\activate
    

> **ÀKÍYÈSÍ:** lórí Windows 10, o lè rí àṣìṣe kan nínú Windows PowerShell náà tó sọ pé `execution of scripts is disabled on this system`. In this case, open another Windows PowerShell with the "Run as Administrator" option. Then try typing the following command before starting your virtual environment:
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

Bẹ̀rẹ̀ àyíká àìrí rẹ nípasẹ̀ ṣíṣe:

{% filename %}command-line{% endfilename %}

    $ source myvenv/bin/activate
    

Rántí láti rọ́pò `myvenv` pẹ̀lú orúkọ `virtualenv` rẹ tó o yàn!

> **NOTE:** sometimes `source` might not be available. In those cases try doing this instead:
> 
> {% filename %}command-line{% endfilename %}
> 
>     $ . myvenv/bin/activate
>     

<!--endsec-->

You will know that you have `virtualenv` started when you see that the prompt in your console is prefixed with `(myvenv)`.

When working within a virtual environment, `python` will automatically refer to the correct version so you can use `python` instead of `python3`.

OK, we have all important dependencies in place. We can finally install Django!

## Installing Django

Now that you have your `virtualenv` started, you can install Django.

Before we do that, we should make sure we have the latest version of `pip`, the software that we use to install Django:

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ python -m pip install --upgrade pip
    

### Installing packages with requirements

A requirements file keeps a list of dependencies to be installed using `pip install`:

Kọ́kọ́ ṣẹ̀dá fáìlì `requirements.txt` kan sínú fódà `djangogirls/` náà, pẹ̀lú lílo olóòtú kóòdù tí o ti ṣàgbékalẹ̀ ṣáájú. You do this by opening a new file in the code editor and then saving it as `requirements.txt` in the `djangogirls/` folder. Àkójọpọ̀ fáìlì rẹ yíò rí báyìí:

    djangogirls
    └───requirements.txt
    

Nínú fáìlì `djangogirls/requirements.txt` rẹ, ó yẹ kí o ṣàfikún ọ̀rọ̀ tó tẹ̀le yìí:

{% filename %}djangogirls/requirements.txt{% endfilename %}

    Django~={{ book.django_version }}
    

Ní báyìí, ṣe `pip install -r requirements.txt` láti ṣàgbékalẹ̀ Django.

{% filename %}command-line{% endfilename %}

    (myvenv) ~$ pip install -r requirements.txt
    Collecting Django~={{ book.django_version }} (from -r requirements.txt (line 1))
      Downloading Django-{{ book.django_version }}-py3-none-any.whl (7.1MB)
    Installing collected packages: Django
    Successfully installed Django-{{ book.django_version }}
    

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
>     C:\Users\Name\djangogirls> python -m pip install -r requirements.txt
>     

<!--endsec-->

<!--sec data-title="Installing Django: Linux" data-id="django_err_linux"
data-collapse=true ces-->

> If you get an error when calling pip on Ubuntu 12.04 please run `python -m pip install -U --force-reinstall pip` to fix the pip installation in the virtualenv.

<!--endsec-->

That's it! You're now (finally) ready to create a Django application!