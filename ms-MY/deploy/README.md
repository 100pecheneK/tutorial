# Menyebarkan!

> **Nota** Bab berikut kadang-kadang agak sukar untuk diteruskan. Terus dan selesaikannya; penyebaran adalah bahagian penting dalam proses pembangunan laman web. Bab ini diletakkan di tengah-tengah tutorial supaya mentor anda dapat membantu dengan proses yang lebih rumit untuk mendapatkan laman web anda dalam talian. Ini bermakna anda masih boleh menyelesaikan tutorial anda sendiri jika anda kehabisan masa.

Hingga kini, laman web anda hanya tersedia di komputer anda. Kini anda akan belajar bagaimana untuk menggunakannya! Menyebarkan adalah proses menerbitkan aplikasi anda di Internet supaya orang akhirnya boleh pergi dan melihat aplikasi anda. :)

Seperti yang anda pelajari, tapak web harus ditempatkan di pelayan. There are a lot of server providers available on the internet, we're going to use [PythonAnywhere](https://www.pythonanywhere.com/). PythonAnywhere is free for small applications that don't have too many visitors so it'll definitely be enough for you now.

The other external service we'll be using is [GitHub](https://www.github.com), which is a code hosting service. Terdapat orang lain di luar sana, tetapi hampir semua pengaturcara mempunyai akaun GitHub hari ini, dan kini begitu juga anda!

Ketiga tempat ini akan menjadi penting bagi anda. Komputer tempatan anda akan menjadi tempat di mana anda melakukan pembangunan dan ujian. Apabila anda berpuas hati dengan perubahan, anda akan meletakkan salinan program anda di GitHub. Laman web anda akan berada di PythonAnywhere dan anda akan mengemas kini dengan mendapatkan salinan baru kod anda dari GitHub.

# Git

> **Note** If you already did the Installation steps, there's no need to do this again – you can skip to the next section and start creating your Git repository.

{% include "/deploy/install_git.md" %}

## Memulakan repositori Git kami

Git menjejaki perubahan pada satu set fail tertentu dalam apa yang dipanggil repositori kod (atau "repo" untuk pendek). Mari kita mulakan projek kami. Open up your console and run these commands, in the `djangogirls` directory:

> **Note** Check your current working directory with a `pwd` (Mac OS X/Linux) or `cd` (Windows) command before initializing the repository. You should be in the `djangogirls` folder.

{% filename %}command-line{% endfilename %}

    $ git init
    Initialized empty Git repository in ~/djangogirls/.git/
    $ git config --global user.name "Your Name"
    $ git config --global user.email you@example.com
    

Memulakan repositori git adalah sesuatu yang perlu kita lakukan hanya sekali bagi setiap projek (dan anda tidak perlu memasukkan semula nama pengguna dan email sekali lagi).

Git akan menjejaki perubahan kepada semua fail dan folder dalam direktori ini, tetapi terdapat beberapa fail yang kami mahu ia diabaikan. We do this by creating a file called `.gitignore` in the base directory. Buka editor anda dan buat fail baru dengan kandungan berikut:

{% filename %}.gitignore{% endfilename %}

    *.pyc
    *~
    __pycache__
    myvenv
    db.sqlite3
    /static
    .DS_Store
    

And save it as `.gitignore` in the "djangogirls" folder.

> **Note** The dot at the beginning of the file name is important! Jika anda mengalami sebarang kesulitan menciptanya (Mac tidak menyukai anda untuk membuat fail yang bermula dengan titik melalui Finder, sebagai contoh), kemudian gunakan ciri "Simpan Sebagai" dalam editor anda; ia peluru.
> 
> **Note** One of the files you specified in your `.gitignore` file is `db.sqlite3`. Fail itu ialah pangkalan data setempat anda, di mana semua jawatan anda disimpan. Kami tidak mahu menambah ini ke repositori anda kerana laman web anda di PythonAnywhere akan menggunakan pangkalan data yang berbeza. Pangkalan data itu boleh menjadi SQLite, seperti mesin pembangunan anda, tetapi biasanya anda akan menggunakan salah satu yang dipanggil MySQL yang boleh menangani pelawat laman web yang lebih banyak daripada SQLite. Dengan cara ini, dengan mengabaikan pangkalan data SQLite anda untuk salinan GitHub, ini bermakna bahawa semua jawatan yang anda buat setakat ini akan tinggal dan hanya boleh didapati di dalam negara, tetapi anda perlu menambah lagi pengeluaran. Anda perlu memikirkan pangkalan data tempatan anda sebagai taman permainan yang bagus di mana anda boleh menguji perkara yang berbeza dan jangan takut bahawa anda akan memadamkan siaran sebenar anda dari blog anda.

