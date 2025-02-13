# Ramificando o trabalho

Já entendemos o problema de realizar commits no mesmo local. Se todos realizarem `push` para os commits no mesmo local, teremos problemas ao colaborar.

Por isso, queremos te mostrar um site interessante chamado [Visualizing Git](https://git-school.github.io/visualizing-git/) (Visualizando Git). Nesse site, como o próprio nome diz, conseguimos visualizar como o Git funciona.

## Conhecendo o Visualizing Git

Por padrão, temos um único commit chamado `first commit`. Repare que temos um `master`, que no nosso caso, chamamos de `main`; e o `HEAD` é exatamente o último commit, que está no mesmo lugar.

No Visualizing Git, podemos executar o comando abaixo:

```
git commit -m "Teste"
```

Com isso, será adicionado um novo commit chamado "Teste". Podemos adicionar alguns commits, inclusive sem mensagem, apenas utilizando o comando `git commit`.

```
git commit
```

## Ramificando o trabalho

Temos nosso projeto desenvolvido e queremos começar a trabalhar em outra funcionalidade. Para isso, podemos criar uma **ramificação**, um galho na nossa árvore. Isso é o que chamamos de **branch**.

Se digitarmos o comando `git branch` no Visualizing Git, ele vai mostrar quais são as branches, isto é, quais são as ramificações existentes no nosso trabalho.

```
git branch
```

Por padrão, só temos a branch `main`, que o Visualizing Git chama de `master`. Antigamente, a branch principal se chamava `master`, mas essa nomenclatura padrão foi alterada para `main`. Sendo assim, hoje em dia, a branch padrão se chama `main`.

Se quisermos renomear a `master` para `main`, usamos o comando abaixo:

```
git branch -m master main
```

Se quisermos **remover** alguma branch, caso tenhamos uma lista de várias branches, podemos usar o comando `git branch -d` seguido do nome da branch que queremos remover. Por exemplo:

```
git branch -d master
```

## Criando uma nova ramificação

Em vez de renomear ou remover, queremos **criar uma nova ramificação**, ou seja, uma nova linha de trabalho, para que possamos criar essa nossa nova funcionalidade.

Vamos chamar essa nova linha de trabalho de `gramatica`. Para isso, basta digitar o comando `git branch` seguido do nome do ramo que queremos trabalhar. Esse ramo, ou seja, essa branch será criada sem espaço, maiúsculas e acentos, porque é uma identificação de algo.

```
git branch gramatica
```

Agora, se fizermos um novo `commit`, ele será feito na branch `master`, onde estamos no momento, ou na branch `gramatica`? Vamos fazer esse `commit` com a mensagem "Onde estou".

```
git commit -m "Onde estou"
```

Perceba que foi feito o `commit` na branch `master`. Não fizemos na branch `gramatica`, porque o local de trabalho do projeto está na branch `master`. Se quisermos modificar a branch atual para outra, precisamos de algum comando, e existem alguns para isso.

## Alternando entre branches

Primeiro, vamos mostrar um comando antigo, depois falamos sobre o mais novo. Inicialmente, digitaremos um comando chamado `git checkout`. O comando `git checkout` faz um monte de coisa. Nesse caso, se passarmos o nome de uma branch, ele vai alterar onde estamos.

```
git checkout gramatica
```

Ao fazer isso, repare que o `HEAD` muda de lugar e vai para baixo da branch `gramatica`. Isso indica que agora estamos na branch `gramatica`, trabalhando a partir desse commit.

Sendo assim, se fizermos um `commit` com a mensagem "Agora na branch certa", por exemplo, visualizaremos uma ramificação no nosso trabalho.

```
git commit -m "Agora na branch certa"
```

Agora, há duas linhas de trabalho diferentes e **independentes**. Portanto, podemos executar o comando `branch -d master` para remover a branch `master` se quisermos.

```
git branch -d master
```

Feito isso, a branch `master` não existirá mais. Podemos fazer o `git checkout` para a branch `main` e adicionar alguns commits com o comando `git commit` sem mensagem.

```
git checkout main
```
```
git commit
```

Repare que temos, novamente, duas linhas de trabalho diferentes. É isso que o comando `git log --graph` mostrou para nós anteriormente: a **ramificação** no nosso trabalho. Depois, podemos mesclar isso.

## Criando ramificações no projeto

Agora que entendemos como funciona o processo no Visualizing Git, vamos fazer o mesmo no projeto real. Com o VS Code aberto, vamos acessar o terminal.

Se digitarmos o comando `git branch`, ele vai retornar que só temos a branch m`ain`:

```
git branch
```

Poderíamos usar o comando `git branch` seguido de uma nova branch que quisermos, referente a qualquer nova funcionalidade. Porém, se quisermos criar uma branch e já mover para ela, podemos usar dois comandos. O primeiro é o `git checkout -b` seguido do nome da nova branch `nova-funcionalidade`.

```
git checkout -b nova-funcionalidade
```

Além desse comando mais antigo, podemos utilizar o `git switch`, também seguido do nome da branch desejada. "Switch" significa **trocar**, ou seja, esse comando basicamente alterna entre branches.

Porém, se digitarmos simplesmente `git switch nova-funcionalidade`, será informado que essa branch não existe. Então, vamos executar `git switch -c nova-funcionalidade` (`-c` referente a "create").

```
git switch -c nova-funcionalidade
```

Agora temos uma nova ramificação do nosso trabalho. Podemos fechar o terminal e adicionar alguma modificação no código do arquivo `index.html`. Por exemplo: vamos adicionar uma quebra de linha na imagem (`<img>`) da linha 32, logo antes dos atributos `alt` e `class`.

```
<img src="./img/ia.png" 
     alt="Uma pessoa olhando para a esquerda"
     class="container__imagem-pessoa" />
```

Essa é a nova funcionalidade que desenvolvemos, com alterações no código. Agora vamos abrir o terminal novamente e executar o comando `git status`.

```
git status
```

Com isso, ele mostra que estamos na branch `nova-funcionalidade`. Vamos adicionar o arquivo `index.html` com o comando `git add`, e depois adicionar um `commit` com a mensagem "Quebrando linha na imagem".

```
git add index.html
```
```
git commit -m "Quebrando linha na imagem"
```

Se fizermos um `git log` agora, temos um retorno um pouco diferente.

```
git log
```

Temos o commit anterior, do merge na branch `main`; temos o `origin/main`; agora o último commit é onde está o `HEAD` atual; e temos a branch `nova-funcionalidade`. Repare que a branch `nova-funcionalidade` ainda não foi para o `origin`, pois não enviamos.

Porém, antes de enviar, vamos fazer um `switch` e voltar para branch `main`:

```
git switch main
```

A funcionalidade que estamos desenvolvendo está nessa branch, isto é, o commit existe nela, não descartamos ele. Porém, voltamos a trabalhar na linha de trabalho principal `main`.

Portanto, se fechamos o terminal e acessamos a tag de imagem que alteramos no código, ela estará sem quebra de linha. Se voltarmos para o terminal e executarmos `git log`, o `head` terá voltado para `main`. Então, o `HEAD` é onde estamos no momento, é o commit atual onde o nosso projeto está.

Dito isso, vamos fazer um `git switch` para nova-funcionalidade:

```
git switch nova-funcionalidade
```

Mais uma vez, o código aparecerá atualizado com a quebra de linha que adicionamos. Assim, podemos fazer o `git push` para o repositório remoto, ou seja, `origin` da branch `nova-funcionalidade`.

```
git push origin nova-funcionalidade
```

Após teclar "Enter", a nova ramificação será criada e teremos uma nova linha de trabalho.

## Conclusão

Repare que trabalhar com branches é relativamente simples. A parte complexa é entender por que fazer isso, mas já explicamos no vídeo anterior. O que ainda pode ser complexo é **unir os trabalhos**.

Na linha principal, alguém pode ter adicionado novos commits e novas funcionalidades. Enquanto isso, temos a linha de trabalho `nova-funcionalidade`, onde adicionamos as quebras de linha. Como podemos unir esses dois mundos? É sobre isso que vamos conversar no próximo vídeo!

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)