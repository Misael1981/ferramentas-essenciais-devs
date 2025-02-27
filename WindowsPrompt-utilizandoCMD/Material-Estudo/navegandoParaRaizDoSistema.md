# Navegando para a Raiz do Sistema

O `cd` (change directory), que nos permite mudar o diretório atual de trabalho para outro especificado. Se quisermos ir para a área de trabalho (Desktop), por exemplo, basta digitar: `cd Desktop`.

```
Microsoft Windows [versão 10.0.2200.1335]
(c) Microsoft Corporation. Todos os direitos reservados.

c:\Users\Emerson>cd Desktop

c:\Users\Emerson\Desktop>
```

Observamos, ao abrir o cmd, que o ponto de partida é a pasta de usuário e que podemos voltar para o diretório anterior com o comando `cd ..`.

```
Microsoft Windows [versão 10.0.2200.1335]
(c) Microsoft Corporation. Todos os direitos reservados.

c:\Users\Emerson>cd Desktop

c:\Users\Emerson\Desktop>cd ..

c:\Users\Emerson>
```

Mas o que será que acontece se tentarmos voltar vários diretórios? Qual o diretório inicial que gera todos os outros?

```
Microsoft Windows [versão 10.0.2200.1335]
(c) Microsoft Corporation. Todos os direitos reservados.

c:\Users\Emerson>cd Desktop

c:\Users\Emerson\Desktop>cd ..

c:\Users\Emerson>cd ..\..\..\..\..\..\..\..\..\..\..\..\..\..\..\..\..\..\
```

Se tentarmos voltar para o diretório anterior quantas vezes quisermos, pararemos no diretório C: que, para o sistema operacional Windows, é o primeiro ou mais alto diretório em uma hierarquia, o qual chamamos de diretório raiz.

Podemos compará-lo a uma árvore onde todos os ramos existentes partiram de uma raiz, assim todos os diretórios partem dessa pasta.

Ao abrir o cmd ou qualquer diretório que estivermos, podemos acessar o diretório raiz de forma prática através do comando `cd /`.

```
c:\Users\Emerson>cd /
c:\>
```

Caso queira visualizar o conteúdo desse diretório, basta usar o comando dir:

```
c:\dir
O volume na unidade C é Windows-SSD
O Número de Série do Volume é 5E18-9CE7

Pasta de c:\

15/05/2022 13:06   <DIR>      $WINDOWS.~BT
11/05/2022 13:41   <DIR>      Drivers
15/05/2022 07:01   <DIR>      Program Files
26/12/2022 18:28   <DIR>      Program Files (x86)
29/03/2022 07:01   <DIR>      Users
26/12/2022 07:01   <DIR>      Windows

              0 arquivo(s)               0 bytes
              6 pasta(s)  56.535.347.200 bytes disponíveis
```

E, aqui, vemos algumas pastas importantes para o funcionamento do nosso sistema, como:

- **Users**: aqui estão as informações dos usuários existentes no computador. Diretórios como Documentos, Downloads, Música, Vídeo e qualquer arquivo na área de trabalho estão disponíveis nesta pasta.

- **Program Files**: também conhecida como “Arquivos de Programas”, em português; por padrão, é a pasta para instalar aplicativos de terceiros no Windows. A pasta inclui diferentes opções de subpastas onde um aplicativo instalado é armazenado.

- **Program Files (x86)**: é outra opção de pasta disponível no diretório raiz que inclui aplicativos de 32 bits. Sempre que instalamos um aplicativo de 32 bits em um Windows de 64 bits, ele se move diretamente para os “Arquivos de Programas (x86)”.

- **Windows**: este diretório é onde todos os arquivos principais do sistema operacional estão armazenados, incluindo a famosa pasta System32, entre outras.

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)