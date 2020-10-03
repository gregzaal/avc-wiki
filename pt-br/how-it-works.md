---
title: Como funciona
description: Explicação de alguns conceitos
published: true
date: 2020-10-03T21:30:26.977Z
tags: 
editor: markdown
---

# O Básico

Este bot tem a intenção de resolver o problema de ter um número imprevisível e variável de canais de voz ativos em seu servidor.

As vezes ninguém está jogando nada e você tem uma lista imensa de canais vazios. Então um jogo é atualizado e de repente todos os seus amigos ficam online novamente para jogar, mas aí você não tem canais de voz o suficiente para todos os esquadrões.

Este bot permite que seus usuários criem canais de voz na hora, ou seja, você pode ter ao mesmo tempo uma lista limpa de canais quando ninguém está online, e centenas de canais quando as coisas ficarem bem ocupadas.

## Canais Primários e Secundários

Para atingir isso, você cria canais "Primários", os quais agem como se fossem botões para criar novos canais para seus usuários. Quando alguém clica no canal Primário para entrar nele, o bot irá criar um novo canal "Secundário" para ele e move-lo para dentro do novo canal.

Canais Secundários são nomeados dinamicamente baseado em diversos fatores, como que jogo os membros do canal estão jogando, o nome do criador, etc. [Uma lista completa dessas opções está disponível aqui](/commands/template).

Você também pode ter quantos canais Primários quiser, cada um com seu próprio modelo de nome, permissões, limites, taxa de transmissão padrão, etc - e cada canal Primário pode ser utilizado para criar quantos canais Secundários quiser, os quais serão apagados automaticamente quando não estiverem mais sendo utilizados.

Utilize [vc/create](/commands/create) para criar um novo canal Primário, e [vc/template](/commands/template) para definir o modelo do nome para os canais Secundários nos quais os usuários aparecerão.

Uma vez que todos deixarem um canal Secundário, o bot irá apagar ele.

# O Criador

Quando um novo canal Secundário é criado, o usuário que fez isso fica atribuído como "criador" do canal.

Existem alguns comando como  [vc/private](/commands/private) que apenas o criador tem permissão para utilizar.

Se o criador original deixar o canal em algum momento, a pessoa que estiver no topo do canal (primeiro em ordem alfabética) é atribuído como o novo criador, ganhando acesso a estes comandos restritos.

# Como canais Seundários funcionam

## Criação de Canal

A maneira principal de criar canais é quando o bot detecta alguém entrando no canal Primário.

Porém existem inúmeras maneiras pelas quais as pessoas podem abusar do bot spamando a criação de canais, o que poderia resultar no banimento do bot do Discord por abusar de sua API.

Para impedir isso, existe um sistema de detecção de abuso que impede os usuários de criarem canais muito rapidamente:

1. O bot cria uma trava por alguns segundos no usuários para que então ele seja ignorado caso ele realmente esteja spamando cliques no canal Primário.
2. Se o usuário conseguir criar muitos canais em um pequeno período de tempo, ele receberá um bloqueio de tempo ainda maior, receberá uma mensagem de aviso, e registrará este evento se o  [registro](/commands/logging) estiver ativado.

Existe também um ciclo em segundo plano que checa por ocupantes de qualquer canal Primário que estiver lá por alguns segundos pelo menos, e então irá criar um canal se não existir nenhum bloqueio para ele.

> O Discord tem um limite interno de 50 canais por categoria, isso não tem nenhuma relação com o bot. Se você precisar de mais de 50 canais, precisará apenas criar mais canais Primários em categorias diferentes.
{.is-info}


## Renomeação de canais

A renomeação dos canais trabalha baseado em um ciclo em segundo plano que checa a cada poucos minutos* se um canal precisa ser renomeado.

A cada ciclo de iteração, é calculado qual deveria ser o nome do canal naquele momento baseado no seu [modelo](/commands/template) e nas diversas informação referentes aos membros do canal. Se forem encontradas diferenças neste cálculo em comparação com o nome atual, então ele renomeará o canal.

> *Nota: A taxa limite do Discord impede que o bot renomeie um canal mais do que duas vezes a cada 10 minutos. Para garantir um bom funcionamento enquanto implementamos um sistema de renomeação baseado em eventos mais imediato, ele poderá apenas renomear canais uma vez a cada 5 minutos.
{.is-info}

> Se você estiver hospedando o bot por conta própria e modificar o código para aprimorar o intervalo de renomeação, você estará arriscando piorar seu desempenho ainda mais e até mesmo ter seu bot banido do Discord.
{.is-warning}

## Exclusão de Canais

Quando o último usuário em um canal Secundário se desconectar dele, o bot irá automáticamente apagar este canal.

Se o canal tiver sido criado muito recentemente, não será apagado imediatamente, mas ao invés disso, será apagado um minuto ou dois depois do bot perceber que ele ainda não está sendo utilizado.

Você pode tranquilamente excluir canais Secundários manualmente também, porém isso pode bagunçar um pouco a numeração e posicionamento dos outros canais Secundários. Levará alguns minutos para que o bot perceba que o canal não existe mais e então remova-o de sua memória.