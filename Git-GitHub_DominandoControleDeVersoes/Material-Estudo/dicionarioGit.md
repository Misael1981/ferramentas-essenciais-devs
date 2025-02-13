# Dicionário Git

- `git log`: exibe o histórico dos commits;

- `git log --oneline`: exibe apenas as mensagens do histórico dos commits;

- `git log -p`: exibe o hash completo dos commits;

- `git log --graph`: mostra um grafo com as branchs dos commits;

- `git log --pretty / git log --format`: Os dois são sinônimos, exibem o log da maneira que desejamos;

- `git log --help`: exibe um manual, uma documentação com os comandos aceitos;

- `git show { hash do commit }`: exibe todas as alterações de um commit específico.

- `git status`: mostra em qual branch estamos, e se tem alguma coisa pra fazer commit;

- `git diff`: mostra a diferença entre dois estados;

- `git branch`: Mostra quais são as branchs ou ramificações existentes no trabalho;

- `git branch -m { nomeDaBranch } { novoNomeDaBranch }`: renomeia o nome da branch;

- `git branch -d { nomeDaBranch }`: remove a branch;

- `git branch { nomeDaBranch }`: cria uma nova branch;

- `git checkout { nomeDaBranch }`: altera a branch em que estamos (***comando antigo***);

- `git checkout -b { nomeDaBranch }`: cria uma nova branch e já move para ela

- `git switch -c { nomeDaBranch }`: também cria uma nova brach e move para ela (comando novo)

- `git switch { nomeDaBranch }`: muda de branch;

- `git merge { nomeDaBranch }`: mescla as 2 branchs;


### [Voltar ao Menu - Git e GitHub: dominando controle de versão de código](../menu.md)