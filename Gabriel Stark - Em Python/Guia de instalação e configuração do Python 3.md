# ![Guia de instalação e configuração do Python 3](https://files.realpython.com/media/Python-3-Installation--Setup-Guide_Watermarked.62f654dcab67.jpg)

## Guia de instalação e configuração do Python 3

Assista agoraEste tutorial tem um curso em vídeo relacionado criado pela equipe Real Python. Assista junto com o tutorial escrito para aprofundar sua compreensão: [**Noções básicas de Python: configurando Python**](https://realpython.com/courses/setting-up-python/)

Instalar ou atualizar o Python no seu computador é o primeiro passo para se tornar um programador Python. Existem vários métodos de instalação: você pode baixar distribuições oficiais do Python em [Python.org](https://python.org/) , instalar a partir de um gerenciador de pacotes e até mesmo instalar distribuições especializadas para computação científica, Internet das Coisas e sistemas embarcados.

Este tutorial se concentra nas distribuições oficiais, pois geralmente são a melhor opção para começar a aprender a programar em Python.

**Neste tutorial você aprenderá como:**

* Verifique qual **versão** do Python, se houver, está instalada em sua máquina
* Instale ou atualize Python no **Windows** , **macOS** e **Linux**
* Use Python em **dispositivos móveis** como telefones ou tablets
* Use Python na Web com **intérpretes online**

Não importa em qual sistema operacional você esteja, este tutorial irá ajudá-lo. Encontre seu sistema operacional abaixo e mergulhe!

## Como instalar Python no Windows

Existem três métodos de instalação no Windows:

1. A loja da Microsoft
2. O instalador completo
3. Subsistema Windows para Linux

Nesta seção, você aprenderá como verificar qual versão do Python, se houver, está instalada em seu computador Windows. Você também aprenderá qual dos três métodos de instalação deve usar. Para obter um guia mais abrangente, consulte [Seu ambiente de codificação Python no Windows: guia de configuração](https://realpython.com/python-coding-setup-windows/) .

[Remover propagandas](https://realpython.com/account/join/)

### Como verificar sua versão do Python no Windows

Para verificar se você já possui Python em sua máquina Windows, primeiro abra um aplicativo de linha de comando, como o PowerShell.

**Dica:** veja como você abre o PowerShell:

1. Pressione a Tecla Windows.
2. Escreva `PowerShell`.
3. Pressione a tecla Enter.

Alternativamente, você pode clicar com o botão direito no botão *Iniciar* e selecionar *Windows PowerShell* ou *Windows PowerShell (Admin)* .

Você também pode usar `cmd.exe`o [Terminal do Windows](https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab) .

**Nota:** Para saber mais sobre suas opções para o terminal do Windows, consulte [Usando o Terminal no Windows](https://realpython.com/courses/using-terminal-windows/) .

Com a linha de comando aberta, digite o seguinte comando e pressione Enter:

Prompt de comando do Windows

```py
C:\> python --version
Python 3.8.4
```

Usar a `--version`opção mostrará a versão que está instalada. Alternativamente, você pode usar a `-V`opção:

Prompt de comando do Windows

```py
C:\> python -V
Python 3.8.4
```

Em ambos os casos, se você vir uma versão inferior a `3.8.4`, que era a versão mais recente no momento em que este artigo foi escrito, você desejará atualizar sua instalação.

**Observação:** se você não tiver uma versão do Python em seu sistema, ambos os comandos acima iniciarão a Microsoft Store e o redirecionarão para a página do aplicativo Python. Você verá como concluir a instalação da Microsoft Store na próxima seção.

Se estiver interessado em saber onde a instalação está localizada, você pode usar o `where.exe`comando no `cmd.exe`ou no PowerShell:

Prompt de comando do Windows

```py
C:\> where.exe python
C:\Users\mertz\AppData\Local\Programs\Python\Python37-32\python.exe
```

Observe que o `where.exe`comando funcionará apenas se o Python tiver sido instalado em sua conta de usuário.

### Quais são suas opções

Conforme mencionado anteriormente, existem três maneiras de instalar a distribuição oficial do Python no Windows:

1. **Pacote da Microsoft Store:** O método de instalação mais simples no Windows envolve a instalação a partir do aplicativo Microsoft Store. Isso é recomendado para usuários iniciantes de Python que procuram uma experiência interativa fácil de configurar.
2. **Instalador completo:** esta abordagem envolve o download do Python diretamente do [site Python.org](https://www.python.org/) . Isso é recomendado para desenvolvedores intermediários e avançados que precisam de mais controle durante o processo de configuração.
3. **Subsistema Windows para Linux (WSL):** O WSL permite executar um ambiente Linux diretamente no Windows. Você pode aprender como habilitar o WSL lendo o [Guia de instalação do subsistema Windows para Linux para Windows 10](https://docs.microsoft.com/en-us/windows/wsl/install-win10) .

Nesta seção, focaremos apenas nas duas primeiras opções, que são os métodos de instalação mais populares em um ambiente Windows.

Se quiser instalar no WSL, você pode ler a [seção Linux](https://realpython.com/installing-python/#how-to-install-python-on-linux) deste tutorial depois de instalar a distribuição Linux de sua escolha.

**Nota:** Você também pode concluir a instalação no Windows usando distribuições alternativas, como [Anaconda](https://www.anaconda.com/) , mas este tutorial cobre apenas distribuições oficiais.

Anaconda é uma plataforma popular para fazer computação científica e ciência de dados com Python. Para saber como instalar o Anaconda no Windows, consulte [Configurando Python para aprendizado de máquina no Windows](https://realpython.com/python-windows-machine-learning-setup/) .

Os dois instaladores oficiais do Python para Windows não são idênticos. O pacote da Microsoft Store tem algumas limitações importantes.

#### Limitações do pacote Microsoft Store

A documentação oficial do Python tem a dizer sobre o pacote da Microsoft Store:

> O pacote da Microsoft Store é um interpretador Python facilmente instalável, destinado principalmente ao uso interativo, por exemplo, por estudantes. ( [Fonte](https://docs.python.org/3/using/windows.html#the-microsoft-store-package) )

A principal conclusão aqui é que o pacote da Microsoft Store é “destinado principalmente ao uso interativo”. Ou seja, o pacote da Microsoft Store foi projetado para ser usado por estudantes e pessoas que estão aprendendo a usar Python pela primeira vez.

Além de ser voltado para Python listas iniciantes, o pacote Microsoft Store tem limitações que o tornam inadequado para um ambiente de desenvolvimento profissional. Em particular, ele [não tem acesso total de gravação a locais compartilhados](https://docs.python.org/3/using/windows.html#known-issues) , como `TEMP`o Registro.

#### Recomendações do instalador do Windows

Se você é novo no Python e está focado principalmente em aprender a linguagem em vez de criar software profissional, instale a partir do pacote da Microsoft Store. Isso oferece o caminho mais curto e fácil para começar com o mínimo de complicações.

Por outro lado, se você é um desenvolvedor experiente que deseja desenvolver software profissional em um ambiente Windows, o instalador oficial do Python.org é a escolha certa. Sua instalação não será limitada pelas políticas da Microsoft Store e você poderá controlar onde o executável será instalado e até mesmo [adicionar Python,`PATH`](https://realpython.com/add-python-to-path/) se necessário.

### Como instalar da Microsoft Store

Se você é novo no Python e deseja começar rapidamente, o pacote Microsoft Store é a melhor maneira de começar a trabalhar sem complicações. Você pode instalar da Microsoft Store em duas etapas.

#### Etapa 1: abra a página do aplicativo Python na Microsoft Store

Abra o aplicativo Microsoft Store e pesquise `Python`.

Você provavelmente verá várias versões que pode optar por instalar:

![![Os resultados da pesquisa da Microsoft Store para ](https://files.realpython.com/media/Screen_Shot_2020-07-16_at_11.06.17_AM.4b41c401c5aa.png)](https://files.realpython.com/media/Screen_Shot_2020-07-16_at_11.06.17_AM.4b41c401c5aa.png)

Selecione *Python 3.8* ou o número de versão mais alto disponível no aplicativo para abrir a página de instalação.

**Aviso:** certifique-se de que o aplicativo Python selecionado seja criado pela **Python Software Foundation** .

O pacote oficial da Microsoft Store sempre será gratuito, portanto, se o aplicativo custar dinheiro, então é o aplicativo **errado .**

Alternativamente, você pode abrir o PowerShell e digitar o seguinte comando:

Prompt de comando do Windows

```py
C:\> python
```

Se você ainda não tiver uma versão do Python em seu sistema, ao pressionar Enter, a Microsoft Store será iniciada automaticamente e levará você para a versão mais recente do Python na loja.

#### Etapa 2: instale o aplicativo Python

Depois de selecionar a versão a ser instalada, siga estas etapas para concluir a instalação:

1. Clique *em Obter* .
2. Aguarde o download do aplicativo. Quando o download terminar, o botão *Obter* será substituído por um botão que diz *Instalar em meus dispositivos* .
3. Clique em *Instalar em meus dispositivos* e selecione os dispositivos nos quais deseja concluir a instalação.
4. Clique em *Instalar agora* e depois *em OK* para iniciar a instalação.
5. Se a instalação for bem-sucedida, você verá a mensagem “Este produto está instalado” na parte superior da página da Microsoft Store.

Parabéns! Agora você tem acesso ao Python, incluindo[`pip`](https://realpython.com/what-is-pip/)

### Como instalar a partir do instalador completo

Para desenvolvedores profissionais que precisam de um ambiente de desenvolvimento Python completo, instalar a partir do instalador completo é a escolha certa. Oferece mais personalização e controle sobre a instalação do que a instalação na Microsoft Store.

Você pode instalar a partir do instalador completo em duas etapas.

#### Etapa 1: Baixe o instalador completo

Siga estas etapas para baixar o instalador completo:

1. Abra uma janela do navegador e navegue até a [página de downloads do Python.org para Windows](https://www.python.org/downloads/windows/) .
2. No título “Versões do Python para Windows”, clique no link para a *versão mais recente do Python 3 - Python* 3.xx. No momento em que este livro foi escrito, a versão mais recente era Python 3.8.4.
3. Role até a parte inferior e selecione *o instalador executável do Windows x86-64 para 64 bits* ou *o instalador executável do Windows x86 para 32 bits* .

Se não tiver certeza se deve selecionar o instalador de 32 ou 64 bits, você pode expandir a caixa abaixo para ajudá-lo a decidir.

Python de 32 ou 64 bits?Aparecer esconder

Quando o download do instalador terminar, vá para a próxima etapa.

#### Etapa 2: execute o instalador

Depois de escolher e baixar um instalador, execute-o clicando duas vezes no arquivo baixado. Uma caixa de diálogo como a abaixo aparecerá:

[![Caixa de diálogo de instalação do Windows](https://files.realpython.com/media/Screen_Shot_2020-07-16_at_11.19.15_AM.6e62bfc6eede.png)](https://files.realpython.com/media/Screen_Shot_2020-07-16_at_11.19.15_AM.6e62bfc6eede.png)

Há quatro coisas a serem observadas sobre esta caixa de diálogo:

1. O caminho de instalação padrão está no [`AppData/`diretório](https://superuser.com/questions/656003/why-is-python-for-windows-not-installed-in-programfiles-c-program-files) do usuário atual do Windows.
2. O botão *Personalizar instalação* pode ser usado para personalizar o local de instalação e quais recursos adicionais serão instalados, incluindo `pip`IDLE.
3. A caixa de seleção *Instalar iniciador para todos os usuários (recomendado)* está marcada por padrão. Isso significa que todos os usuários da máquina terão acesso ao [`py.exe` inicializador](https://docs.python.org/3/using/windows.html#launcher) . Você pode desmarcar esta caixa para restringir o Python ao usuário atual do Windows.
4. A caixa de seleção *Adicionar Python 3.8 a `PATH`* está desmarcada por padrão. Existem [vários motivos](https://discuss.python.org/t/could-we-add-python-to-system-path-by-default/3067) pelos quais você pode não querer o Python ativado `PATH`, portanto, certifique-se de compreender as implicações antes de marcar esta caixa.

O instalador completo oferece controle total sobre o processo de instalação.

**Aviso:** Se você não sabe o que [`PATH`](https://realpython.com/add-python-to-path/)é, é altamente recomendável **não** instalar com o instalador completo. Use o [pacote da Microsoft Store](https://realpython.com/installing-python/#how-to-install-from-the-microsoft-store) .

Personalize a instalação para atender às suas necessidades usando as opções disponíveis na caixa de diálogo. Em seguida, clique em *Instalar agora* . Isso é tudo que há para fazer!

Parabéns – agora você tem a versão mais recente do Python 3 em sua máquina Windows!

## Como instalar Python no macOS

Python 2 vem pré-instalado em versões mais antigas do macOS. Este não é mais o caso das versões atuais do macOS, [começando pelo macOS Catalina](https://developer.apple.com/documentation/macos-release-notes/macos-catalina-10_15-release-notes#Scripting-Language-Runtimes) .

Existem dois métodos de instalação no macOS:

1. O instalador oficial
2. O gerenciador de pacotes Homebrew

Nesta seção, você aprenderá como verificar qual versão do Python, se houver, está instalada no seu dispositivo macOS. Você também aprenderá qual dos dois métodos de instalação deve usar.

### Como verificar sua versão do Python em um Mac

Para verificar qual versão do Python você possui no seu Mac, primeiro abra um aplicativo de linha de comando, como o [Terminal](https://realpython.com/courses/using-terminal-macos/) .

**Dica:** veja como você abre o Terminal:

1. Pressione as teclas Cmd+Space .
2. Tipo `Terminal`.
3. Imprensa Enter.

Alternativamente, você pode abrir o Finder e navegar até *Aplicativos → Utilitários → Terminal* .

Com a linha de comando aberta, digite os seguintes comandos:

Concha

```py
# Check the system Python version
$python--version

# Check the Python 2 version
$python2--version

# Check the Python 3 version
$python3--version
```

Se você tiver Python em seu sistema, um ou mais desses comandos deverão responder com um número de versão.

Por exemplo, se o Python 3.8.4 já estivesse configurado no seu computador, o `python3`comando exibiria esse número de versão:

Concha

```py
$ python3--version
Python 3.8.4
```

Como alternativa `--version`, você pode usar a `-V`opção mais curta:

Concha

```py
$ python3-V
Python 3.8.4
```

Qualquer uma dessas opções fornecerá o número da versão da instalação do Python à qual o comando está associado.

Você desejará obter a versão mais recente do Python se alguma destas condições for verdadeira:

* Nenhum dos comandos acima retorna um número de versão.
* A única versão exibida está na série Python 2.X.
* Você tem uma versão do Python 3 que não é a mais recente disponível, que era a versão 3.8.4 no momento em que este livro foi escrito.

**Quais são suas opções?**
Existem duas maneiras de instalar a distribuição oficial do Python no macOS:

1. **O instalador oficial:** Este método envolve baixar o instalador oficial do site Python.org e executá-lo em sua máquina.
2. **O gerenciador de pacotes Homebrew:** Este método envolve baixar e instalar [o gerenciador de pacotes Homebrew](https://brew.sh/) , se você ainda não o tiver instalado, e então digitar um comando em um aplicativo de terminal.

Tanto o instalador oficial quanto o gerenciador de pacotes Homebrew funcionarão, mas apenas o instalador oficial é mantido pela Python Software Foundation.

**Observação:** você também pode concluir a instalação no macOS usando distribuições alternativas, como [Anaconda](https://www.anaconda.com/) , mas este tutorial cobre apenas distribuições oficiais.

Anaconda é uma plataforma popular para fazer computação científica e ciência de dados com Python. Para saber como instalar o Anaconda no macOS, verifique o [guia de instalação do macOS](https://docs.anaconda.com/anaconda/install/mac-os/) na documentação oficial do Anaconda.

As distribuições instaladas pelo instalador oficial e pelo gerenciador de pacotes Homebrew não são idênticas. A instalação do Homebrew tem algumas limitações.

#### Limitações da instalação do Homebrew

A distribuição Python para macOS disponível no Homebrew [não inclui a dependência Tcl/Tk](https://github.com/Homebrew/homebrew-core/pull/34424) exigida pelo módulo Tkinter. Tkinter é o módulo de biblioteca padrão para o desenvolvimento [de interfaces gráficas de usuário em Python](https://realpython.com/python-gui-tkinter/) e é na verdade uma interface para o [kit de ferramentas Tk GUI](https://www.tcl.tk/) , que não faz parte do Python.

O Homebrew não instala a dependência do kit de ferramentas Tk GUI. Em vez disso, ele depende de uma versão existente instalada no seu sistema. A versão do sistema do Tcl/Tk pode estar desatualizada ou totalmente ausente e pode impedir a importação do módulo Tkinter.

#### Recomendações do instalador do macOS

O gerenciador de pacotes Homebrew é um método popular para instalar o Python no macOS porque é fácil de gerenciar a partir da linha de comando e oferece comandos para atualizar o Python sem a necessidade de acessar um site. Como o Homebrew é um utilitário de linha de comando, ele pode ser automatizado com scripts bash.

No entanto, a distribuição Python oferecida pelo Homebrew não é controlada pela Python Software Foundation e pode mudar a qualquer momento. O método mais confiável no macOS é usar o instalador oficial, especialmente se você planeja [programar Python GUI com Tkinter](https://realpython.com/python-gui-tkinter/) .

[Remover propagandas](https://realpython.com/account/join/)

### Como instalar a partir do instalador oficial

Instalar o Python a partir do instalador oficial é o método de instalação mais confiável no macOS. Inclui todas as dependências do sistema necessárias para desenvolver aplicativos com Python.

Você pode instalar a partir do instalador oficial em duas etapas.

#### Etapa 1: Baixe o instalador oficial

Siga estas etapas para baixar o instalador completo:

1. Abra uma janela do navegador e navegue até a [página de downloads do Python.org para macOS](https://www.python.org/downloads/mac-osx/) .
2. No título “Versões do Python para Mac OS X”, clique no link para a *versão mais recente do Python 3 - Python* 3.xx. No momento em que este livro foi escrito, a versão mais recente era Python 3.8.4.
3. Role até a parte inferior e clique no *instalador do macOS de 64 bits* para iniciar o download.

Quando o download do instalador terminar, vá para a próxima etapa.

#### Etapa 2: Execute o instalador

Execute o instalador clicando duas vezes no arquivo baixado. Você deverá ver a seguinte janela:

[![A janela de instalação do macOS.](https://files.realpython.com/media/Screen_Shot_2020-07-15_at_8.31.24_AM.2e5b82dbc195.png)](https://files.realpython.com/media/Screen_Shot_2020-07-15_at_8.31.24_AM.2e5b82dbc195.png)

Siga estas etapas para concluir a instalação:

1. Pressione *Continuar* algumas vezes até ser solicitado a concordar com o contrato de licença do software. Em seguida, clique em *Concordo* .
2. Será exibida uma janela informando o destino da instalação e quanto espaço será necessário. Provavelmente você não deseja alterar o local padrão, então vá em frente e clique em *Instalar* para iniciar a instalação.
3. Quando o instalador terminar de copiar os arquivos, clique duas vezes no comando *Instalar certificados* na janela do Finder para garantir que seus certificados raiz SSL estejam atualizados.

Parabéns – agora você tem a versão mais recente do Python 3 no seu computador macOS!

### Como instalar a partir do Homebrew

Para usuários que precisam instalar a partir da linha de comando, especialmente aqueles que não usarão Python para desenvolver interfaces gráficas de usuário com o módulo Tkinter, o gerenciador de pacotes Homebrew é uma boa opção. Você pode instalar a partir do gerenciador de pacotes Homebrew em duas etapas.

#### Passo 1: Instale o Homebrew

Se você já possui o Homebrew instalado, pode pular esta etapa. Se você não tiver o Homebrew instalado, use o seguinte procedimento para instalar o Homebrew:

1. Abra um navegador e navegue até [http://brew.sh/](http://brew.sh/) .
2. Você deverá ver um comando para instalar o Homebrew próximo ao topo da página, sob o bloco “Instalar Homebrew”. Este comando será algo como o seguinte:
   Concha

   ```py
   $/bin/bash-c"$(curl-fsSLhttps://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
   ```

   Destaque o comando com o cursor e pressione Cmd+C para copiá-lo para a área de transferência.
3. Abra uma janela de terminal e cole o comando e pressione Enter. Isso iniciará a instalação do Homebrew.
4. Digite sua senha de usuário do macOS quando solicitado.

Dependendo da sua conexão com a Internet, pode demorar alguns minutos para baixar todos os arquivos necessários do Homebrew. Assim que a instalação for concluída, você retornará ao prompt do shell na janela do terminal.

**Observação:** se estiver fazendo isso em uma nova instalação do macOS, você poderá receber um alerta pop-up solicitando a **instalação das ferramentas de desenvolvedor de linha de comando da Apple.** Essas ferramentas são necessárias para a instalação, portanto você pode confirmar a caixa de diálogo clicando em *Instalar* .

Após a instalação das ferramentas do desenvolvedor, você precisará pressionar Enterpara continuar a instalação do Homebrew.

Agora que o Homebrew está instalado, você está pronto para instalar o Python.

#### Etapa 2: instale o Python

Siga estas etapas para concluir a instalação com Homebrew:

1. Abra um aplicativo de terminal.
2. Digite o seguinte comando para atualizar o Homebrew:
   Concha

   ```py
   $brewupdate&&brewupgrade
   ```

Instalar com Homebrew agora é tão simples quanto executar o comando `brew install python3`. Isso fará o download e configurará a versão mais recente do Python em sua máquina.

Você pode ter certeza de que tudo correu corretamente testando se consegue acessar o Python a partir do terminal:

1. Abra um terminal.
2. Digite `pip3`e pressione Enter.
3. Você deverá ver o texto de ajuda do gerenciador de pacotes [do Python `pip`](https://realpython.com/what-is-pip/) . Se você receber uma mensagem de erro em execução `pip3`, siga as etapas de instalação novamente para garantir que a instalação esteja funcionando.

Parabéns – agora você tem Python em seu sistema macOS!

## Como instalar Python no Linux

Existem dois métodos de instalação no Linux:

1. Usando o gerenciador de pacotes do seu sistema operacional
2. Construindo Python a partir do código-fonte

Nesta seção, você aprenderá como verificar qual versão do Python, se houver, está em seu computador Linux. Você também aprenderá qual dos dois métodos de instalação deve usar.

### Como verificar sua versão do Python no Linux

Muitas distribuições Linux vêm empacotadas com Python, mas provavelmente não será a versão mais recente e pode até ser Python 2 em vez de Python 3. Você deve verificar a versão para ter certeza.

Para descobrir qual versão do Python você possui, abra uma janela [de terminal](https://realpython.com/courses/using-terminal-linux/) e tente os seguintes comandos:

Concha

```py
# Check the system Python version
$python--version

# Check the Python 2 version
$python2--version

# Check the Python 3 version
$python3--version
```

Se você tiver Python em sua máquina, um ou mais desses comandos deverão responder com um número de versão.

Por exemplo, se você já tinha o Python 3.6.10 em seu computador, o `python3 --version`comando exibiria esse número de versão:

Concha

```py
$ python3--version
Python 3.8.4
```

Como alternativa `--version`, você pode usar a `-V`opção mais curta:

Concha

```py
$ python3-V
Python 3.8.4
```

Qualquer uma dessas opções fornecerá o número da versão da instalação do Python à qual o comando está associado.

Você desejará obter a versão mais recente do Python se sua versão atual estiver na série Python 2.X ou não for a versão mais recente do Python 3 disponível, que era 3.8.4 no momento em que este livro foi escrito.

## *Quais são suas opções*

Existem duas maneiras de instalar a distribuição oficial do Python no Linux:

1. **Instalar a partir de um gerenciador de pacotes:** Este é o método de instalação mais comum na maioria das distribuições Linux. Envolve a execução de um comando na linha de comando.
2. **Construir a partir do código-fonte:** Este método é mais difícil do que usar um gerenciador de pacotes. Envolve a execução de uma série de comandos na linha de comando, além de garantir que você tenha as dependências corretas instaladas para compilar o código-fonte Python.

Nem toda distribuição Linux possui um gerenciador de pacotes, e nem todo gerenciador de pacotes possui Python em seu repositório de pacotes. Dependendo do seu sistema operacional, construir Python a partir do código-fonte pode ser sua única opção.

**Nota:** Você também pode concluir a instalação no Linux usando distribuições alternativas, como [Anaconda](https://www.anaconda.com/) , mas este tutorial cobre apenas distribuições oficiais.

Anaconda é uma plataforma popular para fazer computação científica e ciência de dados com Python. Para saber como instalar o Anaconda no Linux, verifique o [guia de instalação do Linux](https://docs.anaconda.com/anaconda/install/linux/) na documentação oficial do Anaconda.

O método de instalação que você usa se resume principalmente a se o seu sistema operacional Linux possui um gerenciador de pacotes e se você precisa controlar os detalhes da instalação.

### Recomendações de instalação do Linux

A maneira mais popular de instalar o Python no Linux é com o gerenciador de pacotes do seu sistema operacional, que é uma boa escolha para a maioria dos usuários. No entanto, dependendo da sua distribuição Linux, o Python pode não estar disponível através de um gerenciador de pacotes. Nesse caso, você precisará construir o Python a partir do código-fonte.

Existem três motivos principais pelos quais você pode escolher construir Python a partir do código-fonte:

1. Você não pode baixar o Python do gerenciador de pacotes do seu sistema operacional.
2. Você precisa controlar como o Python é compilado, como quando você deseja reduzir o consumo de memória em sistemas embarcados.
3. Você deseja experimentar versões beta e lançar candidatos da versão melhor e mais recente antes que ela esteja disponível para o público geral.

Para concluir a instalação em sua máquina Linux, encontre sua distribuição Linux abaixo e siga as etapas fornecidas.

[Remover propagandas](https://realpython.com/account/join/)

### Como instalar no Ubuntu e Linux Mint

Nesta seção, você aprenderá como instalar o Python usando `apt`o gerenciador de pacotes do Ubuntu. Se você quiser construir Python a partir do código-fonte, vá para a seção [Como construir Python a partir do código-fonte](https://realpython.com/installing-python/#how-to-build-python-from-source-code) .

**Nota:** Os usuários do Linux Mint podem pular para a seção “Linux Mint e Ubuntu 17 e abaixo”.

Dependendo da versão da distribuição Ubuntu que você executa, o processo de configuração do Python em seu sistema pode variar. Você pode determinar sua versão local do Ubuntu executando o seguinte comando:

Concha

```py
$ lsb_release-a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 16.04.4 LTS
Release:        16.04
Codename:       xenial
```

Siga as instruções abaixo que correspondem ao número da versão que você vê `Release`na saída do console:

* **Ubuntu 18.04, Ubuntu 20.04 e superior:** Python 3.8 não vem por padrão no Ubuntu 18.04 e superior, mas está disponível no repositório Universe. Para instalar a versão 3.8, abra um aplicativo de terminal e digite os seguintes comandos:
  Concha

  ```py
  $sudoapt-getupdate
  $sudoapt-getinstallpython3.8python3-pip
  ```

  Assim que a instalação for concluída, você pode executar o Python 3.8 com o `python3.8`comando e `pip`com o `pip3`comando.
* **Linux Mint e Ubuntu 17 e anteriores:** Python 3.8 não está no repositório Universe, então você precisa obtê-lo em um Personal Package Archive (PPA). Por exemplo, para instalar a partir do [PPA “deadsnakes”](https://launchpad.net/~deadsnakes/+archive/ubuntu/ppa) , use os seguintes comandos:
  Concha

  ```py
  $sudoadd-apt-repositoryppa:deadsnakes/ppa
  $sudoapt-getupdate
  $sudoapt-getinstallpython3.8python3-pip
  ```

  Assim que a instalação for concluída, você pode executar o Python 3.8 com o `python3.8`comando e executar `pip`com o `pip3`comando.

Parabéns! Agora você tem o Python 3 configurado em sua máquina!

### Como instalar no Debian Linux

Antes de instalar o Python 3.8 no Debian, você precisará instalar o `sudo`comando. Para instalá-lo, execute os seguintes comandos em um terminal:

Concha

```py
$su
$apt-getinstallsudo
$Sudovim/etc/sudoers
```

Depois disso, abra o `/etc/sudoers`arquivo usando o `sudo vim`comando ou seu editor de texto favorito. Adicione a seguinte linha de texto ao final do arquivo, substituindo `your_username`pelo seu nome de usuário real:

Texto

```py
your_username ALL=(ALL) ALL
```

Agora você pode pular para a seção [Como construir Python a partir do código-fonte](https://realpython.com/installing-python/#how-to-build-python-from-source-code) para concluir a instalação do Python.

### Como instalar no openSUSE

Construir a partir do código-fonte é a maneira mais confiável de configurar o Python no openSUSE. Para isso, será necessário instalar as ferramentas de desenvolvimento, o que pode ser feito através `YaST`dos menus ou usando `zypper`:

Concha

```py
$sudozypperinstall-tpatterndevel_C_C
```

Isso pode demorar um pouco para ser concluído, pois instala mais de 150 pacotes. Depois de concluído, vá para a seção [Como construir Python a partir do código-fonte](https://realpython.com/installing-python/#how-to-build-python-from-source-code) .

### Como instalar no CentOS e Fedora

O Python 3.8 não está disponível nos repositórios CentOS e Fedora, então você terá que construir o Python a partir do código-fonte. Antes de compilar o Python, porém, você precisa ter certeza de que seu sistema está preparado.

Primeiro, atualize o [`yum`gerenciador de pacotes](http://yum.baseurl.org/) :

Concha

```py
$sudoyum-yupdate
```

Assim que `yum`terminar a atualização, você pode instalar as dependências de compilação necessárias com os seguintes comandos:

Concha

```py
$sudoyum-ygroupinstall"Development Tools"
$sudoyum-yinstallgccopenssl-develbzip2-devellibffi-devel
```

Quando a instalação estiver concluída, vá para a seção [Como construir Python a partir do código-fonte](https://realpython.com/installing-python/#how-to-build-python-from-source-code).

### Como instalar no Arch Linux

Arch Linux é bastante diligente em acompanhar os lançamentos do Python. É provável que você já tenha a versão mais recente. Caso contrário, use o seguinte comando para atualizar o Python:

Concha

```py
$packman-Spython
```

Quando o Python terminar de atualizar, você estará pronto!

### Como construir Python a partir do código-fonte

Às vezes, sua distribuição Linux não tem a versão mais recente do Python, ou talvez você apenas queira construir a melhor e mais recente versão sozinho. Aqui estão as etapas que você precisa seguir para construir Python a partir do código-fonte:

#### Etapa 1: Baixe o código-fonte

Para começar, você precisa obter o código-fonte do Python. Python.org torna isso bastante simples. Se você acessar a página [Downloads](https://www.python.org/downloads/source/) , verá a fonte mais recente do Python 3 na parte superior. Apenas certifique-se de não pegar o Legacy Python, Python 2!

Ao selecionar a versão Python 3, você verá uma seção “Arquivos” na parte inferior da página. Selecione *Local de origem compactado* e baixe-o para sua máquina. Se preferir um método de linha de comando, você pode usar `wget`para baixar o arquivo em seu diretório atual:

Concha

```py
$wgethttps://www.python.org/ftp/python/3.8.4/Python-3.8.4.tgz
```

Quando o download do tarball terminar, há algumas coisas que você precisará fazer para preparar seu sistema para construir o Python.

#### Etapa 2: prepare seu sistema

Existem algumas etapas específicas da distribuição envolvidas na construção do Python do zero. O objetivo de cada etapa é o mesmo em todas as distros, mas pode ser necessário traduzir para sua distribuição se ela não usar `apt-get`:

1. Primeiro, atualize seu gerenciador de pacotes e atualize seus pacotes:
   Concha

   ```py
   $sudoapt-getupdate
   $sudoapt-getupgrade
   ```

2. Em seguida, certifique-se de ter todos os requisitos de compilação instalados:
   Concha

   ```py
   # For apt-based systems (like Debian, Ubuntu, and Mint)
   $sudoapt-getinstall-ymakebuild-essentiallibssl-devzlib1g-dev\
   libbz2-devlibreadline-devlibsqlite3-devwgetcurlllvm\
   libncurses5-devlibncursesw5-devxz-utilstk-dev

   # For yum-based systems (like CentOS)
   $sudoyum-ygroupinstall"Development Tools"
   $sudoyum-yinstallgccopenssl-develbzip2-devellibffi-devel
   ```

   Tudo bem se você já tiver alguns dos requisitos instalados em seu sistema. Você pode executar os comandos acima e nenhum pacote existente será sobrescrito.

Agora que seu sistema está pronto para funcionar, é hora de começar a construir o Python!

#### Etapa 3: construir Python

1. Depois de ter os pré-requisitos e o arquivo TAR, você poderá descompactar a fonte em um diretório. Observe que o comando a seguir criará um novo diretório chamado `Python-3.8.3`naquele em que você está:
   Concha

   ```py
   $tarxvfPython-3.8.4.tgz
   $cdPython-3.8.4
   ```

2. Agora você precisa executar a `./configure`ferramenta para preparar a compilação:
   Concha

   ```py
   $./configure--enable-optimizations--with-ensurepip=install
   ```

   O `enable-optimizations`sinalizador permitirá algumas otimizações no Python para fazê-lo funcionar cerca de 10% mais rápido. Isso pode adicionar vinte ou trinta minutos ao tempo de compilação. O `with-ensurepip=install`sinalizador será instalado `pip`junto com esta instalação.

3. A seguir, você cria Python usando `make`. A `-j`opção simplesmente diz `make`para dividir a construção em etapas paralelas para acelerar a compilação. Mesmo com compilações paralelas, esta etapa pode levar vários minutos:
   Concha

   ```py
   $make-j8
   ```

4. Finalmente, você desejará instalar sua nova versão do Python. Você usará o `altinstall`alvo aqui para evitar sobrescrever o sistema Python. Como você está instalando no `/usr/bin`, você precisará executar como root:
   Concha

   ```py
   $sudomakealtinstall
   ```

Pode demorar um pouco para concluir a instalação. Quando terminar, você pode verificar se o Python está configurado corretamente.

#### Etapa 4: verifique sua instalação

Teste se o `python3.8 --version`comando retorna a versão mais recente:

Concha

```py
$python3.8--version
Python 3.8.4
```

Se você ver `Python 3.8.4`, então está tudo pronto!

Se você tiver algum tempo extra disponível, também pode executar o [conjunto de testes](https://devguide.python.org/runtests/) para ter certeza de que tudo está funcionando corretamente em seu sistema.

Para executar o conjunto de testes, digite o seguinte comando:

Concha

```py
$python3.8-mtest
```

Você provavelmente desejará encontrar outra coisa para fazer por um tempo, pois seu computador estará executando testes por algum tempo. Se todos os testes forem aprovados, você pode ter certeza de que sua nova versão do Python está funcionando conforme o esperado!

[Remover propagandas](https://realpython.com/account/join/)

## Como instalar Python no iOS

O [aplicativo Pythonista](http://omz-software.com/pythonista/) para iOS é um ambiente de desenvolvimento Python completo que você pode executar no seu iPhone ou iPad. Ele apresenta um editor Python, documentação técnica e um intérprete, tudo reunido em um único aplicativo.

Pythonista é surpreendentemente divertido de usar. É uma ótima ferramenta quando você está sem um laptop e deseja aprimorar suas habilidades em Python em qualquer lugar. Ele vem com a biblioteca padrão completa do Python 3 e ainda inclui documentação completa que você pode navegar offline.

Para configurar o Pythonista, você precisa [baixá-lo na loja de aplicativos iOS](https://geo.itunes.apple.com/us/app/pythonista-3/id1085978097?ls=1&mt=8&at=1000lqsw) .

## Como instalar Python no Android

Se você possui um tablet ou telefone Android e deseja praticar Python em qualquer lugar, existem várias opções disponíveis. Aquele que achamos que suporta o Python 3.8 de forma mais confiável é [o Pydroid 3](https://play.google.com/store/apps/details?id=ru.iiec.pydroid3) .

O Pydroid 3 apresenta um interpretador que você pode usar para sessões REPL e também permite editar, salvar e executar código Python.

Você pode [baixar e instalar o Pydroid 3 na Google Play Store](https://play.google.com/store/apps/details?id=ru.iiec.pydroid3) . Existe uma versão gratuita e também uma versão Premium paga que suporta previsão e análise de código.

## Intérpretes Python on-line

Se você quiser experimentar os exemplos deste tutorial sem configurar o Python em sua máquina, existem vários sites que oferecem um interpretador Python online:

* [Console on-line do Python.org](https://www.python.org/shell)
* [Repl.it](https://repl.it/)
* [Violino Python](http://pythonfiddle.com/)
* [Bugiganga](https://trinket.io/)
* [Python em qualquer lugar](https://www.pythonanywhere.com/)

Esses intérpretes Python baseados em nuvem podem não ser capazes de executar alguns dos exemplos mais complexos deste tutorial, mas são adequados para executar a maior parte do código e podem ser uma ótima maneira de começar. Mais informações sobre como usar esses sites são apresentadas no próximo tutorial desta série.

## Conclusão

Parabéns! Agora você tem acesso à versão mais recente do Python para o seu sistema. Sua jornada em Python está apenas começando.

**Neste tutorial você aprendeu como:**

* Verifique qual **versão do Python** , se houver, está instalada em seu sistema
* Instale a versão mais recente do Python no **Windows** , **macOS** e **Linux**
* Use Python em **dispositivos móveis** como telefones ou tablets
* Use Python na Web com **intérpretes online**

Agora você está pronto para começar a programar em Python! Certifique-se de compartilhar seu progresso e quaisquer dúvidas que você possa ter nos comentários abaixo.
