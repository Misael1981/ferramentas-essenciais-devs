# Parâmetros do log

## O que é o git log?

Imagine seu repositório Git como um álbum de fotos digital, onde cada foto é um “commit” que registra uma alteração no seu código. O comando `git log` é como folhear esse álbum, permitindo que você visualize a sequência de eventos e alterações que ocorrem ao longo do tempo.

### Para que serve?

- **Ver o histórico de commits**: Visualize a ordem cronológica dos commits, incluindo quem os fez, quando foram feitos e qual a mensagem associada a cada um.
- **Entender as mudanças**: Comparar versões diferentes do código para identificar quais partes foram alteradas e porquê.
- **Buscar commits específicos**: Filtrar o histórico para encontrar commits que se encaixem em determinados critérios, como dados, autor ou mensagem.
- **Analisar o desenvolvimento do projeto**: Obtenha uma visão geral do progresso do projeto ao longo do tempo.

## Parâmetros do log

### `--oneline`

- Exibe apenas as mensagens do commit, de forma simplificada.

#### Sintaxe:

```
git log --oneline
```

#### Exemplo:

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

Com `git log --oneline`, teremos nosso histórico de commits exibido com os hashes reduzidos, mostrando apenas os primeiros caracteres do hash. Isso já é suficiente para identificarmos algum commit.

E apenas a mensagem do commit, por exemplo "removendo foto". Não visualizamos quem foi a autora ou o autor, em que momento isso foi feito, etc. Assim, temos uma visualização um pouco mais clara do nosso log.

### Visualizando a alteração do commit `-p`

No entanto, o oposto pode ocorrer. Estamos interessados em examinar o commit e suas alterações, não apenas sua mensagem, mas também seu conteúdo. Portanto, ao retornar ao terminal, limpamos a tela e digitamos o comando `git log -p`.

```
git log -p
```

Essa opção `-p` vai nos fornecer, além das informações padrão, **o hash completo**, o autor ou autora, a data e a mensagem do commit.

```
O retorno abaixo foi parcialmente transcrito. Para conferi-lo na íntegra, execute o código na sua máquina
```
```
commit 237cadaa5c19dcb03263d08f9f7c107dc03268a7 (HEAD -> main, origin/main, origin/ HEAD)
Author: Rodrigo Ferreira <rodrigo.alura87@gmail.com>
Date: Wed Sep 6 10:31:17 2023 -0300

    mudanças no titulo e gitignore

diff --git a/.gitignore b/.gitignore
new file mode 100644
index 0000000..cd78447
---- /dev/null
+++ b/.gitignore
@@ -0,0 +1 @@
+temp/
\ No newline at end of file
diff --git a/index.htmlb/index.html
index 61ff158…7eb8cc 100644
---- a/index.html
+++  b/index.html
@@ -19,7 +19,7 @@
    <div class="container_conteudo">
        <div class="container_informacoes">
            <div class="container_texto">
-			<h1>Adivinhe o <span class="container__texto-azul">numero secreto</span></h1>
+			<h1>Descubra o <span class="container__texto-azul">numero secreto</span></h1>

            <p class=texto__paragrafo>Escolha um número entre 1 a 40</p>
</div>

// retorno omitido
```

Além disso, ele mostrará um `diff`, que é essencialmente um formato que o git utiliza para exibir as **alterações** de um commit específico.

Vamos entender o formato dessas alterações. Primeiramente, descemos, pressionando a tecla de seta para baixo, até a seção referente ao index.html, nosso arquivo principal, onde a maioria das alterações está ocorrendo.

Aqui, ele mostra como esse formato funciona. Ele diz que as linhas que começam com "`-`" (`---- a/index.html`), **significa que foram linhas que foram removidas**. E as linhas que começam com "`+`" (`+++ b/index.html`), **são as linhas adicionadas**.

Então, se houver alguma modificação, uma mudança em uma linha, veremos duas entradas nesse `diff`: uma em que a linha começa com "`-`" e outra em que a linha começa com "`+`", indicando que trocamos uma linha por outra.

Ao analisar a saída no terminal, fechamos esse menu com os arquivos para visualizar essa saída um pouco melhor. Observamos que a linha com o `h1` foi alterada; portanto, foi mudado de "Adivinhe" para "Descubra". **Esse é o formato diff**.

