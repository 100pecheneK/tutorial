Você pode [pular este capítulo](http://tutorial.djangogirls.org/en/installation/#install-python) se não estiver usando um Chromebook. Caso esteja, sua experiência de instalação será um pouco diferente. Você pode ignorar o restante das instruções de instalação.

### Cloud 9

Cloud 9 é uma ferramenta que te dá um editor de código e acesso a um computador conectado à Internet onde você pode instalar, escrever e executar software. Durante o tutorial, o Cloud 9 atuará como sua *máquina local*. Você ainda estará executando comandos em uma interface de terminal, como seus colegas de classe no OS X, Ubuntu ou Windows, mas seu terminal será conectado a um computador que está em algum outro lugar que o Cloud 9 configurou para você.

1. Instale o Cloud 9 através da [Chrome Web Store](https://chrome.google.com/webstore/detail/cloud9/nbdmccoknlfggadpfkmcpnamfnbkmkcp)
2. Acesse o site [c9.io](https://c9.io)
3. Cadastre-se para criar uma conta
4. Clique em *Create a New Workspace*
5. Dê o nome de *django-girls*
6. Selecione *Blank* (segundo a partir da direita na linha inferior com logotipo laranja)

Agora a sua tela deve exibir uma interface com uma barra lateral, uma grande janela principal com algum texto e uma pequena janela na parte inferior, semelhante a isto:

{% filename %}Cloud 9{% endfilename %}

    seunomedeusuário:~/workspace $
    

Esta área inferior é seu *terminal*, onde você vai dar as instruções para o computador que o Cloud 9 preparou para você. Você pode redimensionar a janela para torná-la um pouco maior.

### Ambiente Virtual

Um ambiente virtual (também chamado de virtualenv) é como se fosse uma caixa privada onde nós podemos colocar código de computador útil para um projeto que estejamos trabalhando. Nós os utilizamos para manter os vários pedaços de código que queremos para nossos vários projetos separados uns dos outros, para que as coisas não se misturem entre os projetos.

No seu terminal, na parte de baixo da interface do Cloud 9, execute o seguinte:

{% filename %}Cloud 9{% endfilename %}

    sudo apt update
    sudo apt install python3.6-venv
    

Se isso ainda não funcionar, peça ajuda ao seu treinador.

Em seguida, execute:

{% filename %}Cloud 9{% endfilename %}

    mkdir djangogirls
    cd djangogirls
    python3.6 -mvenv myvenv
    source myvenv/bin/activate
    pip install django~=1.11.0
    

(note que na última linha nós utilizamos um til seguido de um sinal de igual: ~=).

### Github

Crie uma conta no [Github](https://github.com).

### PythonAnywhere

O tutorial do Django Girls inclui uma seção do que chamamos de Deployment (algo como "implantação", em Português).

Esta parte é um pouco esquisita quando o tutorial é feito num Chromebook, dado que já estamos usando um computador que está na Internet (ao contrário de, digamos, um laptop). No entanto, ainda é útil, já que podemos pensar no nosso espaço de trabalho Cloud 9 como um lugar para o nosso trabalho "em andamento" e o Python Anywhere seria um lugar para mostrar nossas coisas à medida em que elas ficam mais completas.

Assim, se crie uma nova conta Python Anywhere em [www.pythonanywhere.com](https://www.pythonanywhere.com).