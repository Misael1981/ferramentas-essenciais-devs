# Vendo as alterações `git show`

Vamos considerar este cenário: estamos revisando nossa lista de commits ao executarmos o comando `git log --oneline`, por exemplo.

```
237cada (HEAD -> main, origin/main, origin/HEAD) mudanças no titulo e gitignore
16018ad Create README.md
7f69ff8 Revert "removendo foto"
2ad48c0 removendo foto
7679e24 Merge branch 'main' of github.com:rodrigoalura87/numero-secreto
5bc160e deixando o jogo mais facil ainda
ea44803 Alterando limite para 40
5880fc1 Deixando o jogo mais facil
dc89722 alterando limite para 100
250c665 projeto inicial
```

Nosso foco está no commit denominado "removendo foto".

## Analisando um `commit` específico

Desejamos compreender as alterações realizadas neste commit específico, independentemente de quem o tenha feito. Portanto, ao pressionarmos "Q", sairemos do registro (log) e solicitaremos ao Git que nos apresente o conteúdo e os detalhes desse commit.

Para isso, copiaremos o hash correspondente e digitaremos `git show`, seguido do respectivo hash.

```
git show {hash do commit}
```
```
git show 2ad48c0
```

O comando `git show` nos proporcionará uma exibição semelhante ao `git log -p`, porém focado apenas no commit em questão, não em todo o registro:

```
O retorno abaixo foi parcialmente transcrito. Para conferi-lo na íntegra, execute o código na sua máquina
```
```
commit 2ad48c068dc9677fb57efec70620700410f97660
Author: Rodrigo Ferreira <rodrigo.alura87@gmail.com>
Date: Tue Sep 5 17:19:08 2023 -0300

        removendo foto

diff --git a/index.html b/index.html
index 61ff158..e993d93 100644
--- a/index.html
+++ b/index.html

// retorno omitido
```

#### São apresentados: 

- o hash do commit, 
- o nome do autor, 
- a data, 
- a mensagem de commit 
- o diff correspondente, 

Que detalha as alterações realizadas. Dessa forma, podemos navegar pelo conteúdo, descendo para visualizar as mudanças específicas. Por exemplo, notamos que uma linha referente à imagem, identificada como uma tag img, foi removida de um arquivo `index.html`.

Agora, ao pressionarmos "Q", sairemos dessa visualização. Podemos executar novamente o comando `git log --oneline`. Ao visualizarmos novamente o registro, podemos selecionar o commit de "7f69ff8 Revert "removendo foto"". Para isso, digitamos `git show` seguido do hash correspondente.

```
git show 7f69ff8
```

Observamos que a mesma linha foi adicionada novamente.

Observe como o comando `git show` é bastante simples, ele exibe o diff para nós. Novamente, basta pressionar "Q" para sair. Um detalhe interessante é que, ao digitarmos `git show --help`, podemos entender melhor como o comando funciona.

```
git show --help
```

O Git segue o padrão de nome do comando seguido de `--help`, com isso, podemos solicitar ajuda em caso de dúvidas em um determinado comando. Obtemos como retorno:

```
NAME
    git-show - Show various types of objects
    
SYNOPSIS
    git show [<options>] [<object>…]
    
// retorno omitido
```

Isso nos mostra que o `git show` espera algumas opções e objetos, como um commit, por exemplo.

Outra possibilidade é que o objeto seja algo diferente, mas para nossos propósitos, vamos focar no commit. Porém, antes de prosseguir, deixe-me explicar brevemente o **formato de sinopse apresentado pelo help.**

```
git show [<options>] [<object>…]
```

Sempre que algo está entre colchetes, isso indica que é **opcional**.

Você percebeu que apenas digitamos `git show` seguido pelo nome do nosso hash do commit, certo? Não especificamos nenhum opcional. Isso significa que, além das opções que já discutimos, esse objeto, o commit, também é opcional. O que isso implica? Vamos voltar ao `help` para esclarecer, descemos um pouco no terminal.

```
// retorno omitido
    
OPTIONS
<object>...
    The names of objects to show (defaults to HEAD). For a more complete list of(…) object names, see "SPECIFYING REVISIONS" section in gitrevisions(7).
    
// retorno omitido
```

Se esse objeto não for informado, o `help` indica que ele "defaults to head" (assume o padrão como sendo o "head"). Portanto, ao pressionar "Q" para sair e digitar `git log` novamente, podemos destacar um detalhe interessante.

```
git log
```

Obtemos:

```
commit 237cadaa5c19dcb03263d08f9f7c107dc03268a7 (HEAD -> main, origin/main, origin/HEAD)
Author: Rodrigo Ferreira <rodrigo.alura87@gmail.com>
Date: Wed Sep 6 10:31:17 2023 -0300

    mudanças no titulo e gitignore

commit 16018ade439fdae0582aa0108f2a94974f9c97ec
Author: rodrigoalura87 <144138057+rodrigoalura87@users.noreply.github.com>
Date: Wed Sep 6 10:20:02 2023-0300
```

O nosso último commit, do lado do hash do commit, temos `(HEAD -> main, origin/main, origin/HEAD)`. O que isso significa?

Primeiro, `main` **é o nome de um branch** e vamos falar sobre branch mais adiante. E esse `origin`, já sabemos que **é o nosso repositório remoto**, é lá no GitHub. Portanto, esse `origin/main` significa que **esse commit também é onde está o nosso branch main no repositório remoto**.

Basicamente, o que isso significa é que este commit representa o estado atual da nossa branch main, ou seja, é o **estado atual da "main"** no nosso repositório remoto.

Agora, o "`HEAD`" e o "`origin/HEAD`", que significam a mesma coisa que "HEAD" no repositório remoto, **referem-se ao estado atual no repositório remoto**. O que isso implica? **"HEAD" representa simplesmente o último commit**, ou seja, o commit atual do qual estamos trabalhando.

<div style="background-color: white; color: black;">
<hr>
<hr>
<hr>
**HEAD: commit mais recente da branch atual**
<hr>
<hr>
<hr>

</div>

Assim, como "mudanças no título e gitignore" é o último commit, ou seja, o mais recente, ele é o nosso HEAD. Portanto, **HEAD é essencialmente um sinônimo, um ponteiro, um apelido para o nosso último commit**, o mais recente estado do nosso projeto no momento.

Então, por que toda essa explicação sobre "HEAD"? Porque ao digitar apenas `git show`, sem mais nada, o Git mostrará os detalhes do último "commit".

```
git show
```

Então, observamos aqui que o último registro de alterações (commit) foi modificado de "adivinha" para "descubra" no nosso cabeçalho (`H1`).

Assim, mais uma vez, o comando `git show` **exibe os detalhes de um ou mais registros de alterações** (commits), e se nenhum registro for especificado, ele por padrão seleciona o cabeçalho (HEAD), que é o último registro de alterações.

Portanto, sempre que encontrarem referências ao HEAD em documentação, artigos, textos ou similares, é bastante simples. Ele é apenas um alias para o registro de alterações mais recente da sua posição atual. Então, entendemos o funcionamento do `git show`. Ele exibe os detalhes do último registro de alterações ou de um registro específico.

### Conclusão

Agora, uma observação interessante: se estivermos no meio de uma edição, realizando alterações, mas ainda não fizemos o registro de alterações? E queremos visualizar o que já foi alterado, o que está pronto para ser registrado.

Como podemos fazer isso? Como podemos ver as diferenças (diff) dos arquivos que ainda não foram incluídos no registro de alterações (commit)? Vamos abordar isso no próximo vídeo.

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)