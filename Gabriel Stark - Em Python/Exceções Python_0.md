# ![Uma introdução às exceções do Python](https://files.realpython.com/media/Python_Exceptions_Watermark.47f814fbeced.jpg)

## Exceções Python: uma introdução

Assista agoraEste tutorial tem um curso em vídeo relacionado criado pela equipe Real Python. Assista junto com o tutorial escrito para aprofundar sua compreensão: [**Criando e Manipulando Exceções Python**](https://realpython.com/courses/raising-handling-exceptions/)

Um programa Python termina assim que encontra um erro. Em Python, um erro pode ser um erro de sintaxe ou uma exceção. Neste tutorial, você verá o que é uma exceção e como ela difere de um erro de sintaxe. Depois disso, você aprenderá como gerar exceções e fazer asserções. Em seguida, você conhecerá todas as palavras-chave relacionadas a exceções que podem ser usadas em um bloco `try`… `except`para ajustar como você pode trabalhar com exceções do Python.

**Neste tutorial, você aprenderá como:**

* **Levante uma exceção** em Python com `raise`
* **Depure e teste** seu código com `assert`
* **Lidar com exceções** com `try`e `except`
* **Ajuste seu tratamento de exceções** com `else`e `finally`

Você conhecerá essas palavras-chave percorrendo um exemplo prático de como lidar com uma exceção relacionada à plataforma. Por fim, você também aprenderá como criar suas próprias exceções Python personalizadas.

## Compreendendo exceções e erros de sintaxe

[Erros de sintaxe](https://realpython.com/invalid-syntax-python/) ocorrem quando o analisador detecta uma instrução incorreta. Observe o seguinte exemplo:

Rastreamento Python

```Python
>>> print(0 / 0))
  File "<stdin>", line 1
print(0 / 0))
^
SyntaxError: unmatched ')'
```

A seta indica onde o analisador encontrou o **erro de sintaxe** . Além disso, a mensagem de erro dá uma dica sobre o que deu errado. Neste exemplo, havia um colchete a mais. Remova-o e execute seu código novamente:

PYTHON

```Python
>>> print(0 / 0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
```

Desta vez, você encontrou um **erro de exceção** . Esse tipo de erro ocorre sempre que o código Python sintaticamente correto resulta em um erro. A última linha da mensagem indica que tipo de erro de exceção você encontrou.

Em vez de apenas escrever *error de exceção* , o Python detalha que *tipo* de erro de exceção encontrou. Neste caso, foi um `ZeroDivisionError`. Python vem com [várias exceções integradas](https://docs.python.org/3/library/exceptions.html) , bem como a possibilidade de criar exceções definidas pelo usuário.

## Levantando uma exceção em Python

Existem cenários em que você pode querer interromper seu programa gerando uma exceção se ocorrer uma condição. Você pode fazer isso com a [`raise`](https://realpython.com/python-raise-exception/)palavra-chave:

![![Ilustração do uso da instrução raise](https://files.realpython.com/media/raise.3931e8819e08.png)](https://files.realpython.com/media/raise.3931e8819e08.png)

Você pode até complementar a declaração com uma mensagem personalizada. Suponha que você esteja escrevendo um pequeno programa de brinquedo que espera apenas números até `5`. Você pode gerar um erro quando ocorre uma condição indesejada:

PYTHON

```Python
number = 10
if number > 5:
    raise Exception(f"The number should not exceed 5. ({number=})")
print(number)
```

Neste exemplo, você levantou um `Exception`objeto e passou a ele uma mensagem informativa personalizada. Você construiu a mensagem usando uma [string f](https://realpython.com/python-f-strings/) e uma [expressão autodocumentada](https://realpython.com/python-f-strings/#self-documenting-expressions-for-debugging) .

Ao executar `low.py`, você obterá a seguinte saída:

Rastreamento Python

```Python
Traceback (most recent call last):
  File "./low.py", line 3, in <module>
raise Exception(f"The number should not exceed 5. ({number=})")
Exception: The number should not exceed 5. (number=10)
```

O programa para e exibe a exceção em seu [terminal](https://realpython.com/terminal-commands/) ou [REPL](https://realpython.com/python-repl/) , oferecendo dicas úteis sobre o que deu errado. Observe que a chamada final [`print()`](https://realpython.com/python-print/)nunca foi executada, porque o Python gerou a exceção antes de chegar a essa linha de código.

Com a `raise`palavra-chave, você pode gerar qualquer objeto de exceção em Python e interromper seu programa quando ocorrer uma condição indesejada.

## Depuração durante o desenvolvimento com `assert`

Antes de passar para a maneira mais comum de trabalhar com exceções em Python usando [o bloco `try`…`except`](https://realpython.com/python-exceptions/#handling-exceptions-with-the-try-and-except-block) , você dará uma olhada rápida em uma exceção que é um pouco diferente das outras.

Python oferece um tipo de exceção específico que você só deve usar ao depurar seu programa durante o desenvolvimento. Esta exceção é o `AssertionError`. O `AssertionError`é especial porque você nunca deve aumentá-lo usando `raise`.

Em vez disso, você usa [a `assert`palavra-chave](https://dbader.org/blog/python-assert-tutorial) para verificar se uma condição foi atendida e permite que o Python aumente `AssertionError`se a condição não for atendida.

A ideia de uma afirmação é que seu programa só deve tentar ser executado se certas condições estiverem em vigor. Se o Python verificar sua afirmação e descobrir que a condição é `True`, então isso é excelente! O programa pode continuar. Se a condição for `False`, então seu programa gera uma `AssertionError`exceção e para imediatamente:

[![Instrução de afirmação Python](https://files.realpython.com/media/assert.f6d344f0c0b4.png)](https://files.realpython.com/media/assert.f6d344f0c0b4.png)

Revisite seu pequeno script, `low.py`da [seção anterior](https://realpython.com/python-exceptions/#raising-an-exception-in-python) . Atualmente, você está levantando explicitamente uma exceção quando uma determinada condição não é atendida:

PYTHON

```Python
number = 1
if number > 5:
    raise Exception(f"The number should not exceed 5. ({number=})")
print(number)
```

Supondo que você lidará com essa restrição com segurança em seu sistema de produção, você poderia substituir esta [instrução condicional](https://realpython.com/python-conditional-statements/) por uma asserção para obter uma maneira rápida de reter essa verificação de integridade durante o desenvolvimento:

PYTHON

```Python
number = 1
assert (number < 5), f"The number should not exceed 5. ({number=})"
print(number)
```

Se o `number`seu programa estiver abaixo de `5`, a asserção será aprovada e seu script continuará com a próxima linha de código. No entanto, se você definir `number`um valor superior a `5`—por exemplo, `10`—então o resultado da afirmação será `False`:

PYTHON

```Python
number = 10
assert (number < 5), f"The number should not exceed 5. ({number=})"
print(number)
```

Nesse caso, o Python gera um `AssertionError`que inclui a mensagem que você passou e finaliza a execução do programa:

Concha

```Python
$ pythonlow.py
Traceback (most recent call last):
  File "./low.py", line 2, in <module>
    assert (number < 5), f"The number should not exceed 5. ({number=})"
            ^^^^^^^^^^
AssertionError: The number should not exceed 5. (number=10)
```

Neste exemplo, gerar uma `AssertionError`exceção é a última coisa que o programa fará. O programa será então interrompido e não continuará. A chamada `print()`que segue a afirmação não será executada.

Usar asserções dessa forma pode ser útil quando você está depurando seu programa durante o desenvolvimento, porque pode ser bastante rápido e direto adicionar asserções ao seu código.

No entanto, você não deve confiar em asserções para capturar condições cruciais de execução do seu programa em produção. Isso ocorre porque o Python desativa globalmente as asserções quando você o executa no modo otimizado usando as opções de linha de comando [`-O`e `-OO`](https://docs.python.org/3/using/cmdline.html#cmdoption-O) :

Concha

```Python
$ python-Olow.py
10
```

Nesta execução do seu programa, você usou a `-O`opção de linha de comando, que remove todas `assert`as instruções. Portanto, seu script foi executado até o fim e exibiu um número *terrivelmente* alto!

**Nota:** Como alternativa, você também pode desabilitar asserções por meio da [`PYTHONOPTIMIZE`variável de ambiente](https://docs.python.org/3/using/cmdline.html#envvar-PYTHONOPTIMIZE) .

Na produção, seu código Python pode ser executado usando esse modo otimizado, o que significa que as asserções não são uma maneira confiável de lidar com erros de tempo de execução no código de produção. Eles podem ser ajudantes rápidos e úteis ao depurar seu código, mas você nunca deve usar asserções para definir restrições cruciais para seu programa.

Se `low.py`falhar de forma confiável quando `number`estiver acima `5`, então é melhor continuar [gerando uma exceção](https://realpython.com/python-exceptions/#raising-an-exception-in-python) . No entanto, às vezes você pode não querer que seu programa falhe ao encontrar uma exceção, então como você deve lidar com essas situações?

## Tratamento de exceções com o bloco `try`and `except`

Em Python, você usa o bloco `try`and `except`para capturar e tratar exceções. Python executa o código seguindo a `try`instrução como uma parte normal do programa. O código que segue a `except`instrução é a resposta do programa a quaisquer exceções na `try`cláusula anterior:

[![Diagrama mostrando instruções try e except](https://files.realpython.com/media/try_except.c94eabed2c59.png)](https://files.realpython.com/media/try_except.c94eabed2c59.png)

Como você viu anteriormente, quando o código sintaticamente correto apresenta um erro, o Python gerará um erro de exceção. Este erro de exceção irá travar o programa se você não lidar com isso. Na `except`cláusula, você pode determinar como seu programa deve responder às exceções.

A função a seguir pode ajudá-lo a entender o bloco `try`e `except`:

PYTHON

```Python
def linux_interaction():
    import sys
    if "linux" not in sys.platform:
        raise RuntimeError("Function can only run on Linux systems.")
    print("Doing Linux things.")
```

O `linux_interaction()`só pode ser executado em um sistema Linux. Python irá gerar uma `RuntimeError`exceção se você chamá-lo em um sistema operacional diferente do Linux.

**Nota:** Escolher o tipo de exceção correto às vezes pode ser complicado. Python vem com [muitas exceções integradas](https://docs.python.org/3/library/exceptions.html#concrete-exceptions) que são [hierarquicamente relacionadas](https://docs.python.org/3/library/exceptions.html#exception-hierarchy) , portanto, se você navegar na documentação, provavelmente encontrará uma que se encaixe.

O Python até agrupa algumas das exceções em categorias, como [avisos](https://docs.python.org/3/library/exceptions.html#warnings) que você deve usar para indicar condições de aviso e [exceções do sistema operacional](https://docs.python.org/3/library/exceptions.html#os-exceptions) que o Python gera dependendo dos códigos de erro do sistema.

Se você ainda não encontrou uma exceção adequada, poderá [criar uma exceção personalizada](https://realpython.com/python-exceptions/#creating-custom-exceptions-in-python) .

Você pode atribuir um a à função `try`adicionando o seguinte código:

PYTHON

```Python
# ...

try:
    linux_interaction()
except:
    pass
```

A maneira como você lidou com o erro aqui foi distribuindo um arquivo `pass`. Se você executar esse código em uma máquina macOS ou Windows, obterá a seguinte saída:

Concha

```Python
$pythonlinux_interaction.py
```

Você não recebeu nada em resposta. O bom aqui é que seu programa não travou. Mas deixar uma exceção que ocorreu passar silenciosamente é uma má prática. Você deve sempre pelo menos saber e [registrar](https://realpython.com/python-logging/) se ocorreu algum tipo de exceção ao executar seu código.

Para isso, você pode mudar `pass`para algo que gere uma mensagem informativa:

PYTHON

```Python
# ...

try:
    linux_interaction()
except:
    print("Linux function wasn't executed.")
```

Ao executar este código em uma máquina macOS ou Windows, você verá a mensagem do seu `except`bloco impressa no console:

Concha

```Python
$ pythonlinux_interaction.py
Linux function wasn't executed.
```

Quando ocorre uma exceção em um programa que executa esta função, o programa continuará e também informará que a chamada da função não foi bem-sucedida.

O que você não conseguiu ver foi o tipo de erro que o Python gerou como resultado da chamada da função. Para ver exatamente o que deu errado, você precisaria capturar o erro que a função gerou.

O código a seguir é um exemplo em que você captura `RuntimeError`e envia essa mensagem para sua tela:

PYTHON

```Python
# ...

try:
    linux_interaction()
except RuntimeError as error:
    print(error)
    print("The linux_interaction() function wasn't executed.")
```

Na `except`cláusula, você atribui o `RuntimeError`à variável temporária `error`- muitas vezes também chamada `err`- para que possa acessar o objeto de exceção no bloco recuado. Nesse caso, você está imprimindo a representação em string do objeto, que corresponde à mensagem de erro anexada ao objeto.

Executar esta função em uma máquina macOS ou Windows resulta no seguinte:

Concha

```Python
$ pythonlinux_interaction.py
Function can only run on Linux systems.
The linux_interaction() function wasn't executed.
```

A primeira mensagem é a `RuntimeError`, informando que Python só pode executar a função em uma máquina Linux. A segunda mensagem informa qual função não foi executada.

No exemplo acima, você chamou uma função que você mesmo escreveu. Ao executar a função, você capturou a `RuntimeError`exceção e a imprimiu na tela.

Aqui está outro exemplo em que você abre um arquivo e usa uma exceção integrada:

PYTHON

```Python
try:
    with open("file.log") as file:
        read_data = file.read()
except:
    print("Couldn't open file.log")
```

Se `file.log`não existir, este bloco de código produzirá o seguinte:

Concha

```Python
$ pythonopen_file.py
Couldn't open file.log
```

Esta é uma mensagem informativa e seu programa continuará em execução. No entanto, seu `except`bloco irá capturar *qualquer* exceção, seja ela relacionada a não conseguir abrir o arquivo ou não. Você pode se levar a um caminho confuso se vir esta mensagem mesmo quando o Python gera uma exceção completamente não relacionada.

Portanto, é sempre melhor ser *específico* ao lidar com uma exceção.

Na [documentação do Python](https://docs.python.org/3/library/exceptions.html) , você pode ver que há algumas exceções integradas que você pode levantar em tal situação, por exemplo:

> *exceção* `FileNotFoundError`
>
> Gerado quando um arquivo ou diretório é solicitado, mas não existe. Corresponde a erro ENOENT. ( [Fonte](https://docs.python.org/3/library/exceptions.html#FileNotFoundError) )

Você deseja lidar com a situação em que o Python não consegue encontrar o arquivo solicitado. Para capturar esse tipo de exceção e imprimi-la na tela, você poderia usar o seguinte código:

PYTHON

```Python
try:
    with open("file.log") as file:
        read_data = file.read()
except FileNotFoundError as fnf_error:
    print(fnf_error)
```

Neste caso, se `file.log`não existir, a saída será a seguinte:

Concha

```Python
$ pythonopen_file.py
[Errno 2] No such file or directory: 'file.log'
```

Você pode ter mais de uma chamada de função em sua `try`cláusula e antecipar a captura de várias exceções. Algo a ser observado aqui é que o código na `try`cláusula irá parar assim que encontrar qualquer exceção.

**Aviso:** quando você usa uma `except`cláusula simples, o Python captura qualquer exceção herdada de `Exception`—que são as exceções mais integradas! Capturar a classe pai `Exception`oculta todos os erros - mesmo aqueles que você não esperava. É por isso que você deve evitar `except`cláusulas simples em seus programas Python.

Em vez disso, você desejará consultar *classes de exceção específicas* que deseja capturar e manipular. Você pode aprender mais sobre por que isso é uma boa ideia [neste tutorial](https://realpython.com/the-most-diabolical-python-antipattern/) .

Observe o código a seguir. Aqui, você primeiro chama `linux_interaction()`e depois tenta abrir um arquivo:

PYTHON

```Python
# ...

try:
    linux_interaction()
    with open("file.log") as file:
        read_data = file.read()
except FileNotFoundError as fnf_error:
    print(fnf_error)
except RuntimeError as error:
    print(error)
    print("Linux linux_interaction() function wasn't executed.")
```

Se você executar este código em uma máquina macOS ou Windows, verá o seguinte:

Concha

```Python
$ pythonlinux_interaction.py
Function can only run on Linux systems.
Linux linux_interaction() function wasn't executed
```

Dentro da `try`cláusula, você encontrou uma exceção imediatamente e não chegou à parte em que tenta abrir o arquivo `file.log`. Agora veja o que acontece quando você executa o código em uma máquina Linux se o arquivo não existir:

Concha

```Python
$ pythonlinux_interaction.py
[Errno 2] No such file or directory: 'file.log'
```

Observe que se você estiver lidando com exceções específicas como fez acima, a ordem das `except`cláusulas não importa muito. É tudo uma questão de qual das exceções o Python levanta primeiro. Assim que o Python levanta uma exceção, ele verifica as cláusulas except de cima para baixo e executa a primeira correspondente que encontrar.

Aqui estão as principais conclusões sobre o uso das instruções `try`… do Python `except`:

* Python executa uma `try`cláusula até o ponto onde encontra a primeira exceção.
* Dentro da `except`cláusula — o manipulador de exceção — você determina como o programa responde à exceção.
* Você pode antecipar [diversas exceções](https://realpython.com/python-catch-multiple-exceptions/) e diferenciar como o programa deve responder a elas.
* [Evite usar `except`cláusulas](https://realpython.com/the-most-diabolical-python-antipattern/) simples , pois elas podem ocultar exceções inesperadas.

Embora usar `try`junto com `except`seja provavelmente o tratamento de erros mais comum que você encontrará, há mais que você pode fazer para ajustar a resposta do seu programa às exceções.

## Continuando após uma tentativa bem-sucedida `else`

Você pode usar a instrução Python `else`para instruir um programa a executar um determinado bloco de código apenas na ausência de exceções:

[![Diagrama de instruções try, except e else em Python](https://files.realpython.com/media/try_except_else.703aaeeb63d3.png)](https://files.realpython.com/media/try_except_else.703aaeeb63d3.png)

Veja o exemplo a seguir:

PYTHON

```Python
# ...

try:
    linux_interaction()
except RuntimeError as error:
    print(error)
else:
    print("Doing even more Linux things.")
```

Se você executasse este código em um sistema Linux, a saída seria a seguinte:

Concha

```Python
$ pythonlinux_interaction.py
Doing Linux things.
Doing even more Linux things.
```

Como o programa não encontrou *nenhuma* exceção, o Python executou o código da `else`cláusula. No entanto, se você executar este código em um sistema macOS ou Windows, obterá uma saída diferente:

Concha

```Python
$ pythonlinux_interaction.py
Function can only run on Linux systems.
```

A `linux_interaction()`função gerou um `RuntimeError`. Você tratou a exceção, então seu programa não trava e, em vez disso, imprime a mensagem de exceção no console. O código aninhado na `else`cláusula, entretanto, não é executado porque o Python encontrou uma exceção durante a execução.

Observe que estruturar seu código assim é diferente de apenas adicionar a chamada `print()`fora do contexto do bloco `try`… `except`:

PYTHON

```Python
# ...

try:
    linux_interaction()
except RuntimeError as error:
    print(error)
print("Doing even more Linux things.")
```

Se você não aninhar a `print()`chamada na `else`cláusula, ela será executada mesmo se o Python encontrar o `RuntimeError`que você trata no `except`bloco acima. Em um sistema Linux, a saída seria a mesma, mas no macOS ou Windows, você obteria a seguinte saída:

Concha

```Python
$ pythonlinux_interaction.py
Function can only run on Linux systems.
Doing even more Linux things.
```

O aninhamento do código sob a `else`cláusula garante que ele só será executado quando o Python não encontrar nenhuma exceção ao executar o bloco `try`… `except`.

Você também pode criar um bloco `try`… aninhado `except`dentro da `else`cláusula e capturar possíveis exceções lá também:

PYTHON

```Python
# ...

try:
    linux_interaction()
except RuntimeError as error:
    print(error)
else:
    try:
        with open("file.log") as file:
            read_data = file.read()
    except FileNotFoundError as fnf_error:
        print(fnf_error)
```

Se você executasse este código em uma máquina Linux, obteria o seguinte resultado:

Concha

```Python
$ pythonlinux_interaction.py
Doing Linux things.
[Errno 2] No such file or directory: 'file.log'
```

Na saída, você pode ver que `linux_interaction()`foi executado. Como o Python não encontrou exceções, ele tentou abrir arquivos `file.log`. Esse arquivo não existia, mas em vez de deixar o programa travar, você capturou a `FileNotFoundError`exceção e imprimiu uma mensagem no console.

## Limpando após a execução com `finally`

Imagine que você sempre tivesse que implementar algum tipo de ação para limpar após executar seu código. Python permite que você faça isso usando a `finally`cláusula:

[![Diagrama explicando as instruções try exceto else, finalmente](https://files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png)](https://files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png)

Dê uma olhada no exemplo a seguir:

PYTHON

```Python
# ...

try:
    linux_interaction()
except RuntimeError as error:
    print(error)
else:
    try:
        with open("file.log") as file:
            read_data = file.read()
    except FileNotFoundError as fnf_error:
        print(fnf_error)
finally:
    print("Cleaning up, irrespective of any exceptions.")
```

Neste código, Python executará tudo na `finally`cláusula. Não importa se você encontrar uma exceção em algum lugar de qualquer um dos `try`… `except`blocos. A execução do código em uma máquina macOS ou Windows resultará no seguinte:

Concha

```Python
$ pythonlinux_interaction.py
Function can only run on Linux systems.
Cleaning up, irrespective of any exceptions.
```

Observe que o código dentro do `finally`bloco será executado independentemente de você estar ou não lidando com as exceções:

PYTHON

```Python
# ...

try:
    linux_interaction()
finally:
    print("Cleaning up, irrespective of any exceptions.")
```

Você simplificou o código de exemplo acima, mas `linux_interaction()`ainda gera uma exceção em um sistema macOS ou Windows. Se você executar esse código em um sistema operacional diferente do Linux, obterá a seguinte saída:

Concha

```Python
$ pythonlinux_interaction.py
Cleaning up, irrespective of any exceptions.
Traceback (most recent call last):
  ...
RuntimeError: Function can only run on Linux systems.
```

Apesar do Python ter gerado o `RuntimeError`, o código na `finally`cláusula ainda foi executado e imprimiu a mensagem em seu console.

Isso pode ser útil porque mesmo o código fora de um bloco `try`… `except`não será necessariamente executado se o seu script encontrar uma exceção não tratada. Nesse caso, seu programa será encerrado e o código *após* o bloco `try`… `except`nunca será executado. No entanto, o Python ainda executará o código dentro da `finally`cláusula. Isso ajuda a garantir que recursos como [identificadores de arquivos](https://realpython.com/why-close-file-python/) e [conexões de banco de dados](https://realpython.com/python-sql-libraries/) sejam limpos corretamente.

## Criando exceções personalizadas em Python

Com o grande número de exceções integradas que o Python oferece, você provavelmente encontrará um tipo adequado ao decidir qual exceção gerar. No entanto, às vezes seu código não se ajusta ao molde.

Python simplifica a criação de tipos de exceção personalizados, herdando de uma exceção integrada. Pense novamente em sua `linux_interaction()`função:

PYTHON

```Python
def linux_interaction():
    import sys
    if "linux" not in sys.platform:
        raise RuntimeError("Function can only run on Linux systems.")
    print("Doing Linux things.")

# ...
```

Usar a [`RuntimeError`](https://docs.python.org/3/library/exceptions.html#RuntimeError)não é uma má escolha nesta situação, mas seria bom se o nome da sua exceção fosse um pouco mais específico. Para isso, você pode criar uma exceção personalizada:

PYTHON

```Python
class PlatformException(Exception):
"""Incompatible platform."""

# ...
```

Geralmente, você cria uma exceção personalizada em Python herdando from `Exception`, que também é a classe base para a maioria das exceções integradas do Python. Você também pode herdar de uma exceção diferente, mas escolher `Exception`geralmente é a melhor opção.

Isso é realmente tudo o que você precisa fazer. No trecho de código acima, você também adicionou uma [docstring](https://realpython.com/documenting-python-code/) que descreve o tipo de exceção e serve como corpo da classe.

**Nota:** Python requer algum código recuado no corpo da sua classe. Alternativamente ao uso da docstring, você também poderia ter usado [`pass`](https://realpython.com/python-pass/)ou [as reticências ( `...`)](https://realpython.com/python-ellipsis/) . No entanto, adicionar uma docstring descritiva agrega mais valor à sua exceção personalizada.

Embora você possa personalizar seu objeto de exceção, não é necessário fazer isso. Muitas vezes é suficiente dar às suas exceções personalizadas do Python um nome descritivo, para que você saiba o que aconteceu quando o Python levanta essa exceção no seu código.

Agora que você definiu a exceção personalizada, você pode criá-la como qualquer outra exceção do Python:

PYTHON

```Python
class PlatformException(Exception):
"""Incompatible platform."""

def linux_interaction():
    import sys
    if "linux" not in sys.platform:
        raise PlatformException("Function can only run on Linux systems.")
    print("Doing Linux things.")

# ...
```

Se você agora chamar `linux_interaction()`o macOS ou o Windows, verá que o Python gera sua exceção personalizada:

Concha

```Python
$ pythonlinux_interaction.py
Traceback (most recent call last):
  ...
PlatformException: Function can only run on Linux systems.
```

Você pode até usar seu custom `PlatformException`como classe pai para outras exceções customizadas que você pode nomear descritivamente para cada uma das plataformas nas quais os usuários podem executar seu código.

## Conclusão

Neste ponto, você está familiarizado com os conceitos básicos do uso de exceções do Python. Depois de ver a diferença entre erros de sintaxe e exceções, você aprendeu várias maneiras de gerar, capturar e tratar exceções em Python. Você também aprendeu como criar suas próprias exceções personalizadas.

Neste artigo, você ganhou experiência trabalhando com as seguintes palavras-chave relacionadas a exceções:

* `raise`permite que você crie uma exceção a qualquer momento.
* `assert`permite verificar se uma determinada condição foi atendida e gera uma exceção se não for.
* Na `try`cláusula, todas as instruções são executadas até que uma exceção seja encontrada.
* `except`permite capturar e tratar a exceção ou exceções que o Python encontrou na `try`cláusula.
* `else`permite codificar seções que devem ser executadas somente quando o Python não encontrar exceções na `try`cláusula.
* `finally`permite que você execute seções de código que sempre devem ser executadas, independentemente de o Python encontrar alguma exceção ou não.
