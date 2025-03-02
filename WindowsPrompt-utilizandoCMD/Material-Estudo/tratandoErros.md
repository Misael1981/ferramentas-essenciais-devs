# Tratamento de erros

Durante o vídeo **Tratando erros**, criamos o seguinte script:

```
@echo off
echo `Compactando arquivos`
tar -cf notas.zip *.xml  2>erros.txt

IF %ERRORLEVEL% NEQ 0 (echo "Erro na execução do script.")
```

Agora vamos entender em detalhes cada uma das linhas desse script:

```
@echo off
```

Com esse comando desabilitamos a exibição dos comandos no prompt do Windows relacionados ao conteúdo das instruções contidas no arquivo.

Vamos usar como exemplo o script `exemplo.bat`, com o conteúdo `echo Olá Mundo!`. Ao executarmos esse simples script, teremos como retorno o seguinte:

```
c:\Users\Emerson\Desktop>.\exemplo.bat

c:\Users\Emerson\Desktop>echo Olá Mundo
Olá Mundo

c:\Users\Emerson\Desktop>
```

Ao  adicionarmos o `@echo off`, teremos como resultado:

```
c:\Users\Emerson\Desktop>.\exemplo.bat
Olá Mundo

c:\Users\Emerson\Desktop>
```

Perceba que não é exibido qual é o comando dentro do arquivo, apenas o seu resultado.

```
echo `Compactando arquivos`
```

Com este comando, exibimos uma mensagem para o usuário sobre a compactação.

```
tar -cf notas.zip *.xml  2>erros.txt
```

Para lidar com arquivos compactados, usamos o comando `tar`. Podemos ver mais detalhes com o comando `tar /?`, que retorna as seguintes informações:

```
C:\Users\Emerson\Desktop>tar /? 

Usage:

List: tar -tf <archive-filename>
Extract: tar -xf <archive-filename>
Create: tar -cf <archive-filename> [filenames…]
Help: tar --help
```

Visto que queremos compactar um arquivo, usamos as flags `cf`.

O próximo argumento, o `notas.zip`, é o nome do arquivo quando for compactado, seguido do que eu quero compactar, no caso, `*.xml`. Com isso, estamos falando que todos os arquivos que terminam com a extensão `.xml` serão compactados.

Finalizando o comando, temos `2>erros.txt`, que nos diz que estamos redirecionando a saída do comando (ou seja, pegando o resultado gerado pelo `tar` e levando para algum lugar).

```
IF %ERRORLEVEL% NEQ 0 (echo "Erro na execução do script.")
```

E, por fim, fazemos uma condição representada pelo `IF`, indicando que se o conteúdo da variável `ERRORLEVEL` não for igual (`NEQ`, ou seja, Not EQual to) a zero, nós exibimos uma mensagem à pessoa informando que não foi possível encontrar os arquivos.

Quase todos os aplicativos e utilitários definirão um código de saída representado pela variável `ERRORLEVEL`. Quando seu valor é zero, indica que houve sucesso na execução. Como estamos avaliando o caso de ser diferente de zero, estamos tratando justamente quando houver algum erro.

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)