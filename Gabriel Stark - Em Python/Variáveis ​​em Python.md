# ![Variáveis em Python](https://files.realpython.com/media/Variables-in-Python_Watermarked.3868fbf92e1d.jpg)

## Variáveis em Python

Assista agora: Este tutorial tem um curso em vídeo relacionado criado pela equipe Real Python. Assista junto com o tutorial escrito para aprofundar sua compreensão: [**Variáveis em Python**](https://realpython.com/courses/variables-python/)

No tutorial anterior sobre [tipos de dados básicos em Python](https://realpython.com/python-data-types/) , você viu como os valores de vários tipos de dados Python podem ser criados. Mas até agora, todos os valores mostrados foram valores literais ou constantes:

PYTHON

```PY
>>> print(5.3)
5.3
```

Se você estiver escrevendo um código mais complexo, seu programa precisará de dados que podem mudar à medida que a execução do programa prossegue.

**Aqui está o que você aprenderá neste tutorial:** Você aprenderá como cada item de dados em um programa Python pode ser descrito pelo termo abstrato **object** e como manipular objetos usando nomes simbólicos chamados **variáveis** .

## Atribuição de Variável

Pense em uma variável como um nome associado a um objeto específico. Em Python, as variáveis não precisam ser declaradas ou definidas antecipadamente, como acontece em muitas outras linguagens de programação. Para criar uma variável, basta atribuir um valor a ela e começar a usá-la. A atribuição é feita com um único sinal de igual ( `=`):

PYTHON

```PY
>>> n = 300
```

Isso é lido ou interpretado como “ `n`é atribuído o valor `300`”. Feito isso, `n`pode ser usado em uma instrução ou expressão, e seu valor será substituído:

PYTHON

```PY
>>> print(n)
300
```

Assim como um valor literal pode ser exibido diretamente do prompt do interpretador em uma sessão REPL sem a necessidade de [`print()`](https://realpython.com/python-print/), uma variável também pode:

PYTHON

```py
>>> n
300
```

Posteriormente, se você alterar o valor de `n`e usá-lo novamente, o novo valor será substituído:

PYTHON

```py
>>> n = 1000
>>> print(n)
1000
>>> n
1000
```

Python também permite atribuição encadeada, o que possibilita atribuir o mesmo valor a diversas variáveis simultaneamente:

PYTHON

```py
>>> a = b = c = 300
>>> print(a, b, c)
300 300 300
```

A atribuição encadeada acima atribui `300`às variáveis `a`, `b`e `c`simultaneamente.

## Tipos de variáveis em Python

Em muitas linguagens de programação, as variáveis são digitadas estaticamente. Isso significa que uma variável é inicialmente declarada como tendo um tipo de dados específico, e qualquer valor atribuído a ela durante seu tempo de vida deve sempre ter esse tipo.

Variáveis em Python não estão sujeitas a esta restrição. Em Python, uma variável pode receber um valor de um tipo e depois reatribuir um valor de um tipo diferente:

PYTHON

```py
>>> var = 23.5
>>> print(var)
23.5

>>> var = "Now I'm a string"
>>> print(var)
Now I'm a string
```

## Referências de objetos

O que realmente está acontecendo quando você faz uma atribuição de variável? Esta é uma questão importante em Python, porque a resposta difere um pouco daquela que você encontraria em muitas outras linguagens de programação.

Python é uma [linguagem altamente orientada a objetos](https://realpython.com/python3-object-oriented-programming/) . Na verdade, praticamente todos os itens de dados em um programa Python são objetos de um tipo ou classe específica. (Este ponto será reiterado muitas vezes ao longo destes tutoriais.)

Considere este código:

PYTHON

```py
>>> print(300)
300
```

Ao receber a declaração `print(300)`, o intérprete faz o seguinte:

* Cria um objeto inteiro
* Dá o valor `300`
* Exibe no console

`type()`Você pode ver que um objeto inteiro é criado usando a função integrada :

PYTHON

```py
>>> type(300)
<class 'int'>
```

Uma variável Python é um nome simbólico que é uma referência ou [ponteiro](https://realpython.com/pointers-in-python/) para um objeto. Depois que um objeto é atribuído a uma variável, você pode referir-se ao objeto por esse nome. Mas os dados em si ainda estão contidos no objeto.

Por exemplo:

PYTHON

```py
>>> n = 300
```

Esta atribuição cria um objeto inteiro com o valor `300`e atribui a variável `n`para apontar para esse objeto.

[![Diagrama de referência variável](https://files.realpython.com/media/t.2d7bcb9afaaf.png)](https://files.realpython.com/media/t.2d7bcb9afaaf.png)
Atribuição de Variável

O código a seguir verifica se `n`aponta para um objeto inteiro:

PYTHON

```py
>>> print(n)
300
>>> type(n)
<class 'int'>
```

Agora considere a seguinte afirmação:

PYTHON

```py
>>> m = n
```

O que acontece quando ele é executado? Python não cria outro objeto. Ele simplesmente cria um novo nome simbólico ou referência, `m`que aponta para o mesmo objeto que `n`aponta.

[![Referências de variáveis Python para o mesmo objeto (ilustração)](https://files.realpython.com/media/t.d368386b8423.png)](https://files.realpython.com/media/t.d368386b8423.png)
Múltiplas referências a um único objeto

A seguir, suponha que você faça isso:

PYTHON

```py
>>> m = 400
```

Agora o Python cria um novo objeto inteiro com o valor `400`e `m`se torna uma referência a ele.

[![Referências para separar objetos em Python (diagrama)](https://files.realpython.com/media/t.d476d91592cd.png)](https://files.realpython.com/media/t.d476d91592cd.png)
Referências a objetos separados

Por último, suponha que esta instrução seja executada a seguir:

PYTHON

```py
>>> n = "foo"
```

Agora o Python cria um objeto string com o valor `"foo"`e faz `n`referência a ele.

[![Ilustração de referência de variável Python](https://files.realpython.com/media/t.344ab0b3aa8c.png)](https://files.realpython.com/media/t.344ab0b3aa8c.png)
Objeto Órfão

Não há mais nenhuma referência ao objeto inteiro `300`. Ele é órfão e não há como acessá-lo.

Os tutoriais desta série ocasionalmente se referirão à vida útil de um objeto. A vida de um objeto começa quando ele é criado, momento em que pelo menos uma referência a ele é criada. Durante a vida útil de um objeto, referências adicionais a ele podem ser criadas, como você viu acima, e referências a ele também podem ser excluídas. Um objeto permanece vivo, por assim dizer, enquanto houver pelo menos uma referência a ele.

Quando o número de referências a um objeto cai para zero, ele não está mais acessível. Nesse ponto, sua vida útil acabou. O Python eventualmente perceberá que está inacessível e recuperará a memória alocada para que possa ser usada para outra coisa. Na linguagem da informática, esse processo é conhecido como [coleta de lixo](https://en.wikipedia.org/wiki/Garbage_collection_%28computer_science%29) .

[Remover propagandas](https://realpython.com/account/join/)

## Identidade do Objeto

Em Python, cada objeto criado recebe um número que o identifica exclusivamente. É garantido que dois objetos não terão o mesmo identificador durante qualquer período em que seus tempos de vida se sobreponham. Uma vez que a contagem de referência de um objeto cai a zero e ele é coletado como lixo, como aconteceu com o `300`objeto acima, seu número de identificação fica disponível e pode ser usado novamente.

A função interna do Python `id()`retorna o identificador inteiro de um objeto. Usando a `id()`função, você pode verificar se duas variáveis realmente apontam para o mesmo objeto:

PYTHON

```py
>>> n = 300
>>> m = n
>>> id(n)
60127840
>>> id(m)
60127840

>>> m = 400
>>> id(m)
60127872
```

Após a atribuição `m = n`, `m`e `n`ambos apontam para o mesmo objeto, confirmado pelo fato de `id(m)`e `id(n)`retornarem o mesmo número. Uma vez `m`é reatribuído `400`e aponta para objetos diferentes com identidades diferentes.`m``n`

> Aprofundamento: Armazenamento em cache de pequenos valores inteiros
>
> Pelo que você sabe agora sobre atribuição de variáveis e referências a objetos em Python, o seguinte provavelmente não irá surpreendê-lo:
>
> PYTHON

 ```py
>>> m = 300
>>> n = 300
>>> id(m)
 60062304
>>> id(n)
 60062896
 ```

> Com a instrução `m = 300`, Python cria um objeto inteiro com o valor `300`e define `m`como referência a ele. `n`é então atribuído de forma semelhante a um objeto inteiro com valor `300`- mas não ao mesmo objeto. Assim, eles possuem identidades diferentes, o que você pode verificar a partir dos valores retornados por `id()`.
>
> Mas considere isto:
>
> PYTHON
>
 ```py
>>> m = 30
>>> n = 30
>>> id(m)
 1405569120
>>> id(n)
 1405569120
 ```

> Aqui, `m`e `n`são atribuídos separadamente a objetos inteiros com valor `30`. Mas neste caso, `id(m)`e `id(n)`são idênticos!
> Para fins de otimização, o interpretador cria objetos para os inteiros do intervalo `[-5, 256]`na inicialização e depois os reutiliza durante a execução do programa. Assim, quando você atribui variáveis separadas a um valor inteiro neste intervalo, elas na verdade farão referência ao mesmo objeto.

## Nomes de variáveis

Os exemplos que você viu até agora usaram nomes de variáveis curtos e concisos como `m`e `n`. Mas os nomes das variáveis podem ser mais detalhados. Na verdade, geralmente é benéfico se o forem, porque torna o propósito da variável mais evidente à primeira vista.

Oficialmente, os nomes de variáveis em Python podem ter qualquer comprimento e consistir em letras maiúsculas e minúsculas ( `A-Z`, `a-z`), dígitos ( `0-9`) e o caractere sublinhado ( `_`). Uma restrição adicional é que, embora um nome de variável possa conter dígitos, o primeiro caractere de um nome de variável não pode ser um dígito.

**Nota:** Uma das adições ao Python 3 foi [o suporte completo a Unicode](https://realpython.com/python-encodings-guide/) , que também permite caracteres Unicode em um nome de variável. Você aprenderá mais sobre Unicode em um tutorial futuro.

Por exemplo, todos os itens a seguir são nomes de variáveis válidos:

PYTHON

```py
>>> name = "Bob"
>>> Age = 54
>>> has_W2 = True
>>> print(name, Age, has_W2)
Bob 54 True
```

Mas este não é, porque o nome de uma variável não pode começar com um dígito:

PYTHON

```py
>>> 1099_filed = False
SyntaxError: invalid token
```

Observe que o caso é significativo. Letras minúsculas e maiúsculas não são iguais. O uso do caractere [sublinhado](https://realpython.com/python-double-underscore/) também é significativo. Cada um dos itens a seguir define uma variável diferente:

PYTHON

```py
>>> age = 1
>>> Age = 2
>>> aGe = 3
>>> AGE = 4
>>> a_g_e = 5
>>> _age = 6
>>> age_ = 7
>>> _AGE_ = 8

>>> print(age, Age, aGe, AGE, a_g_e, _age, age_, _AGE_)
1 2 3 4 5 6 7 8
```

Não há nada que impeça você de criar duas variáveis diferentes no mesmo programa chamado `age`and `Age`, ou nesse caso `agE`. Mas provavelmente é imprudente. Certamente seria provável que confundisse qualquer um que tentasse ler seu código, e até você mesmo, depois de ficar longe dele por algum tempo.

Vale a pena dar a uma variável um nome que seja descritivo o suficiente para deixar claro para que ela está sendo usada. Por exemplo, suponha que você esteja contando o número de pessoas que se formaram na faculdade. Você poderia escolher qualquer um dos seguintes:

PYTHON

```py
>>> numberofcollegegraduates = 2500
>>> NUMBEROFCOLLEGEGRADUATES = 2500
>>> numberOfCollegeGraduates = 2500
>>> NumberOfCollegeGraduates = 2500
>>> number_of_college_graduates = 2500

>>> print(numberofcollegegraduates, NUMBEROFCOLLEGEGRADUATES,
... numberOfCollegeGraduates, NumberOfCollegeGraduates,
... number_of_college_graduates)
2500 2500 2500 2500 2500
```

Todos eles são provavelmente escolhas melhores do que `n`, ou `ncg`, ou similares. Pelo menos você pode dizer pelo nome o que o valor da variável deve representar.

Por outro lado, nem todos são necessariamente igualmente legíveis. Tal como acontece com muitas coisas, é uma questão de preferência pessoal, mas a maioria das pessoas consideraria os dois primeiros exemplos, onde as letras estão todas juntas, mais difíceis de ler, especialmente aquele em letras maiúsculas. Os métodos mais comumente usados para construir um nome de variável com várias palavras são os três últimos exemplos:

* **Camel Case:** A segunda palavra e as palavras subsequentes são maiúsculas, para facilitar a visualização dos limites das palavras. (Presumivelmente, em algum momento alguém percebeu que as letras maiúsculas espalhadas pelo nome da variável lembram vagamente corcundas de camelo.)
  * Exemplo:`numberOfCollegeGraduates`
* **Caso Pascal:** Idêntico ao Caso Camel, exceto que a primeira palavra também é maiúscula.
  * Exemplo:`NumberOfCollegeGraduates`
* **Snake Case:** as palavras são separadas por sublinhados.
  * Exemplo:`number_of_college_graduates`

Os programadores debatem acaloradamente, com surpreendente fervor, qual destes é preferível. Argumentos decentes podem ser apresentados para todos eles. Use o que for mais atraente visualmente para você. Escolha um e use-o de forma consistente.

Você verá mais tarde que variáveis não são as únicas coisas que podem receber nomes. Você também pode nomear funções, classes, módulos e assim por diante. As regras que se aplicam aos nomes de variáveis também se aplicam aos identificadores, o termo mais geral para nomes dados a objetos de programa.

O [Guia de Estilo para Código Python](https://www.python.org/dev/peps/pep-0008/) , também conhecido como **PEP 8** , contém [Convenções de Nomenclatura](https://www.python.org/dev/peps/pep-0008/#naming-conventions) que listam padrões sugeridos para nomes de diferentes tipos de objetos. O PEP 8 inclui as seguintes recomendações:

* Snake Case deve ser usado para funções e nomes de variáveis.
* Pascal Case deve ser usado para nomes de classes. (PEP 8 refere-se a isso como a convenção “CapWords”.)

## Palavras reservadas (palavras-chave)

Há mais uma restrição aos nomes de identificadores. A linguagem Python reserva um pequeno conjunto de [palavras-chave](https://realpython.com/python-keywords/) que designam funcionalidades especiais da linguagem. Nenhum objeto pode ter o mesmo nome que uma palavra reservada.

No Python 3.6, existem 33 palavras-chave reservadas:

| ``Palavras-chave Python |           |            |          |
| ----------------------- | --------- | ---------- | -------- |
| `False`                 | `def`     | `if`       | `raise`  |
| `None`                  | `del`     | `import`   | `return` |
| `True`                  | `elif`    | `in`       | `try`    |
| `and`                   | `else`    | `is`       | `while`  |
| `as`                    | `except`  | `lambda`   | `with`   |
| `assert`                | `finally` | `nonlocal` | `yield`  |
| `break`                 | `for`     | `not`      |          |
| `class`                 | `from`    | `or`       |          |
| `continue`              | `global`  | `pass`     |          |

Você pode ver esta lista a qualquer momento digitando `help("keywords")`no interpretador Python. As palavras reservadas diferenciam maiúsculas de minúsculas e devem ser usadas exatamente como mostrado. Eles estão todos em letras minúsculas, exceto `False`, [`None`](https://realpython.com/null-in-python/), e `True`.

Tentar criar uma variável com o mesmo nome de qualquer palavra reservada resulta em erro:

PYTHON

```py
>>> for = 3
SyntaxError: invalid syntax
```

## Conclusão

Este tutorial abordou os fundamentos das **variáveis** Python , incluindo referências e identidade de objetos e nomenclatura de identificadores Python.

Agora você tem um bom entendimento de alguns tipos de dados do Python e sabe como criar variáveis que fazem referência a objetos desses tipos.
