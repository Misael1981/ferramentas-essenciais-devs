# Gerando uma Release

Para verificar a tag `v 0.1.1`, serão exibidas informações indicando para qual commit ela aponta, o tipo (podemos criar uma tag para outra coisa, mas vamos focar no tipo de commit aqui), o nome dessa tag, quem a criou e sua mensagem. Temos, portanto, as informações dessa tag.

Se tentarmos fazer o mesmo para a tag que não é annotated, teremos um erro, porque o nome `v 0.1.0` é basicamente um apelido para um commit, então ela não existe como tag propriamente dita. Essa é uma diferença entre Annotated Tags e Unannotated Tags.

## Releases

Agora, vamos falar sobre releases. Imagine o seguinte cenário: lançamos uma nova versão. Nessa nova versão, queremos disponibilizar, por exemplo, se for um projeto compilado, um binário compilado desse projeto, um changelog, um documento mostrando as modificações dessa versão.

Podemos disponibilizar alguns artefatos além do projeto em si.

É para isso que serve uma release no GitHub. Se você quer disponibilizar um documento a mais, uma descrição diferente para essa release, além da tag, ou se quer disponibilizar um arquivo binário, por exemplo, resultante do projeto, com uma release você pode fazer isso.

Releases podem ser criadas automaticamente, **através de GitHub Actions**, por exemplo, mas aqui vamos criar uma manualmente, até porque não temos nenhum projeto de compilação, temos apenas HTML, JavaScript e CSS.

## Como criar releases

Vamos clicar no botão "Releases" e escolher uma tag para criá-la. Essa release será a partir de nossa tag `v11`. Podemos criar o título dessa release, que será: "lançamento da v0.1.1".

Poderíamos ter um título mais chamativo, cada projeto terá um padrão de títulos, o título pode ser a versão ou qualquer outra coisa que você preferir.

Em seguida, vamos criar as nossas **release notes**, ou seja, as alterações que foram feitas nessa release, nessa nova versão. Inclusive, isso pode ser feito automaticamente com o botão "Generate release notes". Ele trará os detalhes de todos os pull requests, etc.

No nosso caso, como não temos isso, ele mostra o full change log, mostrará o diff entre `0.1.0` e `0.1.1`. Ele já coloca um link para o GitHub mostrando aquele diff de uma versão para outra, isso é bem interessante.

E no campo de inserir arquivos poderíamos colocar um arquivo binário, por exemplo. Se tivéssemos um projeto compilado de nossa aplicação, selecionaríamos esse projeto compilado, adicionaríamos aqui, e esse arquivo binário estaria disponível para download quando alguém acessar nossa página de release.

Para publicar a release basta clicar em "Publish release".

Agora, temos uma página de lançamento do nosso projeto.

Nessa página de lançamento, a pessoa pode ver toda a documentação, no nosso caso, colocamos apenas o full change log, com um link para uma página que mostra tudo o que foi alterado, que foi uma linha.

Poderíamos ter todo um change log, toda uma documentação específica desse lançamento. E poderíamos ter em Assets, um arquivo binário. Além do projeto em si, que pode ser baixado como zip, poderíamos ter algum artefato a mais. Um binário, por exemplo, compilado. Se fosse um projeto Java, poderíamos ter um `.jar`, ou coisa do tipo. Algo que seja referente a esse lançamento.

### Conclusão

Portanto, as releases no GitHub são utilizadas para esse cenário. Quando queremos disponibilizar uma nova versão, criamos uma tag, a partir dessa tag podemos gerar uma release.

Novamente, isso pode ser gerado automaticamente a partir de uma GitHub Action, mas aqui não estamos falando de automatização, então criamos manualmente uma release a partir de uma tag, que é uma funcionalidade muito interessante do GitHub.

Agora que já falamos do GitHub, vamos voltar para o Git, vamos voltar para nossa linha de comando, e entender alguns detalhes a mais que podemos fazer. Por exemplo, pegar um commit específico e adicionar um novo branch. Vamos voltar para a linha de comando e aprender mais alguns detalhes sobre Git.

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)