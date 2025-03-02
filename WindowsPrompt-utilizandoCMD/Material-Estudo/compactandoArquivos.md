# Compactando arquivos

O comando `tar` é uma ferramenta para compactação e descompactação de arquivos.

Esse comando possui duas flags, ou parâmetros:

- `-C`: indica que a ação que realizaremos naquele momento é a compactação de arquivos;
- `-F`: para nomear o arquivo compactado ao final.

Para compactar, digitamos um hífen (`-`) indicando que queremos inserir uma flag para esse comando, junto da letra `c`, **flag de compactação**. Damos um espaço e digitamos mais um hífen com a flag `f`, de nomeação: `tar -c -f`

Podemos construir o comando desse jeito ou unificar as flags, digitando o hífen apenas uma vez e inserindo as flags em sequência: `tar -cf`.

O próximo parâmetro que esse comando exige é o nome do arquivo compactado. Vamos nomeá-lo como "notas" junto da extensão `.zip`, usada para compactar arquivos.

Por fim, passamos o que, afinal, queremos compactar. No caso, são os nossos dois arquivos XML: `NF001.xml` e `NF002.xml`.

### Exemplo:

```
Desktop>tar -cf notas.zip NF001.xml NF002.xml
```

Para ajuda ao nosso terminal com o comando `help tar`. Temos como resposta:

```
O utilitário de ajuda não dá suporte a este comando. Experimente usar "tar /?"
```
```
Desktop>tar /?
```

Com isso, nos são dadas algumas opções de como utilizar o comando `tar`. São eles e suas respectivas funções:

- **Help tar `--help`**: obter informações mais detalhadas sobre esse comando;
- **Create tar `-cf`**: compactar um arquivo
- **Extract tar `-xf`**: descompactar um arquivo
- **List tar `-tf`**: listar o conteúdo de um arquivo compactado

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)