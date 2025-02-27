# Outros Comandos Interessantes do Windows

O cmd oferece diversos outros comandos, como:

- `fc`: **File Compare** ou “Comparação de Arquivos” (em português); compara dois arquivos ou grupos de arquivos e mostra as diferenças entre eles. Caso não haja diferença, uma mensagem é exibida informando que nenhuma diferença foi encontrada. Por exemplo:

```
C:\Users\Emerson\Desktop>type a.txt
texto a

C:\Users\Emerson\Desktop>type b.txt
texto b

C:\Users\Emerson\Desktop>fc a.txt b.txt
Comparando os arquivos a.txt e B.TXT
***** a.txt
texto a
***** B.TXT
texto b
*****

C:\Users\Emerson\Desktop>fc a.txt a.txt
Comparando os arquivos a.txt e A.TXT
FC: nenhuma diferença encontrada
```

- `systeminfo`: como o nome do comando sugere, ele traz informações em detalhes sobre o seu Windows.
- `rmdir`: vimos o `mkdir` para criar um diretório, mas caso queiramos excluí-lo, usamos o `rmdir` (**remove directory** ou, em português, remover diretório). **Obs**: o comando `del` também pode ser utilizado para excluir um diretório.
- `shutdown`: permite desligar ou reiniciar o computador de forma imediata ou agendada.
- `date`: exibe a data atual e permite alterá-la. Por 
exemplo:

```
C:\Users\Emerson\Desktop>date
Data atual: 04/01/2023
Digite a nova data: (dd-mm-aa)  _
```

- `find`: busca uma sequência de texto em um arquivo ou arquivos. Por exemplo:

```
C:\Users\Emerson\Desktop>type exemplo.txt
Estou muito feliz, pois estou aprendendo mais sobre o prompt de comando

C:\Users\Emerson\Desktop>find “triste” exemplo.txt
- - - - - - - - - -  EXEMPLO.TXT

C:\Users\Emerson\Desktop>find “feliz” exemplo.txt
- - - - - - - - - -  EXEMPLO.TXT
    Estou muito feliz, pois estou aprendendo mais sobre o prompt de comando
```

- `exit`: fecha o cmd.

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)