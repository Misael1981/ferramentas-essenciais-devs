# Próximas alterações `git diff`

Já nos familiarizamos um pouco mais com o log e aprendemos sobre o `git show`. Agora, queremos levantar o seguinte cenário.

## Explorando outros comandos

Primeiro, vamos abrir o terminal e digitar `git status`.

```
git status
```

Obtemos como retorno:

```
On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean
```

Este comando nos indica em qual ramificação (branch) estamos - abordaremos isso em breve - e se há algo para adicionar e realizar um commit. Vamos fechar o terminal. No arquivo `index.html`, renomeamos "JS Game" para "Jogo em JS".

```
<!-- código omitido -->

    <link rel="stylesheet" href="style.css">
    <title>Jogo em JS</title>
</head>

<!-- código omitido -->
```

Salvamos este arquivo.

Ao retornar ao **terminal**, digitamos `git status` novamente.

```
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
    (use "git add <file>..." to update what will be committed)
    (use "git restore <file>..." to discard changes in working directory)
        modified: index.html

no changes added to commit (use "git add" and/or "git commit -a")
```

Neste `git status`, encontramos "Changes not staged for commit", ou seja, modificações que ainda não foram adicionadas para realizar o commit. Aqui há apenas uma modificação, fácil de visualizar.

Em um contexto mais prático, como trabalhar em equipe em um projeto de grande escala, é comum realizar alterações em vários arquivos. Ao concluir as modificações no último arquivo, é natural desejar revisar todas as mudanças antes de confirmar o commit, garantindo assim sua correção. Essencialmente, o objetivo é visualizar todas as alterações antes de prosseguir com o commit.

## Usando o `git diff`

Para isso, é possível utilizar o comando `git diff`, que já é familiar.

```
git diff
```

Ao executar `git diff`, são exibidas as diferenças entre **dois estados**.

```
O retorno abaixo foi parcialmente transcrito.
```
```
diff --git a/index.html b/index.html
index 7eb8bcc..c5d087d 100644
a/index.html
+++ b/index.html
@@ -10,7 +10,7 @@
    <link href="https://fonts.googleapis.com/cssfamily=Chakra+Petch:wght@700&family=…splay=swap"
        rel="stylesheet">
    <link rel="stylesheet" href="style.css">
-  <title>JS Game</title>
+  <title>Jogo em JS</title>
```

Por padrão, os estados comparados são as modificações que foram realizadas e ainda não foram adicionadas ao commit, e o último commit realizado, também conhecido como head. Esse comando exibe a diferença entre o último commit e o que temos modificado no arquivo. No nosso caso, é apenas a alteração do title

Portanto, com o `git diff` conseguimos visualizar a diferença entre os dois estados.

Vamos voltar para aquela documentação digitando `git diff --help`.

```
git diff --help
```
```
Obtemos como retorno:
```
```
NAME
    git-diff - Show changes between commits, commit and working tree, etc

SYNOPSIS
    git diff [<options>] [<commit>] [--] [<path>...]
    git diff [<options>] --cached [<commit>] [--] [<path>...]
    git diff [<options>] <commit> <commit> [--] [<path>...]
```

Ao utilizar o comando `--help`, ele exibe as alterações, diferenças entre commits, diferenças entre um commit e o projeto de trabalho (working tree), e assim por diante. Em resumo, ele mostra as diferenças entre dois estados distintos.

Por padrão, o Git compara o último commit com o estado atual do código, mas é possível especificar outras opções, como o commit com o qual deseja-se fazer a comparação.

Teclamos "Q" para sair.

Para visualizar as mudanças entre os commits "deixando o jogo mais fácil" e "deixando o jogo mais fácil ainda" enquanto usamos o comando `git log --oneline`, observamos que existe um commit intermediário entre eles.

```
237cada (HEAD -> main, origin/main, origin/HEAD) mudanças no titulo e gitignore
16018ad Create README.md
7f69ff8 Revert "removendo foto"
2ad48c0 removendo foto
7679e24 Merge branch 'main' of github.com:rodrigoalura87/numero-secreto
**5bc160e deixando o jogo mais facil ainda**
ea44803 Alterando limite para 40
**5880fc1 Deixando o jogo mais facil**
dc89722 alterando limite para 100
250c665 projeto inicial
```

Desejamos analisar a diferença entre eles.

Para analisar a diferença entre esses dois commits específicos, precisamos incluir os três commits em nossa análise. Podemos fazer isso utilizando o comando `git diff`.

Primeiro, copiamos o hash do commit mais antigo que desejamos comparar, que é o "deixando o jogo mais fácil", e depois colamos esse hash seguido de "`..`": `git diff 5880fc1..`. Em seguida, copiamos o hash do commit mais recente que queremos comparar, que é o "deixando o jogo mais fácil ainda", e o colamos após "`..`".

```
git diff 5880fc1..5bc160e
```

O comando completo fica `git diff`, o commit mais antigo, "`..`", o commit mais novo. Ao teclarmos "Enter", ele mostra todas as alterações.

