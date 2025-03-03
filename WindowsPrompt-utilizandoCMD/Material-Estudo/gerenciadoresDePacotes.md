# Gerenciadores de Pacotes

Gerenciadores de pacotes são ferramentas essenciais para automatizar a instalação, atualização e remoção de software no Windows. Vamos explorar o Winget e o Chocolatey:

## O que são Gerenciadores de Pacotes?

Gerenciadores de pacotes simplificam o processo de instalação de software, semelhante às lojas de aplicativos em smartphones. Eles automatizam o download, a instalação e a configuração de programas, economizando tempo e esforço.

### Winget

O Winget (Gerenciador de Pacotes do Windows) é uma ferramenta de linha de comando nativa do Windows, desenvolvida pela Microsoft. Ele permite instalar aplicativos do repositório oficial da Microsoft e de outras fontes.

- **Instalação**:
  - O Winget geralmente vem pré-instalado nas versões mais recentes do Windows 10 e 11.
  - Para verificar se ele está instalado, abra o Prompt de Comando ou o PowerShell e digite winget --version.
  - Se não estiver instalado, você poderá encontrá-lo na Microsoft Store.
- **Uso básico**:
  - `winget search <nome_do_aplicativo>`: Busca por aplicativos no repositório.
  - `winget install <nome_do_aplicativo>`: Instale um aplicativo.
  - `winget upgrade`: Atualiza os aplicativos instalados.
  - `winget uninstall <nome_do_aplicativo>`: Desinstale um aplicativo.
- **Vantagens**:
  - Nativo do Windows, integrado ao sistema.
  - Repositório oficial da Microsoft, garantindo segurança.
  - Simples e fácil de usar.
- **Desvantagens**:
  - O repositório ainda está em crescimento, com menos opções que o Chocolatey.

### Chocolatey

O Chocolatey é um gerenciador de pacotes de terceiros, muito popular na comunidade Windows. Ele possui um vasto repositório de aplicativos, incluindo muitos que não estão disponíveis no Winget.

- **Instalação**:

  - Abra o PowerShell como administrador.
  - Execute o seguinte comando:
    - `Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-ObjectSystem.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))`

- **Uso básico**:

- `choco search <nome_do_aplicativo>`: Busca por aplicativos no repositório.
- `choco install <nome_do_aplicativo>`: Instale um aplicativo.
- `choco upgrade all`: Atualiza todos os aplicativos instalados.
- `choco uninstall <nome_do_aplicativo>`: Desinstale um aplicativo.

- **Vantagens**:

- Vasto repositório com milhares de aplicativos.
  Comunidade ativa e suporte robusto.
- Flexível e personalizável.

- **Desvantagens**:

- Requer instalação separada.
- A segurança dos pacotes depende da comunidade.

### Qual escolher?

Se você busca uma solução nativa e simples, o Winget é uma ótima opção.
Se você precisa de um repositório mais abrangente e flexível, o Chocolatey é a escolha ideal.
Muitos usuários usam os dois em conjunto, para aproveitar o melhor de cada um.

### [Voltar ao Menu - Windows Prompt: utilizando o CMD](../menu.md)
