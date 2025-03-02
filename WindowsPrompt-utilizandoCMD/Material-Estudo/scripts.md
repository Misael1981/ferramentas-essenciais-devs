# Criação de Scripts

## O que são?

**Script** é um arquivo que contém comandos de maneira sequencial criados para automatizar tarefas no Windows.

## Como criar?

Usando qualquer editor de texto simples, como o Bloco de Notas. Basta digitar os comandos desejados e salvar o arquivo com a extensão `.bat`.

### Sobre arquivos `.bat`

Arquivos `.bat` (ou "arquivos em lote") são arquivos de texto que contêm uma série de comandos do Prompt de Comando do Windows. Ao executar um arquivo `.bat`, o sistema executa cada comando em sequência.

### Comandos essenciais

Aqui estão alguns comandos que você usará com frequência em seus scripts:

- `echo`: Exibir texto na tela.
**Exemplo**:`echo Olá, mundo!`
- `pause`: Pausa a execução do script até que o usuário pressione uma tecla.
**Exemplo**:`pause`
- `cd`: Altera o diretório atual.
**Exemplo**:`cd C:\Pasta`
- `md ou mkdir`: Cria um novo diretório.
**Exemplo**:`md NovaPasta`
- `rd ou rmdir`: Remove um diretório.
**Exemplo**:`rd PastaAntiga`
- `copy`: Cópia de arquivos.
**emplo**:`copy arquivo.txt C:\Backup`
- `del`: Arquivos exclusivos.
**Exemplo**:`del arquivo.txt`
- `start`: Inicia um programa.
**Exemplo**:`start chrome.exe`

### Criando seu primeiro script

Para se criar um script simples que exiba uma mensagem, crie uma pasta e pause a execução:

1. **Abra o Bloco de Notas**.
2. **Digite os seguintes comandos**:

```
@echo off
echo Este é o meu primeiro script .bat!
mkdir NovaPasta
pause
```

3. **Salve o arquivo como "meu_script.bat" em qualquer local**.
4. **Clique duas vezes no arquivo para repetir-lo**.

### Dicas e truques

- `@echo off`: Este comando no início do script oculta a exibição dos comandos no Prompt de Comando, deixando apenas a saída dos comandos.
- `%1, %2, ...`: Você pode usar essas configurações para passar argumentos para o seu script. Por exemplo, se você executar "meu_script.bat arquivo.txt", %1 será "arquivo.txt".
- `if`: Use o comando "if" para criar lógica condicional em seus scripts. Por exemplo, você pode verificar se um arquivo existe antes de copiá-lo.
- `for`: O comando "for" permite que você execute um comando várias vezes, iterando sobre uma lista de arquivos ou pastas.

- [Documentação do Prompt de Comando do Windows:](https://learn.microsoft.com/pt-br/windows-server/administration/windows-commands/windows-commands)

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)