```
O retorno abaixo foi parcialmente transcrito. Para conferi-lo na íntegra, execute o código na sua máquina
```
```
diff --git a/app.js b/app.js
index d9966e1..c4aa249 100644
--- a/app.js
+++ b/app.js
@@ -1,5 +1,5 @@ 
    let listaDeNumerosSorteados = [];
-let numeroLimite = 50;
+let numeroLimite = 30;
    let numeroSecreto = gerarNumeroAleatorio();
    let tentativas = 1;
```

Obervamos que mudamos o número de limite de 50 para 30, alteramos o texto na "Escolha um número entre 1 e 30", alteramos de 50 para 30.

```
O retorno abaixo foi parcialmente transcrito. Para conferi-lo na íntegra, execute o código na sua máquina
```
```
- <p class="texto_paragrafo">Escolha um número entre 1 a 50</p>
+ <p class="texto__paragrafo">Escolha um número entre 1 a 30</p>
```

Então, visualizamos que entre esses commits, que são três aqui, "deixando o jogo mais fácil", tem um commit no meio e "deixando mais fácil ainda", conseguimos verificar todas as modificações feitas de uma vez só, conseguimos unificar esse diff.

```
Isso se torna especialmente interessante quando há necessidade de comparar o trabalho em dois estados distintos.
```

Vamos recapitular.

## Recapitulando

O comando `git diff`, por padrão, compara as modificações que foram feitas mas ainda não foram adicionadas para serem commitadas, mostrando a **diferença entre o estado atual do projeto e o último commit**.

Quando utilizamos `git add` em um arquivo, como por exemplo `index.html` (`git add index.html`), e em seguida executamos `git diff`, percebemos que não é mais exibido nenhum resultado. Por quê?

```
git add index.html
git diff
```

Ao executar `git status`, observamos que o arquivo `index.html` já foi adicionado e está pronto para ser commitado.

Retorno do comando `git status`:

```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
    (use "git restore --staged <file>..." to unstage) 
        modified: index.html I
```

Ou seja, ele está em um estado que chamamos de **stage** (palco), ou seja, ele foi **colocado em um local onde os commits são realizados**.

Portanto, o arquivo não está mais no estado anterior, fora do stage, onde o diff normalmente aponta. Assim, o comando `git diff` não mostrará mais diferenças para esse arquivo. Se rodarmos o `git diff`, não obtivemos nenhum retorno.

## Realizando o `commit`

Agora estamos prontos para realizar o `commit` dele. Vamos incluir uma mensagem indicando "alteração do título para português".

```
git commit -m "Mudando o título para português"
```

Obtemos a mensagem de confirmação como retorno:

```
[main 39dd858] Mudando o titulo para portugues 
1 file changed, 1 insertion(+), 1 deletion(-)
```

Se executarmos `git diff` neste momento, com nenhum arquivo no stage, nenhum arquivo preparado após o `git add`, e nenhum arquivo modificado em nosso projeto, ele não mostrará nenhuma diferença. Isto é, não retorna nada.

Porém, podemos utilizar novamente o comando `git log --oneline`.

```
39dd858 (HEAD -> main) Mudando o titulo para portugues
237cada (origin/main, origin/HEAD) mudanças no titulo e gitignore
16018ad Create README.md
7f69ff8 Revert "removendo foto"
2ad48c0 removendo foto
7679e24 Merge branch 'main' of github.com:rodrigoalura87/numero-secreto
5bc160e deixando o jogo mais facil ainda
ea44803 Alterando limite para 40
5880fc1 Deixando o jogo mais facil
dc89722 alterando limite para 100
```

Podemos visualizar a diferença entre os dois pontos.

Então, estamos interessados em identificar as diferenças desde a criação do `readme` até o nosso último commit. Para isso, utilizamos o comando `git diff`. Copiamos o registro "Create README.md" e o colamos.

```
git diff 16018ad
```

Agora, neste último ponto, notamos que apenas um commit foi realizado:

```
diff --git a/.gitignore b/.gitignore
new file mode 100644
index 0000000..cd78447
--- /dev/null
+++ b/.gitignore
@@ -0,0 +1 @@
+temp/
\ No newline at end of file
diff --git a/index.html b/index.html
index 61ff158..c5d087d 100644

// retorno omitido
```

Quando há apenas um commit no `diff`, ele compara com o último commit, ou seja, com nosso head atual. Descemos um pouco mais o retorno.

Dessa forma, podemos observar a alteração no título feita no último commit, a mudança de "adivinha" para "descubra" no commit anterior, e essas são as duas modificações entre a criação do readme e nosso head atual.

Então, essencialmente, o comando `git diff` revela a diferença entre dois estados. Por padrão, ele compara o último commit com as alterações presentes no momento atual, mas também podemos especificar a diferença entre dois commits, ou entre um commit e o estado atual do projeto, ou seja, nosso head.

Dessa forma, podemos sempre visualizar as discrepâncias entre dois momentos distintos.

### Conclusão

Em algumas ocasiões, mencionamos o termo branch.

Agora é hora de compreender o significado de **branch**, assim como o que representa essa referência à `main` quando executamos `git status`. Portanto, primeiro realizaremos um `git push origin main` e, em seguida, no próximo vídeo, nos aprofundaremos no entendimento do conceito de **branch**.

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)