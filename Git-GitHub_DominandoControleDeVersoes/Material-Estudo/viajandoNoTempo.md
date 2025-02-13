# Viajando no tempo

O comando `git restore` pode restaurar estados de um arquivo ou de um projeto inteiro. Dissemos que queríamos "viajar no tempo", mas antes precisamos mostrar um detalhe interessante.

Vamos supor que removemos todas as quebras de linhas extras que inserimos no arquivo. Estamos prontos para adicionar nosso `app.js` para fazer o commit.

Adicionamos com o comando `git add app.js`, então, ele está no "stage", pronto para ser comitado. Isso é o que chamamos de "stage" ou "staging area". Mas, o que acontece se quisermos desfazer isso? Não estamos prontos para comitar. Queremos fazer mais alterações ou simplesmente desistir dessa modificação.

Note que o próprio `git` já nos mostra que podemos fazer um `restore` do que está em nossa "staging area". Se fizermos `git restore --staged`, significa que estamos modificando algo que está dentro dessa "staging area", dentro de algo que fizemos com o `git add`.

Assim, com `git restore --staged app.js`, não desfazemos a alteração, mas retornamos ao estado anterior. Agora, é como se não tivéssemos feito o `git add`. Observe que ele está pronto para fazermos o `git add` e as linhas, ainda estão removidas.

Agora, se quisermos desfazer as alterações, fazemos o `git restore app.js`. Sendo assim, desfizemos as alterações. Repare a diferença entre o `--staged` e o `staged`.

Um outro parâmetro que podemos passar para o `restore` é, suponha que queremos mover nosso `index.html` para o estado que estava quando fizemos o `Merge branch 'nova-funcionalidade' into main`.

O que podemos fazer? Podemos copiar o hash do commit, fazer o `git restore --source =` e colá-lo em seguida. Queremos restaurar para esse estado nosso `index.html`. O comando inteiro ficará parecido com o seguinte:

```
git restore --source = 5081a55bc92af2917c8519f16a7412b86ba3b1c2 index.html
```

Quando fazemos isso, ele pega o `index` e o coloca no estado que estava nesse commit.

Ao acessar o `index`, observe que tem algumas alterações: O nosso script está em uma linha só, a nossa tag de link não está indentada e os botões também não estão indentados. Ele retornou para esse estado. Se fizermos um `git status`, podemos modificar o arquivo a partir daquele estado e adicionar um novo commit, se quisermos.

Mas, se quisermos apenas visualizar o arquivo e entender como ele estava naquele estado, podemos desfazer esse trabalho, ou seja, restaurar para o estado normal dele com o `git restore index.html`, que é equivalente a fazer `--source = head`.

```
Fazer o restore sem esse --source é equivalente a fazer --source = head, que corresponde ao último commit que temos no branch atual.
```

Agora, se fizermos o `git status`, temos nossa branch `movendo-detalhes` correta. Se fizermos um `git log`, nossa branch `movendo-detalhes` está no mesmo lugar que a branch `main`.

Vamos voltar para a nossa branch com `git switch main` e vamos remover com `git branch -d movendo-detalhes`, que foi um branch que criamos apenas para simular a criação de uma nova funcionalidade, mas não chegamos a comitar nada lá.

Nesse vídeo, aprendemos a manipular nossa "working tree", que é o que estiver em nosso projeto, mesmo que não tenhamos adicionado para commit.

Quando temos algo indicado com `modified`, isso está na nossa "working tree", o nosso projeto, basicamente. Manipulamos também nossa staging area, que é o que está verde quando fazemos o `git statu`s, o que modificamos quando fazemos nosso `git add`.

Aprendemos a manipular esses dois status com o `git restore`, seja removendo algo da nossa staging area com o `git restore staged` ou removendo algo da nossa working tree com o `git restore` sem o `staged`. Assim, aprendemos a manipular nosso código, a working tree e a staging area.

Suponha que esse projeto, no estado que está, está aceitável. Queremos apontar que temos uma nova versão (a 0.1.0). Como podemos gerenciar versões ou marcar um checkpoint, um ponto onde queremos salvar e dar um nome para esse estado? Vamos falar sobre isso, sobre criar versões e gerar releases na próxima aula.

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)