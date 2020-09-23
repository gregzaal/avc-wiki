---
title: Comandos
description: Uma lista de todos os comandos do bot com links para uma documentação mais datalhada para cada um.
published: true
date: 2020-09-23T02:31:05.221Z
tags: 
editor: markdown
---

O prefixo padrão para todos os comandos é `vc/`, e.g. `vc/create`. Você também pode @mencionar o bot, como `@Auto Voice Channels create`.

Se você mudar o prefixo e esquecer como ele é, a única maneira de utilizar o bot novamente seria @mencionar ele com o comando de prefixo, e.g. `@Auto Voice Channels prefix vc/`.

Para obter mais informações sobre um comando específico, digite `vc/help nomedocomando`.


# Comandos comuns

Aqui estão os comandos mais comumente usados. Mais abaixo nesta página também temos uma lista completa em ordem alfabética de  [todos os comandos](/commands#list-of-all-commands).


### [vc/create](/commands/create)
Cria um novo canal de voz [primário](/how-it-works#primary-and-secondary-channels).

Canais de voz primários são canais como "botões" nos quais clicamos para criar novos canais secundários. O nome padrão do canal é "➕ New Session", mas você pode renomea-lo como quiser clicando com o botão direito nele e editando-o como de costume. O Discord suporta [emojis padrões](http://www.unicode.org/emoji/charts/full-emoji-list.html) em nomes de canais de voz, mas não aceita emojis customizados ou especificos do Discord.

O canal primário será criado em algum lugar próximo do topo do seu servidor, você pode move-lo para baixo para onde você quiser. Apenas **tenha certeza de que o bot tem permissão para criar e editar canais de voz lá.**


### [vc/template](/commands/template)
Canais secundários que são criados pelo canal primário serão nomeados conforme o seu modelo. Este comando permite que você mude o modelo. O modelo padrão é `## [@@game_name@@]`.

Veja aqui uma [lista completa de todas as variáveis de modelos disponíveis](/commands/template) que você pode utilizar para personalizar os nomes de seu canais, incluindo exemplos.


### [vc/private](/commands/private)
Deixa o seu canal de voz privado, evitando que qualquer um se junte a ele diretamente.

Cria um canal "⇩ Join (usuário)" acima de você para que as pessoas peçam para se juntar a você. Quando alguém entra neste canal, o bot irá te enviar uma mensagem pedindo que você aprove/negue/bloqueie a solicitação.


### [vc/lock](/commands/limit) ou [vc/limit](/commands/limit)
Bloqueia ou define um limite de usuários para seu canal impedindo mais pessoas de se juntarem a ele.

Estes dois na verdade são o mesmo comando e são duplicados por comodidade. Se você não adicionar um número no final (e.g. executando `vc/lock`), ele irá definir o limite de usuários para o número atual de usuários no canal. Se você adicionar um número (e.g. `vc/limit 5`), ele irá definir o limite para este número.

Se você deseja fazer isso definitivamente para todos os canais secundários criados pelo mesmo canal primário, você precisa apenas editar o limite de usuários do canal primário, ou utilizar [vc/defaultlimit](/commands/defaultlimit).


### [vc/ping](/commands/ping)
Um comando de teste rápido para checar se o bot está funcionando, e exibe seu tempo de resposta. Normalmente tempos de resposta altos (>2s) podem indicar problemas de performance.

Também exibe a região do servidor e a região em que o bot está hospedado. Quanto mais próximas essas regiões estiverem, melhor deverá ser o tempo de resposta.


# Lista de Todos os Comandos

Abaixo segue uma lista de todos os comandos separados por Comandos de Configuração e Comandos de Utilização.

Se você estiver utilizando o bot público e gratuito, "💳" indica que este comando pode ser utilizado apenas por [Patreons](https://patreon.com/pixaal) Ouro. Se você estiver hospedando seu próprio bot, todos os comandos podem ser utilizados.

## Comandos de Configuração

Comandos que você provavelmente utilizará poucas vezes quando estiver configurando seus canais.

Todos estes comandos podem ser utilizados apenas pela equipe do servidor (pessoas com as permisões de cargo *Gerenciar canais* and *Gerencias cargos*).

* [alias](/commands/alias) - Define um apelido para o nome de um jogo.
* [aliases](/commands/aliases) - Lista todos os apelidos de nomes de jogo que você definiu.
* [asip](/commands/asip) - Assume que jogadores offline/sem-status estão jogando o mesmo jogo.
* [create](/commands/create) - Cria um novo canal primário.
* [dcnf](/commands/dcnf) - Desabilita o erro "command not found" (comando não encontrado).
* [defaultlimit](/commands/defaultlimit) - Define um limite padrão de usuários para os canais secundários de um  canal primário.
* [disable](/commands/disable) - Desativa o bot.
* [ecnf](/commands/ecnf) - Habilita o erro "command not found" (comando não encontrado).
* [enable](/commands/enable) - Ativa o bot (ativado por padrão).
* [general](/commands/general)💳 - Define a palavra que será utilizada nos nomes de canais ao invés de "General".
* [inheritpermissions](/commands/inheritpermissions) - Define de onde os canais secundários herdarão suas permisões (por padrão herdam do canal primário).
* [listroles](/commands/listroles) - Lista todos os cargos em seu servidor e seus IDs.
* [logging](/commands/logging)💳 - Configura o canal de registro de atividades.
* [prefix](/commands/prefix) - Define o prefixo do bot no seu servidor (o padrão é `vc/`).
* [removealias](/commands/removealias) - Remove todos os apelidos de nomes de jogo.
* [restrict](/commands/restrict)💳 - Impede que usuários sem determinado cargo utilizem determinados comandos.
* [restrictions](/commands/restrictions)💳 - Lista todas as restrições de comandos que você definiu.
* [servercheck](/commands/servercheck) - Exibe informações sobre seu servidor e os canais que o bot conhece.
* [showtextchannelsto](/commands/showtextchannelsto)💳 - Define o cargo para o qual os canais de texto criados pelo bot serão visíveis.
* [template](/commands/template) - Define o modelo do nome para os canais secundários.
* [textchannelname](/commands/textchannelname)💳 - Define o nome para os canais de texto criados pelo bot.
* [textchannels](/commands/textchannels)💳 - Instrui o bot a criar um canal de texto privado para todo canal de voz secundário.
* [toggleposition](/commands/toggleposition) - Define onde os canais secundários serão criados, acima ou abaixo de seus primários.
* [uniquenames](/commands/uniquenames)💳 - Obriga nomes definidos com [vc/name](/commands/name) a serem únicos.

## Comandos de Utilização

Comandos que você provavelmente utilizará com frequência para contolar e modificar os canais em que você está.

A maior parte destes comandos podem ser utilizados por qualquer um no seu servidor. Use o comando [restrict](/commands/restrict) para evitar isso se você não quiser que aconteça.

Comandos que modificam um canal de voz normalmente exigem que você seja o criador do canal, ou um administrador.

* [allyourbase](/commands/allyourbase) - (apenas administradores) Assume a propriedade do canal no qual você está dentro.
* [bitrate](/commands/bitrate)💳 - Define uma taxa de bits personalizada para você.
* [channelinfo](/commands/channelinfo) - Um comando de depuração para exibir informações sobre a taxa de bits e o jogo dos usuários em seu canal
* [help](/commands/help) - Exibe informações sobre como utilizar o bot.
* [invite](/commands/invite) - Fornece um link para convidar o bot para um novo servidor.
* [kick](/commands/kick) - Inicia uma votação para expulsar alguém de seu canal.
* [limit](/commands/limit)/[lock](/commands/limit) - Define o limite de usuários para seu canal.
* [name](/commands/name)💳 - Renomeia o seu canal de voz (suporta todas as opções de modelos).
* [nick](/commands/nick)💳 - Altera como o seu nome é exibido no nome do canal.
* [patreon](/commands/patreon) - Fornece um link para a página do Patreons dos desenvolvedores do bot.
* [ping](/commands/ping) - Testa o tempo de resposta do bot.
* [private](/commands/private) - Evita que outros usuários se juntem a você diretamente.
* [public](/commands/public) - Torna o seu canal público novamente depois de ter definido como privado.
* [rename](/commands/rename)💳 - (apenas administradores) Semelhante à [vc/name](/commands/name), mas você pode renomear o canal de outras pessoas.
* [source](/commands/source) - Fornece um link para o código fonte do bot.
* [transfer](/commands/transfer) - Transfere a propriedade de seu canal para outra pessoa.
* [unlimit](/commands/unlimit)/[unlock](/commands/unlimit) - Remove o limite de usuários de seu canal.
