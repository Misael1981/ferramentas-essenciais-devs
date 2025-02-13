# Unindo as ramificações

Entendemos o problema que as **branches** (ramificações) vêm para resolver e como criar e alternar entre elas.

Note que fizemos o `push` de `nova-funcionalidade`, e no GitHub, ele exibe uma mensagem que indica que podemos criar uma **pull request** a partir da nossa nova branch.

O GitHub já identificou que existe uma nova branch e que, em algum momento, vamos querer **unir** a branch `nova-funcionalidade` com a `main`, que é a branch principal.

Basicamente, queremos unir o trabalho da branch `nova-funcionalidade` à branch `main`.

## Unindo as ramificações

Não precisamos utilizar o GitHub para esse objetivo, então vamos acessar o[ Visualizing Git](https://git-school.github.io/visualizing-git/). Em uma nova linha de trabalho, vamos adicionar dois commits com o comando `git commit`, criar a branch `nova-funcionalidade` com o comando `git checkout -b`, e adicionar mais dois commits a essa nova branch.

```
git commit
```
```
git checkout -b nova-funcionalidade
```

Em seguida, vamos fazer um `git switch` para a branch `master`:

```
git switch master
```

Queremos pegar tudo o que foi feito em `nova-funcionalidade` e trazer para o ramo principal `master`. Existe um comando que faz isso de forma bastante simples: o `git merge` ("mesclar" em inglês).

Você se lembra que quando fizemos o `pull` e o `push` com dois usuários diferentes, chegamos nesse cenário de **merge**, isto é, de **mescla de trabalhos**? Podemos fazer isso ativamente.

Podemos dizer que estamos na branch `main`, a branch principal, pegar tudo o que tem na branch `nova-funcionalidade` e mesclar com o que já temos na `main`.

Se fizermos o `merge` de `nova-funcionalidade`, ele vai levar a `main` para o mesmo local.

```
git merge nova-funcionalidade
```

## O que é fast forward?

Existem algumas formas do `merge` ser feito. Nesse caso, ele executou o que é chamado de **fast forward** (mover adiante). Até o ponto da `nova-funcionalidade` ser criada, a `master` estava no terceiro commit. A partir desse ponto, criamos uma nova branch, e a branch `nova-funcionalidade` evoluiu na mesma linha, sem que a `master` tivesse novos commits.

Então, na hora de fazer o `merge`, é muito simples: não precisamos criar nenhum novo commit; o Git entende tudo e só move as coisas. Se queremos unir as coisas, a partir de agora, a branch principal estará no mesmo ponto que a `nova-funcionalidade`. Isso é o chamado **fast forward**.

Vamos fazer isso no terminal do Visual Studio Code. Começaremos fazendo o `git switch` para a branch principal `main`, e faremos um `merge` com `nova-funcionalidade`.

```
git switch main
```
```
git merge nova-funcionalidade
```

Com isso, ele fará exatamente o que dissemos: o fast forward. Isso quer dizer que ele não cria um novo commit, nem faz nada de diferente; ele simplesmente diz que, a partir de agora, a branch `main` está no mesmo lugar que a branch `nova-funcionalidade`.

Se executarmos o comando `git log --graph`, notaremos que não precisamos de uma nova ramificação.

```
git log --graph
```

## Realizando alterações

Vamos voltar para a branch `nova-funcionalidade` e alterar algo no código.

```
git switch nova-funcionalidade
```

Podemos acessar o arquivo `README.md`, por exemplo, e fazer alguma alteração simples. Nesse caso, vamos adicionar uma quebra de linha entre cada uma das imagens a partir da linha 8.

```
## 🚀 Tecnologias
<div>
  <img src="https://img.shields.io/badge/HTML-239120?style=for-the-badge&logo=html5&logoColor=white">

  <img src="https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white">

  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">
</div>
```

Novamente, o comando `git status` vai nos mostrar que estamos na branch `nova-funcionalidade`:

```
git status
```

Vamos adicionar o arquivo `README.md` com o comando `git add` e, na sequência, adicionar um novo `commit` com a mensagem "Quebra de linha entre imagens". Podemos até fazer o `git push` de `nova-funcionalidade` para ir ao `repositório remoto`.

```
git add README.md
```
```
git commit -m "Quebra de linha entre imagens"
```
```
git push origin nova-funcionalidade
```

Feito isso, vamos voltar para a branch `main`.

```
git switch main
```

Imagine que outras funcionalidades estão acontecendo e outras pessoas estão desenvolvendo. Dito isso, vamos ao arquivo `style.css`, por exemplo, e mudaremos a propriedade `font-size` da tag `h1` de `50px` para `51px`, dentro do `@media screen` na linha 116.

```
@media screen and (max-width: 1250px) {

    h1 {
        font-size: 51px;
    }
}
```

Suponha que outras pessoas estão trabalhando e vão adicionar essa modificação na branch principal `main`. Pense que elas já fizeram o trabalho delas em outra branch e mesclaram com a `main`.

É isso que vai acontecer: vamos adicionar o arquivo de estilo com o comando `git add`, e a mensagem do `commit` será "Aumentando a fonte".

```
git add style.css
```
```
git commit -m "Aumentando a fonte"
```

Agora, se executarmos o comando `git log`, temos o commit "Aumentando a fonte". Se alternarmos para a branch `nova-funcionalidade` com `git switch`, e executarmos novamente `git log` para verificar o que temos em `nova-funcionalidade`, o commit "Aumentando a fonte" não fará parte dessa linha de trabalho.

## Fazendo um merge commit

Estamos no cenário onde as duas branches evoluíram de forma **independente**. Este é o cenário mais comum: trabalhamos na branch de alguma funcionalidade, e outras funcionalidades foram adicionadas à main, outras coisas foram feitas e já estão na linha de trabalho principal.

Sendo assim, quando fizermos um `git switch` para `main` e tentarmos fazer um` git merge` de `nova-funcionalidade`, o Git vai entender que esses dois trabalhos estão independentes e não evoluíram de forma igual. Dessa forma, ele irá unir criando um novo commit automaticamente. Ele criará um novo commit de merge, ou **merge commit**, como normalmente é chamado nas documentações.

```
git switch main
```
```
git merge nova-funcionalidade
```

Com esses comandos, será aberto um editor que permite a alteração da mensagem de commit de merge. No nosso caso, vamos deixar o commit como está.

Como o editor é o VI, basta executar `:x` para salvar e sair. Ao final, teremos um novo commit criado. Se executarmos o comando `git log --graph`, podemos observar o que acontece na `main`.

Primeiramente, temos o commit "Quebrando linha na imagem". Depois ele cria uma nova linha de trabalho, onde temos o commit "Aumentando a fonte". Na sequência, temos "Quebra de linha entre imagens", e por último o merge commit, isto é, o commit de **mescla**.

Reparem que bifurcamos o nosso trabalho e depois unimos. Lembrando que tudo isso é feito automaticamente pelo Git, mas é importante entender que existem essas duas estratégias: de **fast forward** e de criação do **merge commit**.

Dessa forma, conseguimos unir trabalho de duas branches diferentes para ter tudo na linha principal. Agora a nossa linha principal possui toda a `nova-funcionalidade`. O ramo `nova-funcionalidade` foi completo, unimos à linha principal, então agora podemos fazer deploy da nossa aplicação.

## Ajustes finais

Para finalizar, vamos executar o comando `git push origin main` para atualizar a `main` com todo o trabalho novo. Em seguida, removeremos a branch `nova-funcionalidade` com `git branch -d`, para manter o projeto limpo e sem excesso de branches.

```
git push origin main
```
```
git branch -d nova-funcionalidade
```

Ainda podemos remover a branch `nova-funcionalidade` do repositório remoto no GitHub. Para isso, executamos o seguinte comando:

```
git push origin :nova-funcionalidade
```

<div style="background-color: white; color: black;">
<hr>
<hr>

Os dois pontos (**:**) indicam que estamos removendo no repositório remoto

<hr>
<hr>
</div>

## Conclusão

Entendemos o motivo para ter branches, como lidar com branches e como unir o trabalho entre branches. Porém, em alguns cenários, não queremos criar o merge commit, mesmo que as duas linhas de trabalho tenham evoluído de forma individual. Vamos mostrar como **reescrever a história com Git** no próximo vídeo!

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)