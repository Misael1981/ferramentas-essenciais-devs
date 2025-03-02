# Variáveis de Ambiente

Variáveis ​​de ambiente são como etiquetas que você coloca em caixas em sua casa, para que você e outras pessoas saibam o que tem dentro sem precisar abrir todas as caixas. No mundo da computação, essas "etiquetas" armazenam informações que os programas e o sistema operacional usam para funcionar corretamente.

## O que são variáveis ​​de ambiente?

- **Definição**:
    - Variáveis ​​de ambiente são valores sonoros nomeados que podem afetar o comportamento de processos em execução em um computador.
    - Elas são configurações globais que podem ser acessadas por qualquer programa em seu sistema.
- **Utilidade**:
    - **Configuração de programas**: Permite que você personalize o comportamento dos aplicativos sem precisar alterar o código-fonte.
    - **Caminhos de arquivos**: Armazenam o local de arquivos importantes, como apresentados e bibliotecas.
    - **Informações do sistema**: Contém dados sobre o sistema operacional, como o nome do usuário e o diretório inicial.
    - **Segurança**: Evite que informações fornecidas, como senhas, sejam escritas diretamente no código.

## Como usar variáveis ​​de ambiente?

A forma de usar variáveis ​​de ambiente varia dependendo do sistema operacional:

### Windows:

1. **Acessar as teclas**:

- Execute por "variáveis ​​de ambiente" no menu Iniciar e selecione "Editar as variáveis ​​de ambiente do sistema".
- Na janela que se abre, clique em "Variáveis ​​de 
Ambiente...".

2. **Criar ou editar variáveis**:

- Na seção "Variáveis ​​do usuário" ou "Variáveis ​​do sistema", clique em "Novo..." para criar uma nova variável ou selecione uma variável existente e clique em "Editar...".
- Insira o nome da variável e o valor desejado.

3. **Usar variáveis ​​em programas**:

- Os programas podem acessar variações de ambiente usando funções específicas da linguagem de programação.
- Por exemplo, em "cmd" você pode acessar as variáveis ​​usando "%NOME_DA_VARIÁVEL%".

### Linux/macOS:

1. **Edite o arquivo de configuração**:

- As variáveis ​​de ambiente são geralmente armazenadas em arquivos como `.bashrc`, `.zshrcou` `.profileno` diretório inicial do usuário.
- Abra o arquivo com um editor de texto.

2. **Adicionar ou modificar variáveis**:

- Use o seguinte formato para definir uma variável: `export NOME_DA_VARIÁVEL=valor`.
- Por exemplo, "`export CAMINHO=/home/usuario/meus_arquivos`".

3. **Aplicar as alterações**:

- Execute o comando `source ~/.bashrc`(ou o arquivo correspondente) para aplicar as alterações.

4. **Usar variáveis ​​em programas**:

- Nos terminais Linux/macOS você pode acessar as variáveis ​​usando "$NOME_DA_VARIÁVEL".

### Exemplos de variáveis ​​de ambiente:

- **PATH**: Contém uma lista de diretórios onde o sistema procura por repetidos.
- **HOME**: Indica o diretório inicial do usuário.
- **TEMP**: Armazena o local dos arquivos temporários.

### Dicas importantes:

- Tenha cuidado ao editar variáveis ​​de ambiente do sistema, pois alterações incorretas podem afetar o funcionamento do sistema operacional.
- Use nomes descritivos para suas variáveis ​​para facilitar a identificação.
- Para segurança, evite armazenar informações diretamente relacionadas a variáveis ​​de ambiente. Em vez disso, use arquivos de configuração ou ferramentas de gerenciamento de segredos.

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)