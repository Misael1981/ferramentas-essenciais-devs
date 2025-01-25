# Adicionando Colaboradores no commit

Cada commit possui por padrão um autor, que é a pessoa que realizou aquelas alterações no código.

Entretanto, quando trabalhamos em equipe pode ser que algum trecho de código seja escrito em dupla ou trio. Assim, como definir a autoria dessas outras pessoas no commit?

O Git oferece a possibilidade de adicionar **mais de um autor** a um commit. Para isso, após escrever a mensagem do commit, pulamos duas linhas e usamos a palavra-chave `Co-authored-by:`, seguido do nome e e-mail associado ao GitHub (entre < >) de cada pessoa colaboradora.

Cada coautor deve estar em uma linha diferente, como é mostrado no exemplo a seguir:

```
$ git commit -m "Adicionar nova funcionalidade.
>
>
Co-authored-by: NOME <nome@email.com>
Co-authored-by: OUTRO-NOME <outro@email.com>"
```

Caso queira entender mais sobre coautoria no GitHub, você pode acessar a [documentação referente ao assunto](https://docs.github.com/pt/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/creating-a-commit-with-multiple-authors).


### [Voltar ao menu - Git e GitHub compartilhando e colaborando em projetos](../menu.md)