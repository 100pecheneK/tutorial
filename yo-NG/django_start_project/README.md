# Iṣẹ́ Django àkọ́kọ́ rẹ!

> Apá kan lára àkòrí yìí dá lórí àwọn àlàyé ti Geek Girls Carrots (https://github.com/ggcarrots/django-carrots).
> 
> Àwọn apá kan lára àkòrí yìí dá lórí [àlàyé django-marcador](http://django-marcador.keimlink.de/) náà tó ní ìwé-àṣẹ lábẹ́ Creative Commons Attribution-ShareAlike 4.0 International License. Àlàyé django-marcador náà ni ẹ̀tọ́ rẹ̀ jẹ́ ti Markus Zapke-Gründemann et al.

A óò ṣẹ̀dá blog kékeré kan!

Ìgbésẹ̀ àkọ́kọ́ ni láti bẹ̀rẹ̀ iṣẹ́ Django tuntun kan. Basically, this means that we'll run some scripts provided by Django that will create the skeleton of a Django project for us. Èyí wulẹ̀ jẹ́ àpapọ̀ àkójọpọ̀ fáìlì àti àwọn fáìlì kan tí a ó lò tó bá yá.

Orúkọ àwọn fáìlì àti àkójọpọ̀ fáìlì kan ṣe pàtàkì gan-an fún Django. Ìwọ kò gbọ́dọ̀ ṣàtúnṣe orúkọ àwọn fáìlì tí a fẹ́ ṣẹ̀dá náà. Gbígbé wọn sí ibi tó yàtọ̀ kan kìí tún ṣe èrò tó dára kan. Django nílò láti máa ní ìgbékalẹ̀ pàtó kan láti lè rí àwọn nnkan pàtàkì.

> Rántí láti ṣe gbogbo nnkan nínú virtualenv náà. Tí ìwọ kò bá rí `(myvenv)` níbẹ̀rẹ̀ nínú console rẹ, o nílò láti mú virtualenv rẹ ṣiṣẹ́. A ti ṣàlàyé bí o ṣe lè ṣe ìyẹn nínú àkòrí **Ìṣàgbékalẹ̀ Django** ní apá **Ìṣiṣẹ́ pẹ̀lú virtualenv** náà. Títẹ `myvenv\Scripts\activate` lórí Windows tàbí `source myvenv/bin/activate` lórí Mac OS X tàbí Linux yíò ṣe èyí fún ọ.

<!--sec data-title="Create project: OS X or Linux" data-id="django_start_project_OSX_Linux" data-collapse=true ces-->

Nínú console Mac OS X tàbí Linux rẹ, ó yẹ kí o ṣe àṣẹ tó tẹ̀le yìí. **Má gbàgbé láti ṣàfikún àmì tó-ín `.` náà ní ìparí!**

{% filename %}command-line{% endfilename %}

    (myvenv) ~/djangogirls$ django-admin startproject mysite .
    

> The period `.` is crucial because it tells the script to install Django in your current directory (for which the period `.` is a short-hand reference).
> 
> **Note** When typing the command above, remember that you only type the part which starts by `django-admin`. The `(myvenv) ~/djangogirls$` part shown here is just example of the prompt that will be inviting your input on your command line.

<!--endsec-->

<!--sec data-title="Create project: Windows" data-id="django_start_project_windows" data-collapse=true ces-->

On Windows you should run the following command. **(Don't forget to add the period (or dot) `.` at the end)**:

{% filename %}command-line{% endfilename %}

    (myvenv) C:\Users\Name\djangogirls> django-admin.exe startproject mysite .
    

> The period `.` is crucial because it tells the script to install Django in your current directory (for which the period `.` is a short-hand reference).
> 
> **Àkíyèsí** Nígbà tí o bá n tẹ àṣẹ tó wà lókè náà, rántí pé apá tó bẹ̀rẹ̀ pẹ̀lú `django-admin.exe` nìkan ni o ma tẹ. Apá `(myvenv) C:\Users\Name\djangogirls>` náà tí a ṣàfihàn níbí wulẹ̀ jẹ́ àpẹẹrẹ prompt náà tí yíò ma dúró de ohun tí o fẹ́ tẹ̀ sórí ìlà ìpàṣẹ rẹ.

<!--endsec-->

`django-admin.py` jẹ́ ìlànà ìṣe (script) kan tí yíò ṣẹ̀dá àwọn àkójọpọ̀ fáìlì àti àwọn fáìlì náà fún ọ. Ó yẹ kí o ní ìgbékalẹ̀ àkójọpọ̀ fáìlì kan tó rí báyìí:

    djangogirls
    ├───manage.py
    ├───mysite
    │        settings.py
    │        urls.py
    │        wsgi.py
    │        __init__.py
    └───requirements.txt
    

> **Àkíyèsí**: nínú ìgbékalẹ̀ àkójọpọ̀ fáìlì rẹ, ìwọ yíò tún rí àkójọpọ̀ fáìlì `venv` rẹ tí a ti ṣẹ̀dá ṣáájú.

`manage.py` jẹ́ ìlànà ìṣe (script) kan tí yíò ṣe ìrànlọ́wọ́ pẹ̀lú ìṣàkóso ààyè náà. Pẹ̀lú rẹ̀, a ó lè (láàrín àwọn nnkan mìíràn) bẹ̀rẹ̀ server ayélujára kan lórí kọ̀mpútà wa láìsí ṣíṣe àgbékalẹ̀ ohunkóhun mìíràn.

Fáìlì `settings.py` náà yíò ní ìṣètò ààyè ayélujára rẹ.

Rántí ìgbà tí a sọ̀rọ̀ nípa òṣìṣẹ́ méèlì kan tó n ṣàyẹ̀wò ibi tí yíò fi lẹ́tà kan jíṣẹ́ sí? Fáìlì `urls.py` yíò ní àkójọ àwọn àpẹẹrẹ kan tó n jẹ́ lílò nípasẹ̀ `urlresolver`.

Jẹ́ ká fojú fo àwọn fáìlì yòókù náà nítorí pé a kò ní ṣàyípadà wọn. Ohun kan ṣoṣo láti rántí ni kí o má ṣèèṣì yọ wọ́n kúrò!

## Changing settings

Let's make some changes in `mysite/settings.py`. Open the file using the code editor you installed earlier.

**Note**: Keep in mind that `settings.py` is a regular file, like any other. You can open it from inside the code editor, using the "file -> open" menu actions. This should get you the usual window in which you can navigate to your `settings.py` file and select it. Alternatively, you can open the file by navigating to the djangogirls folder on your desktop and right-clicking on it. Then, select your code editor from the list. Selecting the editor is important as you might have other programs installed that can open the file but will not let you edit it.

Yíò dára láti ní àkókò tó tọ́ lórí ààyè ayélujára wa. Lọ sí [Àkọsílẹ̀ àwọn agbègbè àkókò ti Wikipedia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) kí o sì ṣe àdàkọ agbègbè àkókò tó yẹ fún ọ (TZ) (fún àpẹẹrẹ `Africa/Lagos`).

Nínú `settings.py`, wá ìlà tó ní `TIME_ZONE` kí o ṣàtúnṣe rẹ̀ láti yan agbègbè àkókò tìẹ. Fún àpẹẹrẹ:

{% filename %}mysite/settings.py{% endfilename %}

```python
TIME_ZONE = 'Africa/Lagos'
```

Kóòdù èdè kan ma ní èdè náà, fún àpẹẹrẹ `en` fún Gẹ̀ẹ́sì tàbí `yo` fún Yorùbá, àti kóòdù orílẹ̀-èdè náà, fún àpẹẹrẹ `de` fún Jámánì tàbí `ng` fún Nàìjíríà. Tí Gẹ̀ẹ́sì kìí ba ṣe èdè abínibí rẹ, o lè ṣàfikún èyí láti ṣàyípadà àwọn bọ́tìnnì ìpìlẹ̀ àti àwọn ìpàkíyèsí láti Django kó wà ní èdè rẹ. Nítorí náà, ìwọ yíò ní bọ́tìnnì "Cancel" (Fagi lé) tí a túmọ̀ sí èdè tí o yàn níbí. [Django wá pẹ̀lú ọ̀pọ̀lọpọ̀ àwọn ìtumọ̀ ní ìpèsè](https://docs.djangoproject.com/en/2.0/ref/settings/#language-code).

Tí o bá fẹ́ èdè mìíràn kan, ṣàyípadà kóòdù èdè náà nípasẹ̀ ṣíṣe ìyípadà ìlà tó tẹ̀lé yìí:

{% filename %}mysite/settings.py{% endfilename %}

```python
LANGUAGE_CODE = 'de-ch'
```

A ó tún nílò láti ṣàfikún atọ́nà kan fún àwọn fáìlì tó wà lójú kan (static files). (A ó ṣèwádìí gbogbo nnkan nípa àwọn fáìlì tó wà lójú kan (static files) àti CSS tó bá yá nínú àlàyé náà.) Lọ sí ìsàlẹ̀ ní *ìparí* fáìlì náà, lábẹ́ ìgbéwọlé `STATIC_URL` náà, ṣàfikún ìgbéwọlé tuntun kan tí a n pè ní `STATIC_ROOT`:

{% filename %}mysite/settings.py{% endfilename %}

```python
STATIC_URL = '/static/'
STATIC_ROOT = os.path.join(BASE_DIR, 'static')
```

When `DEBUG` is `True` and `ALLOWED_HOSTS` is empty, the host is validated against `['localhost', '127.0.0.1', '[::1]']`. This won't match our hostname on PythonAnywhere once we deploy our application so we will change the following setting:

{% filename %}mysite/settings.py{% endfilename %}

```python
ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']
```

> **Àkíyèsí**: Tí o bá n lo Chromebook kan, ṣàfikún ìlà yìí nísàlẹ̀ fáìlì settings.py rẹ: `MESSAGE_STORAGE = 'django.contrib.messages.storage.session.SessionStorage'`
> 
> Tún ṣàfikún `.amazonaws.com` sí `ALLOWED_HOSTS` náà tí o bá n lo cloud9

## Ṣàgbékalẹ̀ àkójọpọ̀ dátà kan

Oríṣiríṣi ètò àkójọpọ̀ dátà ló wà tó lè tọ́jú dátà fún ààyè rẹ. A ó lo ti ìpìlẹ̀ náà, `sqlite3`.

Èyí ti wà ní àgbékalẹ̀ tẹ́lẹ̀ nínú apá yìí ti fáìlì `mysite/settings.py` rẹ:

{% filename %}mysite/settings.py{% endfilename %}

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```

Láti ṣẹ̀dá àkójọpọ̀ dátà kan fún blog wa, jẹ́ ká ṣe èyí nínú console náà: `python manage.py migrate` (a nílò láti wà nínú àkójọpọ̀ fáìlì `djangogirls` tó kó fáìlì `manage.py` náà sínú). Tí ìyẹn bá ń lọ bí ó ti yẹ, ó yẹ kí o rí nnkan kan báyìí:

{% filename %}command-line{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py migrate
    Operations to perform:
      Apply all migrations: auth, admin, contenttypes, sessions
    Running migrations:
      Rendering model states... DONE
      Applying contenttypes.0001_initial... OK
      Applying auth.0001_initial... OK
      Applying admin.0001_initial... OK
      Applying admin.0002_logentry_remove_auto_add... OK
      Applying contenttypes.0002_remove_content_type_name... OK
      Applying auth.0002_alter_permission_name_max_length... OK
      Applying auth.0003_alter_user_email_max_length... OK
      Applying auth.0004_alter_user_username_opts... OK
      Applying auth.0005_alter_user_last_login_null... OK
      Applying auth.0006_require_contenttypes_0002... OK
      Applying auth.0007_alter_validators_add_error_messages... OK
      Applying auth.0008_alter_user_username_max_length... OK
      Applying auth.0009_alter_user_last_name_max_length... OK
      Applying sessions.0001_initial... OK
    

Àti pé a ti parí! Àkókò láti bẹ̀rẹ̀ server ayélujára náà àti ṣàyẹ̀wò tí ààyè ayélujára wa bá n ṣiṣẹ́!

## Bíbẹ̀rẹ̀ server ayélujára náà

O nílò láti wà nínú àkójọpọ̀ fáìlì tó kó fáìlì `manage.py` náà sínú (àkójọpọ̀ fáìlì `djangogirls` náà). Nínú console náà, a lè bẹ̀rẹ̀ server ayélujára náà nípasẹ̀ ṣíṣe `python manage.py runserver`:

{% filename %}command-line{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py runserver
    

Tí o bá wà lórí Chromebook kan, lo àṣẹ yìí dípò:

{% filename %}Cloud 9{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py runserver 0.0.0.0:8080
    

Tí o bá wà lórí Windows tí èyí sì kùnà pẹ̀lú àṣìṣe `UnicodeDecodeError`, lo àṣẹ yìí dípò:

{% filename %}command-line{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py runserver 0:8000
    

Ní báyìí, o nílò láti ṣàyẹ̀wò tí ààyè ayélujára rẹ bá n ṣiṣẹ́. Ṣí aṣàwákiri rẹ (Firefox, Chrome, Safari, Internet Explorer tàbí èyíkéyìí tó bá n lò) kí o sì tẹ àdírẹ́ẹ̀sì yìí:

{% filename %}browser{% endfilename %}

    http://127.0.0.1:8000/
    

Tí o bá n lo Chromebook kan àti Cloud9, dípò, tẹ URL tó wà nínú fèrèsé aṣẹ́yọsókè tó yẹ kó ti farahàn ní igun òkè lápá ọ̀tún ti fèrèsé ìpàṣẹ níbi tí server ayélujára náà tí n ṣiṣẹ́. URL náà yíò rí báyìí:

{% filename %}browser{% endfilename %}

    https://<a bunch of letters and numbers>.vfs.cloud9.us-west-2.amazonaws.com
    

Kú oríire! O ṣẹ̀ṣẹ̀ ṣẹ̀dá ààyè ayélujára àkọ́kọ́ rẹ tí o sì mú u ṣiṣẹ́ pẹ̀lú lílo server ayélujára kan! Ṣe ìyẹn kò dára ni?

![Àgbékalẹ̀ ti ṣiṣẹ́!](images/install_worked.png)

Ṣàkíyèsí pé fèrèsé ìpàṣẹ kan lè ṣe ohun kan ṣoṣo ní àkókò kan, àti pé fèrèsé ìpàṣẹ tí o ṣí tẹ́lẹ̀ tí n ṣiṣẹ́ pẹ̀lú server ayélujára náà. Níwọ̀n ìgbà tí server ayélujára náà bá n ṣiṣẹ́ tó sì n dúró de àwọn ìbéèrè mìíràn tí ń bọ̀, èbúté náà yíò gba ọ̀rọ̀ tuntun ṣùgbọ́n kò ní ṣiṣẹ́ lórí àwọn àṣẹ tuntun.

> A ti ṣàgbéyẹ̀wò bí àwọn server ayélujára ṣé n ṣiṣẹ́ nínú àkòrí **Bí Íńtánẹ́ẹ̀tì ṣé n ṣiṣẹ́** náà.

Láti tẹ àwọn àṣẹ mìíràn nígbà tí server ayélujára náà bá n ṣiṣẹ́, ṣí fèrèsé èbúté tuntun kan kí o sì mú virtualenv rẹ ṣiṣẹ́ -- láti ṣàgbéyẹ̀wò àwọn ìtọ́sọ́nà lórí bí o ṣe lè ṣí fèrèsé èbúté kejì kan, wo [Ìfihàn sí ìlà ìpàṣẹ náà](../intro_to_command_line/README.md). Láti dáwọ́ server ayélujára náà dúró, padà sí fèrèsé èyí tí server náà tí n ṣiṣẹ́ náà kí o sì tẹ CTRL+C - àwọn bọ́tìnnì Control àti C papọ̀ (lórí Windows, o lè ní láti tẹ Ctrl+Break).

Ṣé o ti ṣetán fún ìgbésẹ̀ tó kàn náà? Àkókò ti tó láti ṣẹ̀dá àwọn àkóónú kan!