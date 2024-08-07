---
layout: posts
title: Note taking + Obsidian
parent: home
author: Pedro Arruda
---
Muitas vezes durante o inicio de minha carreira me deparei com várias situações onde várias coisas  foram faladas para mim, mostradas e mais do que isso ENSINADAS. No tempo de um ou dois dias depois eu simplesmente esquecia metade, e me vi no cenário de ter que voltar para essas memórias de forma que relembrasse o que tinha feito, mas isso nunca era fácil. Depois de algumas anotações atabalhoadas cheguei no meu sistema de anotações. Sei que ele não resolve todos os problemas, mas com certeza pode ser o ponto de partida para que sejam feitas coisas incríveis na sua carreira.

Nos próximos tópicos irei explorar alguns temas importantes no que tangem organização no geral, ferramentas para usar no dia-a-dia e formas de automatizar as coisas para um melhor desempenho no seu dia.

## Ferramentas

### Markdown Language
Para começar eu gosto bastante de usar linguagem de [Markdown](https://www.markdownguide.org/) para minhas anotações, é uma relação de "ganha ganha", onde você tem um método rápido para digitar e ainda consegue aprender para fazer documentações no geral.

### Obsidian
Outra coisa que gosto de fazer é usar o [Obsidian](https://obsidian.md/) para organizar esses arquivos. No artigo iremos explorar várias features da ferramenta, mas toda a parte de organização pode ser feita na ferramenta de sua escolha, sendo ela o [Vs Code](https://code.visualstudio.com/) ou o [Notion](https://www.notion.so/pt).

### Excalidraw
Caso precise desenhar coisas simples, como caixas se conectando ou HLAs (High Level Architecture), eu recomendo o [Excalidraw](https://excalidraw.com/) por ser mais bonito e simples do que o [draw.io](http://draw.io).

## Organização
Eu organizei minhas anotações na seguinte estrutura de pastas:
```
|Vault
├───Assets
│   ├───Documentos
│   ├───Dotfiles
│   ├───Excalidraw
│   ├───Images
│   └───Templates
├───Common
├───Corporativo
│   ├───Eventos
│   └───Squad
│       ├───Cerimonias
│       ├───Débitos Técnicos
│       ├───Monitoramento
│       ├───Projetos
│       ├───Releases
│       ├───Rotinas
│       ├───Spikes
│       └───Sustentação
└───Pessoal
    ├───Diário
    ├───Documentos
    ├───PDI
    └───Tech
```

>Não se preocupe. Tudo estará no [github](https://github.com/pedroarrudant/NoteTakingTemplate)

Algumas notas sobre a organização de pastas:
- A pasta *assets* será responsável por guardar todas as coisas que não serão criadas por você + templates;
- Na pasta *corporativo* ficarão todas as coisas da sua organização. Eu criei alguns itens como *eventos* e dentro da *squad* estão coisas mais específicas do time em que vc estiver trabalhando;
- Na pasta *common* ficarão coisas que pertencem aos dois mundos, como *emails* e *chamados*;
- Dentro de *pessoal* estarão todas as coisas das quais você será o responsável exclusivo;

>Se vc for usar outro aplicativo para anotações sinta-se a vontade para terminar o artigo por aqui.

## Obsidian
Vamos agora a algumas configurações específicas do Obsidian. Ao abrir ele pela primeira vez você se deparará com a seguinte tela:

![notetaking1.png]({{ site.baseurl }}/images/notetaking1.png)

Daqui em diante você pode colar os arquivos que estão no Github direto no diretório onde criou o seu Vault. Após isso, vamos colocar os templates para funcionar.

Em configurações selecione *Daily Notes* e coloque essas configurações:

Date Format:
```
[Anotações de] DD [de] MMM [de] YYYY
```

New file location:
```
Pessoal/Diário
```

Template file location:
```
Assets/Templates/Diário Template
```

Ficando assim:

![notetaking2.png]({{ site.baseurl }}/images/notetaking2.png)

Depois disso vá em *templates* e coloque as seguintes configurações:

Date format:
```
DD/MM/YYYY
```

Template folder location:
```
Assets/Templates
```

Ficando assim:

![notetaking3.png]({{ site.baseurl }}/images/notetaking3.png)

>Para usar um template dentro de uma nota, basta digitar *ctrl+p* e buscar a opção *inserir modelo*

## Plugins
Uma vantagem do Obsidian é a possibilidade de usar plugins para personalizar a sua experiência. No meu caso coloco algumas recomendações para o dia-a-dia comum:

Plugins da comunidade:
- [Reminder](https://github.com/uphy/obsidian-reminder) => Coloca lembretes em notas e te avisa com notificações em tela.
- [Excalidraw](https://github.com/zsviczian/obsidian-excalidraw-plugin) => Possibilita a criação de diagramas do Excalidraw sem precisar sair do Obsidian.
- [Calendar](https://github.com/liamcain/obsidian-calendar-plugin) => Adiciona um calendário no menu lateral do Obsidian para ter um tracking melhor das suas notas.
- [Emoji Shortcodes](https://github.com/phibr0/obsidian-emoji-shortcodes) => Como o nome diz possibilita a inserção de emojis via short code, como um 😄.

Core plugins:
- [Slides](https://help.obsidian.md/Plugins/Slides) => Habilita a criação de slides, estilo PowerPoint dentro do próprio Obsidian.
- [Sync](https://obsidian.md/sync) => O maior downside desse aqui é que ele é pago, mas possibilita muita flexibilidade para levar suas notas de um lugar para o outro.

>Caso não deseje pagar, você pode usar o [SyncThing](https://syncthing.net/).

Com todo  esse toolkit você nunca mais será pego desprevenido novamente!
Até mais!