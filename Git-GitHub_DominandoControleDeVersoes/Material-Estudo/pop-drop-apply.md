# Pop, Drop e Apply

Os comandos `pop`, `drop` e `apply` do `git stash` possuem semelhanças e diferenças bem importantes, então vamos fazer um pequeno resumo de suas funcionalidades aqui:

## Apply

O comando `git stash apply` espera um índice de um item na stash e o aplica ao repositório, porém, esse comando não remove o item da stash, ou seja, se após executar o comando `git stash apply 1` você executar `git stash list`, o item referente ao índice 1 continuará na stash.

## Pop

O `git stash pop` faz exatamente a mesma coisa que o git stash apply, porém, além de aplicar o item da stash, ele também o remove de lá. Esse comando, sem nenhum parâmetro extra, vai aplicar o último item adicionado à stash, mas nós também podemos informar um índice para ele, como `git stash pop 1`.

## Drop

O `git stash drop` funciona exatamente como o `pop`, mas com uma simples diferença: ele apenas remove o item da stash, sem aplicá-lo em nosso repositório. Dessa forma, `git stash drop` remove o último item adicionado à stash, enquanto o `git stash drop 1` remove da stash o item com índice 1.

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)