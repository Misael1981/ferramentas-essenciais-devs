# Criando uma versão

Imaginem um jogo, como Sonic ou Mario, onde passamos por alguns pontos no jogo, chamados checkpoints ou save points.

Caso o personagem seja derrotado, ao invés de voltar no início do jogo, volta para aquele ponto. São pontos onde salvamos o estado do jogo. Podemos criar algo semelhante no Git. Podemos dar um nome para um ponto específico do nosso projeto.

## Criando commits com tags

Por exemplo, no Terminal do VS Code, vamos executar o comando `git log --oneline`. Vemos que nossa `HEAD` no branch `main`, que está em um commit chamado `Quebrando a linha do script`. Este foi o último commit que criamos. Sabemos que um branch, conforme adicionamos novos commits. Logo, a `HEAD` muda de local.

Queremos marcar um ponto no commit `Quebrando a linha do script` e torná-lo um save point, indicando que ele representa o lançamento da nossa versão 0.1.0, por exemplo. Ou qualquer outra versão. Portanto, conseguimos nomear pontos específicos do nosso código, e, **no Git, chamamos esse processo de tag**.

Uma tag no Git é criada através do comando `git tag nome_da_tag`, que rodamos no Terminal. Por exemplo, vamos rodar o comando `git tag v0.1.0`. Assim, criamos uma tag na nossa `HEAD`, ou seja, no momento mais recente da branch que tivermos feito o commit. Após criarmos a tag e rodarmos o comando `git log` de novo, recebemos as informações do commit com a nossa tag.

```
$ git log
```
```
commit c53eb1654ecc7a9ece1294ec68f78b4d8172189b (HEAD -> main, tag: v0.1.0,origin/nova-funcionalidade, origin/main, origin/HEAD, nova-funcionalidade)
Author : Vinicios Dias <carlosv775@gmail.com>
Date: Dat Dec 23 14:06:11 2023 -0300

    Quebrando linha do script
```
```
Dica: A tag pode ter qualquer nome. Utilizamos o nome v0.1.0 para parecer com uma versão de lançamento, porque faz bastante sentido para esse exemplo.
```

## Entendendo o funcionamento das tags

Dessa forma, vamos descobrir o que acontece se adicionarmos outro commit. Por exemplo, no arquivo `index.html`, removeremos a quebra de linha entre o `<head>` e o `<body>`, na linha 16. Em seguida, faremos um novo commit, abrindo o terminal e rodando o comando `git commit -m "Removendo quebra de linha"`. Após criarmos esse novo commit e fazermos um `git log --oneline`, notamos que a `tag: v0.1.0` ainda aparece no commit anterior, que é o commit `Quebrando a linha do script`.

```
502afbc6 (HEAD -> main) Removendo quebra de linha
c53eb16c (tag: v0.1.0, origin/nova-funcionalidade, origin/main, origin/HEAD, nova-funcionalidade) Quebrando linha do script
bc493a6c Corrigindo indentação
```

Podemos rodar o `git push origin main` e o `git push origin nova-funcionalidade`. Após fazermos o push de tudo e rodarmos o `git log --oneline`, ainda teremos o retorno da `tag: v.0.1.0` no commit `Quebrando linha do script`. Portanto, a tag nunca vai se mover, ela sempre vai apontar para o mesmo commit.

Da forma como fizemos, a tag é um ponteiro nomeado para um commit específico: o nome que damos para algum commit. Dessa forma, conseguimos salvar o estado da aplicação naquele momento. Agora vamos tentar criar a `tag v0.1.1`.

## Criando tags para commits fora da HEAD

Se rodarmos simplesmente `git tag v.0.1.1`, ele cria um commit no nosso `HEAD`. Porém, se quisermos, podemos **criar uma tag para algum commit específico**. Criaremos para o último commit: o "Removendo quebra de linha", tem o código `502afb6`.

Com o código que aparece no começo da linha de commit, podemos criar uma tag para qualquer commit no nosso histórico, através da estrutura: `git tag nome_da_tag código_do_commit`. No caso, executamos o `git tag v0.1.1 502afb6` e, em seguida, ao executarmos o `git log` encontraremos as tags `v0.1.0` e `v0.1.1`.

```
git tag v0.1.1 502afb6
git log
```
```
commit 502afbb6235b26346a0efefec0a6b73431bf7d4703 (HEAD -> main, tag: v0.1.1, origin/main, origin/HEAD)
Author: Vinicius Dias <carlosv775@gmail.com>
Date:   Sat Dec 23 15:12:41 2023 -0300

    Removendo quebra de linha

commit c53eb1654ecc7a9ece1294ec68f78b4d8172189b (HEAD -> main, tag: v0.1.0,origin/nova-funcionalidade, origin/main, origin/HEAD, nova-funcionalidade)
Author : Vinicios Dias <carlosv775@gmail.com>
Date: Dat Dec 23 14:06:11 2023 -0300

    Quebrando linha do script
```

Então, se fizermos `git log`, temos agora nossas duas tags, `0.1.1` e a `v0.1.0`. Se quisermos ver todas as nossas tags, é só executarmos `git tag` no terminal, e ele mostrará para nós.

```
git tag
```
```
v0.1.0

v0.1.1
```

Se quisermos, podemos enviar a nossa tag para o nosso repositório remoto, o GitHub, com o comando `git push origin v.0.1.0`, que fará o push da tag que passamos o nome. Ou podemos executar `git push origin --tags`, que fará o `push` de todas as tags.

## Conferindo as tags no GitHub

Em seguida, podemos acessar o GitHub e, na coluna da esquerda, na seção "Relaeases" (Lançamentos), temos um link indicando que existem duas tags. Ao clicarmos nesse link, vamos para a página de Tags, onde conseguimos visualizar todas as tags do projeto.

Quando criamos uma tag, conseguimos fornecer, através do GitHub, opções de download do projeto em arquivos compactados, tanto no formato `.zip`, quanto no `.tar.gz`, no estado em que criamos a tag. Um detalhe que talvez você reparou e possa perguntar: "Não tem nenhuma mensagem para cada uma das versões que criamos? Não conseguimos definir uma mensagem ou algumas informações a mais?".

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)