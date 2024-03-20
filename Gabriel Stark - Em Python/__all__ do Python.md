#

![all do Python: pacotes, módulos e importações de curingas](https://files.realpython.com/media/Pythons-__all__-Set-Up-Your-Packages-and-Modules-for-Wildcard-Imports_Watermarked.698d61e0300d.jpg)

## __all__ do Python: pacotes, módulos e importações de curingas

Python tem algo chamado *importações curinga* , que se parecem com `from module import *`. Este tipo de importação permite que você coloque rapidamente todos os objetos de um módulo em seu name space. No entanto, usar esta importação em um pacote pode ser confuso porque não está claro o que você deseja importar: sub pacotes, módulos, objetos? Python tem a  *`__all__`* variável para contornar esse problema.

A `__all__`variável é uma lista de strings onde cada string representa o nome de uma variável, função, classe ou módulo que você deseja expor para importações curinga.

**Neste tutorial, você:**

* Entenda *as importações de curingas* em Python
* Use `__all__` para controlar os módulos que você *expõe* às importações de caracteres curinga
* Controle os *nomes* que você expõe em *módulos* e *pacotes*
* Explore *outros casos de uso* da `__all__`variável
* Conheça alguns *benefícios* e *práticas recomendadas* de uso `__all__`

Para aproveitar ao máximo este tutorial, você deve estar familiarizado com alguns conceitos do Python, incluindo [módulos e pacotes](https://realpython.com/python-modules-packages/) , e o sistema [de importação](https://realpython.com/python-import/) .

## Importando objetos em Python

Ao criar um projeto ou aplicativo Python, você precisará de uma maneira de acessar o código da [biblioteca padrão](https://docs.python.org/3/library/index.html) ou de bibliotecas de terceiros. Você também precisará acessar seu próprio código a partir dos vários arquivos que podem constituir seu projeto. [O sistema de importação](https://docs.python.org/3/reference/import.html#the-import-system) do Python é o mecanismo que permite fazer isso.

O sistema de importação permite obter objetos de diferentes maneiras. Você pode usar:

* Importações explícitas
* Importações curinga

Nas seções a seguir, você aprenderá os fundamentos de ambas as estratégias. Você aprenderá sobre as diferentes sintaxes que podem ser usadas em cada caso e o resultado da execução de uma [`import`](https://realpython.com/python-import/)instrução.

### Importações explícitas

Em Python, quando você precisa obter um objeto específico de um [módulo](https://realpython.com/python-modules-packages/#python-modules-overview) ou um módulo específico de um [pacote](https://realpython.com/python-modules-packages/#python-packages) , você pode usar uma instrução *explícita `import`* . Esse tipo de instrução permite trazer o objeto de destino para seu [name space](https://realpython.com/python-namespaces-scope/) atual para que você possa usar o objeto em seu código.

Para importar um módulo pelo seu nome, você pode usar a seguinte sintaxe:

PYTHON

```py
import module [as name]
```

Esta instrução permite importar um módulo pelo seu nome. [O módulo deve estar listado no import path](https://realpython.com/python-import/#pythons-import-path) do Python , que é uma lista de locais onde o [localizador baseado em caminho pesquisa](https://docs.python.org/3/glossary.html#term-path-based-finder) quando você executa uma importação.

A parte da sintaxe entre colchetes é opcional e permite criar um [alias](https://realpython.com/python-mutable-vs-immutable-types/#aliasing-variables) para o nome importado. Essa prática pode ajudá-lo a evitar colisões de nomes em seu código.

Por exemplo, digamos que você tenha o seguinte módulo:

PYTHON `calculations.py`

```py
def add(a, b):
    return float(a + b)

def subtract(a, b):
    return float(a - b)

def multiply(a, b):
    return float(a * b)

def divide(a, b):
    return float(a / b)
```

Este módulo de amostra fornece funções que permitem realizar cálculos básicos. O módulo que contém é chamado `calculations.py`. Para importar este módulo e usar as funções em seu código, vá em frente e inicie uma sessão [REPL](https://realpython.com/python-repl/) no mesmo diretório onde você salvou o arquivo.

Em seguida, execute o seguinte código:

PYTHON

```py
>>> import calculations

>>> calculations.add(2, 4)
6.0
>>> calculations.subtract(8, 4)
4.0
>>> calculations.multiply(5, 2)
10.0
>>> calculations.divide(12, 2)
6.0
```

 A `import`instrução no início deste trecho de código traz o nome do módulo para o seu name space atual. Para usar as funções ou qualquer outro objeto de `calculations`, você precisa usar [nomes totalmente qualificados](https://docs.python.org/3/glossary.html#term-qualified-name) com notação de ponto.

**Nota:** Você pode criar um alias `calculations`usando a seguinte sintaxe:

PYTHON

```py
import calculations as calc
```

Essa prática permite evitar conflitos de nomes em seu código. Em alguns contextos, também é prática comum reduzir o número de caracteres a serem digitados ao usar nomes qualificados.

Por exemplo, se você estiver familiarizado com bibliotecas como [NumPy](https://realpython.com/numpy-tutorial/) e [pandas](https://realpython.com/python-pandas-tricks/) , saberá que é comum usar as seguintes importações:

PYTHON

```py
import numpy as np
import pandas as pd
```

Usar aliases mais curtos ao importar módulos facilita o uso de seu conteúdo, aproveitando nomes qualificados.

Você também pode usar uma sintaxe semelhante para importar um pacote Python:

PYTHON

```py
import package [as name]
```

Nesse caso, o Python carrega o conteúdo do `__init__.py`arquivo do seu pacote no seu name space atual. Se esse arquivo exportar objetos, esses objetos estarão disponíveis para você.

Finalmente, se quiser ser mais específico no que importa para seu name space atual, você pode usar a seguinte sintaxe:

PYTHON

```py
from module import name [as name]
```

Com esta `import`instrução, você pode importar nomes específicos de um determinado módulo. Essa abordagem é recomendada quando você precisa apenas de alguns nomes de um módulo longo que define muitos objetos ou quando não espera colisões de nomes em seu código.

Para continuar com o `calculations`módulo, você pode importar apenas a função necessária:

PYTHON

```py
>>> from calculations import add

>>> add(2, 4)
6.0
```

Neste exemplo, você usa apenas a `add()`função. A `from module import name`sintaxe permite importar o nome do destino explicitamente. Nesse caso, o restante das funções e o próprio módulo não estarão acessíveis em seu name space ou [escopo](https://realpython.com/python-scope-legb-rule/) .

### Importações curinga em módulos

Ao trabalhar com módulos Python, uma *importação curinga* é um tipo de importação que permite obter todos os nomes [públicos](https://realpython.com/python-double-underscore/#public-and-non-public-names-in-modules-and-packages) de um módulo de uma só vez. Este tipo de importação possui a seguinte sintaxe:

PYTHON

```py
from module import *
```

O nome *importação curinga* deriva do asterisco no final da instrução, que indica que você deseja importar todos os objetos do `module`.

Volte para a janela do [terminal](https://realpython.com/terminal-commands/) e reinicie a sessão REPL. Em seguida, execute o seguinte código:

PYTHON

```py
>>> from calculations import *

>>> dir()
[
    ...
    'add',
    'divide',
    'multiply',
    'subtract'
]
```

Neste trecho de código, você primeiro executa uma importação curinga. Esta importação disponibiliza todos os nomes dos `calculations`módulos e os traz para o seu name space atual. A função integrada [`dir()`](https://realpython.com/python-scope-legb-rule/#dir)permite ver quais nomes estão disponíveis no name space atual. Como você pode confirmar na saída, todas as funções existentes `calculations`agora estão disponíveis.

Quando você tiver certeza absoluta de que precisa de todos os objetos definidos por um determinado módulo, usar uma importação curinga é uma solução rápida. Na prática, essa situação é rara e você acaba sobrecarregando seu name space com objetos e nomes desnecessários.

O uso de importações curinga é explicitamente desencorajado no [PEP 8](https://peps.python.org/pep-0008/) quando dizem:

> As importações de caracteres curinga ( `from <module> import *`) *devem ser evitadas* , pois não deixam claro quais nomes estão presentes no name space, confundindo tanto os leitores quanto muitas ferramentas automatizadas. Há um caso de uso defensável para uma importação curinga, que é republicar uma interface interna como parte de uma API pública (por exemplo, sobrescrevendo uma implementação Python pura de uma interface com as definições de um módulo acelerador opcional e exatamente quais definições serão sobrescrito não é conhecido antecipadamente). ( [Fonte](https://peps.python.org/pep-0008/#imports) )

A principal desvantagem da importação curinga é que você não tem controle sobre os objetos importados. Você não pode ser específico. Portanto, você pode confundir os usuários do seu código e sobrecarregar seu name space com objetos desnecessários.

Embora as importações de curingas sejam desencorajadas, algumas bibliotecas e ferramentas os utilizam. Por exemplo, se você pesquisar aplicativos criados com [Tkinter](https://docs.python.org/3/library/tkinter.html#tkinter-modules) , perceberá que muitos dos exemplos usam o formato:

PYTHON

```py
from tkinter import *
```

Esta importação dá acesso a todos os objetos definidos no `tkinter`módulo, o que é bastante conveniente se você está começando a aprender como usar esta ferramenta.

Você pode encontrar muitas outras ferramentas e bibliotecas de terceiros que usam importações de curingas para exemplos de código em sua documentação, e tudo bem. Porém, em projetos do mundo real, você deve evitar esse tipo de importação.

Na prática, você não pode controlar como os usuários do seu código gerenciarão suas importações. Portanto, é melhor você preparar seu código para importações curinga. Você aprenderá como fazer isso nas próximas seções. Primeiro, você aprenderá como usar importações curinga em pacotes.

### Importação de curingas e nomes não públicos

[Python tem uma convenção de nomenclatura](https://realpython.com/python-double-underscore/#public-interfaces-and-naming-conventions-in-python) bem estabelecida que permite informar aos usuários do seu código quando um determinado nome em um módulo é para uso interno ou externo.

Se o nome de um objeto começar com um [único sublinhado inicial](https://realpython.com/python-double-underscore/#single-leading-underscore-in-python-names) , esse nome será considerado *não público* e, portanto, será apenas para uso interno. Por outro lado, se um nome começar com uma letra minúscula ou maiúscula, então esse nome é *público* e, portanto, faz parte da [API](https://en.wikipedia.org/wiki/API) pública do módulo .

**Nota:** Em Python, para definir [identificadores](https://docs.python.org/3/reference/lexical_analysis.html#identifiers) ou nomes, você pode usar letras maiúsculas e minúsculas, o sublinhado ( `_`) e os dígitos de `0`até `9`. Observe que você não pode usar um dígito como primeiro caractere do nome.

Quando você tiver nomes não públicos em um determinado módulo, saiba que as importações de curingas não importarão esses nomes. Digamos que você tenha o seguinte módulo:

PYTHON `shapes.py`

```py
from math import pi as _pi

class Circle:
    def __init__(self, radius):
        self.radius = _validate(radius)

    def area(self):
        return _pi * self.radius**2

class Square:
    def __init__(self, side):
        self.side = _validate(side)

    def area(self):
        return self.side**2

def _validate(value):
    if not isinstance(value, int | float) or value <= 0:
        raise ValueError("positive number expected")
    return value
```

Neste módulo, você tem dois objetos não públicos `_pi`e `_validate()`. Você sabe disso porque eles têm um sublinhado inicial em seus nomes. Se alguém executar uma importação curinga neste módulo, os nomes não públicos não serão importados:

PYTHON

```py
>>> from shapes import *

>>> dir()
[
    'Circle',
    'Square',
    ...
]
```

Se você der uma olhada na saída de `dir()`, notará que apenas as classes `Circle`e `Square`estão disponíveis em seu name space atual. Os objetos não públicos `_pi`e `_validate()`, não estão disponíveis. Portanto, as importações de curingas não importarão nomes não públicos.

## Importação de curinga em pacotes

Até agora, você sabe como as importações de curingas funcionam com módulos. Você também pode usar esse tipo de importação com pacotes. Nesse caso, a sintaxe é a mesma, mas você precisa usar um nome de pacote em vez de um nome de módulo:

PYTHON

```py
from package import *
```

Agora, o que acontece quando você executa esse tipo de importação? Você pode esperar que esta importação faça com que o Python pesquise o sistema de arquivos, encontre os módulos e sub pacotes presentes no pacote e os importe.

No entanto, fazer essa pesquisa no sistema de arquivos pode levar muito tempo. Além disso, a importação de módulos pode ter [efeitos colaterais](https://en.wikipedia.org/wiki/Side_effect_(computer_science)) indesejados , porque quando você importa um módulo, todo o código executável desse módulo é executado.

Devido a esses possíveis problemas, o Python possui a [`__all__`](https://docs.python.org/3/tutorial/modules.html#importing-from-a-package)variável especial, que permitirá definir explicitamente a lista de módulos que você deseja expor para importação de curinga em um determinado pacote. Você explorará os detalhes na próxima seção.

## Preparando seus pacotes para importações curinga com `__all__`

Python tem dois comportamentos diferentes ao lidar com importações de curingas em pacotes. Ambos os comportamentos dependem da  *`__all__`* presença da variável no `__init__.py`arquivo do pacote.

* Se `__init__.py`não definir `__all__`, nada acontecerá quando você executar uma importação curinga no pacote.
* Se `__init__.py`define `__all__`, os objetos listados nele serão importados.

Para ilustrar o primeiro comportamento, vá em frente e crie uma nova pasta chamada `shapes/`. Dentro da pasta, crie os seguintes arquivos:

```py
shapes/
├── __init__.py
├── circle.py
├── square.py
└── utils.py
```

Deixe o `__init__.py`arquivo vazio por enquanto. Pegue o código do seu `shapes.py`arquivo e divida-o no restante dos arquivos. Clique na seção recolhível abaixo para ver como fazer isso:

O `shapes`pacoteAparecer esconder

Neste pacote de amostra, o `__init__.py`arquivo não define a `__all__`variável. Portanto, se você executar uma importação curinga neste pacote, não importará nenhum nome para o seu name space:

PYTHON

```py
>>> from shapes import *

>>> dir()
[
    '__annotations__',
    '__builtins__',
    ...
]
```

Neste exemplo, a `dir()`função revela que a importação de curinga não trouxe nenhum nome para o seu name space atual. Os módulos `circle`, `square`e `utils`não estão disponíveis em seu name space.

Se você não definir `__all__`em um pacote, a instrução `from package import *`não importará todos os módulos do pacote de destino para o name space atual. Nesse caso, a instrução import apenas garante que o pacote foi importado e executa qualquer código no formato `__init__.py`.

Se quiser preparar um pacote Python para importações curinga, você precisará definir a `__all__`variável no `__init__.py`arquivo do pacote. A `__all__`variável deve ser uma lista de [strings](https://realpython.com/python-strings/) contendo os nomes que você deseja exportar do seu pacote quando alguém usar uma importação curinga.

Vá em frente e adicione a seguinte linha ao arquivo:

PYTHON `shapes/__init__.py`

```py
__all__ = ["circle", "square"]
```

Ao definir a `__all__`variável no `__init__.py`arquivo, você estabelece os nomes dos módulos que uma importação curinga trará para o seu name space. Nesse caso, você deseja exportar apenas os módulos `circle`e `square`do seu pacote.

Agora, execute o seguinte código em sua sessão interativa:

PYTHON

```py
>>> from shapes import *

>>> dir()
[
    ...
    'circle',
    'square'
]
```

Agora, quando você executa uma importação curinga em seu `shapes`pacote, os módulos `circle`e `square`ficam disponíveis em seu name space. Observe que o `utils`módulo não está disponível porque você não o listou no arquivo `__all__`.

Cabe a você, como autor do pacote, construir esta lista e mantê-la atualizada. Manter a lista atualizada é crucial quando você lança uma nova versão do seu pacote. Nesse caso, também é importante observar que você receberá uma `AttributeError`exceção se `__all__`contiver nomes indefinidos.

**Nota:** Ao definir `__all__`, você deve estar ciente de que os módulos podem ser ocultados por nomes definidos localmente. Por exemplo, se você adicionou uma `square()`função ao `__init__.py`arquivo, a função irá ocultar o `square`módulo.

Finalmente, se você definir `__all__`como uma lista vazia, nada será exportado do seu pacote. É como não definir `__all__`no pacote.

## Expondo nomes de módulos e pacotes com `__all__`

Você já sabe que ao executar uma importação curinga em um módulo, você importará todas as [constantes](https://realpython.com/python-constants/) públicas , [variáveis](https://realpython.com/python-variables/) , [funções](https://realpython.com/defining-your-own-python-function/) , [classes](https://realpython.com/python-classes/) e outros objetos no módulo. Às vezes, esse comportamento é aceitável. No entanto, em alguns casos, você precisa ter um controle preciso sobre o que o módulo exporta. Você também pode usar `__all__`para esse objetivo.

Outro caso de uso interessante `__all__`é quando você precisa exportar nomes ou objetos específicos de um pacote. Nesse caso, você também pode usar `__all__`de uma forma um pouco diferente.

Nas seções a seguir, você aprenderá como `__all__`controlar quais nomes um módulo exporta e como exportar nomes específicos de um pacote.

### Nomes de um módulo

Você pode usar a `__all__`variável para controlar explicitamente quais nomes um módulo expõe às importações de curingas. Neste sentido, `__all__`permite estabelecer uma interface pública ou API de um módulo. Essa técnica também é uma forma de comunicar explicitamente qual é a API do módulo.

Se você tiver um módulo grande com muitos nomes públicos, poderá usá-lo `__all__`para criar uma lista de nomes exportáveis para que as importações de curingas não poluam o name space dos usuários do seu código.

Em geral, os módulos podem ter alguns tipos diferentes de nomes:

* *Os nomes públicos* fazem parte da interface pública do módulo.
* *Os nomes não públicos* são apenas para uso interno.
* *Nomes importados* são nomes que o módulo importa como nomes públicos ou não públicos.

Como você já sabe, nomes públicos são aqueles que começam com letra minúscula ou maiúscula. Nomes não públicos são aqueles que começam com um único sublinhado inicial.

Finalmente, os nomes importados são aqueles que você importa como nomes públicos em um módulo. Esses nomes também são exportados desse módulo. Então é por isso que você verá importações como as seguintes em muitas bases de código:

PYTHON

```py
import sys as _sys
```

Neste exemplo, você importa o `sys`módulo como `_sys`. O `as`especificador permite criar um alias para o objeto importado. Neste caso, o alias é um nome não público. Com esta pequena adição à sua instrução de importação, você evita `sys`a exportação quando alguém usa uma importação curinga no módulo.

Portanto, se você não quiser exportar objetos importados de um módulo, use o `as`especificador e um alias não público para os objetos importados.

Idealmente, a `__all__`lista deve conter apenas nomes públicos definidos no módulo que a contém. Por exemplo, digamos que você tenha o seguinte módulo contendo funções e classes que permitem fazer solicitações HTTP:

PYTHON `webreader.py`

```py
import requests

__all__ = ["get_page_content", "WebPage"]

BASE_URL = "http://example.com"

def get_page_content(page):
    return _fetch_page(page).text

def _fetch_page(page):
    url = f"{BASE_URL}/{page}"
    return requests.get(url)

class WebPage:
    def __init__(self, page):
        self.response = _fetch_page(page)

    def get_content(self):
        return self.response.text
```

Neste módulo de amostra, você importa a [`requests`](https://realpython.com/python-requests/)biblioteca. Em seguida, você define a `__all__`variável. Neste exemplo, `__all__`inclui a `get_page_content()`função e a `WebPage`classe, que são nomes públicos.

**Nota:** Você precisa ter a `requests`biblioteca instalada em seu ambiente Python atual para que o exemplo acima funcione corretamente.

Observe que a função auxiliar `_fetch_page()`é apenas para uso interno. Portanto, você não deseja expô-lo a importações curinga. Além disso, você não deseja que a `BASE_URL`constante ou o `requests`módulo importado sejam expostos a importações curinga.

Veja como o módulo responde a uma importação curinga:

PYTHON

```py
>>> from webreader import *

>>> dir()
[
    'WebPage',
    ...
    'get_page_content'
]
```

Ao executar uma importação curinga no `webreader`módulo, somente os nomes listados em `__all__`serão importados. Agora vá em frente e comente a linha onde você define `__all__`, reinicie sua sessão REPL e execute a importação novamente:

PYTHON

```py
>>> from webreader import *

>>> dir()
[
    'BASE_URL',
    'WebPage',
    ...
    'get_page_content',
    'requests'
]
```

Uma rápida olhada na saída `dir()`mostra que agora seu módulo exporta todos os nomes públicos, incluindo e até mesmo a biblioteca `BASE_URL`importada .`requests`

A `__all__`variável permite que você tenha controle total sobre o que um módulo expõe às importações de curingas. No entanto, observe que isso `__all__`não impede que você importe nomes específicos de um módulo usando uma importação explícita:

PYTHON

```py
>>> from webreader import _fetch_page

>>> dir()
[
    ...
    '_fetch_page'
]
```

Observe que você pode usar a importação explícita para trazer qualquer nome de um determinado módulo, até mesmo nomes não públicos como `_fetch_page()`no exemplo acima.

### Nomes de um pacote

Na seção anterior, você aprendeu como definir `__all__`quais objetos serão expostos a importações curinga. Às vezes, você deseja fazer algo semelhante, mas no nível do pacote. Se quiser controlar os objetos e nomes que um pacote expõe às importações de curingas, você pode fazer algo como o seguinte no `__init__.py`arquivo do pacote:

PYTHON `package/__init__.py`

```py
from module_0 import name_0, name_1, name_2, name_3
from module_1 import name_4, name_5, name_6

__all__ = [
    "name_0",
    "name_1",
    "name_2",
    "name_3",
    "name_4",
    "name_5",
    "name_6",
]
```

As `import`instruções dizem ao Python para obter os nomes de cada módulo do pacote. Então, em `__all__`, você lista os nomes importados como strings. Essa técnica é ótima para aqueles casos em que você possui um pacote com muitos módulos e deseja fornecer um caminho direto para importações.

Para exemplificar como essa técnica funciona na prática, volte ao `shapes`pacote e atualize o `__init__.py`arquivo conforme o código abaixo:

PYTHON `shapes/__init__.py`

```py
from shapes.circle import Circle
from shapes.square import Square

__all__ = ["Circle", "Square"]
```

Nesta atualização, você adicionou duas importações explícitas para obter as classes `Circle`e `Square`de seus respectivos módulos. Em seguida, você adiciona os nomes das classes como strings à `__all__`variável.

Veja como o pacote responde às importações de curingas agora:

PYTHON

```py
>>> from shapes import *

>>> dir()
[
    'Circle',
    'Square',
    ...
]
```

Seu `shapes`pacote expõe as classes `Circle`e `Square`às importações de curingas. Essas classes são o que você definiu como interface pública do seu pacote. Observe como esta técnica facilita o acesso direto a nomes que de outra forma você teria que importar através de nomes qualificados.

## Explorando casos de uso alternativos `__all__`em Python

Além de permitir que você controle o que seus módulos e pacotes expõem às importações de curingas, a `__all__`variável pode servir a outros propósitos. Você pode usar `__all__`para iterar sobre os nomes e objetos que compõem a interface pública de um pacote ou módulo. Você também pode aproveitar `__all__`quando precisar expor nomes dunder.

### Iterando na interface de um pacote

Como `__all__`normalmente é um [`list`](https://realpython.com/python-list/)objeto, você pode usá-lo para iterar sobre os objetos que compõem a interface de um módulo. A vantagem de usar `__all__`over `dir()`é que o autor do pacote definiu explicitamente quais nomes eles consideram fazer parte da interface pública do seu pacote. Se você iterar `__all__`, não precisará filtrar nomes não públicos como faria ao iterar `dir(module)`.

Por exemplo, digamos que você tenha um módulo com algumas classes semelhantes que compartilham a mesma interface. Aqui está um exemplo de brinquedo:

PYTHON `vehicles.py`

```py
__all__ = ["Car", "Truck"]

class Car:
    def start(self):
        print("The car is starting")

    def drive(self):
        print("The car is driving")

    def stop(self):
        print("The car is stopping")

class Truck:
    def start(self):
        print("The truck is starting")

    def drive(self):
        print("The truck is driving")

    def stop(self):
        print("The truck is stopping")
```

Neste módulo, você tem duas classes que representam veículos. Eles compartilham a mesma interface, então você pode usá-los em locais semelhantes. Você também definiu a `__all__`variável, listando as duas classes como strings.

Agora digamos que você queira usar essas classes em um loop. Como você pode fazer isso? Você pode usar `__all__`como no código abaixo:

PYTHON

```py
>>> import vehicles

>>> for v in vehicles.__all__:
...     vehicle = getattr(vehicles, v)()
...     vehicle.start()
...     vehicle.drive()
...     vehicle.stop()
...
The car is starting
The car is driving
The car is stopping
The truck is starting
The truck is driving
The truck is stopping
```

Neste exemplo, você primeiro importa o `vehicles`módulo. Então, você inicia um [`for`](https://realpython.com/python-for-loop/)loop sobre a `__all__`variável. Como `__all__`é uma lista de strings, você pode usar a função integrada `getattr()`para acessar os objetos especificados de `vehicles`. Dessa forma, você iterou as classes que compõem a API pública do módulo.

### Acessando nomes não públicos e Dunder

Ao escrever módulos e pacotes, às vezes você usa nomes em nível de módulo que começam e terminam com sublinhados duplos. Esses nomes são normalmente chamados de *nomes dunder* . Existem algumas [constantes dunder](https://realpython.com/python-constants/#module-level-dunder-constants) , como `__version__`e `__author__`, que você pode precisar expor para importações curinga.

Lembre-se de que o comportamento padrão é que esses nomes não sejam importados porque começam com um sublinhado à esquerda. Para contornar esse problema, você pode listar explicitamente esses nomes em sua `__all__`variável.

Para ilustrar esta prática, recupere seu `webreader.py`arquivo e atualize-o conforme o código abaixo:

PYTHON `webreader.py`

```py
import requests

__version__ = "1.0.0"
__author__ = "Real Python"

__all__ = ["get_page_content", "WebPage", "__version__", "__author__"]

BASE_URL = "http://example.com"

def get_page_content(page):
    return _fetch_page(page).text

# ...
```

Nesta atualização, você define duas constantes em nível de módulo que usam nomes dunder. A primeira constante fornece informações sobre a versão do módulo e a segunda constante contém o nome do autor.

Veja como funciona uma importação curinga neste módulo:

PYTHON

```py
>>> from webreader import *

>>> dir()
[
    'WebPage',
    ...
    '__author__',
    ...
    '__version__',
    'get_page_content'
]
```

Agora, quando alguém usa uma importação curinga no `webreader`módulo, ele obtém as variáveis dunder importadas para seu name space.

## Usando `__all__`em Python: benefícios e práticas recomendadas

Até agora, você aprendeu muito sobre a `__all__`variável e como usá-la em seu código. Embora você não precise usar `__all__`, ele oferece controle total sobre o que seus pacotes e módulos expõem às importações curinga.

A `__all__`variável também é uma forma de comunicar aos usuários de seus pacotes e módulos quais partes do seu código eles devem usar como interface pública.

Aqui está um rápido resumo dos *principais benefícios* que `__all__`pode proporcionar:

* *Controle sobre o que você expõe às importações curinga* : O uso `__all__`permite especificar explicitamente a interface pública de seus pacotes e módulos. Esta prática evita o uso acidental de objetos que não deveriam ser usados fora do módulo. Ele fornece um limite claro entre a implementação interna do módulo e sua API pública.
* *Melhorar a legibilidade* : o uso `__all__`permite que outros desenvolvedores aprendam rapidamente quais objetos compõem a API do código sem examinar toda a base de código. Isso melhora a legibilidade do código e economiza tempo, especialmente para projetos maiores com vários módulos.
* *Reduza a confusão de name spaces* : o uso `__all__`permite listar os nomes a serem expostos às importações de curingas. Dessa forma, você evita que outros desenvolvedores poluam seu name space com nomes desnecessários ou conflitantes.

Embora as importações de curingas sejam desencorajadas em Python, você não tem como controlar o que os usuários do seu código farão ao usá-lo. Portanto, using `__all__`é uma boa maneira de limitar o uso errado do seu código.

Aqui está uma lista rápida de *práticas recomendadas* para usar `__all__`em seu código:

* *Procure sempre definir `__all__`em seus pacotes e módulos.* Esta variável fornece controle explícito sobre o que outros desenvolvedores podem importar com importações curinga.
* *Aproveite `__all__`como uma ferramenta para definir explicitamente a interface pública de seus pacotes e módulos.* Esta prática deixa claro para outros desenvolvedores quais objetos são destinados ao uso externo e quais são apenas para uso interno.
* *Mantenha `__all__`o foco.* As `__all__`variáveis não devem incluir todos os objetos do seu módulo, apenas aqueles que fazem parte da API pública.
* *Use `__all__`em conjunto com boa documentação.* Uma documentação clara sobre o uso pretendido e o comportamento de cada objeto na API pública é o melhor complemento para o `__all__`.
* *Seja consistente no uso `__all__`de todos os seus pacotes e módulos.* Essa prática permite que outros desenvolvedores entendam melhor como usar seu código.
* *Revise e atualize regularmente `__all__`.* A `__all__`variável deve sempre refletir as alterações mais recentes na API do seu código. A manutenção regular `__all__`garante que seu código permaneça limpo e utilizável.

Por fim, lembre-se de que isso `__all__`afeta apenas as importações curinga. Se um usuário do seu código importar um objeto específico de um pacote ou módulo, esse objeto será importado mesmo que você não o tenha listado no arquivo `__all__`.

## Conclusão

Agora você sabe o que são importações curinga em Python. Você aprendeu que essas importações permitem obter rapidamente todos os objetos públicos de módulos e pacotes. Para controlar o processo, Python possui a `__all__`variável, que você pode definir em seus módulos e pacotes como uma lista de objetos que estão disponíveis para importações curinga.

A `__all__`variável é uma lista de strings onde cada string representa o nome de uma variável, função, classe ou módulo.

**Neste tutorial, você aprendeu como:**

* Trabalhe com *importações curinga* em Python
* Controle os módulos que você *expõe* às importações curinga com**`__all__`**
* Controle os *nomes* que você expõe em *módulos* e *pacotes* .
* Explore *outros casos de uso* para a `__all__`variável
* Entenda os *benefícios* e *as melhores práticas* de uso `__all__`

Com esse conhecimento, agora você pode escrever módulos e pacotes mais robustos, legíveis e confiáveis, com comportamento explícito em relação a importações de curingas em seu código.