Conseguimos visualizar neste commit o que aconteceu, e esse é o formato `diff`. Ao percorrer a lista de alterações, em cada arquivo conseguimos verificar tudo o que foi modificado.

<div style="background-color: white; color: black">

Em suma, temos o `git log --online` para **visualizar o log de forma compacta**. Temos também o `git log -p` **para ver isso de forma expandida**, com as alterações.

</div>

## Outras formas de exibição do log

E várias outras opções também, como o `git log --graph`, que exibirá uma linha do nosso log, e isso será ainda mais útil quando falarmos um pouco sobre ***branches***.

Mas, essencialmente, se percorro isso até a parte em que temos um `merge`, que foi feito no curso anterior, percebemos que ele representa graficamente uma linha do tempo se desviando para outro ponto e depois retornando à nossa linha principal.

Note que à esquerda há uma linha vertical, e a partir do ponto de `merge`, outra linha se ramifica dessa vertical, estendendo-se até o `commit` do Rodrigo. Isso ficará um pouco mais claro, mas com o uso de `--graph`, conseguimos visualizar o log de uma forma mais `visual`.

Há ainda uma opção interessante, que é o `--pretty` ou `--format`. Ambos são sinônimos.

```
git log --pretty 
git log --format
```

Com `--format` ou `--pretty`, podemos exibir o commit da maneira que desejar. Por exemplo, utilizarmos `--format=""` e dentro das aspas digitar `%H %an`.

```
git log --format="%H %an"
```

Ao pressionarmos "Enter", o hash do `commit` e o autor de cada `commit` é exibido:

```
O retorno abaixo foi parcialmente transcrito.
```
```
237cadaa5c19dcb03263d08f9f7c107dc03268a7 Rodrigo Ferreira
16018ade439fdae0582aa0108f2a94974f9c97ec rodrigoalura87
7f69ff8220e093d2c8ad234ceec109a6e794e5f6 Gabrielle Ribeiro
2ad48c068dc9677fb57efec70620700410f976b0 Rodrigo Ferreira
7679e2478db577be411adf8c02cac57aae6bfa3b Rodrigo Ferreira
5bc160e8a7a3b53861e2e3da1a75c23e230a3c51 Rodrigo Ferreira
```

Esse `--format` nos permite exibir o que desejarmos desse `commit`.

## Usando o `git log --help`

E como sabemos quais são as opções, de onde vem esse `%H`, `%an`? Se digitamos `git log --help`, temos um manual, uma ajuda desse comando. E se digitarmos `/pretty formats` e teclarmos "Enter".

```
/PRETTY FORMATS
```

Em "PRETTY FORMATS", visualizamos que conseguimos escolher diversos formatos. Temos o formato de one line, short, medium, full, fuller, e aqui conseguimos colocar coisas específicas, um formato específico.

```
Exemplo de formato:
```
```
short
commit <hash> 
Author: <author>

<title line>
```

Os placeholders para nova linha, ou então, por exemplo, mudar a cor para deixar esse log mais legível, bem formatado. Mas temos o hash do `commit` com `%H` maiúsculo, ou o hash abreviado com `%h` minúsculo.

Também temos o nome da autora ou do autor, que é o `%an`, ou o nome do autor com `%aN` maiúsculo, o email com `%ae`, a data do `commit`, então `%aD`, temos diversas informações que podemos utilizar aqui.

Portanto, se descermos nesta página de documentação, veremos que esse `pretty` ou `format` pode ser utilizado de forma bem ampla. Isso normalmente é usado quando estamos criando algum script, automatizando alguma coisa. Então, no dia a dia, não vamos utilizar tanto.

Agora, o git `log --oneline` e o `git log -p`, esses sim são comandos bastante utilizados no dia a dia.

### Conclusão

Agora, sobre esse `-p` aqui, onde visualizamos quais arquivos foram removidos, modificados ou adicionados, como podemos verificar isso? Somente para um `commit`, ao invés de verificar no `log`.

Se desejamos visualizar, por exemplo, no último `commit`, o que foi feito, quais foram as alterações, como podemos verificar isso? Aprenderemos exatamente sobre esse caso no próximo vídeo!

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)