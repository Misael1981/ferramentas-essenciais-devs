# CLI (Comand line interface)

Quando se trabalha com Prompt e cmd, é muito comum fazermos a instalação de alguns programas que oferecem uma **CLI (Comand line interface)**, no português **interface de linha de comando**. Para usarmos as funcionalidades dessas ferramentas basta integrá-las no Prompt.

## O que é CLI?

A CLI é uma interface de usuário baseada em texto que permite interagir com o computador através de comandos digitados. Ao clicar nos ícones e menus, você digita comandos para executar tarefas.

## Por que usar a CLI?

- **Eficiência**: A CLI pode ser muito mais rápida do que uma interface gráfica para determinadas tarefas.
- **Automação**: Você pode criar scripts para automatizar tarefas repetitivas.
- **Controle**: A CLI oferece um controle mais preciso sobre o sistema operacional.
- **Desenvolvimento**: Essencial para desenvolvedores, especialmente para trabalhar com Python.

### Usando uma CLI do Python no Prompt de Comando do Windows

1. **Verifique a instalação do Python**:

- Abra o Prompt de Comando (pressione a tecla Windows, digite "cmd" e pressione Enter).
- Digite python `--version` e pressione Enter.
- Se o Python estiver instalado, você verá a versão do Python. Caso contrário, você precisará instalar o Python. Você pode baixar o instalador do Python no site oficial:python.org.
- **Adicionando o Python ao PATH**: Para executar o Python diretamente do prompt de comando, você precisa adicionar o Python à variável de ambiente PATH do Windows. Durante a instalação do Python, marque a opção "Adicionar Python ao PATH". Se você já instalou o Python, você pode adicionar o Python ao PATH manualmente.

2. **Iniciando o interpretador Python**:

- No Prompt de Comando, digite `python` e pressione Enter.
- Isso iniciará o interpretador Python, onde você pode digitar e executar o código Python interativamente.

3. **Executando scripts Python**:

- Crie um arquivo Python com extensão ".py" (por exemplo, "meu_script.py").
- No Prompt de Comando, navegue até o diretório onde você salvou o arquivo usando o comando `cd`(por exemplo, `cd C:\meus_projetos`).
- Digite `python meu_script.py`e pressione Enter para executar o script.

4. **Usando o pip (gerenciador de pacotes do Python)**:

- O pip é usado para instalar e gerenciar pacotes Python.
- Para instalar um pacote, use o comando `pip install nome_do_pacote`(por exemplo, `pip install requests`).
- Para listar os pacotes instalados use o comando `pip list`.

## Comandos úteis do Prompt de Comando:

- `cd`: Alterar o diretório atual.
- `dir`: Lista os arquivos e diretórios no diretório atual.
- `mkdir`: Cria um novo diretório.
- `rmdir`: Remover um diretório.
- `cls`: Limpe a tela do Prompt de Comando.

### Exemplo de um script Python:

```
# meu_script.py
nome = input("Digite seu nome: ")
print(f"Olá, {nome}!")
```

### Executando o script:

1. Salve o código acima em um arquivo chamado "meu_script.py".
2. Abra o Prompt de Comando e navegue até o diretório onde você salvou o arquivo.
3. Digite python meu_script.pye pressione Enter.
4. Digite seu nome quando solicitado e pressione Enter.

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)
