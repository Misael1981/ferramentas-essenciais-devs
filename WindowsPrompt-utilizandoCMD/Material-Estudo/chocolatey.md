# O Comando choco list

Vimos que podemos verificar os pacotes disponíveis baixados através do site do [Chocolatey](https://chocolatey.org/), porém também é possível fazer isso pela linha de comando!

O comando `choco list` lista todos os pacotes que podem ser instalados pelo Chocolatey, mas antes de executá-lo, tome cuidado porque ele possui milhares de pacotes e seu computador vai passar um bom tempo listando-os!

Para executar uma busca por pacotes mais específica, podemos utilizar o comando `choco list` com o nome do pacote que queremos buscar:

```
choco list <nome_do_pacote>
```

Por exemplo: se utilizarmos o comando `choco list git`, serão exibidos diversos pacotes que possuem git no nome ou em suas dependências. Bem mais fácil do que procurar o pacote desejado em uma lista gigantesca, não é mesmo?!

## Pacotes locais

Uma outra opção de uso do `choco list` é para listar os pacotes locais que foram instalados pelo Chocolatey. Para isso, basta usarmos a flag `-l`, deste modo:

```
choco list -l
```

Ele exibe uma lista de todos os pacotes do seu computador! Muito útil quando queremos saber quais pacotes e suas versões que possuímos instalados.

### choco search

Você pode acabar encontrando na internet pessoas utilizando o `choco search` para fazer buscas, de um jeito muito semelhante ao que foi ensinado aqui, e se perguntando qual é a diferença. A resposta é: nenhuma! O `choco search` é um comando análogo ao `choco list` e ambos fazem a mesma coisa por baixo dos panos. Eles são intercambiáveis entre si e tudo que você pode passar como argumento em um, pode usar no outro também. Então não se preocupe, os dois fazem a mesma coisa!

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)
