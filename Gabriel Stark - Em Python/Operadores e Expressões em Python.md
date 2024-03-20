# ![Operadores e Expressões em Python](https://files.realpython.com/media/Operators-and-Expressions-in-Python_Watermarked.651045da4031.jpg)

## Operadores e Expressões em Python

Em Python, **os operadores** são símbolos especiais, combinações de símbolos ou palavras-chave que designam algum tipo de computação. Você pode combinar objetos e operadores para criar **expressões** que executem o cálculo real. Portanto, os operadores são os blocos de construção das expressões, que você pode usar para manipular seus dados. Portanto, entender como os operadores funcionam em Python é essencial para você como programador.

Neste tutorial, você aprenderá sobre os operadores que o Python suporta atualmente. Você também aprenderá o básico sobre como usar esses operadores para construir expressões.

**Neste tutorial, você:**

* Conheça **os operadores aritméticos** do Python e use-os para construir **expressões aritméticas**
* Explore os operadores **de comparação** , **booleano** , **identidade** e **associação do Python**
* Crie **expressões** com operadores de comparação, booleanos, de identidade e de associação
* **Aprenda sobre os operadores bit a bit** do Python e como usá-los
* Combine e repita sequências usando os operadores **de concatenação** e **repetição**
* Entenda os operadores **de atribuição aumentada** e como eles funcionam

## Introdução aos operadores e expressões

Na programação, um **operador** geralmente é um símbolo ou combinação de símbolos que permite realizar uma operação específica. Esta operação pode atuar sobre um ou mais **operandos** . Se a operação envolver um único operando, então o operador é **unário** . Se o operador envolver dois operandos, então o operador é **binário** .

Por exemplo, em Python, você pode usar o sinal de menos ( `-`) como operador unário para declarar um número negativo. Você também pode usá-lo para subtrair dois números:

PYTHON

```py
>>> -273.15
-273.15

>>> 5 - 2
3
```

Neste trecho de código, o sinal de menos ( `-`) no primeiro exemplo é um operador unário e o número `273.15`é o operando. No segundo exemplo, o mesmo símbolo é um operador binário, e os números `5`e `2`são seus operandos esquerdo e direito.

As linguagens de programação normalmente possuem operadores integrados como parte de sua sintaxe. Em muitas linguagens, incluindo Python, você também pode criar seu próprio operador ou modificar o comportamento dos existentes, o que é um recurso poderoso e avançado.

