# Deploy!

> **Nota** O capítulo seguinte pode ser às vezes um pouco difícil de terminar. Persista e termine-o; o deploy é uma parte importante do processo de desenvolvimento de um website. Colocar o seu site no ar é um pouco mais complicado, então esse capítulo está no meio do tutorial para que seu treinador possa lhe ajudar nessa tarefa. Isto significa que você ainda pode terminar o tutorial por conta própria se o tempo acabar.

Até agora, seu site só estava disponível no seu computador. Agora você aprenderá como implantá-lo (fazer o 'deploy')! O deploy é o processo de publicação do seu aplicativo na Internet de tal forma que as pessoas possam, finalmente, ver seu aplicativo. :)

Como você aprendeu, um website precisa estar em um servidor. Existem vários provedores de servidores na internet, nós vamos usar o [PythonAnywhere](https://www.pythonanywhere.com/). O PythonAnywhere é gratuito para pequenas aplicações que não recebem muitos visitantes, então definitivamente vai ser suficiente para você por enquanto.

O outro serviço externo que usaremos é [GitHub](https://www.github.com), que é um serviço de hospedagem de código. Existem outros, mas quase todos os programadores possuem uma conta no GitHub atualmente e agora você também!

Estes três lugares serão importantes para você. Seu computador local será o lugar onde você faz o desenvolvimento e testes. Quando você estiver satisfeito com as mudanças, você colocará uma cópia de seu programa no GitHub. Seu site estará na PythonAnywhere e você irá atualizá-lo ao subir uma nova cópia do seu código para o GitHub.

# Git

> **Nota** Se você já fez os passos de instalação, não precisa fazer isso novamente - você pode pular para a próxima seção e comece a criar seu repositório Git.

{% include "/deploy/install_git.md" %}

## Começando nosso repositório no Git

O Git controla as alterações em um determinado conjunto de arquivos no que chamamos de repositório de código (ou "repo"). Vamos criar um para o nosso projeto. Abra o seu console e execute esses comandos, no diretório `djangogirls`:

> **Nota**: Verifique o seu diretório atual com um `pwd` (OSX/Linux) ou o comando `cd` (Windows) antes de inicializar o repositório. Você deve estar na pasta `djangogirls`.

{% filename %}command-line{% endfilename %}

    $ git init
    Initialized empty Git repository in ~/djangogirls/.git/
    $ git config --global user.name "Seu Nome"
    $ git config --global user.email voce@exemplo.com
    

Só necessitamos de iniciar o repositório git apenas uma vez por projeto (e não será necessário colocar novamente o nome do utilizador e email).

O Git irá controlar as alterações em todos os arquivos e pastas neste diretório, mas existem alguns arquivos que queremos ignorar. Fazemos isso através da criação de um arquivo chamado `.gitignore` no diretório base. Abra seu editor e crie um novo arquivo com o seguinte conteúdo:

{% filename %}.gitignore{% endfilename %}

    *.pyc
    *~
    __pycache__
    myvenv
    db.sqlite3
    /static
    .DS_Store
    

E salve-o como `.gitignore` na pasta "djangogirls".

> **Nota** O ponto no início do nome do arquivo é importante! Se você estiver tendo alguma dificuldade em criá-lo (Macs, por exemplo, não gostam quando você tenta criar arquivos que começam com um ponto através do Finder), use a função "Salvar Como..." no seu editor; não tem como errar.
> 
> **Nota** Um dos arquivos especificados no seu `.gitignore` é o `db.sqlite3`. Este arquivo é o seu banco de dados local, onde todos os seus posts ficarão guardados. Nós não queremos que você adicione este arquivo ao repositório porque o seu site no PythonAnywhere vai utilizar um banco de dados diferente. Esse banco poderia ser SQLite, como na sua máquina de desenvolvimento, mas normalmente você irá utilizar um chamado MySQL, que consegue lidar com bem mais visitantes ao site do que o SQLite. De qualquer forma, ao ignorar o banco de dados SQLite para a cópia do GitHub, isso significa que todos os posts que você criou até agora irão estar disponíveis somente no seu ambiente local, e você terá que adicioná-los novamente em produção. Pense no seu banco de dados local como um bom parque de diversões onde você pode testar coisas diferentes e não ter medo de apagar os posts reais do seu blog.

É uma boa idéia usar um comando `git status` antes de `git add` ou sempre que você não tiver certeza do que mudou. Isso irá evitar quaisquer surpresas, como os arquivos errados serem adicionados ou commitados. O comando `git status` mostra informações sobre arquivos que não estão sendo controlados, arquivos que foram modificados ou preparados (staged), o status do branch, e muito mais. A saída do comando deve ser parecida com o seguinte:

{% filename %}linha de comando{% endfilename %}

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
    

E finalmente nós salvamos nossas alterações. Vá para o seu console e execute estes comandos:

{% filename %}linha de comando{% endfilename %}

    $ git add --all .
    $ git commit -m "My Django Girls app, first commit"
     [...]
     13 files changed, 200 insertions(+)
     create mode 100644 .gitignore
     [...]
     create mode 100644 mysite/wsgi.py
    

## Subindo o seu código para o GitHub

Vá em [GitHub.com](https://www.github.com) e crie uma conta nova, gratuita. (Se você já fez isso em preparação para o workshop, ótimo!)

Em seguida, crie um novo repositório chamado "my-first-blog". Deixe a caixa "Initialize with a README" desmarcada, deixe a opção do .gitignore em branco (nós já fizemos isso manualmente) e deixe a licença como "None".

![](images/new_github_repo.png)

> **Nota** O nome `my-first-blog` é importante - você poderia escolher qualquer outra coisa, mas ele vai aparecer várias vezes nas instruções abaixo, e você teria que substituir todas as vezes. É mais fácil simplesmente manter o nome `my-first-blog`.

Na próxima tela, você verá a URL pra clonar o seu repo. Escolha a versão "HTTPS", copie-a, e nós iremos colá-la no terminal em seguida:

![](images/github_get_repo_url_screenshot.png)

Agora nós precisamos conectar o repositório Git no seu computador com o que existe no GitHub.

Digite o seguinte no seu terminal (Substitua `<your-github-username>` pelo nome de usuário que você colocou quando criou a sua conta no GitHub, sem os sinais de menor e maior):

{% filename %}linha de comando{% endfilename %}

    $ git remote add origin https://github.com/<your-github-username>/my-first-blog.git
    $ git push -u origin master
    

Digite o seu nome e senha do GitHub e você deverá ver algo parecido com isso:

{% filename %}linha de comando{% endfilename %}

    Username for 'https://github.com': ola
    Password for 'https://ola@github.com':
    Counting objects: 6, done.
    Writing objects: 100% (6/6), 200 bytes | 0 bytes/s, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To https://github.com/ola/my-first-blog.git
    
     * [new branch]      master -> master
    Branch master set up to track remote branch master from origin.
    

<!--TODO: maybe do ssh keys installs in install party, and point ppl who dont have it to an extension -->

O seu código agora está no GitHub. Vai lá ver! Você perceberá que ele esta em ótima companhia - o [Django](https://github.com/django/django), o [Tutorial Django Girls](https://github.com/DjangoGirls/tutorial) e vários outros incríveis projetos open source também hospedam seu código no GitHub. :)

# Configurando o nosso blog no PythonAnywhere

## Crie uma conta no PythonAnywhere

> **Nota** Você talvez já tenha criado uma conta no PythonAnywhere durante os passos de instalação. Se tiver, não precisa criar outra.

{% include "/deploy/signup_pythonanywhere.md" %}

## Configurando nosso site no PythonAnywhere

Navegue para a [Dashboard do PythonAnywhere](https://www.pythonanywhere.com/) clicando no logo, e escolha a opção de iniciar um console "Bash" - isso é a versão do PythonAnywhere da linha de comando, igual à que tem no seu computador.

![Pointing at Bash in the New Console section](images/pythonanywhere_bash_console.png)

> **Nota** O PythonAnywhere é baseado em Linux, então se você estiver no Windows, o console terá uma cara um pouco diferente do que tem no seu computador.

Fazer o deploy de uma aplicação web no PythonAnywhere envolve baixar o seu código do GitHub e configurar o PythonAnywhere para reconhecê-lo e começar a servi-lo como uma aplicacão web. Existem formas manuais de fazer isso, mas o PythonAnywhere fornece uma ferramenta que vai fazer tudo pra você. Vamos instalar ela primeiro:

{% filename %}linha de comando do PythonAnywhere{% endfilename %}

    $ pip3.6 install --user pythonanywhere
    

Isso deve mostrar na tela coisas como `Collecting pythonanywhere`, e depois de algum tempo finalizar com uma linha dizendo `Successfully installed (...) pythonanywhere (...)`.

Agora nós vamos executar a ferramenta para configurar a nossa app do GitHub automaticamente. Digite os seguintes comandos no console do PythonAnywhere (não se esqueça de usar o seu nome de usuário no GitHub ao invés de `<your-github-username>`):

{% filename %}linha de comando do PythonAnywhere{% endfilename %}

    $ pa_autoconfigure_django.py https://github.com/<your-github-username>/my-first-blog.git
    

Ao assistir a execução da ferramenta, você poderá ver o que ela está fazendo:

- Baixando o seu código do GitHub
- Criando um virtualenv no PythonAnywhere, igual ao que existe no seu computador
- Atualizando o seu arquivo de configuração com algumas configurações sobre o deploy
- Criando um banco de dados no PythonAnywhere usando o comando `manage.py migrate`
- Criando os seus arquivos estáticos (nós aprenderemos sobre eles mais tarde)
- E configurando o PythonAnywhere para servir a sua web app através da sua API

No PythonAnywhere todos esses passos são automatizados, mas são os mesmos passos que você executaria ao utilizar qualquer outro provedor. O principal agora é reparar que o seu banco de dados no PythonAnywhere é na verdade completamente separado do banco de dados no seu computador — isso significa que eles têm posts e contas de admin completamente diferentes.

Por causa disso, da mesma forma que tivemos que fazer no nosso computador, nós precisamos criar a conta de admin com `createsuperuser`. O PythonAnywhere já ativou o seu virtualenv automaticamente pra você, então tudo o que precisa fazer é rodar:

{% filename %}linha de comando do PythonAnywhere{% endfilename %}

    (ola.pythonanywhere.com) $ python manage.py createsuperuser
    

Digite as informações sobre a sua conta de admin. É mais facil usar os mesmos que você usou no seu computador pra evitar qualquer confusão, a menos que você queira criar uma senha mais segura para a conta no PythonAnywhere.

Agora, se quiser, você pode dar uma olhada no seu código no PythonAnywhere usando `ls`:

{% filename %}linha de comando do PythonAnywhere{% endfilename %}

    (ola.pythonanywhere.com) $ ls
    blog  db.sqlite3  manage.py  mysite  static
    (ola.pythonanywhere.com) $ ls blog/
    __init__.py  __pycache__  admin.py  forms.py  migrations  models.py  static
    templates  tests.py  urls.py  views.py
    

Você também pode visitar a aba "Files" e dar uma olhada usando o gerenciador de arquivos do PythonAnywhere.

## Estamos no ar!

O seu site deve agora estar no ar, na internet! Clique na aba "Web" do PythonAnywhere para pegar o link dele. Você pode compartilhar esse link com quem quiser :)

> **Nota** Este é um tutorial para iniciantes, e ao fazer o deploy do site desta forma nós tomamos alguns atalhos que não são ideais do ponto de vista de segurança. Se e quando você decidir continuar trabalhando nesse projeto, ou começar um novo, você deveria revisar a [checklist de deploy do Django](https://docs.djangoproject.com/en/1.11/howto/deployment/checklist/) para pegar algumas dicas de como tornar o seu site seguro.

## Dicas de debugging

Se você vir um erro ao rodar o script `pa_autoconfigure_django.py`, aqui vão algumas causas comuns:

- Esquecer de criar um token de API do PythonAnywhere.
- Digitar a URL do seu GitHub incorretamente
- Se você vir um erro dizendo *"Could not find your settings.py"* (settings.py não encontrado), é provavelmente porque você não adicionou todos os seus arquivos ao Git, e/ou você não fez o push deles para o GitHub. Dê uma revisada na sessão sobre Git acima

Se você vir um erro ao visitar o seu site, o primeiro lugar para procurar informações sobre o erro é no **log de erros**. Você vai encontrar um link para o log na aba [Web](https://www.pythonanywhere.com/web_app_setup/) do PythonAnywhere. See if there are any error messages in there; the most recent ones are at the bottom.

There are also some [general debugging tips on the PythonAnywhere help site](http://help.pythonanywhere.com/pages/DebuggingImportError).

And remember, your coach is here to help!

# Check out your site!

The default page for your site should say "It worked!", just like it does on your local computer. Try adding `/admin/` to the end of the URL, and you'll be taken to the admin site. Log in with the username and password, and you'll see you can add new Posts on the server.

Once you have a few posts created, you can go back to your local setup (not PythonAnywhere). From here you should work on your local setup to make changes. This is a common workflow in web development – make changes locally, push those changes to GitHub, and pull your changes down to your live Web server. This allows you to work and experiment without breaking your live Web site. Pretty cool, huh?

Give yourself a *HUGE* pat on the back! Server deployments are one of the trickiest parts of web development and it often takes people several days before they get them working. But you've got your site live, on the real Internet, just like that!