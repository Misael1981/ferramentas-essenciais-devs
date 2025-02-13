# Guardando para depois

Imagine o seguinte cenário: Estamos desenvolvendo uma funcionalidade grande. Estamos no meio da implementação dela, ela ainda não está pronta. No entanto, precisamos interromper o trabalho nela para resolver um bug urgente ou mudar nosso foco para alguma correção pequena que seja urgente. Ou seja, queremos **interromper nosso trabalho**.

Como estamos no meio de uma funcionalidade, nosso código pode não estar compilando ou não estar em um estado que possamos criar um commit.

```
Lembre-se: sempre criamos commits quando o nosso projeto está em um estado funcional.
```

Se o código está compilando, se está, pelo menos, executando da forma esperada. Portanto, não vamos criar um commit com nosso código em um estado incompleto.

O que fazemos se nos deparamos com um cenário onde estamos no meio da implementação de uma funcionalidade, mas precisamos interromper aquele processo? Vamos simular o cenário da criação de uma nova funcionalidade.


## Criando uma nova funcionalidade

Primeiro, se estamos criando uma nova funcionalidade, vamos criar um novo branch. Portanto, escreveremos no terminal `git switch -c movendo-detalhes`.

Estamos em uma nova branch, podemos criar nossa nova funcionalidade. Abrimos então o arquivo `app.js` e queremos mover a chamada de função `exibirMensagemInicial()`, que está na linha 17 para a linha 5 para deixar a declaração das variáveis, depois a chamada de função e depois as declarações das funções.

Como podemos fazer isso? Vamos recortar a linha `exibirMensagemInicial()` e movê-la para cima. Só que fomos interrompidos: Um bug muito urgente surgiu, então precisamos trabalhar em outra coisa. O que acontece?

Não podemos criar um commit agora. Nosso projeto está em um estado inválido, removemos a chamada de função. Além disso, se executarmos um `git status`, temos modificações. Portanto, não podemos começar a trabalhar em outra coisa e ir para outro branch, porque o arquivo `app.js` está modificado. Precisamos desfazer essa alteração, mas guardar o que já alteramos.

## Guardando as alterações feitas

O que queremos fazer é **engavetar a alteração** que fizemos até agora, mas sem criar um commit. Queremos guardar ela para depois, queremos estocar ela para depois poder recuperar e continuar trabalhando. E é exatamente isso que o comando `git stash` faz. Ele guarda uma alteração para continuarmos trabalhando nela depois.

Se executarmos o comando `git stash`, ele vai pegar tudo o que está no nosso estado atual e estocar. Ele vai guardar para que possamos recuperá-lo depois. Portanto, ele vai guardar essa alteração que fizemos de recortar a linha `exibirMensagemInicial()` e desfazê-la.

Está guardada a alteração, mas a partir disso podemos voltar a trabalhar. O `git stash` nos diz que salvou o nosso estado na nossa gaveta, no nosso estoque ("Saved working directory and index state WIP on movendo-detalhes: linha do script"). Portanto, se voltarmos para o nosso arquivo, repare que ele está no seu estado válido, ele voltou lá com a nossa alteração.

Digamos que já cuidamos do bug e queremos voltar para esse branch de nova funcionalidade e retomar o trabalho. Como podemos recuperar o que está no nosso stash?

## Recuperando as alterações

Podemos executar o comando `git stash` pop. Esse pop, ele aplica o que tiver na nossa gaveta, no nosso estoque.

Após executarmos o `git stash` pop, a função não está mais na linha 12. Então, podemos continuar a implementação e trazê-la para cima. Agora temos o nosso estado finalizado.

```
Portanto, o git stash guarda uma alteração para que ela possa ser retomada depois.
```

Ele guarda um estado para que possamos retomá-lo depois. E normalmente é utilizado quando estamos no meio de uma alteração, queremos guardar algo rapidamente para corrigir um bug e trabalhar em outra coisa rapidamente e depois voltar a trabalhar nisso. Portanto, não podemos criar um commit.

Um detalhe: vamos criar esse stash novamente. Vamos limpar o nosso terminal e rodar o `git stash`. Se executarmos o comando `git stash list`, ele lista tudo o que está nesse nosso estoque. E repare que temos duas coisas no nosso stash, já tínhamos adicionado algo antes.

```
$ git stash list
stash@{0}: WIP on movendo-detalhes: c53eb16 Quebrando linha do script
stash@{1}: WIP on main: c53eb16 Quebrando linha do script
$
```

Digamos que não queremos mais nada na stash. Ou então, queremos fazer o `git stash pop` primeiro para recuperar essa nossa alteração. Feito o `git stash pop`, a nossa alteração voltou a aparecer e estamos com o nosso código no estado correto.

Mas repare que os nomes que esse nosso `git stash list` nos mostra não são muito descritivos. Ele coloca um work in progress (WIP) na branch que estávamos e o último commit antes de adicionarmos esse stash. Portanto, isso não é muito útil.

## Limpando as alterações guardadas

Vamos mostrar duas coisas. A primeira é que temos aqui no nosso `git stash list` algo anterior que fizemos alguns testes que não fazem parte dessa aula. Portanto, como podemos limpar a nossa stash, apagar tudo? Podemos fazer um `git stash clear`, limpamos a nossa stash. Portanto, se fizermos o `git stash list`, não tem mais nada lá.

