# Definir a visibilidade do repositório

Você pode escolher quem pode visualizar seu repositório.

## Tornar um repositório privado

- O GitHub desanexará os forks públicos do repositório público e os colocará em uma nova rede. Bifurcações públicas não se tornam privadas.
- Se você estiver usando GitHub Free para contas pessoais ou organizações, alguns recursos não estarão disponíveis no repositório depois de alterar a visibilidade para privada. Qualquer site publicado do GitHub Pages terá sua publicação cancelada automaticamente. Se você adicionou um domínio personalizado ao site do GitHub Pages, deverá remover ou atualizar os registros de DNS antes de tornar o repositório privado para evitar o risco de uma aquisição de domínio. Para saber mais, confira Planos do GitHub e [Gerenciar um domínio personalizado do seu site do GitHub Pages](https://docs.github.com/pt/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).
- GitHub não incluirá mais o repositório no GitHub Archive Program. Para saber mais, confira [Sobre o arquivamento de conteúdo e dados no GitHub](https://docs.github.com/pt/repositories/archiving-a-github-repository/about-archiving-content-and-data-on-github#about-the-github-archive-program).
- As funcionalidades de GitHub Advanced Security, como code scanning, irão parar de funcionar Para saber mais, confira [Sobre a Segurança Avançada do GitHub](https://docs.github.com/pt/get-started/learning-about-github/about-github-advanced-security).

## Consequências de alterar a visibilidade de um repositório

### Alterar de público para privado

- Estrelas e observadores deste repositório serão apagados permanentemente, o que afetará as classificações do repositório.
- As regras de alerta personalizadas de Dependabot serão desabilitadas, a menos que GitHub Advanced Security esteja habilitado para este repositório. O gráfico de dependência e Dependabot alerts permanecerão habilitados com permissão para executar a análise somente leitura neste repositório.
- A verificação de código ficará indisponível.
- As bifurcações atuais permanecerão públicas e serão desanexadas deste repositório.

### Alterar de privado para público

- O código ficará visível para todos que puderem visitar o GitHub.com.
- Qualquer pessoa pode bifurcar seu repositório.
- Todos os conjuntos de regras por push serão desabilitados.
- Suas alterações serão publicadas como atividade.
- O histórico e logs do Actions ficarão visíveis para todos.
- Estrelas e observadores deste repositório serão apagados permanentemente.

### Alterar de privado para interno

- Todos os membros da empresa terão acesso de leitura.
- Colaboradores externos não podem mais ser adicionados a bifurcações, a menos que sejam adicionados à raiz.
- Estrelas e observadores deste repositório serão apagados permanentemente.

### Alterar de interno para privado

- Estrelas e observadores deste repositório serão apagados permanentemente, o que afetará as classificações do repositório.
- As regras de alerta personalizadas Dependabot serão desabilitadas, a menos que o GitHub Advanced Security esteja habilitado para este repositório. O gráfico de dependência e Dependabot alerts permanecerão habilitados com permissão para executar a análise somente leitura neste repositório.
- A verificação de código ficará indisponível.
- As bifurcações atuais permanecerão públicas e serão desanexadas deste repositório.

### Alterar de interno para público

- O código ficará visível para todos que puderem visitar o GitHub.com.
- Qualquer pessoa pode bifurcar seu repositório.
- Todos os conjuntos de regras por push serão desabilitados.
- Suas alterações serão publicadas como atividade.
- O histórico e logs do Actions ficarão visíveis para todos.
- Estrelas e observadores deste repositório serão apagados permanentemente.

### Alterar de público para interno

- Todos os membros da empresa terão acesso de leitura.
- Colaboradores externos não podem mais ser adicionados a bifurcações, a menos que sejam adicionados à raiz.
- Estrelas e observadores deste repositório serão apagados permanentemente.

## Alterar a visibilidade de um repositório

1. Em GitHub, acesse a página principal do repositório.

2. Abaixo do nome do repositório, clique em  Configurações. Caso não consiga ver a guia "Configurações", selecione o menu suspenso  , clique em Configurações.

<img src="../../img/vidibilidade.webp">

3. Captura de tela de um cabeçalho de repositório que mostra as guias. A guia "Configurações" é realçada por um contorno laranja-escuro.
Na seção "Zona de Perigo", à direita de "Alterar visibilidade do repositório", clique em Alterar visibilidade.

4. Selecione uma visibilidade.

5. Para verificar se você está alterando a visibilidade do repositório correto, digite o nome do repositório que deseja alterar a visibilidade.

5. Clique em Entendi. Alterar a visibilidade do repositório.

- ### [Artigo - Definir a visibilidade do repositório](https://docs.github.com/pt/repositories/managing-your-repositorys-settings-and-features/managing-repository-settings/setting-repository-visibility)

### [Voltar ao menu - Git e GitHub compartilhando e colaborando em projetos](../menu.md)