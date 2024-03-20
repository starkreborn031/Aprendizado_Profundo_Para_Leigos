# Variáveis Python

Variável Python são contêineres que armazenam valores. Python não é “digitado estaticamente”. Não precisamos declarar variáveis antes de usá-las ou declarar seu tipo. Uma variável é criada no momento em que atribuímos um valor a ela pela primeira vez. Uma variável Python é um nome dado a um local de memória. É a unidade básica de armazenamento de um programa. Neste artigo, veremos como definir uma variável em [Python](https://www.geeksforgeeks.org/python-programming-language/) .

## Exemplo de variável em Python

Um exemplo de variável em Python é um nome representacional que serve como um ponteiro para um objeto. Depois que um objeto é atribuído a uma variável, ele pode ser referido por esse nome. Em termos leigos, podemos dizer que Variável em Python são contêineres que armazenam valores.

Aqui armazenamos “ **Geeks forgeeks** ”  em uma variável var , e quando chamarmos seu nome as informações armazenadas serão impressas.

* Python3

| `Var ``=` `"Geeksforgeeks"``print``(Var)` |
| ----------------------------------------- |
|                                           |

**Saída:**

Geeks forgeeks

> ****Notas:****
>
> * O valor armazenado em uma variável pode ser alterado durante a execução do programa.
> * Uma variável em Python é apenas um nome dado a um local de memória, todas as operações feitas na variável afetam esse local de memória.

### ****Regras para variáveis Python****

* O nome de uma variável Python deve começar com uma letra ou sublinhado.
* O nome de uma variável Python não pode começar com um número.
* Um nome de variável Python pode conter apenas caracteres alfanuméricos e sublinhados (Az, 0-9 e _).
* Os nomes de variáveis em Python diferenciam maiúsculas de minúsculas (nome, Nome e NOME são três variáveis diferentes).
* As [palavras reservadas (palavras-chave)](https://www.geeksforgeeks.org/python-keywords-and-identifiers/) em Python não podem ser usadas para nomear a variável em Python.

## **Exemplo**

* Python3

| `# valid variable name``geeks ``=` `1``Geeks ``=` `2``Ge_e_ks ``=` `5``_geeks ``=` `6``geeks_ ``=` `7``_GEEKS_ ``=` `8` `print``(geeks, Geeks, Ge_e_ks)``print``(_geeks, geeks_, _GEEKS_)` |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|                                                                                                                                                                                            |

**Saída:**

```py
1 2 5 
6 7 8
```

## **Atribuição de variáveis em Python**

Aqui, definiremos uma variável em python. Aqui, claramente atribuímos um número, um número de ponto flutuante e uma string a uma variável como idade, salário e nome.

* Python3

| `# An integer assignment``age ``=` `45` `# A floating point``salary ``=` `1456.8` `# A string``name ``=` `"John"` `print``(age)``print``(salary)``print``(name)` |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                                                                  |

**Saída:**

```py
45 
1456,8 
João
```

### **Declaração e inicialização de variáveis**

Vamos ver como declarar uma variável e como definir uma variável e imprimir a variável.

* Python3

| `# declaring the var``Number ``=` `100` `# display``print``( Number)` |
| --------------------------------------------------------------------- |
|                                                                       |

**Saída:**

```py
100
```

### **Redeclarando variáveis em Python**

Podemos declarar novamente a variável Python depois de declarar a variável e já definir a variável em python.

* Python3

| `# declaring the var``Number ``=` `100` `# display``print``(``"Before declare: "``, Number)` `# re-declare the var``Number ``=` `120.3`` ``print``(``"After re-declare:"``, Number)` |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                                                                                        |

**Saída:**

```py
Antes da declaração: 100 
Depois da nova declaração: 120,3
```

### **Python atribui valores a múltiplas variáveis**

Além disso, Python permite atribuir um único valor a várias variáveis simultaneamente com operadores “=”.
Por exemplo:

* Python3

| `a ``=` `b ``=` `c ``=` `10` `print``(a)``print``(b)``print``(c)` |
| ----------------------------------------------------------------- |
|                                                                   |

**Saída:**

```py
10 
10 
10
```

### **Atribuindo valores diferentes a múltiplas variáveis**

Python permite adicionar valores diferentes em uma única linha com operadores “,”.

* Python3

| `a, b, c ``=` `1``, ``20.2``, ``"GeeksforGeeks"` `print``(a)``print``(b)``print``(c)` |
| ------------------------------------------------------------------------------------- |
|                                                                                       |

**Saída:**

```py
120,2 Geeks 
para 
Geeks
```

### **Podemos usar** o mesmo **nome para tipos diferentes?**

Se usarmos o mesmo nome, a variável passa a se referir a um novo valor e tipo.

* Python3

| `a ``=` `10``a ``=` `"GeeksforGeeks"` `print``(a)` |
| -------------------------------------------------- |
|                                                    |

**Saída:**

```py
GeeksparaGeeks
```

### **Como o operador + funciona com variáveis?**

O operador Python plus + fornece uma maneira conveniente de adicionar um valor se for um número e [concatenar](https://www.geeksforgeeks.org/python-string-concatenation/) se for uma string. Se uma variável já tiver sido criada, ele atribui o novo valor de volta à mesma variável.

* Python3

| `a ``=` `10``b ``=` `20``print``(a``+``b)` `a ``=` `"Geeksfor"``b ``=` `"Geeks"``print``(a``+``b)` |
| -------------------------------------------------------------------------------------------------- |
|                                                                                                    |

### **Podemos usar + para diferentes tipos de dados também?**

Nenhum uso para tipos diferentes produziria um erro.

* Python3

| `a ``=` `10``b ``=` `"Geeks"``print``(a``+``b)` |
| ----------------------------------------------- |
|                                                 |

**Saída :**

```py
TypeError: tipos de operandos não suportados para +: 'int' e 'str'
```

## Variáveis Python globais e locais

**Variáveis locais** em Python são aquelas definidas e declaradas dentro de uma função. Não podemos chamar esta variável fora da função.

* Python3

| `# This function uses global variable s``def` `f():``    ``s ``=` `"Welcome geeks"``    ``print``(s)`  `f()` |
| ------------------------------------------------------------------------------------------------------------ |
|                                                                                                              |

**Saída:**

```py
Bem-vindos geeks
```

****Variáveis globais** em Python são aquelas definidas e declaradas fora de uma função, e precisamos usá-las dentro de uma função.

* Python3

| `# This function has a variable with``# name same as s``def` `f():``    ``print``(s)` `# Global scope``s ``=` `"I love Geeksforgeeks"``f()` |
| ------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                                             |

**Saída:**

```py
Eu amo Geeksforgeeks
```

## Palavra-chave global em Python

Python global é uma palavra-chave que permite ao usuário modificar uma variável fora do escopo atual. É usado para criar [variáveis globais](https://www.geeksforgeeks.org/global-local-variables-python/) a partir de um escopo não global, ou seja, dentro de uma função. A palavra-chave global é usada dentro de uma função apenas quando queremos fazer atribuições ou quando queremos alterar uma variável. Global não é necessário para impressão e acesso.

### **Regras de palavra-chave global**

* Se for atribuído um valor a uma variável em qualquer lugar do corpo da função, ela será considerada local, a menos que seja explicitamente declarada como global.
* Variáveis que são referenciadas apenas dentro de uma função são implicitamente globais.
* Usamos global em Python para usar uma variável global dentro de uma função.
* Não há necessidade de usar uma palavra-chave global em Python fora de uma função.

**Exemplo:**

Programa Python para modificar um valor global dentro de uma função.

* Python3

| `x ``=` `15` `def` `change():` ```# using a global keyword``` `global` `x` ```# increment value of a by 5``` `x ``=` `x ``+` `5``    ``print``(``"Value of x inside a function :"``, x)`  `change()``print``(``"Value of x outside a function :"``, x)` |

**Saída:**

```py
Valor de x dentro de uma função: 20 
Valor de x fora de uma função: 20
```

## Tipos de variáveis em Python

Os tipos de dados são a classificação ou categorização de itens de dados. Representa o tipo de valor que indica quais operações podem ser executadas em um determinado dado. Como tudo é um objeto na programação Python, os tipos de dados são na verdade classes e as variáveis são instâncias (objeto) dessas classes.

### Os tipos de dados Python integrados são

* [Numérico](https://www.geeksforgeeks.org/python-numbers/)
* [Tipo de texto](https://www.geeksforgeeks.org/python-string/)
* [lista Python](https://www.geeksforgeeks.org/python-lists/), [tupla Python](https://www.geeksforgeeks.org/python-tuples/), [intervalo Python](https://www.geeksforgeeks.org/python-range-function/)
* [boleano](https://www.geeksforgeeks.org/boolean-data-type-in-python/)
* [Definir](https://www.geeksforgeeks.org/sets-in-python/)
* [Dicionário](https://www.geeksforgeeks.org/python-dictionary/)

**Exemplo:**

Neste exemplo, mostramos diferentes exemplos de tipos de dados integrados em Python.

* Python3

| `# numberic``var ``=` `123``print``(``"Numeric data : "``, var)` `# Sequence Type``String1 ``=` `'Welcome to the Geeks World'``print``(``"String with the use of Single Quotes: "``)``print``(String1)` `# Boolean``print``(``type``(``True``))``print``(``type``(``False``))` `# Creating a Set with``# the use of a String``set1 ``=` `set``(``"GeeksForGeeks"``)``print``(``"\nSet with the use of String: "``)``print``(set1)` `# Creating a Dictionary``# with Integer Keys``Dict` `=` `{``1``: ``'Geeks'``, ``2``: ``'For'``, ``3``: ``'Geeks'``}``print``(``"\nDictionary with the use of Integer Keys: "``)``print``(``Dict``)` |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**Saída:**

```py
Dados numéricos: 123 
String com o uso de aspas simples: 
Bem-vindo ao mundo Geeks 
<class 'bool'> 
<class 'bool'> 
Definido com o uso de String: 
{'r', 'G', 'e', ' k', 'o', 's', 'F'} 
Dicionário com o uso de chaves inteiras: 
{1: 'Geeks', 2: 'For', 3: 'Geeks'}
```

## **Referência de objeto em Python**

Vamos atribuir uma variável x ao valor 5.

```py
x = 5
```

![Referências de objetos](https://media.geeksforgeeks.org/wp-content/uploads/20220720165502/1.png)

Outra variável é ****y**** elevado à variável ****x.****

```py
y = x
```

![Referências de objetos em Python](https://media.geeksforgeeks.org/wp-content/uploads/20220720165503/2.png)

Quando Python olha para a primeira instrução, o que ele faz é, primeiro, criar um objeto para representar o valor 5. Em seguida, ele cria a variável x se ela não existir e faz dela uma referência a esse novo objeto 5. A segunda linha faz com que o Python crie a variável y, e ela não é atribuída a x, mas sim para fazer referência ao objeto que x faz. O efeito líquido é que as variáveis x e y acabam referenciando o mesmo objeto. Esta situação, com vários nomes referenciando o mesmo objeto, é chamada de ****Referência Compartilhada**** em Python.
Agora, se escrevermos:

```py
x = 'Geeks'
```

Esta instrução cria um novo objeto para representar 'Geeks' e faz com que x faça referência a esse novo objeto.

![Variável Python](https://media.geeksforgeeks.org/wp-content/uploads/20220720165503/3.png)

Agora, se atribuirmos o novo valor em ****Y,**** então o objeto anterior se refere aos valores de lixo.

```py
y = "Computador"
```

![Referências de objetos em Python](https://media.geeksforgeeks.org/wp-content/uploads/20220720165504/4.png)

### **Criando objetos (ou variáveis de um tipo de classe)**

Consulte [Classe, Objeto e Membros](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-1-class-and-its-members/) para obter mais detalhes.

* Python3

| `class` `CSStudent:``    ``# Class Variable``    ``stream ``=` `'cse'``    ``# The init method or constructor``    ``def` `__init__(``self``, roll):``        ``# Instance Variable``        ``self``.roll ``=` `roll` `# Objects of CSStudent class``a ``=` `CSStudent(``101``)``b ``=` `CSStudent(``102``)` `print``(a.stream)  ``# prints "cse"``print``(b.stream)  ``# prints "cse"``print``(a.roll)    ``# prints 101` `# Class variables can be accessed using class``# name also``print``(CSStudent.stream)  ``# prints "cse"` |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |

### 1. Como definir uma variável em Python?

> Em Python, podemos definir uma variável atribuindo um valor a um nome. Os nomes das variáveis devem começar com uma letra (az, AZ) ou um sublinhado (_) e podem ser seguidos por letras, sublinhados ou dígitos (0-9). Python é digitado dinamicamente, o que significa que não precisamos declarar explicitamente o tipo da variável; será inferido com base no valor atribuído.

### 2. **Existem convenções de nomenclatura para variáveis Python?**

> Sim, Python segue a convenção Snake_case para nomes de variáveis (por exemplo, `<span>my_variable</span>`). Eles devem começar com uma letra ou sublinhado, seguido de letras, sublinhados ou números. As constantes geralmente são nomeadas em ALL_CAPS.

### 3. **Posso alterar o tipo de uma variável Python?**

> Sim, Python é digitado dinamicamente, o que significa que você pode alterar o tipo de uma variável atribuindo um novo valor de um tipo diferente. Por exemplo:

* Python3

| `my_variable ``=` `42` `# Integer``my_variable ``=` `"Hello, Python!"` `# String` |
| --------------------------------------------------------------------------------- |
|                                                                                   |

Não perca a chance de aproveitar a onda da revolução dos dados! Cada setor está alcançando novos patamares ao aproveitar o poder dos dados. Aprimore suas habilidades e faça parte da tendência mais quente do século XXI.

Mergulhe no futuro da tecnologia - explore o [Programa Completo de Aprendizado de Máquina e Ciência de Dados](https://www.geeksforgeeks.org/courses/data-science-live?utm_source=geeksforgeeks&utm_medium=article_bottom_text&utm_campaign=courses) da Geeks forGeeks e fique à frente da curva.
