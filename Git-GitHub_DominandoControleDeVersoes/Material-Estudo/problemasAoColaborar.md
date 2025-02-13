#  Problemas ao colaborar

Queremos levantar um ponto para você: se realizamos, por exemplo, um `push` que gerou erro na aula anterior, é porque utilizamos o usuário de trabalho e não o usuário pessoal. Com o usuário correto selecionado, fizemos o `push` novamente.

```
git push origin main
```

Agora vamos executar o comando abaixo:

```
git log --graph
```

Comentamos que existe uma linha, e em alguns momentos, pode existir uma **bifurcação** nessa linha. Vamos entender o que é essa bifurcação?

## Simulando um cenário

Imagine um cenário mais próximo da realidade, onde trabalhamos em um projeto real, grande, com vários arquivos, funcionalidades e uma equipe com diversas pessoas, e nesse trabalho, alteramos alguns arquivos. Para simular esse caso, vamos abrir outro terminal e fazer o `git clone` do projeto:

```
git clone git@github.com:CViniciusSDias/numero-secreto.git
```

Em seguida, vamos acessar o projeto numero-secreto em outro lugar:

```
cd numero-secreto/
```

Ou seja, estamos fora do Visual Studio Code, em um terminal em outro local, e vamos abrir o arquivo `index.html` no ambiente diferente de outro editor para modificá-lo.

```
vim index.html
```

Feito isso, vamos remover o "em" do título "Jogo em JS"; será somente "Jogo JS".

```
<title>Jogo JS</title>
```

Uma vez salvo o arquivo, podemos executar o comando `git status`. Além disso, com o comando `git diff`, conseguimos visualizar o que foi alterado.

```
git status
```
```
git diff
```

Agora vamos adicionar o arquivo `index.html`, e na sequência, adicionaremos um `commit` chamado "Removendo palavra do título". Após o `commit`, faremos o `push` para a `origin main`.

```
git add index.html
```
```
git commit -m "Removendo palavra do título"
```
```
git push origin main
```

Imagine que isso foi feito por uma pessoa que trabalha conosco, ou seja, outra pessoa fez o `commit`, o `push`, e está agora no repositório. Nós, ao mesmo tempo, trabalhamos em outra funcionalidade, como, por exemplo, corrigir o acento da palavra "número" na tag `<h1>` da linha 22.

```
<h1>Descubra o <span class="container__texto-azul">número secreto</span></h1>
```

Após fazer a alteração, vamos abrir o terminal no Visual Studio Code, executar o comando `git diff` para garantir que está tudo certo e que vamos comitar corretamente. Novamente, vamos adicionar o `index.html`, e adicionar o `commit` com a mensagem "Adicionando acento".

```
git commit -m "Adicionando acento"
```

izemos o `commit`, mas agora, quando formos fazer o `git push origin main`, o Git vai rejeitar esse `push`, dizendo que existem atualizações feitas que ainda não estão no código.

Isso é um "problema" que já conhecemos antes, então o que precisa ser feito? Primeiro, precisamos fazer um `git pull`. Com isso, ele vai trazer as alterações e fazer o que ele chama de **merge**.

```
git pull
```

Vamos aceitar esse merge. No nosso editor, basta executar o comando `:x` para salvar. Assim, fizemos o merge e agora podemos fazer o `push` do `origin main`, ou seja, ele **buscou as alterações** que estavam no repositório, **mesclou** com as nossas (significado de "merge"), e agora temos o **repositório atualizado**. Com o repositório atualizado, podemos enviar as alterações.

Porém, já abordamos tudo isso no curso anterior e você já passou por esse problema. Tanto que, se fizermos `git log --graph`, temos exatamente o cenário de bifurcação que já vimos anteriormente.

```
git log --graph
```

Por que mostramos isso de novo? Porque, novamente, pensando em um cenário colaborativo, imagine uma equipe pequena, com 10 pessoas. Imagine um projeto pequeno, com 1.000 arquivos.

Isso, em uma escala de mundo real, são coisas pequenas; uma equipe de 10 pessoas é pequena, da mesma forma que um projeto com 1.000 arquivos é pequeno. Imagine ter que lidar com essa situação toda vez que alteramos algum desses 1.000 arquivos para cada uma dessas 10 pessoas.

Toda hora terá alguém enviando modificação para o repositório, porque a cada alteração que fazemos no projeto, executamos um `commit` e enviamos essa alteração, para garantir que, caso nosso computador dê problema, nada seja perdido.

Há ainda outro ponto: imagine que estamos fazendo uma alteração e estamos no processo de tornar a nossa aplicação como um todo **gramaticalmente** correta, então adicionamos o acento em "número", temos que verificar outros arquivos que provavelmente têm a palavra "número" sem acento, e assim por diante.

Com isso, podemos ter vários commits nessa funcionalidade, isto é, uma única funcionalidade pode conter vários commits.

Imagine que corrigimos a palavra "número" e fizemos o `push` para enviar a alteração para o repositório remoto. Assim, todas as pessoas que utilizarem esse repositório, irão visualizar a alteração no meio do caminho. Ainda não terminamos a funcionalidade, mas ela já está no repositório remoto para todos verem.

Imagine que queremos colocar isso em produção. Sempre que vamos colocar um código em produção e disponibilizar efetivamente esse projeto para o mundo ver, ele deve estar pronto, no estado completo.

Portanto, se estamos no meio de uma alteração, **não podemos fazer o deploy (implantação)**, não podemos colocar esse projeto no ar.

Sendo assim, alguém que desenvolvia outra funcionalidade, agora precisará nos esperar terminar essa funcionalidade para colocar a dela no ar, porque também enviamos metade de uma alteração.

### Conclusão

Perceba que se todas as pessoas estiverem trabalhando na mesma linha de trabalho, no mesmo local, temos vários problemas: um problema **organizacional**, onde as funcionalidades estarão todas juntas no mesmo lugar; o problema de sempre precisar fazer a mescla dos trabalhos de outras pessoas com os nossos; entre outras questões.

Há alguns problemas ao colaborar dessa forma. Por isso, vamos entender como separar linhas de trabalho, ou seja, como ramificar nossas alterações através de branches no Git. É isso que vamos abordar no próximo vídeo!

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)