Na prática, os operadores fornecem um atalho rápido para manipular dados, realizar cálculos matemáticos, comparar valores, executar testes [booleanos](https://realpython.com/python-boolean/) , atribuir valores a variáveis e muito mais. Em Python, um operador pode ser um símbolo, uma combinação de símbolos ou uma [palavra-chave](https://realpython.com/python-keywords/) , dependendo do tipo de operador com o qual você está lidando.

Por exemplo, você já viu o operador de subtração, que é representado por um único sinal de menos ( `-`). O operador de igualdade é um sinal de igual duplo ( `==`). Então, é uma combinação de símbolos:

Python

```Python
>>> 42 == 42
True
```

Neste exemplo, você usa o operador de igualdade do Python ( `==`) para comparar dois números. Como resultado, você obtém [`True`](https://docs.python.org/3/library/constants.html#True), que é um dos valores booleanos do Python.

Falando em valores booleanos, os operadores booleanos ou lógicos em Python são palavras-chave em vez de sinais, como você aprenderá na seção sobre [operadores e expressões booleanas](https://realpython.com/python-operators-expressions/#boolean-operators-and-expressions-in-python) . Portanto, em vez dos sinais estranhos como `||`, `&&`e `!`que muitas outras linguagens de programação usam, Python usa `or`, `and`e `not`.

Usar palavras-chave em vez de sinais estranhos é uma decisão de design muito legal, consistente com o fato de que Python adora e incentiva [a legibilidade do código](https://pep20.org/#readability) .

Você encontrará diversas categorias ou grupos de operadores em Python. Aqui está uma lista rápida dessas categorias:

* Operadores de atribuição
* Operadores aritméticos
* Operadores de comparação
* *Operadores booleanos* ou lógicos
* Operadores de identidade
* Operadores de adesão
* Operadores de concatenação e *repetição*
* Operadores bit a bit

Todos esses tipos de operadores cuidam de tipos específicos de cálculos e tarefas de processamento de dados. Você aprenderá mais sobre essas categorias ao longo deste tutorial. Porém, antes de entrar em discussões mais práticas, você precisa saber que o objetivo mais elementar de um operador é fazer parte de uma [expressão](https://docs.python.org/3/glossary.html#term-expression) . Os operadores por si só não fazem muito:

Python

```Python
>>> -
  File "<input>", line 1
-
^
SyntaxError: incomplete input

>>> ==
  File "<input>", line 1
==
^^
SyntaxError: incomplete input

>>> or
  File "<input>", line 1
or
^^
SyntaxError: incomplete input
```

Como você pode ver neste trecho de código, se usar um operador sem os operandos necessários, você receberá um [erro de sintaxe](https://realpython.com/invalid-syntax-python/) . Portanto, os operadores devem fazer parte de expressões, que você pode construir usando objetos Python como operandos.

Então, afinal, o que é uma expressão? Python possui instruções [simples](https://docs.python.org/3/reference/simple_stmts.html) e [compostas](https://docs.python.org/3/reference/compound_stmts.html)Uma instrução simples é uma construção que ocupa uma única [linha lógica](https://docs.python.org/3/reference/lexical_analysis.html#logical-lines) , como uma instrução de atribuição. Uma instrução composta é uma construção que ocupa múltiplas linhas lógicas, como um [`for`loop](https://realpython.com/python-for-loop/) ou uma instrução [condicional](https://realpython.com/python-conditional-statements/) . Uma **expressão** é uma instrução simples que produz e retorna um valor.

Você encontrará operadores em muitas expressões. Aqui estão alguns exemplos:

Python

```Python
>>> 7 + 5
12

>>> 42 / 2
21.0

>>> 5 == 5
True
```

Nos dois primeiros exemplos, você usa os operadores de adição e divisão para construir duas expressões aritméticas cujos operandos são números inteiros. No último exemplo, você usa o operador de igualdade para criar uma expressão de comparação. Em todos os casos, você obtém um valor específico após executar a expressão.

Observe que nem todas as expressões usam operadores. Por exemplo, uma [chamada de função](https://realpython.com/defining-your-own-python-function/#function-calls-and-definition) simples é uma expressão que não requer nenhum operador:

Python

```Python
>>> abs(-7)
7

>>> pow(2, 8)
256

>>> print("Hello, World!")
Hello, World!
```

No primeiro exemplo, você chama a função integrada [`abs()`](https://realpython.com/python-absolute-value/)para obter o [valor absoluto](https://en.wikipedia.org/wiki/Absolute_value) de `-7`. Em seguida, você calcula `2`a potência de `8`usar a função integrada `pow()`. Essas chamadas de função ocupam uma única linha lógica e retornam um valor. Então, são expressões.

Finalmente, a chamada para a função interna [`print()`](https://realpython.com/python-print/)é outra expressão. Desta vez, a função não [retorna](https://realpython.com/python-return-statement/) um valor frutífero, mas ainda retorna `None`, que é o [tipo nulo](https://realpython.com/null-in-python/) do Python . Então, a chamada é tecnicamente uma expressão.

**Nota: Todas as** [funções](https://realpython.com/defining-your-own-python-function/) Python possuem um valor de retorno, explícito ou implícito. Se você não fornecer uma `return`instrução explícita ao definir uma função, o Python fará com que a função retorne automaticamente `None`.

Embora todas as expressões sejam declarações, nem todas as declarações são expressões. Por exemplo, [instruções de atribuição](https://realpython.com/python-operators-expressions/#the-assignment-operator-and-statements) puras não retornam nenhum valor, como você aprenderá em breve. Portanto, não são expressões. O operador de atribuição é um operador especial que não cria uma expressão, mas uma instrução.

**Nota:** Desde a versão 3.8, Python também possui o que chama de expressões de atribuição. Esses são tipos especiais de atribuições que retornam um valor. Você aprenderá mais sobre este tópico na seção [O Operador Walrus e Expressões de Atribuição](https://realpython.com/python-operators-expressions/#the-walrus-operator-and-assignment-expressions) .

OK! Essa foi uma rápida introdução aos operadores e expressões em Python. Agora é hora de nos aprofundarmos no assunto. Para começar, você começará com o operador de atribuição e as instruções.

## O operador de atribuição e instruções

O **operador de atribuição** é um dos operadores mais usados em Python. O operador consiste em um único sinal de igual ( `=`) e opera em dois operandos. O operando à esquerda normalmente é uma [variável](https://realpython.com/python-variables/) , enquanto o operando à direita é uma expressão.

**Nota:** Como você já aprendeu, o operador de atribuição não cria uma expressão. Em vez disso, cria uma instrução que não retorna nenhum valor.

O operador de atribuição permite *atribuir valores às variáveis* . A rigor, em Python, este operador faz com que variáveis ou nomes se refiram a objetos específicos na memória do seu computador. Em outras palavras, uma atribuição cria uma referência a um objeto concreto e anexa essa referência à variável de destino.

**Observação:** para se aprofundar no uso do operador de atribuição, consulte [Operador de atribuição do Python: escrever atribuições robustas](https://realpython.com/python-assignment-operator/).

Por exemplo, todas as instruções abaixo criam novas variáveis que contêm referências a objetos específicos:

Python

```Python
>>> number = 42
>>> day = "Friday"
>>> digits = (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
>>> letters = ["a", "b", "c"]
```

Na primeira instrução, você cria a `number`variável, que contém uma referência ao [número](https://realpython.com/python-numbers/) `42` na memória do seu computador. Você também pode dizer que o nome `number` [aponta](https://realpython.com/pointers-in-python/) para `42`, que é um objeto concreto.

No restante dos exemplos, você cria outras variáveis que apontam para outros tipos de objetos, como [string](https://realpython.com/python-strings/) , [tuple](https://realpython.com/python-tuple/) e [list](https://realpython.com/python-list/) , respectivamente.

Você usará o operador de atribuição em muitos dos exemplos que escreverá ao longo deste tutorial. Mais importante ainda, você usará esse operador muitas vezes em seu próprio código. Será seu amigo para sempre. Agora você pode mergulhar em outros operadores Python!

## Operadores aritméticos e expressões em Python

**Operadores aritméticos** são aqueles operadores que permitem realizar *operações aritméticas* em valores numéricos. Sim, eles vêm da matemática e, na maioria dos casos, você os representará com os sinais matemáticos usuais. A tabela a seguir lista os operadores aritméticos que o Python suporta atualmente:

| Operador | Tipo    | Operação                           | Expressão de amostra | Resultado                                                                           |
| -------- | ------- | ---------------------------------- | -------------------- | ----------------------------------------------------------------------------------- |
| `+`      | Unário  | Positivo                           | `+a`                 | `a`sem qualquer transformação, pois isso é simplesmente um complemento à negação    |
| `+`      | Binário | Adição                             | `a + b`              | A soma aritmética de `a`e `b`                                                       |
| `-`      | Unário  | Negação                            | `-a`                 | O valor de `a`mas com sinal oposto                                                  |
| `-`      | Binário | Subtração                          | `a - b`              | `b`subtraído de `a`                                                                 |
| `*`      | Binário | Multiplicação                      | `a * b`              | O produto de `a`e `b`                                                               |
| `/`      | Binário | Divisão                            | `a / b`              | O quociente de `a`dividido por `b`, expresso como um ponto flutuante                |
| `%`      | Binário | Módulo                             | `a % b`              | O restante `a`dividido por `b`                                                      |
| `//`     | Binário | Divisão de piso ou divisão inteira | `a // b`             | O quociente de `a`dividido por `b`, arredondado para o próximo menor número inteiro |
| `**`     | Binário | Exponenciação                      | `a**b`               | `a`elevado ao poder de `b`                                                          |

Observe que `a`e `b`na coluna *Expressão de Amostra* representam valores numéricos, como números [inteiros](https://realpython.com/python-numbers/#integers) , [de ponto flutuante](https://realpython.com/python-numbers/#floating-point-numbers) , [complexos](https://realpython.com/python-complex-numbers/) , [racionais](https://realpython.com/python-fractions/) e [decimais](https://docs.python.org/3/library/decimal.html#decimal.Decimal) .

Aqui estão alguns exemplos desses operadores em uso:

Python

```Python
>>> a = 5
>>> b = 2

>>> +a
5
>>> -b
-2
>>> a + b
7
>>> a - b
3
>>> a * b
10
>>> a / b
2.5
>>> a % b
1
>>> a // b
2
>>> a**b
25
```

Neste trecho de código, você primeiro cria duas novas variáveis, `a`e `b`, segurando `5`e `2`, respectivamente. Então você usa essas variáveis para criar diferentes expressões aritméticas usando um operador específico em cada expressão.

**Nota:** O Python [REPL](https://realpython.com/python-repl/) exibirá o valor de retorno de uma expressão como forma de fornecer feedback imediato para você. Assim, quando você estiver em uma sessão interativa, não será necessário usar a `print()`função para verificar o resultado de uma expressão. Você pode simplesmente digitar a expressão e pressionar Enterpara obter o resultado.

Novamente, o operador de divisão padrão ( `/`) sempre retorna um número de ponto flutuante, mesmo que o dividendo seja divisível igualmente pelo divisor:

Python

```Python
>>> 10 / 5
2.0

>>> 10.0 / 5
2.0
```

No primeiro exemplo, `10`é divisível por `5`. Portanto, esta operação poderia retornar o inteiro `2`. No entanto, ele retorna o número de ponto flutuante `2.0`. No segundo exemplo, `10.0`é um número de ponto flutuante e `5`é um número inteiro. Nesse caso, o Python promove e executa internamente `5`a `5.0`divisão. O resultado também é um número de ponto flutuante.

**Nota:** Com números complexos, o operador de divisão não retorna um número de ponto flutuante, mas sim um número complexo:

Python

```Python
>>> 10 / 5j
-2j
```

Aqui, você executa uma divisão entre um número inteiro e um número complexo. Neste caso, o operador de divisão padrão retorna um número complexo.

Por fim, considere os seguintes exemplos de uso do `//`operador de divisão de piso ( ):

Python

```Python
>>> 10 // 4
2
>>> -10 // -4
2

>>> 10 // -4
-3
>>> -10 // 4
-3
```

A divisão do piso é sempre [arredondada para baixo](https://realpython.com/python-rounding/#rounding-down) . Isso significa que o resultado é o maior número inteiro menor ou igual ao quociente. Para números positivos, é como se a parte fracionária fosse truncada, restando apenas a parte inteira.

[Remover propagandas](https://realpython.com/account/join/)

## Operadores de comparação e expressões em Python

Os **operadores de comparação** do Python permitem comparar *valores* numéricos e quaisquer outros objetos que os suportem. A tabela abaixo lista todos os operadores de comparação atualmente disponíveis em Python:

| Operador | Operação              | Expressão de amostra | Resultado                                                                |
| -------- | --------------------- | -------------------- | ------------------------------------------------------------------------ |
| `==`     | Igual a               | `a == b`             | •`True`se o valor de `a`for igual ao valor de `b`• `False`caso contrário |
| `!=`     | Não é igual a         | `a != b`             | •`True`se `a`não é igual a `b`• `False`caso contrário                    |
| `<`      | Menor que             | `a < b`              | •`True`se `a`é menor que `b`• `False`caso contrário                      |
| `<=`     | Menos que ou igual a  | `a <= b`             | •`True`se `a`for menor ou igual a `b`• `False`caso contrário             |
| `>`      | Maior que             | `a > b`              | •`True`se `a`é maior que `b`• `False`caso contrário                      |
| `>=`     | Melhor que ou igual a | `a >= b`             | •`True`se `a`for maior ou igual a `b`• `False`caso contrário             |

Os operadores de comparação são todos binários. Isso significa que eles exigem operandos esquerdo e direito. Esses operadores sempre retornam um valor booleano ( `True`ou `False`) que depende do [valor verdade](https://en.wikipedia.org/wiki/Truth_value) da comparação em questão.

Observe que comparações entre objetos de diferentes tipos de dados geralmente não fazem sentido e às vezes não são permitidas em Python. Por exemplo, você pode comparar um número e uma string quanto à igualdade com o `==`operador. No entanto, você obterá `False`como resultado:

Python

```Python
>>> 2 == "2"
False
```

O número inteiro `2`não é igual à string `"2"`. Portanto, você obtém `False`o resultado. Você também pode usar o `!=`operador na expressão acima e, nesse caso, você obterá `True`o resultado.

Comparações de não igualdade entre operandos de diferentes tipos de dados geram uma `TypeError`exceção:

Python

```Python
>>> 5 < "7"
Traceback (most recent call last):
...
TypeError: '<' not supported between instances of 'int' and 'str'
```

Neste exemplo, Python gera uma `TypeError`exceção porque uma comparação menor que ( `<`) não faz sentido entre um número inteiro e uma string. Portanto, a operação não é permitida.

É importante observar que, no contexto de comparações, valores inteiros e de ponto flutuante são compatíveis e você pode compará-los.

Normalmente, você usará e encontrará operadores de comparação em contextos booleanos, como [instruções condicionais](https://realpython.com/python-conditional-statements/) e [`while`loops](https://realpython.com/python-while-loop/) . Eles permitem que você tome decisões e defina o [fluxo de controle](https://en.wikipedia.org/wiki/Control_flow) de um programa .

Os operadores de comparação funcionam em vários tipos de operandos, como números, strings, tuplas e listas. Nas seções a seguir, você explorará as diferenças.

### Comparação de valores inteiros

Provavelmente, as comparações mais diretas em Python e em matemática são aquelas que envolvem números inteiros. Eles permitem contar objetos reais, o que é uma tarefa familiar do dia a dia. Na verdade, os inteiros não negativos também são chamados de [números naturais](https://en.wikipedia.org/wiki/Natural_number) . Portanto, comparar esse tipo de número é provavelmente bastante intuitivo, e fazer isso em Python não é exceção.

Considere os seguintes exemplos que comparam números inteiros:

Python

```Python
>>> a = 10
>>> b = 20
>>> a == b
False
>>> a != b
True
>>> a < b
True
>>> a <= b
True
>>> a > b
False
>>> a >= b
False

>>> x = 30
>>> y = 30
>>> x == y
True
>>> x != y
False
>>> x < y
False
>>> x <= y
True
>>> x > y
False
>>> x >= y
True
```

No primeiro conjunto de exemplos, você define duas variáveis, `a`e `b`, para fazer algumas comparações entre elas. O valor de `a`é menor que o valor de `b`. Portanto, cada expressão de comparação retorna o valor booleano esperado. O segundo conjunto de exemplos usa dois valores iguais e, novamente, você obtém os resultados esperados.

### Comparação de valores de ponto flutuante

Comparar números de ponto flutuante é um pouco [mais complicado](https://realpython.com/python-numbers/#make-python-lie-to-you) do que comparar números inteiros. O valor armazenado em um `float`objeto pode não ser exatamente o que você imagina. Por esse motivo, é uma má prática comparar valores de ponto flutuante para obter igualdade exata usando o `==`operador.

Considere o exemplo abaixo:

Python

```Python
>>> x = 1.1 + 2.2
>>> x == 3.3
False

>>> 1.1 + 2.2
3.3000000000000003
```

Caramba! A representação interna desta adição não é exatamente igual a `3.3`, como você pode ver no exemplo final. Portanto, comparando `x`com `3.3`o operador de igualdade retorna `False`.

Para comparar números de ponto flutuante quanto à igualdade, você precisa usar uma abordagem diferente. A maneira preferida de determinar se dois valores de ponto flutuante são iguais é determinar se eles estão próximos um do outro, dada alguma tolerância.

O `math`módulo da biblioteca padrão fornece uma função convenientemente chamada `isclose()`que o ajudará na `float`comparação. A função pega dois números e os testa quanto à igualdade aproximada:

Python

```Python
>>> from math import isclose

>>> x = 1.1 + 2.2

>>> isclose(x, 3.3)
True
```

Neste exemplo, você usa a `isclose()`função para comparar `x`e `3.3`para obter igualdade aproximada. Desta vez, você obtém `True`o resultado porque os dois números estão próximos o suficiente para serem considerados iguais.

Para obter mais detalhes sobre como usar `isclose()`, consulte a seção [Encontre a proximidade dos números com Python `isclose()`](https://realpython.com/python-math-module/#find-the-closeness-of-numbers-with-python-isclose) em [O `math`módulo Python: tudo o que você precisa saber](https://realpython.com/python-math-module/) .

### Comparação de Strings

Você também pode usar os operadores de comparação para comparar strings Python em seu código. Nesse contexto, você precisa estar ciente de como o Python compara internamente objetos string. Na prática, o Python compara strings caractere por caractere usando o ponto de código [Unicode](https://realpython.com/python-encodings-guide/) de cada caractere . Unicode é o conjunto de caracteres padrão do Python .[](https://docs.python.org/3/howto/unicode.html#the-string-type)

Você pode usar a função integrada [`ord()`](https://docs.python.org/3/library/functions.html#ord)para aprender o ponto de código Unicode de qualquer caractere em Python. Considere os seguintes exemplos:

Python

```Python
>>> ord("A")
65
>>> ord("a")
97

>>> "A" == "a"
False
>>> "A" > "a"
False
>>> "A" < "a"
True
```

As letras maiúsculas `"A"`têm um ponto Unicode mais baixo que as letras minúsculas `"a"`. Então, `"A"`é menor que `"a"`. No final, Python compara caracteres usando números inteiros. Portanto, as mesmas regras que Python usa para comparar números inteiros se aplicam à comparação de strings.

Quando se trata de strings com vários caracteres, o Python executa a comparação caractere por caractere em um loop.

A comparação utiliza [ordenação lexicográfica](https://docs.python.org/3/tutorial/datastructures.html?highlight=lexicographical#comparing-sequences-and-other-types) , o que significa que o Python compara o primeiro item de cada string. Se os pontos de código Unicode forem diferentes, essa diferença determinará o resultado da comparação. Se os pontos de código Unicode forem iguais, o Python compara os próximos dois caracteres e assim por diante, até que uma das strings se esgote:

Python

```Python
>>> "Hello" > "HellO"
True

>>> ord("o")
111
>>> ord("O")
79
```

Neste exemplo, Python compara ambos os operandos caractere por caractere. Quando chega ao final da string, ele compara `"o"`and `"O"`. Como a letra minúscula tem um ponto de código Unicode maior, a primeira versão da sequência é maior que a segunda.

Você também pode comparar strings de comprimentos diferentes:

Python

```Python
>>> "Hello" > "Hello, World!"
False
```

Neste exemplo, Python executa uma comparação caractere por caractere normalmente. Se ficar sem caracteres, a string mais curta será menor que a mais longa. Isso também significa que a string vazia é a menor string possível.

### Comparação de listas e tuplas

Em sua jornada no Python, você também pode enfrentar a necessidade de comparar listas com outras listas e tuplas com outras tuplas. Esses tipos de dados também oferecem suporte aos operadores de comparação padrão. Assim como acontece com strings, quando você usa um operador de comparação para comparar duas listas ou duas tuplas, o Python executa uma comparação item por item.

Observe que o Python aplica regras específicas dependendo do tipo de itens contidos. Aqui estão alguns exemplos que comparam listas e tuplas de valores inteiros:

Python

```Python
>>> [2, 3] == [2, 3]
True
>>> (2, 3) == (2, 3)
True

>>> [5, 6, 7] < [7, 5, 6]
True
>>> (5, 6, 7) < (7, 5, 6)
True

>>> [4, 3, 2] < [4, 3, 2]
False
>>> (4, 3, 2) < (4, 3, 2)
False
```

Nestes exemplos, você compara listas e tuplas de números usando os operadores de comparação padrão. Ao comparar esses tipos de dados, o Python executa uma comparação item por item.

Por exemplo, na primeira expressão acima, Python compara o `2`operando à esquerda e o `2`operando à direita. Por serem iguais, o Python continua comparando `3`e `3`conclui que ambas as listas são iguais. A mesma coisa acontece no segundo exemplo, onde você compara tuplas contendo os mesmos dados.

É importante observar que você pode comparar listas com tuplas usando os operadores `==`e `!=`. No entanto, você *não pode* comparar listas e tuplas usando os operadores `<`, `>`, `<=`e :`>=`

Python

```Python
>>> [2, 3] == (2, 3)
False
>>> [2, 3] != (2, 3)
True

>>> [2, 3] > (2, 3)
Traceback (most recent call last):
...
TypeError: '>' not supported between instances of 'list' and 'tuple'

>>> [2, 3] <= (2, 3)
Traceback (most recent call last):
...
TypeError: '<=' not supported between instances of 'list' and 'tuple'
```

Python oferece suporte à comparação de igualdade entre listas e tuplas. No entanto, ele não suporta o restante dos operadores de comparação, como você pode concluir nos dois exemplos finais. Se você tentar usá-los, receberá uma `TypeError`mensagem informando que a operação não é suportada.

Você também pode comparar listas e tuplas de diferentes comprimentos:

Python

```Python
>>> [5, 6, 7] < [8]
True
>>> (5, 6, 7) < (8,)
True

>>> [5, 6, 7] == [5]
False
>>> (5, 6, 7) == (5,)
False

>>> [5, 6, 7] > [5]
True
>>> (5, 6, 7) > (5,)
True
```

Nos dois primeiros exemplos, você obtém `True`como resultado porque `5`é menor que `8`. Esse fato é suficiente para o Python resolver a comparação. No segundo par de exemplos, você obtém `False`. Este resultado faz sentido porque as sequências comparadas não têm o mesmo comprimento, portanto não podem ser iguais.

No par final de exemplos, Python compara `5`com `5`. Eles são iguais, então a comparação continua. Como não há mais valores para comparar nos operandos do lado direito, o Python conclui que os operandos do lado esquerdo são maiores.

Como você pode ver, comparar listas e tuplas pode ser complicado. É também uma operação cara que, na pior das hipóteses, requer a passagem de duas sequências inteiras. As coisas ficam mais complexas e caras quando os itens contidos também são sequências. Nessas situações, o Python também terá que comparar os itens valor por valor, o que agrega custo à operação.

## Operadores e expressões booleanas em Python

Python tem três operadores booleanos ou lógicos: [`and`](https://realpython.com/python-and-operator/),, [`or`](https://realpython.com/python-or-operator/)e [`not`](https://realpython.com/python-not-operator/). Eles definem um conjunto de operações denotadas pelos operadores genéricos [`AND`](https://en.wikipedia.org/wiki/Logical_conjunction),, [`OR`](https://en.wikipedia.org/wiki/Logical_disjunction)e [`NOT`](https://en.wikipedia.org/wiki/Negation). Com esses operadores, você pode criar condições compostas.

Nas seções a seguir, você aprenderá como funcionam os operadores booleanos do Python. Especialmente, você aprenderá que alguns deles se comportam de maneira diferente quando usados com valores booleanos ou com objetos regulares como operandos.

### Expressões booleanas envolvendo operandos booleanos

Você encontrará muitos objetos e expressões do tipo booleano ou `bool`, como o Python chama esse tipo. Em outras palavras, muitos objetos são avaliados como `True`ou `False`, que são os valores booleanos do Python.

Por exemplo, quando você avalia uma expressão usando um operador de comparação, o resultado dessa expressão é sempre do `bool`tipo:

Python

```Python
>>> age = 20

>>> is_adult = age > 18
>>> is_adult
True

>>> type(is_adult)
<class 'bool'>
```

Neste exemplo, a expressão `age > 18`retorna um valor booleano, que você armazena na `is_adult`variável. Now `is_adult`é do `bool`tipo, como você pode ver depois de chamar a função integrada [`type()`](https://docs.python.org/3/library/functions.html#type).

Você também pode encontrar funções integradas e personalizadas do Python que retornam um valor booleano. Este tipo de função é conhecida como função [de predicado](https://realpython.com/python-return-statement/#returning-true-or-false) . As funções integradas [`all()`](https://realpython.com/python-all/), [`any()`](https://realpython.com/any-python/), [`callable()`](https://docs.python.org/3/library/functions.html#callable)e [`isinstance()`](https://docs.python.org/3/library/functions.html?highlight=built#isinstance)são bons exemplos dessa prática.

Considere os seguintes exemplos:

Python

```Python
>>> number = 42

>>> validation_conditions = (
...     isinstance(number, int),
...     number % 2 == 0,
... )

>>> all(validation_conditions)
True

>>> callable(number)
False
>>> callable(print)
True
```

Neste trecho de código, você primeiro define uma variável chamada `number`usando seu velho amigo, o operador de atribuição. Então você cria outra variável chamada `validation_conditions`. Esta variável contém uma tupla de expressões. A primeira expressão usa `isinstance()`para verificar se `number`é um valor inteiro.

A segunda é uma expressão composta que combina os operadores módulo ( `%`) e igualdade ( `==`) para criar uma condição que verifica se o valor de entrada é um número par. Nessa condição, o operador módulo retorna o resto da divisão `number`por `2`e o operador de igualdade compara o resultado com `0`, retornando `True`ou `False`como resultado da comparação.

Então você usa a `all()`função para determinar se todas as condições são verdadeiras. Neste exemplo, porque `number = 42`, as condições são verdadeiras e `all()`retorna `True`. Você pode brincar com o valor de `number`se quiser experimentar um pouco.

Nos dois exemplos finais, você usa a `callable()`função. Como o próprio nome sugere, esta função permite determinar se um objeto pode ser **chamado** . Ser chamável significa que você pode chamar o objeto com um par de parênteses e argumentos apropriados, como chamaria qualquer função Python.

A `number`variável não pode ser chamada e a função retorna `False`, respectivamente. Por outro lado, a `print()`função pode ser chamada, então `callable()`retorna `True`.

Toda a discussão anterior é a base para entender como os operadores lógicos Python funcionam com operandos booleanos.

Expressões lógicas envolvendo `and`, `or`e `not`são diretas quando os operandos são booleanos. Aqui está um resumo. Observe que `x`e `y`representa operandos booleanos:

| Operador | Expressão de amostra | Resultado                                                   |
| -------- | -------------------- | ----------------------------------------------------------- |
| `and`    | `x and y`            | •`True`se ambos `x`e `y`forem `True`• `False`caso contrário |
| `or`     | `x or y`             | •`True`se um `x`ou `y`for `True`• `False`caso contrário     |
| `not`    | `not x`              | •`True`se `x`for `False`• se `False`for `x``True`           |

Esta tabela resume o valor verdade das expressões que você pode criar usando os operadores lógicos com operandos booleanos. Há algo a ser observado neste resumo. Ao contrário de `and`e `or`, que são operadores binários, o `not`operador é unário, o que significa que opera em um operando. Este operando deve estar sempre do lado direito.

Agora é hora de dar uma olhada em como os operadores funcionam na prática. Aqui estão alguns exemplos de uso do `and`operador com operandos booleanos:

Python

```Python
>>> 5 < 7 and 3 == 3
True

>>> 5 < 7 and 3 != 3
False

>>> 5 > 7 and 3 == 3
False

>>> 5 > 7 and 3 != 3
False
```

No primeiro exemplo, ambos os operandos retornam `True`. Portanto, a `and`expressão retorna `True`como resultado. No segundo exemplo, o operando esquerdo é `True`, mas o operando direito é `False`. Por causa disso, o `and`operador retorna `False`.

No terceiro exemplo, o operando esquerdo é `False`. Neste caso, o `and`operador retorna imediatamente `False`e nunca avalia a `3 == 3`condição. Esse comportamento é chamado de [avaliação de curto-circuito](https://realpython.com/python-boolean/#short-circuit-chain-evaluation) . Você aprenderá mais sobre isso em um momento.

**Nota:** A avaliação de curto-circuito também é chamada de **avaliação McCarthy** em homenagem ao cientista da computação [John McCarthy](https://en.wikipedia.org/wiki/John_McCarthy_(computer_scientist)) .

No exemplo final, ambas as condições retornam `False`. Novamente, `and`retorna `False`como resultado. Entretanto, devido à avaliação de curto-circuito, a expressão à direita não é avaliada.

E a `or`operadora? Aqui estão alguns exemplos que demonstram como funciona:

Python

```Python
>>> 5 < 7 or 3 == 3
True

>>> 5 < 7 or 3 != 3
True

>>> 5 > 7 or 3 == 3
True

>>> 5 > 7 or 3 != 3
False
```

Nos três primeiros exemplos, pelo menos uma das condições retorna `True`. Em todos os casos, o `or`operador retorna `True`. Observe que se o operando esquerdo for `True`, então `or`aplica a avaliação de curto-circuito e não avalia o operando direito. Isso faz sentido. Se o operando da esquerda for `True`, então `or`já se sabe o resultado final. Por que seria necessário continuar a avaliação se o resultado não mudará?

No exemplo final, ambos os operandos são `False`, e esta é a única situação em que `or`retorna `False`. É importante notar que se o operando da esquerda for `False`, então `or`será necessário avaliar o operando da direita para chegar a uma conclusão final.

Finalmente, você tem o `not`operador, que nega o valor verdade atual de um objeto ou expressão:

Python

```Python
>>> 5 < 7
True

>>> not 5 < 7
False
```

Se você colocar `not`antes de uma expressão, obterá o valor de verdade inverso. Quando a expressão retorna `True`, você obtém `False`. Quando a expressão é avaliada como `False`, você obtém `True`.

Há uma distinção fundamental de comportamento entre `not`os outros dois operadores booleanos. Em uma `not`expressão, você sempre obtém um valor booleano como resultado. Essa nem sempre é a regra que rege `and`as `or`expressões, como você aprenderá na seção [Expressões booleanas que envolvem outros tipos de operandos](https://realpython.com/python-operators-expressions/#boolean-expressions-involving-other-types-of-operands) .

### Avaliação de objetos regulares em um contexto booleano

Na prática, a maioria dos objetos e expressões Python não são booleanos. Em outras palavras, a maioria dos objetos e expressões não possui um valor `True`ou `False`, mas um tipo diferente de valor. Entretanto, você pode usar qualquer objeto Python em um contexto booleano, como uma instrução condicional ou um `while`loop.

Em Python, todos os objetos têm um valor verdade específico. Assim, você pode usar os operadores lógicos com todos os tipos de operandos.

Python possui regras bem estabelecidas para determinar o valor verdade de um objeto quando você usa esse objeto em um contexto booleano ou como um operando em uma expressão construída com operadores lógicos. Aqui está o que a documentação diz sobre este tópico:

> Por padrão, um objeto é considerado verdadeiro, a menos que sua classe defina um [`__bool__()`](https://docs.python.org/3/reference/datamodel.html#object.__bool__)método que retorne `False`ou um [`__len__()`](https://docs.python.org/3/reference/datamodel.html#object.__len__)método que retorne zero, quando chamado com o objeto. Aqui estão a maioria dos objetos integrados considerados falsos:
>
> * constantes definidas como falsas: `None`e `False`.
> * zero de qualquer tipo numérico: `0`, `0.0`, `0j`, `Decimal(0)`,`Fraction(0, 1)`
> * sequências e coleções vazias: `''`, `()`, `[]`, `{}`, `set()`,`range(0)`
>
> ( [Fonte](https://docs.python.org/3/library/stdtypes.html#truth-value-testing) )

Você pode determinar o valor verdadeiro de um objeto chamando a função integrada [`bool()`](https://docs.python.org/3/library/functions.html#bool)com esse objeto como argumento. Se `bool()`retornar `True`, então o objeto é **verdadeiro** . Se `bool()`retornar `False`, então é **falso** .

Para valores numéricos, você afirma que um valor zero é falso, enquanto um valor diferente de zero é verdadeiro:

Python

```Python
>>> bool(0), bool(0.0), bool(0.0+0j)
(False, False, False)

>>> bool(-3), bool(3.14159), bool(1.0+1j)
(True, True, True)
```

Python considera o valor zero de todos os tipos numéricos falso. Todos os outros valores são verdadeiros, independentemente de quão próximos de zero estejam.

**Nota:** Em vez de uma função, `bool()`é uma classe. Entretanto, como os desenvolvedores Python normalmente usam essa classe como uma função, você descobrirá que a maioria das pessoas se refere a ela como uma função e não como uma classe. Além disso, a documentação lista esta classe na página [de funções integradas](https://docs.python.org/3/library/functions.html#built-in-functions) . Este é um daqueles casos em que [a praticidade vence a pureza](https://pep20.org/#practicality) .

Quando se trata de avaliar strings, você percebe que uma string vazia é sempre falsa, enquanto uma string não vazia é verdadeira:

Python

```Python
>>> bool("")
False

>>> bool(" ")
True

>>> bool("Hello")
True
```

Observe que strings contendo espaços em branco também são verdadeiras aos olhos do Python. Portanto, não confunda strings vazias com strings de espaço em branco.

Por fim, os tipos de dados de contêiner integrados, como listas, tuplas, [conjuntos](https://realpython.com/python-sets/) e [dicionários](https://realpython.com/python-dicts/) , são falsos quando estão vazios. Caso contrário, o Python os considera objetos verdadeiros:

Python

```Python
>>> bool([])
False
>>> bool([1, 2, 3])
True

>>> bool(())
False
>>> bool(("John", 25, "Python Dev"))
True

>>> bool(set())
False
>>> bool({"square", "circle", "triangle"})
True

>>> bool({})
False
>>> bool({"name": "John", "age": 25, "job": "Python Dev"})
True
```

Para determinar o valor verdadeiro dos tipos de dados contêineres, Python depende do `.__len__()` [método especial](https://realpython.com/python-classes/#special-methods-and-protocols) . Este método fornece suporte para a função integrada [`len()`](https://realpython.com/len-python-function/), que você pode usar para determinar o número de itens em um determinado contêiner.

Em geral, se `.__len__()`return `0`, então o Python considera o contêiner um objeto falso, o que é consistente com as regras gerais que você acabou de aprender antes.

Toda a discussão sobre o valor verdade dos objetos Python nesta seção é fundamental para entender como os operadores lógicos se comportam quando tomam objetos arbitrários como operandos.

### Expressões booleanas envolvendo outros tipos de operandos

Você também pode usar quaisquer objetos, como números ou strings, como operandos para `and`, `or`e `not`. Você pode até usar combinações de um objeto booleano e um objeto normal. Nestas situações, o resultado depende do valor verdade dos operandos.

**Nota:** Expressões booleanas que [combinam dois operandos booleanos](https://realpython.com/python-operators-expressions/#boolean-expressions-involving-boolean-operands) são um caso especial de uma regra mais geral que permite usar operadores lógicos com todos os tipos de operandos. Em todos os casos, você obterá um dos operandos como resultado.

Você já aprendeu como o Python determina o valor verdade dos objetos. Então, você está pronto para mergulhar na criação de expressões com operadores lógicos e objetos regulares.

Para começar, abaixo está uma tabela que resume o que você obtém quando usa dois objetos, `x`e `y`, em uma `and`expressão:

| Se `x`é    | `x and y`retorna |
| ---------- | ---------------- |
| Verdadeiro | `y`              |
| Falsidade  | `x`              |

É importante enfatizar um detalhe sutil na tabela acima. Quando você usa `and`uma expressão, nem sempre obtém `True`ou `False`como resultado. Em vez disso, você obtém um dos operandos. Você só obtém `True`ou `False`se o operando retornado tiver um desses valores.

Aqui estão alguns exemplos de código que usam valores inteiros. Lembre-se de que em Python, o valor zero dos tipos numéricos é falso. O resto dos valores são verdadeiros:

Python

```Python
>>> 3 and 4
4

>>> 0 and 4
0

>>> 3 and 0
0
```

Na primeira expressão, o operando esquerdo ( `3`) é verdadeiro. Então, você obtém o operando do lado direito ( `4`) como resultado.

No segundo exemplo, o operando esquerdo ( `0`) é falso e você o obtém como resultado. Neste caso, Python aplica a técnica de avaliação de curto-circuito. Ele já sabe que toda a expressão é falsa porque `0`é falsa, então o Python retorna `0`imediatamente sem avaliar o operando do lado direito.

Na expressão final, o operando esquerdo ( `3`) é verdadeiro. Portanto, o Python precisa avaliar o operando do lado direito para chegar a uma conclusão. Como resultado, você obtém o operando do lado direito, não importa qual seja seu valor verdade.

**Observação:** para se aprofundar no `and`operador, consulte [Usando o operador booleano “e” em Python](https://realpython.com/python-and-operator/) .

Quando se trata de usar o `or`operador, você também obtém um dos operandos como resultado. Isto é o que acontece com dois objetos arbitrários `x`e `y`:

| Se `x`é    | `x or y`retorna |
| ---------- | --------------- |
| Verdadeiro | `x`             |
| Falsidade  | `y`             |

Novamente, a expressão `x or y`não é avaliada como `True`or `False`. Em vez disso, ele retorna um de seus operandos, `x`ou `y`.

Como você pode concluir na tabela acima, se o operando esquerdo for verdadeiro, você o obterá como resultado. Caso contrário, você obterá o segundo operando. Aqui estão alguns exemplos que demonstram esse comportamento:

Python

```Python
>>> 3 or 4
3

>>> 0 or 4
4

>>> 3 or 0
3
```

No primeiro exemplo, o operando esquerdo é verdadeiro e `or`o retorna imediatamente. Neste caso, o Python não avalia o segundo operando porque já conhece o resultado final. No segundo exemplo, o operando da esquerda é falso e o Python precisa avaliar o operando da direita para determinar o resultado.

No último exemplo, o operando esquerdo é verdadeiro e esse fato define o resultado da expressão. Não há necessidade de avaliar o operando do lado direito.

Uma expressão como `x or y`é verdadeira se um `x`ou `y`for verdadeiro, e falsa se ambos `x`e `y`forem falsos. Este tipo de expressão retorna o primeiro operando verdadeiro que encontra. Se ambos os operandos forem falsos, a expressão retornará o operando do lado direito. Para ver este último comportamento em ação, considere o seguinte exemplo:

Python

```Python
>>> 0 or []
[]
```

Nesta expressão específica, ambos os operandos são falsos. Portanto, o `or`operador retorna o operando do lado direito e, como resultado, toda a expressão é falsa.

**Observação:** para saber mais sobre o `or`operador, consulte [Usando o operador booleano “ou” em Python](https://realpython.com/python-or-operator/) .

Finalmente, você tem a `not`operadora. Você também pode usar este com qualquer objeto como operando. Aqui está o que acontece:

| Se `x`é    | `not x`retorna |
| ---------- | -------------- |
| Verdadeiro | `False`        |
| Falsidade  | `True`         |

O `not`operador tem um comportamento uniforme. Sempre retorna um valor booleano. Esse comportamento difere de seus operadores irmãos, `and`e `or`.

Aqui estão alguns exemplos de código:

Python

```Python
>>> not 3
False

>>> not 0
True
```

No primeiro exemplo, o operando, `3`, é verdadeiro do ponto de vista do Python. Então, o operador retorna `False`. No segundo exemplo, o operando é falso e `not`retorna `True`.

**Nota:** Para entender melhor o `not`operador, consulte [Usando o operador booleano “not” em Python](https://realpython.com/python-not-operator/) .

Em resumo, o `not`operador Python nega o valor verdade de um objeto e sempre retorna um valor booleano. Este último comportamento difere do comportamento de seus operadores irmãos `and`e `or`, que retornam operandos em vez de valores booleanos.

### Expressões Lógicas Compostas e Avaliação de Curto-Circuito

Até agora, você viu expressões com apenas um operador `or` or `and`e dois operandos. No entanto, você também pode criar expressões lógicas compostas com vários operadores e operandos lógicos.

Para ilustrar como criar uma expressão composta usando `or`, considere o seguinte exemplo de brinquedo:

PythonPython

```Python
x1 or x2 or x3 or ... or xn
```

Esta expressão retorna o primeiro valor verdadeiro. Se todas as `x`variáveis anteriores forem falsas, a expressão retornará o último valor, `xn`.

**Nota:** Em uma expressão como a acima, Python usa [avaliação de curto-circuito](https://en.wikipedia.org/wiki/Short-circuit_evaluation) . Os operandos são avaliados em ordem da esquerda para a direita. Assim que uma é considerada verdadeira, toda a expressão é considerada verdadeira. Nesse ponto, o Python para de avaliar operandos. O valor de toda a expressão é aquele `x`que encerra a avaliação.

Para ajudar a demonstrar a avaliação de curto-circuito, suponha que você tenha uma [função identidade](https://en.wikipedia.org/wiki/Identity_function) , `f()`, que se comporte da seguinte maneira:

* Leva um único argumento
* Exibe a função e seu argumento na tela
* Retorna o argumento como seu valor de retorno

Aqui está o código para definir esta função e também alguns exemplos de como ela funciona:

Python

```Python
>>> def f(arg):
...     print(f"-> f({arg}) = {arg}")
...     return arg
...

>>> f(0)
-> f(0) = 0
0

>>> f(False)
-> f(False) = False
False

>>> f(1.5)
-> f(1.5) = 1.5
1.5
```

A `f()`função exibe seu argumento, que confirma visualmente se você chamou a função. Ele também retorna o argumento conforme você o passou na chamada. Devido a esse comportamento, você pode tornar a expressão `f(arg)`verdadeira ou falsa especificando um valor para `arg`verdadeiro ou falso, respectivamente.

Agora, considere a seguinte expressão lógica composta:

Python

```Python
>>> f(0) or f(False) or f(1) or f(2) or f(3)
-> f(0) = 0
-> f(False) = False
-> f(1) = 1
1
```

Neste exemplo, o Python avalia primeiro `f(0)`, que retorna `0`. Este valor é falso. A expressão ainda não é verdadeira, então a avaliação continua da esquerda para a direita. O próximo operando, `f(False)`, retorna `False`. Esse valor também é falso, por isso a avaliação continua.

O próximo é `f(1)`. Isso é avaliado como `1`, o que é verdade. Nesse ponto, o Python interrompe a avaliação porque já sabe que toda a expressão é verdadeira. Consequentemente, Python retorna `1`como o valor da expressão e nunca avalia os operandos restantes, `f(2)`e `f(3)`. Você pode confirmar na saída que as chamadas `f(2)`e `f(3)`não ocorrem.

Um comportamento semelhante aparece em uma expressão com múltiplos `and`operadores como o seguinte:

Python

```Python
x1 and x2 and x3 and ... and xn
```

Esta expressão é verdadeira se todos os operandos forem verdadeiros. Se pelo menos um operando for falso, então a expressão também será falsa.

Neste exemplo, a avaliação de curto-circuito determina que o Python pare de avaliar assim que um operando for falso. Nesse ponto, toda a expressão é conhecida como falsa. Quando for esse o caso, o Python para de avaliar os operandos e retorna o operando falso que encerrou a avaliação.

Aqui estão dois exemplos que confirmam o comportamento de curto-circuito:

Python

```Python
>>> f(1) and f(False) and f(2) and f(3)
-> f(1) = 1
-> f(False) = False
False

>>> f(1) and f(0.0) and f(2) and f(3)
-> f(1) = 1
-> f(0.0) = 0.0
0.0
```

Em ambos os exemplos, a avaliação para no primeiro termo falso – `f(False)`no primeiro caso, `f(0.0)`no segundo caso – e nem o `f(2)`nem a `f(3)`chamada ocorrem. No final, as expressões retornam `False`e `0.0`, respectivamente.

Se todos os operandos forem verdadeiros, então o Python avalia todos eles e retorna o último (mais à direita) como o valor da expressão:

Python

```Python
>>> f(1) and f(2.2) and f("Hello")
-> f(1) = 1
-> f(2.2) = 2.2
-> f(Hello) = Hello
'Hello'

>>> f(1) and f(2.2) and f(0)
-> f(1) = 1
-> f(2.2) = 2.2
-> f(0) = 0
0
```

No primeiro exemplo, todos os operandos são verdadeiros. A expressão também é verdadeira e retorna o último operando. No segundo exemplo, todos os operandos são verdadeiros, exceto o último. A expressão é falsa e retorna o último operando.

### Expressões idiomáticas que exploram a avaliação de curto-circuito

Ao se aprofundar no Python, você descobrirá que existem alguns padrões idiomáticos comuns que exploram a avaliação de curto-circuito para obter concisão de expressão, desempenho e segurança. Por exemplo, você pode aproveitar esse tipo de avaliação para:

* Evitando uma exceção
* Fornecendo um valor padrão
* Ignorando uma operação cara

Para ilustrar o primeiro ponto, suponha que você tenha duas variáveis, `a`e `b`, e queira saber se a divisão de `b`por `a`resulta em um número maior que `0`. Nesse caso, você pode executar a seguinte expressão ou condição:

Python

```Python
>>> a = 3
>>> b = 1

>>> (b / a) > 0
True
```

Este código funciona. No entanto, você precisa considerar a possibilidade de que isso `a`possa ocorrer `0`e, nesse caso, você receberá uma [exceção](https://realpython.com/python-exceptions/) :

Python

```Python
>>> a = 0
>>> b = 1

>>> (b / a) > 0
Traceback (most recent call last):
...
ZeroDivisionError: division by zero
```

Neste exemplo, o divisor é `0`, o que faz o Python gerar uma `ZeroDivisionError`exceção. Esta exceção quebra seu código. Você pode ignorar esse erro com uma expressão como a seguinte:

Python

```Python
>>> a = 0
>>> b = 1

>>> a != 0 and (b / a) > 0
False
```

Quando `a`é `0`, `a != 0`é falso. A avaliação de curto-circuito do Python garante que a avaliação pare nesse ponto, o que significa que `(b / a)`nunca será executada e o erro nunca ocorrerá.

Usando esta técnica, você pode implementar uma função para determinar se um número inteiro é divisível por outro número inteiro:

Python

```Python
def is_divisible(a, b):
    return b != 0 and a % b == 0
```

Nesta função, if `b`is `0`, then `a / b`não está definido. Portanto, os números não são divisíveis. Se `b`for diferente de `0`, então o resultado dependerá do restante da divisão.

Selecionar um valor padrão quando um valor especificado é falso é outra expressão que aproveita o recurso de avaliação de curto-circuito dos operadores lógicos do Python.

Por exemplo, digamos que você tenha uma variável que deveria conter o nome de um país. Em algum momento, esta variável pode acabar contendo uma string vazia. Se for esse o caso, então você gostaria que a variável mantivesse um nome de condado padrão. Você também pode fazer isso com o `or`operador:

Python

```Python
>>> country = "Canada"
>>> default_country = "United States"

>>> country or default_country
'Canada'

>>> country = ""
>>> country or default_country
'United States'
```

Se `country`não estiver vazio, então é verdadeiro. Neste cenário, a expressão retornará o primeiro valor verdadeiro, que está `country`na primeira `or`expressão. A avaliação é interrompida e você obtém `"Canada"`o resultado.

Por outro lado, se `country`for uma [string](https://realpython.com/python-strings/) vazia , então é falso. A avaliação continua para o próximo operando, `default_country`, que é verdadeiro. Finalmente, você obtém o país padrão.

Outro caso de uso interessante para avaliação de curto-circuito é evitar operações dispendiosas ao criar expressões lógicas compostas. Por exemplo, se você tiver uma operação cara que só deve ser executada se uma determinada condição for falsa, você pode usar `or`como no seguinte trecho:

Python

```Python
data_is_clean or clean_data(data)
```

Nesta construção, sua `clean_data()`função representa uma operação cara. Devido à avaliação de curto-circuito, esta função só será executada quando `data_is_clean`for falsa, o que significa que seus dados não estão limpos.

Outra variação desta técnica é quando você deseja executar uma operação dispendiosa se uma determinada condição for verdadeira. Neste caso, você pode usar o `and`operador:

Python

```Python
data_is_updated and process_data(data)
```

Neste exemplo, o `and`operador avalia `data_is_updated`. Se esta variável for verdadeira, a avaliação continua e a `process_data()`função é executada. Caso contrário, a avaliação será interrompida e `process_data()`nunca será executada.

### Expressões compostas versus expressões encadeadas

Às vezes você tem uma expressão composta que usa o `and`operador para unir expressões de comparação. Por exemplo, digamos que você queira determinar se um número está em um determinado intervalo. Você pode resolver esse problema com uma expressão composta como a seguinte:

Python

```Python
>>> number = 5
>>> number >= 0 and number <= 10
True

>>> number = 42
>>> number >= 0 and number <= 10
False
```

Neste exemplo, você usa o `and`operador para unir duas expressões de comparação que permitem descobrir se `number`está no intervalo de `0`até `10`, ambas incluídas.

Em Python, você pode tornar essa expressão composta mais concisa encadeando os operadores de comparação. Por exemplo, a seguinte expressão encadeada é equivalente à expressão composta anterior:

Python

```Python
>>> number = 5
>>> 0 <= number <= 10
True
```

Esta expressão é mais concisa e legível do que a expressão original. Você pode perceber rapidamente que esse código está verificando se o número está entre `0`e `10`. Observe que na maioria das linguagens de programação, esta expressão encadeada não faz sentido. Em Python, funciona perfeitamente.

Em outras linguagens de programação, esta expressão provavelmente começaria avaliando `0 <= number`, o que é verdade. Esse valor verdadeiro seria então comparado com `10`, o que não faz muito sentido, então a expressão falha.

O Python processa internamente esse tipo de expressão como uma `and`expressão equivalente, como `0 <= number and number <= 10`. É por isso que você obtém o resultado correto no exemplo acima.

## Expressões Condicionais ou Operador Ternário

Python tem o que chama de [expressões condicionais](https://docs.python.org/3/reference/expressions.html#conditional-expressions) . Esses tipos de expressões são inspirados no [operador ternário](https://en.wikipedia.org/wiki/Ternary_conditional_operator) que se parece `a ? b : c`e é usado em outras linguagens de programação. Esta construção é avaliada como `b`se o valor de `a`for verdadeiro e, caso contrário, é avaliada como `c`. Por causa disso, às vezes a sintaxe equivalente do Python também é conhecida como operador ternário.

No entanto, em Python, a expressão parece mais legível:

Python

```Python
variable = expression_1 if condition else expression_2
```

Esta expressão retorna `expression_1`se a condição for verdadeira e `expression_2`caso contrário. Observe que esta expressão é equivalente a uma condicional regular como a seguinte:

Python

```Python
if condition:
    variable = expression_1
else:
    variable = expression_2
```

Então, por que o Python precisa dessa sintaxe? [O PEP 308](https://peps.python.org/pep-0308/) introduziu expressões condicionais como um esforço para evitar a prevalência de tentativas propensas a erros para obter o mesmo efeito de um operador ternário tradicional usando os operadores `and`e `or`em uma expressão como a seguinte:

Python

```Python
variable = condition and expression_1 or expression_2
```

Porém, esta expressão não funciona conforme o esperado, retornando `expression_2`quando `expression_1`é falsa.

Alguns desenvolvedores Python evitariam a sintaxe de expressões condicionais em favor de uma instrução condicional regular. De qualquer forma, esta sintaxe pode ser útil em algumas situações porque fornece uma ferramenta concisa para escrever condicionais bidirecionais.

Aqui está um exemplo de como usar a sintaxe da expressão condicional em seu código:

Python

```Python
>>> day = "Sunday"
>>> open_time = "11AM" if day == "Sunday" else "9AM"
>>> open_time
'11AM'

>>> day = "Monday"
>>> open_time = "11AM" if day == "Sunday" else "9AM"
>>> open_time
'9AM'
```

Quando `day`é igual a `"Sunday"`, a condição é verdadeira e você obtém a primeira expressão,, `"11AM"`como resultado. Se a condição for falsa, você obterá a segunda expressão, `"9AM"`. Observe que, da mesma forma que os operadores `and`e `or`, a expressão condicional retorna o valor de uma de suas expressões em vez de um valor booleano.

## Operadores e expressões de identidade em Python

Python fornece dois operadores, `is`e `is not`, que permitem determinar se dois operandos têm a mesma **identidade** . Em outras palavras, permitem verificar se os operandos se referem ao mesmo objeto. Observe que identidade não é a mesma coisa que igualdade. Este último visa verificar se dois operandos contêm os mesmos dados.

**Nota:** Para saber mais sobre a diferença entre identidade e igualdade, consulte [Python &#39;!=&#39; Is Not &#39; is not&#39;: Comparing Objects in Python](https://realpython.com/python-is-identity-vs-equality/) .

Aqui está um resumo dos operadores de identidade do Python. Observe que `x`e `y`são variáveis que apontam para objetos:

| Operador                                                                | Expressão de amostra | Resultado                                                                                             |
| ----------------------------------------------------------------------- | -------------------- | ----------------------------------------------------------------------------------------------------- |
| [`is`](https://docs.python.org/3/reference/expressions.html#is)         | `x is y`             | •`True`se `x`e `y`mantém uma referência ao mesmo objeto na memória``• `False`caso contrário           |
| [`is not`](https://docs.python.org/3/reference/expressions.html#is-not) | `x is not y`         | •`True`se `x`aponta para um objeto diferente do objeto para o qual `y`aponta``• `False`caso contrário |

Esses dois operadores Python são palavras-chave em vez de símbolos ímpares. Isso faz parte do objetivo do Python de favorecer a legibilidade em sua sintaxe.

Aqui está um exemplo de duas variáveis, `x`e `y`, que se referem a objetos que são iguais, mas não idênticos:

Python

```Python
>>> x = 1001
>>> y = 1001

>>> x == y
True

>>> x is y
False
```

Neste exemplo, `x`e `y`refere-se a objetos cujo valor é `1001`. Então, eles são iguais. No entanto, eles não fazem referência ao mesmo objeto. É por isso que o `is`operador retorna `False`. Você pode verificar a identidade de um objeto usando a função integrada `id()`:

Python

```Python
>>> id(x)
4417772080

>>> id(y)
4417766416
```

Como você pode concluir pela `id()`saída, `x`e `y`não têm a mesma identidade. Então, são objetos diferentes e por isso a expressão `x is y`retorna `False`. Em outras palavras, você consegue `False`porque tem duas instâncias diferentes `1001`armazenadas na memória do seu computador.

Quando você faz uma atribuição como `y = x`, o Python cria uma segunda referência para o mesmo objeto. Novamente, você pode confirmar isso com a `id()`função ou o `is`operador:

Python

```Python
>>> a = "Hello, Pythonista!"
>>> b = a

>>> id(a)
4417651936
>>> id(b)
4417651936

>>> a is b
True
```

Neste exemplo, `a`e `b`mantenha referências ao mesmo objeto, a string `"Hello, Pythonista!"`. Portanto, a `id()`função retorna a mesma identidade quando você a chama com `a`e `b`. Da mesma forma, o `is`operador retorna `True`.

**Observação:** você deve observar que, no seu computador, você receberá um número de identidade diferente ao ligar `id()`no exemplo acima. O detalhe principal é que o número de identidade será o mesmo para `a`e `b`.

Finalmente, o `is not`operador é o oposto de `is`. Então, você pode usar `is not`para determinar se dois nomes *não* se referem ao mesmo objeto:

Python

```Python
>>> x = 1001
>>> y = 1001
>>> x is not y
True

>>> a = "Hello, Pythonista!"
>>> b = a
>>> a is not b
False
```

No primeiro exemplo, porque `x`e `y`apontam para diferentes objetos na memória do seu computador, o `is not`operador retorna `True`. No segundo exemplo, como `a`e `b`são referências ao mesmo objeto, o `is not`operador retorna `False`.

**Nota:** A sintaxe `not x is y`também funciona da mesma forma que `x is not y`. No entanto, a sintaxe anterior parece estranha e difícil de ler. É por isso que o Python é reconhecido `is not`como um operador e incentiva seu uso para facilitar a leitura.

Novamente, o `is not`operador destaca os objetivos de legibilidade do Python. Em geral, ambos os operadores de identidade permitem que você emita cheques que são lidos em inglês simples.

## Operadores e expressões de associação em Python

Às vezes você precisa determinar se um valor está presente em um tipo de dados contêiner, como uma lista, tupla ou conjunto. Em outras palavras, pode ser necessário verificar se um determinado valor *é* ou *não* membro de **uma** coleção de valores. Python chama esse tipo de verificação de [teste de adesão](https://docs.python.org/3/reference/expressions.html#membership-test-operations) .

**Observação:** para se aprofundar em como funcionam os testes de associação do Python, verifique [os operadores “in” e “not in” do Python: Check for Membership](https://realpython.com/python-in-operator/) .

Os testes de adesão são bastante comuns e úteis na programação. Tal como acontece com muitas outras operações comuns, Python possui operadores dedicados para testes de adesão. A tabela abaixo lista os **operadores de associação** em Python:

| Operador                                                                | Expressão de amostra      | Resultado                                                                                |
| ----------------------------------------------------------------------- | ------------------------- | ---------------------------------------------------------------------------------------- |
| [`in`](https://docs.python.org/3/reference/expressions.html#in)         | `value in collection`     | •`True`se `value` *está* presente em `collection`• `False`caso contrário                 |
| [`not in`](https://docs.python.org/3/reference/expressions.html#not-in) | `value not in collection` | •`True`se `value` *não estiver* presente em `collection`valores``• `False`caso contrário |

Como sempre, o Python favorece a legibilidade usando palavras em inglês como operadores, em vez de símbolos ou combinações de símbolos potencialmente confusos.

**Nota:** A sintaxe `not value in collection`também funciona em Python. No entanto, esta sintaxe parece estranha e difícil de ler. Portanto, para manter seu código limpo e legível, você deve usar `value not in collection`, que quase parece um inglês simples.

O Python `in`e `not in`os operadores são binários. Isso significa que você pode criar expressões de associação conectando dois operandos com qualquer um dos operadores. Entretanto, os operandos em uma expressão de pertinência possuem características particulares:

* **Operando esquerdo** : o valor que você deseja procurar em uma coleção de valores
* **Operando direito** : a coleção de valores onde o valor alvo pode ser encontrado

Para entender melhor o `in` operador, segue abaixo dois exemplos demonstrativos que consistem em determinar se um valor está em uma lista:

Python

```Python
>>> 5 in [2, 3, 5, 9, 7]
True

>>> 8 in [2, 3, 5, 9, 7]
False
```

A primeira expressão retorna `True`porque `5`está na lista de números. A segunda expressão retorna `False`porque `8`não está na lista.

O `not in`operador de associação executa o teste oposto ao `in`operador. Permite verificar se um valor inteiro *não está* em uma coleção de valores:

Python

```Python
>>> 5 not in [2, 3, 5, 9, 7]
False

>>> 8 not in [2, 3, 5, 9, 7]
True
```

No primeiro exemplo, você obtém `False`porque `5`está na lista de alvos. No segundo exemplo, você obtém `True`porque `8`não está na lista de valores. Isso pode soar como um trava-língua por causa da lógica negativa. Para evitar confusão, lembre-se de que você está tentando determinar se o valor *não faz* parte de uma determinada coleção de valores.

## Operadores e Expressões de Concatenação e Repetição

Existem dois operadores em Python que adquirem um significado ligeiramente diferente quando você os usa com tipos de dados de sequência, como listas, tuplas e strings. Com estes tipos de operandos, o `+`operador define um **operador de concatenação** , e o `*`operador representa o **operador de repetição** :

| Operador | Operação     | Expressão de amostra | Resultado                                                         |
| -------- | ------------ | -------------------- | ----------------------------------------------------------------- |
| `+`      | Concatenação | `seq_1 + seq_2`      | Uma nova sequência contendo todos os itens de ambos os operandos  |
| `*`      | Repetição    | `seq * n`            | Uma nova sequência contendo os itens de tempos `seq`repetidos `n` |

Ambos os operadores são binários. O operador de concatenação toma duas sequências como operandos e retorna uma nova sequência do mesmo tipo. O operador de repetição utiliza uma sequência e um número inteiro como operandos. Como na multiplicação regular, a ordem dos operandos não altera o resultado da repetição.

**Observação:** para saber mais sobre concatenação de objetos string, consulte [Concatenação eficiente de strings em Python](https://realpython.com/python-string-concatenation/) .

Aqui estão alguns exemplos de como o operador de concatenação funciona na prática:

Python

```Python
>>> "Hello, " + "World!"
'Hello, World!'

>>> ("A", "B", "C") + ("D", "E", "F")
('A', 'B', 'C', 'D', 'E', 'F')

>>> [0, 1, 2, 3] + [4, 5, 6]
[0, 1, 2, 3, 4, 5, 6]
```

No primeiro exemplo, você usa o operador de concatenação ( `+`) para unir duas strings. O operador retorna um objeto string completamente novo que combina as duas strings originais.

No segundo exemplo, você concatena duas tuplas de letras. Novamente, o operador retorna um novo objeto tupla contendo todos os itens dos operandos originais. No exemplo final, você faz algo semelhante, mas desta vez com duas listas.

**Observação:** para saber mais sobre concatenação de listas, confira a seção [Concatenação de listas](https://realpython.com/python-list/#concatenating-lists) no tutorial Tipo de dados [do Python `list`: um mergulho profundo com exemplos](https://realpython.com/python-list/) .

Quando se trata do operador de repetição, a ideia é repetir o conteúdo de uma determinada sequência um determinado número de vezes. Aqui estão alguns exemplos:

Python

```Python
>>> "Hello" * 3
'HelloHelloHello'
>>> 3 * "World!"
'World!World!World!'

>>> ("A", "B", "C") * 3
('A', 'B', 'C', 'A', 'B', 'C', 'A', 'B', 'C')

>>> 3 * [1, 2, 3]
[1, 2, 3, 1, 2, 3, 1, 2, 3]
```

No primeiro exemplo, você usa o operador de repetição ( `*`) para repetir a `"Hello"`string três vezes. No segundo exemplo, você altera a ordem dos operandos colocando o número inteiro à esquerda e a string de destino à direita. Este exemplo mostra que a ordem dos operandos não afeta o resultado.

Os próximos exemplos utilizam os operadores de repetição com uma tupla e uma lista, respectivamente. Em ambos os casos, você obtém um novo objeto do mesmo tipo contendo os itens da sequência original repetida três vezes.

## O operador Walrus e expressões de atribuição

Instruções de atribuição regulares com o `=`operador não possuem valor de retorno, como você já aprendeu. Em vez disso, o operador de atribuição cria ou atualiza variáveis. Por causa disso, o operador não pode fazer parte de uma expressão.

Desde [o Python 3.8](https://realpython.com/python38-new-features/) , você tem acesso a um novo operador que permite um novo tipo de atribuição. Esta nova atribuição é chamada de **expressão de atribuição** ou **expressão nomeada** . O novo operador é chamado de **operador morsa** e é a combinação de dois pontos e um sinal de igual ( `:=`).

**Nota:** O nome *morsa* vem do fato deste operador se assemelhar aos olhos e presas de uma morsa deitada de lado. Para se aprofundar em como esse operador funciona, consulte [The Walrus Operator: Python 3.8 Assignment Expressions](https://realpython.com/python-walrus-operator/) .

Ao contrário das atribuições regulares, as expressões de atribuição têm um valor de retorno, e é por isso que são *expressions* . Assim, o operador realiza duas tarefas:

1. Retorna o resultado da expressão
2. Atribui o resultado a uma variável

O operador morsa também é um operador binário. Seu operando esquerdo deve ser um nome de variável e seu operando direito pode ser qualquer expressão Python. O operador avaliará a expressão, atribuirá seu valor à variável de destino e retornará o valor.

A sintaxe geral de uma expressão de atribuição é a seguinte:

Python

```Python
(variable := expression)
```

Esta expressão parece uma atribuição regular. Porém, em vez de usar o operador de atribuição ( `=`), ele usa o operador morsa ( `:=`). Para que a expressão funcione corretamente, os parênteses são necessários na maioria dos casos de uso. No entanto, em certas situações, você não precisará deles. De qualquer forma, eles não vão machucar você, então é seguro usá-los.

As expressões de atribuição são úteis quando você deseja reutilizar o resultado de uma expressão ou parte de uma expressão sem usar uma atribuição dedicada para obter esse valor antecipadamente. É particularmente útil no contexto de uma declaração condicional. Para ilustrar, o exemplo abaixo mostra uma função de brinquedo que verifica o comprimento de um objeto string:

Python

```Python
>>> def validate_length(string):
...     if (n := len(string)) < 8:
...         print(f"Length {n} is too short, needs at least 8")
...     else:
...         print(f"Length {n} is okay!")
...

>>> validate_length("Pythonista")
Length 10 is okay!

>>> validate_length("Python")
Length 6 is too short, needs at least 8
```

Neste exemplo, você usa uma instrução condicional para verificar se a string de entrada tem menos de `8`caracteres.

A expressão de atribuição `(n := len(string))`calcula o comprimento da string e o atribui a `n`. Em seguida, ele retorna o valor resultante da chamada `len()`, que finalmente é comparado com `8`. Dessa forma, você garante que terá uma referência ao comprimento da string para usar em operações posteriores.

## Operadores e expressões bit a bit em Python

**Os operadores bit a bit** tratam os operandos como sequências de dígitos [binários](https://realpython.com/python-bitwise-operators/#binary-system-in-five-minutes) e operam neles bit a bit. Atualmente, Python oferece suporte aos seguintes operadores bit a bit:

| Operador | Operação                               | Expressão de amostra | Resultado                                                                                                                                                                   |
| -------- | -------------------------------------- | -------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `&`      | E bit a bit                            | `a & b`              | • Cada posição de bit no resultado é o AND lógico dos bits na posição correspondente dos operandos.``• `1`se ambos os bits forem `1`, caso contrário `0`.                   |
| `\|`     | OU bit a bit                           | `a \| b`             | • Cada posição de bit no resultado é o**OR** lógico dos bits na posição correspondente dos operandos.``• `1`se um dos bits for `1`, caso contrário `0`.                     |
| `~`      | Bit a bit NÃO                          | `~a`                 | • Cada posição de bit no resultado é a negação lógica do bit na posição correspondente do operando.``• `1`se o bit for `0`e `0`se o bit for `1`.                            |
| `^`      | XOR bit a bit (OU exclusivo)           | `a ^ b`              | • Cada posição de bit no resultado é o**XOR** lógico dos bits na posição correspondente dos operandos.``• `1`se os bits dos operandos forem diferentes, `0`se forem iguais. |
| `>>`     | Deslocamento bit a bit para a direita  | `a >> n`             | Cada bit é deslocado para `n`os lugares certos.                                                                                                                             |
| `<<`     | Deslocamento bit a bit para a esquerda | `a << n`             | Cada bit é deslocado `n`para a esquerda.               |

Como você pode ver nesta tabela, a maioria dos operadores bit a bit são binários, o que significa que eles esperam dois operandos. O operador NOT bit a bit ( `~`) é o único operador unário porque espera um único operando, que deve aparecer sempre no lado direito da expressão.

Você pode usar os operadores bit a bit do Python para manipular seus dados em seu nível mais granular, os bits. Esses operadores são comumente úteis quando você deseja escrever algoritmos de baixo nível, como compactação, criptografia e outros.

**Observação:** para se aprofundar nos operadores bit a bit, consulte [Operadores bit a bit em Python](https://realpython.com/python-bitwise-operators/) . Você também pode verificar [Construir um solucionador de labirinto em Python usando gráficos](https://realpython.com/python-maze-solver/#step-4-load-the-maze-from-a-binary-file) para obter um exemplo de uso de operadores bit a bit para construir um formato de arquivo binário.

Aqui estão alguns exemplos que ilustram como alguns dos operadores bit a bit funcionam na prática:

Python

```Python
>>> # Bitwise AND
>>> #   0b1100    12
>>> # & 0b1010    10
>>> # --------
>>> # = 0b1000     8
>>> bin(0b1100 & 0b1010)
'0b1000'
>>> 12 & 10
8

>>> # Bitwise OR
>>> #   0b1100    12
>>> # | 0b1010    10
>>> # --------
>>> # = 0b1110    14
>>> bin(0b1100 | 0b1010)
'0b1110'
>>> 12 | 10
14
```

No primeiro exemplo, você usa o operador AND bit a bit. As linhas comentadas começam `#`e fornecem uma representação visual do que acontece no nível do bit. Observe como cada bit no resultado é o AND lógico dos bits na posição correspondente dos operandos.

O segundo exemplo mostra como funciona o operador OR bit a bit. Neste caso, os bits resultantes são o teste lógico OR dos bits correspondentes nos operandos.

Em todos os exemplos, você usou a função integrada `bin()`para exibir o resultado como um objeto binário. Se você não agrupar a expressão em uma chamada para `bin()`, obterá a representação inteira da saída.

## Precedência do Operador em Python

Até este ponto, você codificou expressões de exemplo que usam principalmente um ou dois tipos diferentes de operadores. Porém, e se você precisar criar expressões compostas que utilizem vários tipos diferentes de operadores, como comparação, aritmética, booleana e outros? Como o Python decide qual operação será executada primeiro?

Considere a seguinte expressão matemática:

Python

```Python
>>> 20 + 4 * 10
60
```

Pode haver ambiguidade nesta expressão. O Python deveria realizar a adição `20 + 4`primeiro e depois multiplicar o resultado por `10`? O Python deveria executar a multiplicação `4 * 10`primeiro e depois a adição?

Como o resultado é `60`, você pode concluir que o Python escolheu a última abordagem. Se tivesse escolhido o primeiro, o resultado seria `240`. Isso segue uma regra algébrica padrão que você encontrará em praticamente todas as linguagens de programação.

Todos os operadores suportados pelo Python têm [precedência](https://docs.python.org/3/reference/expressions.html#operator-precedence) em comparação com outros operadores. Esta precedência define a ordem em que o Python executa os operadores em uma expressão composta.

Em uma expressão, o Python executa primeiro os operadores de maior precedência. Depois de obter esses resultados, o Python executa os operadores da próxima precedência mais alta. Este processo continua até que a expressão seja totalmente avaliada. Quaisquer operadores de igual precedência são executados na ordem da esquerda para a direita.

Aqui está a ordem de precedência dos operadores Python que você viu até agora, do maior para o menor:

| Operadores                                                      | Descrição                                                                                        |
| --------------------------------------------------------------- | ------------------------------------------------------------------------------------------------ |
| `**`                                                            | Exponenciação                                                                                    |
| `+x`, `-x`,`~x`                                                 | Positivo unário, negação unária, negação bit a bit                                               |
| `*`, `/`, `//`,`%`                                              | Multiplicação, divisão, divisão de piso,[módulo](https://realpython.com/python-modulo-operator/) |
| `+`,`-`                                                         | Adição subtração                                                                                 |
| `<<`,`>>`                                                       | Mudanças bit a bit                                                                               |
| `&`                                                             | E bit a bit                                                                                      |
| `^`                                                             | XOR bit a bit                                                                                    |
| `\|`                                                            | OU bit a bit                                                                                     |
| `==`, `!=`, `<`, `<=`, `>`, `>=`, `is`, `is not`, `in`,`not in` | Comparações, identidade e associação                                                             |
| `not`                                                           | Booleano NÃO                                                                                     |
| `and`                                                           | Booleano E                                                                                       |
| `or`                                                            | Booleano OU                                                                                      |
| `:=`                                                            | Morsa                                                                                            |

Os operadores no topo da tabela têm a precedência mais alta e os que estão na parte inferior da tabela têm a precedência mais baixa. Quaisquer operadores na mesma linha da tabela têm precedência igual.

Voltando ao seu exemplo inicial, Python executa a multiplicação porque o operador de multiplicação tem uma precedência maior que o de adição.

Aqui está outro exemplo ilustrativo:

Python

```Python
>>> 2 * 3 ** 4 * 5
810
```

No exemplo acima, Python primeiro eleva `3`à potência de `4`, que é igual a `81`. Em seguida, realiza as multiplicações na ordem da esquerda para a direita: `2 * 81 = 162`e `162 * 5 = 810`.

Você pode substituir a precedência do operador padrão usando parênteses para agrupar termos, como faz em matemática. As sub expressões entre parênteses serão executadas antes das expressões que não estão entre parênteses.

Aqui estão alguns exemplos que mostram como um par de parênteses pode afetar o resultado de uma expressão:

Python

```Python
>>> (20 + 4) * 10
240

>>> 2 * 3 ** (4 * 5)
6973568802
```

No primeiro exemplo, o Python calcula a expressão `20 + 4`primeiro porque ela está entre parênteses. Então Python multiplica o resultado por `10`e a expressão retorna `240`. Este resultado é completamente diferente do que você obteve no início desta seção.

No segundo exemplo, o Python avalia `4 * 5`primeiro. Em seguida, aumenta `3`à potência do valor resultante. Finalmente, Python multiplica o resultado por `2`, retornando `6973568802`.

Não há nada de errado em fazer uso liberal de parênteses, mesmo quando eles não são necessários para alterar a ordem de avaliação. Às vezes é uma boa prática usar parênteses porque eles podem melhorar a legibilidade do seu código e evitar que o leitor tenha que recuperar a precedência do operador da memória.

Considere o seguinte exemplo:

Python

```Python
(a < 10) and (b > 30)
```

Aqui os parênteses são desnecessários, pois os operadores de comparação têm precedência maior que `and`. No entanto, alguns podem achar a versão entre parênteses mais clara do que a versão sem parênteses:

Python

```Python
a < 10 and b > 30
```

Por outro lado, alguns desenvolvedores podem preferir esta última versão da expressão. É uma questão de preferência pessoal. A questão é que você sempre pode usar parênteses se achar que eles tornam seu código mais legível, mesmo que não sejam necessários para alterar a ordem de avaliação.

## Operadores e Expressões de Atribuição Aumentada

Até agora, você aprendeu que um único sinal de igual ( `=`) representa o operador de atribuição e permite atribuir um valor a uma variável. Ter um operando à direita que contenha outras variáveis é perfeitamente válido, como você também aprendeu. Em particular, a expressão à direita do operador de atribuição pode incluir a mesma variável que está à esquerda do operando.

A última frase pode parecer confusa, então aqui está um exemplo que esclarece o ponto:

Python

```Python
>>> total = 10
>>> total = total + 5
>>> total
15
```

Neste exemplo, `total`é uma variável **acumuladora** que você usa para *acumular* valores sucessivos. Você deve ler este exemplo como *`total`igual ao valor atual de `total` plus `5`* . Esta expressão aumenta efetivamente o valor de `total`, que agora é `15`.

Note que este tipo de atribuição só faz sentido se a variável em questão já possuir um valor. Se você tentar a atribuição com uma variável indefinida, receberá um erro:

Python

```Python
>>> count = count + 1
Traceback (most recent call last):
...
NameError: name 'count' is not defined. Did you mean: 'round'?
```

Neste exemplo, a `count`variável não está definida antes da atribuição, portanto não possui um valor atual. Consequentemente, o Python levanta uma [`NameError`](https://realpython.com/python-traceback/#nameerror)exceção para informar você sobre o problema.

Este tipo de atribuição ajuda a criar acumuladores e variáveis de contador, por exemplo. Portanto, é uma tarefa bastante comum em programação. Como em muitos casos semelhantes, o Python oferece uma solução mais conveniente. Ele suporta uma sintaxe abreviada chamada [atribuição aumentada](https://realpython.com/python-assignment-operator/#augmented-assignment-operators-in-python) :

Python

```Python
>>> total = 10
>>> total += 5
>>> total
15
```

Na linha destacada, você usa o operador de adição aumentada ( `+=`). Com esse operador, você cria uma atribuição totalmente equivalente a `total = total + 5`.

Python oferece suporte a muitos operadores de atribuição aumentada. Em geral, a sintaxe para este tipo de atribuição é mais ou menos assim:

Python

```Python
variable $= expression
```

Observe que o cifrão ( `$`) não é um operador Python válido. Neste exemplo, é um espaço reservado para um operador genérico. A afirmação acima funciona da seguinte maneira:

1. Avaliar `expression`para produzir um valor.
2. Execute a operação definida pelo operador que prefixa o operador de atribuição ( `=`), usando o valor atual de `variable`e o valor de retorno de `expression`como operandos.
3. Atribua o valor resultante de volta a `variable`.

A tabela abaixo mostra um resumo dos operadores aumentados para operações aritméticas:

| Operador | Descrição                                                                                                                                                              | Expressão de amostra | Expressão Equivalente |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- | --------------------- |
| `+=`     | Adiciona o operando direito ao operando esquerdo e armazena o resultado no operando esquerdo                                                                           | `x += y`             | `x = x + y`           |
| `-=`     | Subtrai o operando direito do operando esquerdo e armazena o resultado no operando esquerdo                                                                            | `x -= y`             | `x = x - y`           |
| `*=`     | Multiplica o operando direito pelo operando esquerdo e armazena o resultado no operando esquerdo                                                                       | `x *= y`             | `x = x * y`           |
| `/=`     | Divide o operando esquerdo pelo operando direito e armazena o resultado no operando esquerdo                                                                           | `x /= y`             | `x = x / y`           |
| `//=`    | Realiza[a divisão](https://docs.python.org/3/glossary.html#term-floor-division) do operando esquerdo pelo operando direito e armazena o resultado no operando esquerdo | `x //= y`            | `x = x // y`          |
| `%=`     | Encontra o restante da divisão do operando esquerdo pelo operando direito e armazena o resultado no operando esquerdo                                                  | `x %= y`             | `x = x % y`           |
| `**=`    | Eleva o operando esquerdo à potência do operando direito e armazena o resultado no operando esquerdo                                                                   | `x **= y`            | `x = x**y`            |

Como você pode concluir nesta tabela, todos os operadores aritméticos têm uma versão aumentada em Python. Você pode usar esses operadores aumentados como atalho ao criar acumuladores, contadores e objetos semelhantes.

Os operadores aritméticos aumentados pareciam simples e úteis para você? A boa notícia é que existem mais. Você também tem operadores bit a bit aumentados em Python:

| Operador | Operação                                                                                     | Exemplo   | Equivalente  |
| -------- | -------------------------------------------------------------------------------------------- | --------- | ------------ |
| `&=`     | AND bit a bit aumentado ([conjunção](https://en.wikipedia.org/wiki/Logical_conjunction) )    | `x &= y`  | `x = x & y`  |
| `\|=`    | OR bit a bit aumentado ([disjunção](https://en.wikipedia.org/wiki/Logical_disjunction) )     | `x \|= y` | `x = x \| y` |
| `^=`     | XOR bit a bit aumentado ([disjunção exclusiva](https://en.wikipedia.org/wiki/Exclusive_or) ) | `x ^= y`  | `x = x ^ y`  |
| `>>=`    | Deslocamento à direita bit a bit aumentado                                                   | `x >>= y` | `x = x >> y` |
| `<<=`    | Deslocamento à esquerda bit a bit aumentado                                                  | `x <<= y` | `x = x << y` |

Finalmente, os operadores de concatenação e repetição também aumentaram as variações. Essas variações se comportam de maneira diferente com tipos de dados mutáveis e imutáveis:

| Operador | Descrição                                                                                                                                                                                                                             | Exemplo          |
| -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- |
| `+=`     | • Executa uma operação de concatenação aumentada na sequência de destino.``• As sequências mutáveis são atualizadas no local.``• Se a sequência for imutável, uma nova sequência será criada e atribuída de volta ao nome de destino. | `seq_1 += seq_2` |
| `*=`     | • Adiciona `seq`a si mesmo `n`tempos.``• As sequências mutáveis são atualizadas no local.``• Se a sequência for imutável, uma nova sequência será criada e atribuída de volta ao nome de destino.                                     | `seq *= n`       |

Observe que o [operador de concatenação](https://realpython.com/python-string-concatenation/#doing-string-concatenation-with-pythons-plus-operator) aumentada funciona em duas sequências, enquanto o [operador de repetição](https://realpython.com/python-string-concatenation/#doing-repeated-concatenation-with-the-star-operator) aumentada funciona em uma sequência e em um número inteiro.

## Conclusão

Agora você sabe quais **operadores** o Python suporta e como usá-los. Operadores são símbolos, combinações de símbolos ou palavras-chave que você pode usar junto com objetos Python para construir diferentes tipos de **expressões** e realizar cálculos em seu código.

**Neste tutorial, você aprendeu:**

* **O que são os operadores aritméticos** do Python e como usá-los em **expressões aritméticas**
* O que são os operadores **de comparação** , **booleano** , **identidade** e **associação** do Python
* Como escrever **expressões** usando operadores de comparação, booleanos, de identidade e de associação
* Quais operadores **bit a bit o** Python suporta e como usá-los
* Como combinar e repetir sequências usando os operadores **de concatenação** e **repetição**
* O que são os operadores **de atribuição aumentada** e como funcionam

Em outras palavras, você cobriu muito terreno! Se você quiser uma folha de dicas útil que possa refrescar sua memória com tudo o que você aprendeu, clique no link abaixo:
