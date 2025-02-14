# Detalhes da versão

## Apagando uma tag

Vamos fazer com que a tag `v.0.1.1` seja annotated. Para isso, precisamos apagar essa tag. No nosso GitHub, no canto direito da tag `v0.1.1`, clicaremos em "… > Delete tag" para apagá-la do repositório remoto. Uma mensagem de confirmação aparece no centro da tela, e basta clicarmos em "Delete this tag" (deletar essa tag) no canto inferior direito da mensagem.

Voltando ao VS Code, onde temos nosso repositório local, abriremos o Terminal, onde vamos rodar o comando `git tag -d v0.1.1"`, para removemos a tag localmente também. Concluída esta etapa, se fizermos o nosso `git log`, não encontramos mais a tag `v.0.1.0`.

## Criando uma Annotated tag

Agora queremos criar uma nova tag com uma informação a mais, por exemplo, uma mensagem. Para isso, podemos usar o comando `git tag -a nome_da_tag -m "mensagem da tag"`, sendo o `-a` de annotated (anotação) e o `-m` de message (mensagem). Chamaremos a tag de v`0.1.1` e passaremos a menagem `"Lançamento da versão 0.1.1`.

```
git tag -a v0.1.1 -m "Lançamento da versão 0.1.1"
```

Ao executarmos esse comando, temos uma tag com tem informações a mais do que apenas um commit. Faremos o push dessa tag, com o comando `git push origin v0.1.1` e retornaremos a página de tags do GitHub.

## Analisando uma Annotated Tag no GitHub

Ao recarregarmos a página, e clicarmos no retângulo com reticências ao lado do nome "v0.1.1", abriremos a mensagem "Lançamento da versão 0.1.1", abaixo do nome da tag.

Também podemos clicar no retângulo com reticências ao lado do nome da tag "v0.1.0", e notamos que a mensagem que aparece é a do commit. Já na "v0.1.1", temos uma mensagem específica da nossa tag. Portanto, agora uma annotated tag, com informações a mais.

A annotated tag, além da mensagem exibida, carrega informações da pessoa autora da tag e a data que a tag foi criada, enquanto a tag comum é apenas um ponteiro para o commit. Existe essa pequena diferença entre uma tag que é annotated e uma tag que não é annotated.

Outro detalhe interessante é que esse parâmetro `-a` é opcional, porque se passamos alguma informação para a nossa tag, como uma mensagem (`-m`), o Git já entende que essa tag é annotated. Portanto, conseguimos criar uma annotated tag mesmo sem o parâmetro `-a`.

## Conclusão

Com isso, aprendemos que `git tag nome_da_tag -m` já cria uma tag com mensagem, ou seja, uma annotated tag. Voltando ao GitHub, na parte superior esquerda da lista de tags, temos as abas "Release" e "Tags". A aba Releases (lançamentos) pode trazer algumas informações a mais, então, no próximo vídeo, conheceremos mais sobre essa aba e criaremos um release (lançamento) do nosso projeto.

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)