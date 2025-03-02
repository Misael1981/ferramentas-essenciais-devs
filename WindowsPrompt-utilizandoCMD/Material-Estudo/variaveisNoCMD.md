# Varáveis no Ambiente CMD

Quando trabalhamos com **script** é comum precisarmos **armazenar uma informação** de forma temporária.

Para isso, nosso computador oferece um espaço de memória chamado **variávies**, justamente para podermos colocar uma informação no mesmo espaço de memória e depois sobrepor com outra informação.

Isso acontece quando criamos nossos scripts e também em programas externos, como Java e Python, por exemplo.

## Criando Variáveis

Para se criar uma variável, insere-se o comando `set`, em seguida o **nome da vriável** e depois o sinal `=` para atribuir, ou seja, dar um valor a essa variável.

```
set nome = Misael
```

Para exibirmos um conteúdo no nosso Prompt, podemos usar o comando `echo`. Porém, para exibirmos o conteúdo dentro de uma variável precisamos colocá-la entre porcentagens.

```
echo %nome% 
// Misael
```

No ambiente CMD (Prompt de Comando) do Windows, você pode trabalhar com variáveis ​​de ambiente de algumas maneiras:

1. **Exibindo Variáveis ​​de Ambiente**:

- **Comando `set`**:
    - Ao digitar `set` no CMD e pressionar Enter, você verá uma lista de todas as variáveis ​​de ambiente atuais e seus valores.
    - Para ver o valor de uma variável específica, use `set NOME_DA_VARIAVEL`. Por exemplo, `set PATH` você exibirá o valor da variável PATH.

2. **Definindo Variáveis ​​de Ambiente**:

- **Comando `set NOME_DA_VARIAVEL=valor`**:
    - Este comando define uma variável de ambiente com o nome e valor especificados.
    - **Exemplo**: s`et MINHA_VARIAVEL=teste` crie uma variável chamada MINHA_VARIAVEL com o valor "teste".
    - **Importante**: Variáveis ​​definidas com `set` essa forma só existem durante a sessão atual do CMD. Quando você fecha o CMD, eles desaparecem.
3. **Definindo Variáveis ​​de Ambiente Permanente**:

- **Usando o comando `setx`**:
    - O comando `setx`permite definir variáveis ​​de ambiente que persistem mesmo após o fechamento do CMD.
    - **Exemplo**:`setx MINHA_VARIAVEL_PERMANENTE "valor permanente"`
    - **Observação**:
        - O comando `setx` altera as variáveis ​​de ambiente do sistema, então use-o com cuidado.
        - As alterações feitas com o comando `setx` não aparecem na sessão de cmd que está aberta. É necessário abrir um novo cmd para que as alterações sejam mostradas.

- **Através das Propriedades do Sistema**:
    - Você também pode definir variáveis ​​de ambiente permanentes através da interface gráfica do Windows:
        1. Execute por "variáveis ​​de ambiente" no menu Iniciar e selecione **"Editar as variáveis ​​de ambiente do sistema"**.
        2. **Na janela que se abre, clique em "Variáveis ​​de Ambiente..."**.
        3. **Na seção "Variáveis ​​do usuário"** ou "**Variáveis ​​do sistema**", clique em "Novo..." para criar uma nova variável ou selecione uma variável existente e clique em "Editar...".   

4. **Usando Variáveis ​​de Ambiente no CMD**:

- **Sintaxe `%NOME_DA_VARIAVEL%`**:
    - Para usar o valor de uma variável de ambiente em um comando CMD, coloque o nome da variável entre sinais de porcentagem (%).
    - **Exemplo**: `echo %MINHA_VARIAVEL%` exibirá o valor da variável MINHA_VARIAVEL.

### Exemplos Práticos:

- **s`et TEMP`**: Exibe o diretório de arquivos temporários do sistema.
- **`set PATH`**: Mostra os diretórios onde o sistema procura por arquivos abaixo.
- **`setx TESTE "Este é um teste"`**: Defina uma variável de ambiente permanente TESTE.
- **`echo %TESTE%`**: Exibe o valor da variável TESTE.

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)