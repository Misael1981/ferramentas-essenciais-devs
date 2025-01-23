# Básico do GitHub: Começando a sua jornada

## O que é o GitHub?

Imagine o GitHub como um repositório online onde você pode armazenar, gerenciar e colaborar em seus projetos de programação. É como um Google Drive para desenvolvedores, mas com muito mais recursos para controlar as mudanças no seu código e trabalhar em equipe.

## Por que usar o GitHub?

- **Controle de Versões**: O GitHub utiliza o Git, um sistema de controle de versões que permite acompanhar todas as alterações feitas no seu código ao longo do tempo. Isso significa que você pode voltar às versões anteriores, comparar diferentes versões e ver quem fez quais modificações.
- **Colaboração**: O GitHub facilita a colaboração entre desenvolvedores. Você pode criar projetos em equipe, revisar o código de outros membros, discutir ideias e trabalhar juntos para construir software de alta qualidade.
- **Hospedagem de Projetos**: O GitHub oferece um espaço gratuito para hospedar seus projetos públicos. Isso permite que outras pessoas vejam, usem e contribuam com o seu código.
- **Comunidade**: O GitHub é uma grande comunidade de desenvolvedores. Você pode encontrar projetos open source, aprender com outros desenvolvedores e construir sua própria rede profissional.

### Conceitos Essenciais:

- **Repositório**: É como uma pasta onde você armazena todos os arquivos do seu projeto. Cada projeto tem seu próprio repositório.
- **Filial**: Uma filial é uma cópia de um repositório. Ela permite que você trabalhe em novas funcionalidades sem afetar o código principal.
- **Commit**: Um commit é uma segurança das alterações feitas no seu código. Cada commit inclui uma mensagem descrevendo as mudanças.
- **Pull Request**: Um pull request é uma solicitação para que as alterações de uma branch sejam mescladas com a branch principal.

### Começando a usar o GitHub:

1. **Crie uma conta**: Acessehttps://github.com/e crie uma conta gratuita.
2. **Crie um repositório**: Clique no botão "Novo repositório" e configure as opções do seu novo repositório.
3. **Clone o repositório**: Clone o repositório para o seu computador usando o Git Bash ou outro terminal.
4. **Faça alterações**: Edite os arquivos do seu projeto e adicione novas funcionalidades.
5. **Faça commit das alterações**: Use o comando `git commit` para salvar as alterações.
6. **Faça push das alterações**: Use o comando `git push` para enviar as alterações para o repositório remoto no GitHub.

### Recursos Úteis:

- [**Documentação do GitHub**:](https://docs.github.com/)
- **Tutoriais em vídeo**: O YouTube oferece diversos tutoriais em vídeo sobre o GitHub para todos os níveis.
Exemplo Básico:

```
# Criar um novo diretório para o projeto
mkdir meu-projeto
cd meu-projeto

# Inicializar um novo repositório Git
git init

# Criar um arquivo
touch README.md

# Adicionar o arquivo ao staging area
git add README.md

# Commit das alterações
git commit -m "Primeira mensagem de commit"

# Conectar o repositório local ao repositório remoto no GitHub
git remote add origin https://github.com/seu-usuario/meu-projeto.git

# Enviar as alterações para o GitHub
git push -u origin main
```

E muito mais!

O GitHub oferece uma variedade de recursos e funcionalidades que vão além deste tutorial básico. Explore a plataforma e descubra como ela pode te ajudar a se tornar um desenvolvedor mais eficiente e colaborativo.

### [Voltar ao menu - Git e GitHub compartilhando e colaborando em projetos](../menu.md)