It's a good idea to use a `git status` command before `git add` or whenever you find yourself unsure of what has changed. Ini akan membantu menghalang sebarang kejutan daripada berlaku, seperti fail salah yang ditambah atau dilakukan. The `git status` command returns information about any untracked/modified/staged files, the branch status, and much more. Keluaran harus sama dengan yang berikut:

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
    
    nothing added to commit but untracked files present (use "git add" to track)
    

Dan akhirnya kami menyelamatkan perubahan kami. Pergi ke konsol anda dan jalankan arahan ini:

{% filename %}command-line{% endfilename %}

    $ git add --all .
    $ git commit -m "My Django Girls app, first commit"
     [...]
     13 files changed, 200 insertions(+)
     create mode 100644 .gitignore
     [...]
     create mode 100644 mysite/wsgi.py
     ```
    
    
    ## Pushing your code to GitHub
    
    Go to [GitHub.com](https://www.github.com) and sign up for a new, free user account. (Jika anda sudah melakukannya dalam persiapan bengkel, itu bagus!) Kemudian, buat repositori baru, memberikan nama "blog pertama saya". Biarkan kotak semak "memulakan dengan README" tidak dicentang, biarkan pilihan .gitignore kosong (kami telah melakukannya secara manual) dan biarkan Lesen sebagai Tiada.
    
    <img src="images/new_github_repo.png" />
    
    > **Note** The name `my-first-blog` is important – you could choose something else, but it's going to occur lots of times in the instructions below, and you'd have to substitute it each time. Mungkin lebih mudah hanya dengan nama `my-first-blog`.
    
    Pada skrin seterusnya, anda akan dipaparkan URL klon repo anda. Choose the "HTTPS" version, copy it, and we'll paste it into the terminal shortly:
    
    <img src="images/github_get_repo_url_screenshot.png" />
    
    Now we need to hook up the Git repository on your computer to the one up on GitHub.
    
    Type the following into your console (Replace `<your-github-username>` with the username you entered when you created your GitHub account, but without the angle-brackets):
    
    {% filename %}command-line{% endfilename %}
    

$ git remote add origin https://github.com/<your-github-username>/my-first-blog.git $ git push -u origin master

    <br />Enter your GitHub username and password and you should see something like this:
    
    {% filename %}command-line{% endfilename %}
    

Username for 'https://github.com': ola Password for 'https://ola@github.com': Counting objects: 6, done. Writing objects: 100% (6/6), 200 bytes | 0 bytes/s, done. Total 3 (delta 0), reused 0 (delta 0) To https://github.com/ola/my-first-blog.git

- [cawangan baru] tuan -> master master Cawangan ditubuhkan untuk mengesan induk cawangan jauh dari asal.

    <br />&lt;!--TODO: maybe do ssh keys installs in install party, and point ppl who dont have it to an extension --&gt;
    
    Your code is now on GitHub. Pergi dan periksa!  You'll find it's in fine company – [Django](https://github.com/django/django), the [Django Girls Tutorial](https://github.com/DjangoGirls/tutorial), and many other great open source software projects also host their code on GitHub. :)
    
    
    # Setting up our blog on PythonAnywhere
    
    ## Sign up for a PythonAnywhere account
    
    &gt; **Note** You might have already created a PythonAnywhere account earlier during the install steps – if so, no need to do it again.
    
    {% include "/deploy/signup_pythonanywhere.md" %}
    
    
    ## Configuring our site on PythonAnywhere
    
    Go back to the main [PythonAnywhere Dashboard](https://www.pythonanywhere.com/) by clicking on the logo, and choose the option to start a "Bash" console – that's the PythonAnywhere version of a command line, just like the one on your computer.
    
    &lt;img src="images/pythonanywhere_bash_console.png" alt="Pointing at Bash in the New Console section" /&gt;
    
    &gt; **Note** PythonAnywhere is based on Linux, so if you're on Windows, the console will look a little different from the one on your computer.
    
    Deploying a web app on PythonAnywhere involves pulling down your code from GitHub, and then configuring PythonAnywhere to recognise it and start serving it as a web application.  There are manual ways of doing it, but PythonAnywhere provides a helper tool that will do it all for you. Let's install it first:
    
    {% filename %}PythonAnywhere command-line{% endfilename %}
    

$ pip3.6 install --user pythonanywhere

    <br />That should print out some things like `Collecting pythonanywhere`, and eventually end with a line saying `Successfully installed (...) pythonanywhere- (...)`.
    
    Now we run the helper to automatically configure our app from GitHub. Type the following into the console on PythonAnywhere (don't forget to use your GitHub username in place of `&lt;your-github-username&gt;`):
    
    {% filename %}PythonAnywhere command-line{% endfilename %}
    

$ pa_autoconfigure_django.py https://github.com/<your-github-username>/my-first-blog.git

    <br />As you watch that running, you'll be able to see what it's doing:
    
    - Downloading your code from GitHub
    - Creating a virtualenv on PythonAnywhere, just like the one on your own PC
    - Updating your settings file with some deployment settings
    - Setting up a database on PythonAnywhere using the `manage.py migrate` command
    - Setting up your static files (we'll learn about these later)
    - And configuring PythonAnywhere to serve your web app via its API
    
    On PythonAnywhere all those steps are automated, but they're the same steps you would have to go through with any other server provider.  The main thing to notice right now is that your database on PythonAnywhere is actually totally separate from your database on your own PC—that means it can have different posts and admin accounts.
    
    As a result, just as we did on your own computer, we need to initialize the admin account with `createsuperuser`. PythonAnywhere has automatically activated your virtualenv for you, so all you need to do is run:
    
    {% filename %}PythonAnywhere command-line{% endfilename %}
    

(ola.pythonanywhere.com) $ python manage.py createsuperuser

    <br />Type in the details for your admin user.  Best to use the same ones as you're using on your own computer to avoid any confusion, unless you want to make the password on PythonAnywhere more secure.
    
    Now, if you like, you can also take a look at your code on PythonAnywhere using `ls`:
    
    {% filename %}PythonAnywhere command-line{% endfilename %}
    

(ola.pythonanywhere.com) $ ls blog db.sqlite3 manage.py mysite static (ola.pythonanywhere.com) $ ls blog/ **init**.py **pycache** admin.py forms.py migrations models.py static templates tests.py urls.py views.py ```

