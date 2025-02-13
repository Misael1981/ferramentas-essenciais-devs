# Desfazendo alterações

Imaginem que nós estamos criando alguma modificação. Então, nós removeremos todas as linhas do final. Nesse ponto, temos vários arquivos modificados e alterados. Porém, nós percebemos que a implementação está incorreta ou a funcionalidade não será mais implementada. Basicamente, **queremos descartar o que foi feito**.

Se temos apenas um arquivo, para descartar essa modificação, podemos fazer um `Ctrl + Z`. Mas, se temos vários arquivos, sair fazendo `Ctrl + Z` em muitos lugares pode ser bastante cansativo. Para isso, podemos utilizar o `git`.

## Descartando várias alterações

Vamos limpar o terminal e executar um `git status`. Temos um arquivo que foi modificado, mas poderíamos ter vários. Por exemplo, também vamos modificar algo no `index.html`. Algo inválido: adicionamos várias quebras de linha.

Então, nosso `git status` tem modificações. E o que queremos fazer é **desfazer essas modificações**. Nós não fizemos `git add` e não commitamos isso. Como não foi commitado, não é um `revert`, nem um `reset`. Não é um comando que já aprendemos no curso anterior.

O que queremos fazer é restaurar o nosso local de trabalho para um estado válido, sem essas modificações. Então, queremos fazer um `git restore`.

```
Podemos fazer o restore para algum estado específico, mas se não informarmos o estado, isso significa que a restauração será feita sem o que foi modificado. Ou seja, o último commit do nosso branch atual.
```

Então, queremos fazer o `restore` de quê? Podemos fazer de `app.js` e de `index.html` um de cada vez. Ou fazer do ponto (`git restore .`). Assim como já aprendemos que o `git add .` adiciona o projeto todo, o `git restore .` restaura todo o projeto também. E esse ponto não é um significado especial do `git`.

```
Na linha de comando, o ponto significa o diretório atual. Então, estamos fazendo o restore de tudo na pasta atual.
```

Então, esse `git restore` vai fazer um `Ctrl + Z` no nosso projeto. Assim, as linhas que adicionamos no `index` sumiram, e aquelas alterações no nosso `app.js` também sumiram. Então, com isso, se fazemos um `git status`, temos o nosso projeto limpo novamente.

E o `git restore` é um dos comandos que veio para substituir o `git checkout`. Então, o `git checkout`, como dissemos, faz muitas coisas. Uma das coisas que ele fazia é o `restore`. Com o `git checkout -- .`, temos o mesmo resultado.

Então, novamente, vamos remover as quebras de linha e salvar. Se fizermos o `git checkout -- .`, ele desfaz as alterações. Então, temos todas as nossas linhas adicionadas de novo.

Como falamos, esse `restore` restaura o projeto ou restaura arquivos específicos para algum ponto específico. Por padrão, ele faz o `restore` para `head`, ou seja, para o nosso último commit, que no nosso caso aqui é quebrando a linha do script.

Mas e se quisermos fazer o `restore` para ver o nosso projeto ou ver um arquivo específico antes de **corrigir a indentação**, ou seja, indentando os botões? Queremos ver como o arquivo era em dado commit, como o nosso projeto todo era nesse outro commit.

Então, conseguimos "viajar no tempo" também utilizando o `git restore`. E isso nós veremos no próximo vídeo.

### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)