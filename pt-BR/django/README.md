# O que é Django?

Django (/ˈdʒæŋɡoʊ/ *jang-goh*) é um framework para aplicações web gratuito e de código aberto, escrito em Python. Um web framework é um conjunto de componentes que ajuda você a desenvolver sites de forma mais rápida e fácil.

Quando você está construindo um site, você sempre precisa de um conjunto similar de componentes: uma maneira de lidar com a autenticação do usuário (inscrever-se, realizar login, realizar logout), um painel de gerenciamento para o seu site, formulários, uma forma de upload de arquivos, etc.

Felizmente para você, outras pessoas perceberam muito tempo atrás que desenvolvedores web enfrentam problemas similares quando estão construindo um novo site, então elas se juntaram e criaram frameworks (sendo Django um deles) que te dão componentes já prontos para usar.

Frameworks existem para evitar que você tenha que reinventar a roda e para ajudar a aliviar parte do trabalho extra quando você está construindo um novo site.

## Por que você precisa de um framework?

Para entender para quê o Django de fato serve, precisamos olhar mais de perto os servidores. A primeira coisa é que o servidor precisa saber que você quer que ele te sirva uma página web.

Imagine uma caixa de correio (porta) que monitora cartas recebidas (requisição). Isso é feito por um servidor web. O servidor web lê a carta e então envia a resposta com uma página web. Mas, quando você quer enviar alguma coisa, você precisa ter um conteúdo. E o Django é aquilo que vai te ajudar a criar esse conteúdo.

## O que acontece quando alguém solicita um site do seu servidor?

Quando uma requisição chega a um servidor web, ela é passada para o Django, que tenta entender o que está sendo requisitado de fato. Ele pega um endereço de página web primeiro e tenta descobrir o que fazer. Essa parte é feita pelo **urlresolver** do Django (note que um endereço de website é chamado de uma URL - Uniform Resource Locator (Localizador de Recursos Uniforme, em tradução livre) -, então o nome *urlresolver* faz sentido). Ele não é muito inteligente - ele pega uma lista de padrões e tenta achar em qual deles a URL se encaixa. O Django checa os padrões de cima pra baixo, e se algum se encaixa, então o Django passa a requisição para a função associada a ele (que é chamada de *view*).

Imagine um carteiro com uma carta. Ela está andando pela rua e compara cada número de casa com o que está na carta. Se ele corresponder, ela coloca a carta lá. É assim que funciona o urlresolver!

Na função *view*, todas as partes interessantes acontecem: nós podemos olhar num banco de dados para procurar por alguma informação. Talvez o usuário tenha solicitado a mudança de algo nos dados? Como uma carta dizendo "Por favor mude a descrição do meu emprego." A *view* pode checar se você tem permissão para fazer isso, e então atualizar a descrição do emprego para você e enviar de volta a mensagem: "Pronto!" Então a *view* gera uma resposta e o Django pode enviá-la para o navegador web do usuário.

Claro, a descrição acima é muito simplificada, mas você não precisa saber detalhes técnicos ainda. Ter uma ideia geral já é suficiente.

Então em vez de mergulhar em muitos detalhes, nós simplesmente vamos começar criando algo com o Django e aprenderemos toda as partes importantes ao longo do caminho!