You can also go to the "Files" tab and navigate around using PythonAnywhere's built-in file browser.

## You are now live!

Your site should now be live on the public Internet! Click through to the PythonAnywhere "Web" tab to get a link to it. You can share this with anyone you want :)

## Debugging tips

If you see an error while running the `pa_autoconfigure_django.py` script, there are a couple of common causes:

- Forgetting to create your API token.
- Making a mistake in your GitHub URL

If you see an error when you try to visit your site, the first place to look for some debugging info is in your **error log**. You'll find a link to this on the PythonAnywhere [Web tab](https://www.pythonanywhere.com/web_app_setup/). See if there are any error messages in there; the most recent ones are at the bottom.

There are also some [general debugging tips on the PythonAnywhere help site](http://help.pythonanywhere.com/pages/DebuggingImportError).

And remember, your coach is here to help!

# Anda hidup!

The default page for your site should say "It worked!", just like it does on your local computer. Try adding `/admin/` to the end of the URL, and you'll be taken to the admin site. Log in with the username and password, and you'll see you can add new Posts on the server.

Once you have a few posts created, you can go back to your local setup (not PythonAnywhere). From here you should work on your local setup to make changes. This is a common workflow in web development – make changes locally, push those changes to GitHub, and pull your changes down to your live Web server. This allows you to work and experiment without breaking your live Web site. Pretty cool, huh?

Give yourself a *HUGE* pat on the back! Server deployments are one of the trickiest parts of web development and it often takes people several days before they get them working. But you've got your site live, on the real Internet, just like that!