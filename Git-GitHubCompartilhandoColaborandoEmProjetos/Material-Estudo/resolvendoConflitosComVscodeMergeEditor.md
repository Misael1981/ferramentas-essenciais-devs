# Resolvendo conflitos com Visual Studio Code Merge Editor

Quando você está trabalhando em um projeto grande, principalmente se muitas pessoas estão envolvidas, é comum aparecerem os chamados "conflitos". 

## Mas o que são esses conflitos?

Imagine que o projeto é um grande quebra-cabeça e cada pessoa está trabalhando em uma parte dele. Se duas pessoas tentarem encaixar peças diferentes no mesmo lugar, surge um conflito. No mundo do desenvolvimento de software, isso ocorre quando duas pessoas editam o mesmo pedaço de código de formas diferentes.

Há várias formas de resolver conflitos, podemos utilizar a linha de comando ou o próprio Visual Studio Code. O editor de código fornece mais de uma forma para resolver **conflitos de mesclagem** entre o **código local** (o que está na sua máquina) e o **remoto**(o que está no github, por exemplo).

Uma possibilidade é utilizar a ferramenta **“Merge Editor”**. Vamos conferir seu funcionamento?

## Resolvendo conflitos no Merge Editor

No exemplo a seguir, nós temos duas versões de um código na branch `main`: uma no repositório do github e outra modificação diferente no ambiente local. Ao realizarmos o `git -push` para a branch `main`, ocorreu um conflito e precisamos resolvê-lo para que a atualização suba para o repositório no github corretamente, como a imagem nos apresenta:

<img src="../../img/merge-01.webp">

Para solucionarmos o problema, clicamos na opção “Resolve in Merge Editor”, como no print abaixo:

<img src="../../img/merge-02.webp">

Após o clique, somos redirecionados para outra aba que apresenta as modificações no arquivo, vamos entender o que cada opção significa:

<img src="../../img/merge-03.webp">

A tela do Visual Studio Code está dividida em três partes:

- **Incoming (remoto)**: modificações que chegam do repositório remoto.

- **Current (local)**: modificações locais.

- **Result (resultado)**: resultado do merge, ou seja, a resolução dos conflitos de mesclagem. É o estado atual do arquivo.

```
Os quadrados na cor amarela em volta do código no campo “Incoming” e “Current” são marcadores de conflito: exibem o conteúdo que apresenta conflito no arquivo.
```

### Campo Incoming

-> No **campo “Incoming”**, acima da linha de código dos marcadores de conflito no campo há outras opções que resultam na alteração do código atual:

- **Accept Incoming**: aceita modificações oriundas do remoto

<img src="../../img/merge-04.webp">

- **Accept Combination Incoming First**: realiza a combinação com as linhas do código do repositório remoto no topo.

<img src="../../img/merge-05.webp">

- **Ignore**: ignora as modificações.

### Campo Current

-> O campo **“Current”** trabalha com as modificações locais do documento.

- **Accept Current**: Aceita a modificação local no resultado do documento

- **Accept combination Current First**: Aceita a combinação local + remoto. Nos resultados a linha de código com a tag `<h2>` fica antes de `<h1>`, comprovando que o código local é inserido primeiro que o remoto.

<img src="../../img/merge-06.webp">

- **Ignore**: ignora as modificações no resultado no final.

### Após selecionarmos a opção com o resultado desejado, devemos:

1. #### Salvar o arquivo
2. #### Clicar no botão “complete Merge”
3. #### Realizar o commit das modificações
4. #### Sincronizar as modificações realizando o push.

### Para saber mais:

- [Como o Visual Studio facilita o controle de versão com o Git](https://learn.microsoft.com/pt-br/visualstudio/version-control/git-with-visual-studio?view=vs-2022)

- [Como resolver conflitos de mesclagem no Visual Studio](https://learn.microsoft.com/pt-br/visualstudio/version-control/git-resolve-conflicts?view=vs-2022)

- [Um guia muito útil para mesclar conflitos - em Inglês](https://www.youtube.com/watch?v=HosPml1qkrg)


### [Voltar ao menu - Git e GitHub compartilhando e colaborando em projetos](../menu.md)