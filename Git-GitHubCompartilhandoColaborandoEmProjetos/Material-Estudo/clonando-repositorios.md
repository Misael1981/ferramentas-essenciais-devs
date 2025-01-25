# Clonando Repositórios no GitHub

## O que é clonar um repositório?

Quando você clona um repositório, você está criando uma cópia completa dele no seu computador. Isso significa que você terá acesso a todos os arquivos, histórico de versões e ramificações do projeto original.

### Por que clonar um repositório?

- **Trabalhar localmente**: Fazer atualizações diretamente no seu computador, sem precisar estar conectado à internet ou no tempo todo.
- **Crie um ambiente de desenvolvimento isolado**: testar novas ideias sem afetar o projeto original.
- **Colabore com outros desenvolvedores**: Trabalhar em conjunto em um mesmo projeto.
- **Fazer um fork**: Criar sua própria versão do projeto para realizar modificações sem afetar o original (mais sobre isso em outro momento).

## Como clonar um repositório?

1. **Abra o terminal (ou Git Bash, se você estiver no Windows).**

2. **Navegue até o diretório onde você deseja clonar o repositório.**

3. **Copie a URL do repositório. No GitHub, você encontra essa URL clicando no botão “Code” e, em seguida, copiando a URL HTTPS.**

4. **Execute o comando:**

```
git clone https://[usuário]/[repositório].git
```

### Substituído:

- `[usuário]` pelo nome de usuário do proprietário do repositório.
- `[repositório]` pelo nome do repositório.

### Exemplo:

```
git clone https://github.com/freeCodeCamp/freecodecamp.git
```

5. #### Pressione Enter. O Git irá clonar o repositório para o seu computador.

### Observações:

- **SSH**: Se você preferir usar SSH, uma URL diferente será. Consulte a documentação do GitHub para mais informações.
- **GitHub Desktop**: Você também pode clonar repositórios usando o GitHub Desktop, uma interface gráfica para o Git.

### E as vantagens?

As vantagens de clonar um repositório já foram mencionadas, mas vale a pena reforçar:

- **Controle de versão**: O Git permite que você acompanhe todas as alterações feitas no código ao longo do tempo, facilitando a volta para versões anteriores se necessário.
- **Colaboração**: O Git facilita a colaboração entre desenvolvedores, permitindo que várias pessoas trabalhem no mesmo projeto simultaneamente.
- **Distribuído**: O Git é um sistema de controle de versão distribuída, o que significa que cada desenvolvedor possui uma cópia completa do repositório, tornando o processo mais eficiente e robusto.

### [Voltar ao menu - Git e GitHub compartilhando e colaborando em projetos](../menu.md)