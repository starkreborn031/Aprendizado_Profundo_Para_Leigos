# ![Interagindo com Python](https://files.realpython.com/media/Interacting-with-Python_Watermarked.0007ad8964b8.jpg)

## Interagindo com Python

Neste ponto, você deve ter um interpretador Python 3 funcional em mãos. Se precisar de ajuda para configurar o Python corretamente, consulte a [seção anterior](https://realpython.com/installing-python/) desta série de tutoriais.

**Aqui está o que você aprenderá neste tutorial:** Agora que você tem uma configuração Python funcional, verá como realmente executar código Python e executar programas Python. Ao final deste artigo, você saberá como:

* Use Python interativamente digitando o código diretamente no interpretador
* Execute o código contido em um arquivo de script na linha de comando
* Trabalhe em um ambiente de desenvolvimento integrado (IDE) Python

É hora de escrever algum código Python!

## Olá Mundo

Há um costume antigo no campo da programação de computadores de que o primeiro código escrito em uma linguagem recém-instalada é um programa curto que simplesmente exibe a string `Hello, World!`no console.

**Nota:** Esta é uma tradição consagrada que remonta à década de 1970. Veja [Olá, mundo!](https://en.wikipedia.org/wiki/%22Hello,_World!%22_program)para uma breve história. Você corre o sério risco de perturbar o *qi* do universo se não seguir esse costume.

O código Python 3 mais simples de exibir `Hello, World!`é:

PYTHON

```py
print("Hello, World!")
```

Você explorará várias maneiras diferentes de executar este código abaixo.

## Usando o interpretador Python interativamente

A maneira mais direta de começar a falar com Python é em um ambiente interativo [Read-Eval-Print Loop (REPL)](https://realpython.com/python-repl/) . Isso significa simplesmente iniciar o interpretador e digitar comandos diretamente nele. O intérprete:

* **Lê** o comando que você digita
* **E** avalia e executa o comando
* **Imprime** a saída (se houver) no console
* **Volta** e repete o processo

A sessão continua dessa maneira até que você instrua o intérprete a encerrá-la. A maior parte do código de exemplo nesta série de tutoriais é apresentada como interação REPL.

### Iniciando o intérprete

Em um ambiente de área de trabalho GUI, é provável que o processo de instalação tenha colocado um ícone na área de trabalho ou um item no sistema de menu da área de trabalho que inicia o Python.

Por exemplo, no Windows, provavelmente haverá um grupo de programas no menu **Iniciar denominado** **Python 3.x** e, abaixo dele, um item de menu denominado **Python 3.x (32 bits)** ou algo semelhante, dependendo da instalação específica que você escolheu .

Clicar nesse item iniciará o interpretador Python:

[![Janela do interpretador Python](https://files.realpython.com/media/python-interpreter-window.24c17cb2fd60.png)](https://files.realpython.com/media/python-interpreter-window.24c17cb2fd60.png)
O interpretador Python (REPL) em execução dentro de uma janela de terminal.

Alternativamente, você pode abrir uma janela de terminal e executar o interpretador na linha de comando. A maneira como você abre uma janela de terminal varia dependendo do sistema operacional que você está usando:

* No Windows, é chamado **de Prompt de Comando** .
* No macOS ou Linux, deve se chamar **Terminal** .

Usar a função de pesquisa do seu sistema operacional para procurar “comando” no Windows ou “terminal” no macOS ou Linux deve encontrá-lo.

Depois que uma janela de terminal estiver aberta, se os caminhos tiverem sido configurados corretamente pelo processo de instalação do Python, você poderá apenas digitar `python`. Então, você deverá ver uma resposta do interpretador Python.

Este exemplo é da janela do prompt de comando do Windows:

Prompt de comando do Windows

```py
C:\Users\john>python
Python 3.6.0 (v3.6.0:41df79263a11, Dec 23 2016, 07:18:10) [MSC v.1900 32 bit (Intel)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

**Nota Técnica:** Se você estiver em um sistema Linux e instalou o Python 3, pode ser que tanto o Python 2 quanto o Python 3 estejam instalados. Nesse caso, é possível que a digitação `python`no prompt inicie o Python 2. Iniciar o Python 3 pode exigir a digitação de outra coisa, como `python3`.

Se você instalou uma versão mais recente do Python 3 do que aquela que foi incluída na distribuição, talvez seja necessário especificar a versão que você instalou especificamente – por exemplo `python3.6`, .

Se você não estiver vendo o `>>>`prompt, então você não está falando com o interpretador Python. Isso pode ocorrer porque o Python não está instalado ou não está no caminho da sessão da janela do terminal. Também é possível que você simplesmente não tenha encontrado o comando correto para executá-lo. Você pode consultar nosso [tutorial de instalação do Python](https://realpython.com/installing-python/) para obter ajuda.

### Executando código Python

Se você estiver vendo o prompt, você está pronto e funcionando! A próxima etapa é executar a instrução exibida `Hello, World!`no console:

1. Certifique-se de que o `>>>`prompt seja exibido e que o cursor esteja posicionado após ele.
2. Digite o comando `print("Hello, World!")`exatamente como mostrado.
3. Pressione a Tecla Enter.

A resposta do intérprete deverá aparecer na próxima linha. Você pode dizer que é uma saída do console porque o `>>>`prompt está ausente:

PYTHON

```py
>>> print("Hello, World!")
Hello, World!
```

Se sua sessão for semelhante à acima, você executou seu primeiro código Python! Reserve um momento para comemorar.

[![Celebração](https://files.realpython.com/media/celebration.e98e35f3e140.png)](https://files.realpython.com/media/celebration.e98e35f3e140.png)

 *Parabéns!*

Algo deu errado? Talvez você tenha cometido um destes erros:

* Você esqueceu de colocar a string a ser impressa entre aspas:
  PYTHON

```py
>>> print(Hello, World!)
File "<stdin>", line 1
print(Hello, World!)
^
SyntaxError: invalid syntax
```

* Você se lembrou das aspas de abertura, mas esqueceu as de fechamento:

PYTHON

```py
>>> print("Hello, World!)
File "<stdin>", line 1
print("Hello, World!)
^
SyntaxError: EOL while scanning string literal
```

* Você usou diferentes aspas de abertura e fechamento:

PYTHON

```py
  >>> print("Hello, World!')
    File "<stdin>", line 1
  print("Hello, World!')
  ^
  SyntaxError: EOL while scanning string literal
  ```

* Você esqueceu os parênteses:

PYTHON

  ```py
  >>> print "Hello, World!"
    File "<stdin>", line 1
  print "Hello, World!"
  ^
  SyntaxError: Missing parentheses in call to 'print'
  ```

* Você inseriu caracteres de espaço em branco extras antes do comando:

PYTHON

  ```py
  >>>     print("Hello, World!")
    File "<stdin>", line 1
  print("Hello, World!")
  ^
  IndentationError: unexpected indent
  ```

(Você verá na próxima seção por que isso é importante.)

Se você recebeu algum tipo de mensagem de erro, volte e verifique se digitou o comando exatamente como mostrado acima.

### Saindo do intérprete

Ao terminar de interagir com o intérprete, você poderá sair de uma sessão REPL de diversas maneiras:

* Digite `exit()`e pressione Enter:

PYTHON

  ```py
  >>> exit()

  C:\Users\john>
  ```

* No Windows, digite Ctrl+Z e pressione Enter:
  
PYTHON

  ```py
  >>> ^Z
  C:\Users\john>
  ```

* No Linux ou macOS, digite Ctrl+D . O intérprete termina imediatamente; pressionar Enter não é necessário.

* Se tudo mais falhar, você pode simplesmente fechar a janela do interpretador. Esta não é a melhor maneira, mas fará o trabalho.

## Executando um script Python na linha de comando

Inserir comandos no interpretador Python de forma interativa é ótimo para testes rápidos e exploração de recursos ou funcionalidades.

Porém, eventualmente, à medida que você cria aplicativos mais complexos, você desenvolverá corpos de código mais longos que desejará editar e executar repetidamente. Você claramente não deseja redigitar o código no interpretador todas as vezes! É aqui que você deseja criar um arquivo de script.

Um script Python é um conjunto reutilizável de código. É essencialmente um programa Python – uma sequência de instruções Python – contida em um arquivo. Você pode executar o programa especificando o nome do arquivo de script para o interpretador.

Os scripts Python são apenas texto simples, então você pode editá-los com qualquer editor de texto. Se você [tiver um editor de programador favorito](https://realpython.com/python-ides-code-editors-guide/) que opere em arquivos de texto, ele poderá ser usado. Caso contrário, os itens a seguir normalmente serão instalados nativamente com seus respectivos sistemas operacionais:

* Windows: Bloco de Notas
* Unix/Linux: vi ou vim
* macOS: TextoEditar

Usando qualquer editor escolhido, crie um arquivo de script chamado `hello.py`contendo o seguinte:

PYTHON

```py
print("Hello, World!")
```

Agora salve o arquivo, acompanhando o diretório ou pasta em que você escolheu salvar.

Inicie um prompt de comando ou janela de terminal. Se o diretório de trabalho atual for o mesmo local em que você salvou o arquivo, você pode simplesmente especificar o nome do arquivo como um [argumento de linha de comando](https://realpython.com/python-command-line-arguments/) para o interpretador Python:`python hello.py`

Por exemplo, no Windows ficaria assim:

Prompt de comando do Windows

```py
C:\Users\john\Documents\test>dir
 Volume in drive C is JFS
 Volume Serial Number is 1431-F891

 Directory of C:\Users\john\Documents\test

05/20/2018  01:31 PM    <DIR>          .
05/20/2018  01:31 PM    <DIR>          ..
05/20/2018  01:31 PM                24 hello.py
               1 File(s)             24 bytes
               2 Dir(s)  92,557,885,440 bytes free

C:\Users\john\Documents\test>python hello.py
Hello, World!
```

Se o script não estiver no diretório de trabalho atual, você ainda poderá executá-lo. Você apenas terá que especificar o nome do caminho para ele:

Prompt de comando do Windows

```py
C:\>cd
C:\

C:\>python c:\Users\john\Documents\test\hello.py
Hello, World!
```

No Linux ou macOS, sua sessão pode ser mais parecida com esta:

Concha

```py
jfs@jfs-xps:~$ pwd
/home/jfs

jfs@jfs-xps:~$ ls
hello.py

jfs@jfs-xps:~$ pythonhello.py
Hello, World!
```

Um arquivo de script não precisa ter uma `.py`extensão. O interpretador Python executará o arquivo independentemente do nome, desde que você especifique corretamente o nome do arquivo na linha de comando:

Concha

```py
jfs@jfs-xps:~$ ls
hello.foo

jfs@jfs-xps:~$ cathello.foo
print("Hello, World!")

jfs@jfs-xps:~$ pythonhello.foo
Hello, World!
```

Mas dar uma `.py`extensão aos arquivos Python é uma convenção útil porque os torna mais facilmente identificáveis. Em ambientes de pastas/ícones orientados para desktop, como Windows e macOS, isso normalmente também permitirá a configuração de uma associação de arquivo apropriada, para que você possa executar o script apenas clicando em seu ícone.

## Interagindo com Python por meio de um IDE

Um Ambiente de Desenvolvimento Integrado (IDE) é um aplicativo que combina mais ou menos todas as funcionalidades que você viu até agora. IDEs geralmente fornecem capacidade REPL, bem como um editor com o qual você pode criar e modificar código para depois enviar ao intérprete para execução.

Você também pode encontrar recursos interessantes, como:

* **Destaque de sintaxe** : IDEs geralmente colorem diferentes elementos de sintaxe no código para facilitar a leitura.
* **Ajuda contextual** : IDEs avançados podem exibir informações relacionadas da documentação do Python ou até mesmo sugestões de correções para tipos comuns de erros de código.
* **Conclusão de código** : alguns IDEs podem completar partes de código parcialmente digitadas (como nomes de funções) para você – um recurso que economiza muito tempo e é conveniente.
* **Depuração** : um depurador permite executar o código passo a passo e inspecionar os dados do programa conforme você avança. Isto é inestimável quando você está tentando determinar por que um programa está se comportando de maneira inadequada, como inevitavelmente acontecerá.

### PARADO

A maioria das instalações do Python contém um IDE rudimentar chamado [IDLE](https://realpython.com/python-idle/) . O nome significa ostensivamente Ambiente Integrado de Desenvolvimento e Aprendizagem, mas um membro da trupe Monty Python se chama [Eric Idle](https://en.wikipedia.org/wiki/Eric_Idle) , o que dificilmente parece uma coincidência.

O procedimento para executar o IDLE varia de um sistema operacional para outro.

#### Iniciando o IDLE no Windows

Vá para o menu Iniciar e selecione **Todos os Programas** ou **Todos os Aplicativos** . Deve haver um ícone de programa denominado **IDLE (Python 3.x 32 bits)** ou algo semelhante. Isso irá variar um pouco entre Win 7, 8 e 10. O ícone IDLE pode estar em uma pasta de grupo de programas chamada **Python 3.x** . Você também pode encontrar o ícone do programa IDLE usando o recurso de pesquisa do Windows no menu Iniciar e digitando `IDLE`.

Clique no ícone para iniciar o IDLE.

#### Iniciando o IDLE no macOS

Abra a Pesquisa Spotlight. Digitar Cmd+Space é uma das várias maneiras de fazer isso. Na caixa de pesquisa, digite `terminal`e pressione Enter.

Na janela do terminal, digite `idle3`e pressione Enter.

#### Iniciando o IDLE no Linux

IDLE está disponível na distribuição Python 3, mas pode não ter sido instalado por padrão. Para descobrir se é, abra uma janela de terminal. Isso varia dependendo da distribuição do Linux, mas você poderá encontrá-lo usando a função de pesquisa da área de trabalho e procurando por `terminal`. Na janela do terminal, digite `idle3`e pressione Enter.

Se você receber um erro dizendo `command not found`ou algo nesse sentido, então o IDLE aparentemente não está instalado, então você precisará instalá-lo.

O método de instalação de aplicativos também varia de uma distribuição Linux para outra. Por exemplo, com Ubuntu Linux, o comando para instalar o IDLE é `sudo apt-get install idle3`. Muitas distribuições Linux possuem gerenciadores de aplicativos baseados em GUI que você também pode usar para instalar aplicativos.

Siga qualquer procedimento apropriado para sua distribuição para instalar o IDLE. Em seguida, digite `idle3`em uma janela de terminal e pressione Enterpara executá-lo. Seu procedimento de instalação também pode ter configurado um ícone de programa em algum lugar da área de trabalho para iniciar o IDLE.

Uau!

#### Usando IDLE

Depois que o IDLE estiver instalado e iniciado com sucesso, você deverá ver uma janela intitulada **Python 3.xx Shell** , onde 3.xx corresponde à sua versão do Python:

[![Captura de tela 1 do IDLE](https://files.realpython.com/media/idle-1.ad05cbe1e2f7.png)](https://files.realpython.com/media/idle-1.ad05cbe1e2f7.png)

O `>>>`prompt deve parecer familiar. Você pode digitar comandos REPL interativamente, assim como quando iniciou o interpretador em uma janela do console. Ciente do *qi* do universo, exiba `Hello, World!`novamente:

[![Captura de tela 2 do IDLE](https://files.realpython.com/media/idle-2.c0a65df087ef.png)](https://files.realpython.com/media/idle-2.c0a65df087ef.png)

O interpretador se comporta mais ou menos da mesma forma que quando você o executa diretamente do console. A interface IDLE adiciona a vantagem de exibir diferentes elementos sintáticos em cores distintas para tornar as coisas mais legíveis.

Ele também fornece ajuda contextual. Por exemplo, se você digitar `print(`sem digitar nenhum dos argumentos da função de impressão ou do parêntese de fechamento, o texto suspenso deverá aparecer especificando as informações de uso da `print()`função.

Um outro recurso que o IDLE oferece é a recuperação de instruções:

* Se você digitou várias instruções, poderá recuperá-las com Alt+P e Alt+N no Windows ou Linux.
* Alt+P retrocede através de instruções executadas anteriormente; Alt+N avança.
* Depois que uma instrução for recuperada, você poderá usar as teclas de edição do teclado para editá-la e executá-la novamente. Os comandos correspondentes no macOS são Cmd+P e Cmd+N .

Você também pode criar arquivos de script e executá-los em IDLE. No menu da janela Shell, selecione **Arquivo → Novo arquivo** . Isso deve abrir uma janela de edição adicional. Digite o código a ser executado:

[![Captura de tela 3 do IDLE](https://files.realpython.com/media/idle-3.104282dbe280.png)](https://files.realpython.com/media/idle-3.104282dbe280.png)

No menu dessa janela, selecione **Arquivo → Salvar** ou **Arquivo → Salvar como…** e salve o arquivo no disco. Em seguida, selecione **Executar → Executar Módulo** . A saída deve aparecer novamente na janela do interpretador Shell:

[![Captura de tela 4 do IDLE](https://files.realpython.com/media/idle-4.4a4d4399093f.png)](https://files.realpython.com/media/idle-4.4a4d4399093f.png)

OK, isso provavelmente é o suficiente `Hello, World!`. O *qi* do universo deveria estar seguro.

Depois que ambas as janelas estiverem abertas, você poderá alternar, editando o código em uma janela, executando-o e exibindo sua saída na outra. Dessa forma, IDLE fornece uma plataforma de desenvolvimento Python rudimentar.

Embora seja um tanto básico, ele suporta algumas funcionalidades adicionais, incluindo preenchimento de código, formatação de código e um depurador. Consulte a [documentação do IDLE](https://docs.python.org/3/library/idle.html) para obter mais detalhes.

[Remover propagandas](https://realpython.com/account/join/)

### Thonny

[Thonny](http://thonny.org/) é um IDE Python gratuito desenvolvido e mantido pelo Instituto de Ciência da Computação da Universidade de Tartu, na Estônia. Ele é voltado especificamente para iniciantes em Python, portanto, a interface é simples e organizada, além de fácil de entender e se familiarizar rapidamente.

Assim como o IDLE, Thonny suporta interação REPL, bem como edição e execução de arquivos de script:

[![Python Thonny REPL](https://files.realpython.com/media/thonny-REPL.ffb0d0a0d58d.png)](https://files.realpython.com/media/thonny-REPL.ffb0d0a0d58d.png)

[![Editor Python Thonny](https://files.realpython.com/media/thonny-editor.fc8d59bbcaa7.png)](https://files.realpython.com/media/thonny-editor.fc8d59bbcaa7.png)

Thonny realiza realce de sintaxe e conclusão de código, além de fornecer um depurador passo a passo. Um recurso que é particularmente útil para quem está aprendendo Python é que o depurador exibe valores em expressões à medida que são avaliados enquanto você percorre o código:

[![Avaliação de Thonny expr](https://files.realpython.com/media/thonny-expr.d833fc5e3562.png)](https://files.realpython.com/media/thonny-expr.d833fc5e3562.png)

Thonny é especialmente fácil de começar porque vem com Python 3.6 integrado. Portanto, você só precisa realizar uma instalação e está pronto para começar!

As versões estão disponíveis para Windows, macOS e Linux. O [site do Thonny](http://thonny.org/) contém instruções de download e instalação.

IDLE e Thonny certamente não são os únicos jogos disponíveis. Existem muitos outros IDEs disponíveis para edição e desenvolvimento de código Python. Consulte nosso [Guia de editores de código e IDEs Python](https://realpython.com/python-ides-code-editors-guide/) para sugestões adicionais.

## Sites Python REPL on-line

Como você viu na seção anterior, existem [sites disponíveis](https://realpython.com/installing-python/#online-python-interpreters) que podem fornecer acesso interativo a um interpretador Python online sem que você precise instalar nada localmente.

Essa abordagem pode ser insatisfatória para alguns dos exemplos mais complicados ou longos deste tutorial. Mas para sessões REPL simples, deve funcionar bem.

A Python Software Foundation fornece um Shell Interativo em seu site. Na [página principal](https://www.python.org/) , clique no botão que se parece com um destes:

[![Ícone do shell interativo da Python Software Foundation](https://files.realpython.com/media/psf-shell1.5e8e53654e7a.png)](https://files.realpython.com/media/psf-shell1.5e8e53654e7a.png)

[![Ícone do shell interativo da Python Software Foundation](https://files.realpython.com/media/psf-shell2.dea07e54567d.png)](https://files.realpython.com/media/psf-shell2.dea07e54567d.png)

Ou vá diretamente para [https://www.python.org/shell](https://www.python.org/shell) .

Você deve obter uma página com uma janela parecida com esta:

[![Janela do shell interativo do Python Software Foundation](https://files.realpython.com/media/psf-shell3.6e56026f9512.png)](https://files.realpython.com/media/psf-shell3.6e56026f9512.png)

O prompt familiar `>>>`mostra que você está conversando com o interpretador Python.

Aqui estão alguns outros sites que fornecem Python REPL:

* [Python Fiddle](http://pythonfiddle.com/)
* [repl.it](https://repl.it/)
* [Bugiganga](https://trinket.io/)

[Remover propagandas](https://realpython.com/account/join/)

## Conclusão

Aplicativos maiores normalmente estão contidos em arquivos de script que são passados ao interpretador Python para execução.

Mas uma das vantagens de uma linguagem interpretada é que você pode executar o interpretador e executar comandos de forma interativa. Python é fácil de usar dessa maneira e é uma ótima maneira de começar a aprender como a linguagem funciona.

Os exemplos ao longo deste tutorial foram produzidos por interação direta com o interpretador Python, mas se você optar por usar IDLE ou algum outro IDE disponível, os exemplos ainda deverão funcionar perfeitamente.