## Acrescentando uma descrição à `stash`

Agora, se quisermos adicionar algo a nossa stash, mas com um nome mais descritivo, podemos fazer, ao invés de só `git stash`, vamos escrever `git stash push -m`. E aí, podemos adicionar uma mensagem qualquer, será `"Movendo chamada de função"`.

```
git stash push -m "Movendo chamada de função"
```

Quando voltamos lá para o nosso código, a alteração foi desfeita. E se fizermos um `git stash list`, temos um nome bem mais descritivo: `Movendo chamada de função`. Agora, sabemos o que isso significa. E podemos adicionar várias coisas na stash, como mostramos.

Por exemplo, temos algo na nossa stash e vamos adicionar algo mais. Como, por exemplo, vamos remover todas essas quebras de linhas no final. Fizemos várias quebra de linha, estamos no meio da implementação, tivemos que parar de novo. Usamos o comando `git stash` novamente.

Fizemos um `git stash`, adicionamos essa modificação lá na nossa lista de modificações que queremos rever depois. Se escrevermos `git stash list`, ele listará o `movendo chamada de função` e a última `stash` que não tem um nome específico. Portanto, ela aparece como `WIP on movento-detalhes: c53eb16 Quebrando linha do script`.

## Entendendo a pilha de modificações

Se fizermos um `git stash pop`, ele sempre vai aplicar a última alteração que adicionamos. Portanto, ele sempre pega esse de índice zero. Ele sempre vai empilhando modificações.

O que isso quer dizer? Imagina que essa nossa `stash` é uma gaveta e nessa gaveta estamos guardando pratos. Portanto, abrimos a gaveta, colocamos um prato. Na gaveta, adicionamos outro prato em cima. Se vamos pegar um prato, pegamos o prato que está em cima, certo? Portanto, é o último que adicionamos. Isso é o **conceito de pilha**.

Temos aqui na stash uma **pilha de modificações**. Portanto, quando fazemos pop, sempre aplicamos a última que adicionamos. Fizemos um `git stash pop`, temos a remoção das quebras de linha.

Portanto, se fizermos nosso `git stash list` de novo, só temos um e agora o nosso índice zero é aquela `movendo chamada da função`. Só que, imagina o seguinte cenário: Removemos todas as quebras de linha e vamos fazer o `git stash` de novo.

## Retomando alterações anteriores à versão mais recente

No nosso `git stash list`, temos lá a `movendo chamada da função`, que agora é o índice 1. E o novo índice zero é essa remoção de quebras de linha lá do final. Só que o que queremos voltar a trabalhar no que está guardado nesse índice 1.

```
$ git stash list
stash@{0}: WIP on movendo-detalhes: c53eb16 Quebrando linha do script
stash@{1}: On movendo-detalhes: Movendo chamada de função
$
```

Portanto, se fizermos o `git stash pop`, não vai funcionar. Vamos pegar a última alteração que não é o que queremos. Portanto, nesses cenários, quando queremos aplicar algo que está na `stash` anterior à versão mais recente, podemos fazer o `git stash apply` e o índice, no nosso caso, o índice 1, que é o `movendo chamada da função`.

Antes de executar, temos todas as quebras de linha no final do arquivo e a chamada da função está na linha 17. Vamos executar agora no nosso terminal, `git stash apply 1`. O que vai acontecer? Temos a nossa função sendo movida, mas todas as quebras de linha continuam lá no final.

Se quisermos, podemos aplicar mais de um item de stash. Portanto, podemos fazer aqui o nosso `git stash pop` sem problema. Só que aí vamos ter um conflito.

```
Podemos aplicar várias stashes se elas não estiverem no mesmo arquivo, se elas não forem conflitar com o que temos.
```

Temos modificações no arquivo que seriam sobrescritas. Portanto, não vamos aplicar essa `stash` mais. Portanto, se fizermos um `stash list`, ele adicionou um novo detalhe lá na nossa `stash`.

Para recapitular, se temos alguma alteração que precisamos adicionar ou salvar para depois, chamamos o comando `git stash`. O comando `git stash` vai adicionando mensagens no formato de pilha.

### Recapitulando:

- Se queremos pegar algo e aplicar uma alteração à última `stash` que adicionamos, usamos `git stash pop`;
- Se queremos aplicar alguma específica, usamos `git stash apply`;
- Se queremos adicionar algo na nossa `stash` com mensagem, usamos `git stash push`;
- Se queremos limpar a nossa `stash`, usamos `git stash clear`.

Vamos desfazer a alteração de mover. Não queremos mover essa mensagem, queremos fazê-la voltar para onde ela estava originalmente. Portanto, agora temos o nosso código no estado original, certo?

No entanto, se fizermos um `git status`, temos uma alteração ainda. Se fizermos um `git diff`, repare que essa alteração é invisível para nós.

Portanto, provavelmente, o nosso Visual Studio Code apagou alguns espaços que estavam em uma linha. Só que não queremos comitar isso, queremos desfazer essa alteração. Como podemos desfazer alterações que estão prontas para serem adicionadas a um commit? Através do `git`. É isso que vamos fazer no próximo vídeo.

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)