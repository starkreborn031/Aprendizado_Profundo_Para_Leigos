# ![Tipos de dados básicos em Python](https://files.realpython.com/media/Basic-Data-Types-in-Python_Watermarked.e3dd34457952.jpg)

## Tipos de dados básicos em Python

## **Inteiros**

No Python 3, efetivamente não há limite para o tamanho que um valor inteiro pode ter. Claro, ele é limitado pela quantidade de memória que seu sistema possui, assim como todas as coisas, mas além disso, um número inteiro pode ser tão longo quanto você precisar:

PYTHON

```Python
>>> print(123123123123123123123123123123123123123123123123 + 1)
123123123123123123123123123123123123123123123124
```

Python interpreta uma sequência de dígitos decimais sem qualquer prefixo como um número decimal:

PYHTON

```Python
>>> print(10)
10
```

As seguintes strings podem ser anexadas a um valor inteiro para indicar uma base diferente de 10:

| Prefixo                                                              | Interpretação | Base |
| -------------------------------------------------------------------- | ------------- | ---- |
| `0b`(zero + letra minúscula `'b'`)`0B`(zero + letra maiúscula `'B'`) | Binário       | 2    |
| `0o`(zero + letra minúscula `'o'`)`0O`(zero + letra maiúscula `'O'`) | octal         | 8    |
| `0x`(zero + letra minúscula `'x'`)`0X`(zero + letra maiúscula `'X'`) | Hexadecimal   | 16   |

Por exemplo:

PYHTON

```Python
>>> print(0o10)
8

>>> print(0x10)
16

>>> print(0b10)
2
```

Para obter mais informações sobre valores inteiros com bases não decimais, consulte os seguintes sites da Wikipédia: [Binário](https://en.wikipedia.org/wiki/Binary_number) , [Octal](https://en.wikipedia.org/wiki/Octal) e [Hexadecimal](https://en.wikipedia.org/wiki/Hexadecimal) .

O tipo subjacente de um inteiro Python, independentemente da base usada para especificá-lo, é chamado `int`:

PYHTON

```Python
>>> type(10)
<class 'int'>
>>> type(0o10)
<class 'int'>
>>> type(0x10)
<class 'int'>
```

**Nota:** Este é um bom momento para mencionar que se você deseja exibir um valor durante uma sessão REPL, não precisa usar a `print()`função. Basta digitar o valor no `>>>`prompt e clicar Enterpara exibi-lo:

PYHTON

```Python
>>> 10
10
>>> 0x10
16
>>> 0b10
2
```

Muitos dos exemplos nesta série de tutoriais usarão esse recurso.

Observe que isso não funciona dentro de um arquivo de script. Um valor que aparece sozinho em uma linha em um arquivo de script não fará nada.

## Números de ponto flutuante

O `float`tipo em Python designa um número de ponto flutuante. `float`os valores são especificados com um ponto decimal. Opcionalmente, o caractere `e`ou `E`seguido por um número inteiro positivo ou negativo pode ser anexado para especificar [a notação científica](https://en.wikipedia.org/wiki/Scientific_notation) :

PYHTON

```Python
>>> 4.2
4.2
>>> type(4.2)
<class 'float'>
>>> 4.
4.0
>>> .2
0.2

>>> .4e7
4000000.0
>>> type(.4e7)
<class 'float'>
>>> 4.2e-4
0.00042
```

> Aprofundamento: Representação de Ponto Flutuante
>
> A seguir estão informações um pouco mais detalhadas sobre como o Python representa números de ponto flutuante internamente. Você pode usar facilmente números de ponto flutuante em Python sem entendê-los até esse nível, então não se preocupe se isso parecer muito complicado. As informações são apresentadas aqui caso você tenha curiosidade.
>
> Quase todas as plataformas representam `float`valores Python como valores de “precisão dupla” de 64 bits, de acordo com o padrão [IEEE 754](https://en.wikipedia.org/wiki/IEEE_754_revision) . Nesse caso, o valor máximo que um número de ponto flutuante pode ter é aproximadamente 1,8 ⨉ 10 ^308^ . Python indicará um número maior que o da string `inf`:
> PYHTON

 ```Python
>>> 1.79e308
 1.79e+308
>>> 1.8e308
 inf
 ```

> O mais próximo que um número diferente de zero pode estar de zero é aproximadamente 5,0 ⨉ 10 ^-324^ . Qualquer coisa mais próxima de zero do que isso é efetivamente zero:
> PYHTON

 ```Python
>>> 5e-324
 5e-324
>>> 1e-325
 0.0
 ```

> Os números de ponto flutuante são representados internamente como frações binárias (base 2). A maioria das frações decimais não pode ser representada exatamente como frações binárias; portanto, na maioria dos casos, a representação interna de um número de ponto flutuante é uma aproximação do valor real. Na prática, a diferença entre o valor real e o valor representado é muito pequena e normalmente não deve causar problemas significativos.

**Leitura adicional:** para obter informações adicionais sobre representação de ponto flutuante em Python e as possíveis armadilhas envolvidas, consulte [Aritmética de ponto flutuante: problemas e limitações](https://docs.python.org/3.6/tutorial/floatingpoint.html) na documentação do Python.

## Números complexos

[Os números complexos](https://realpython.com/python-complex-numbers/) são especificados como `<real part>+<imaginary part>j`. Por exemplo:

PYHTON

```Python
>>> 2+3j
(2+3j)
>>> type(2+3j)
<class 'complex'>
```

## Cordas

Strings são sequências de dados de caracteres. O [tipo de string](https://realpython.com/python-strings/) em Python é chamado `str`.

Literais de string podem ser delimitados usando aspas simples ou duplas. Todos os caracteres entre o delimitador de abertura e o delimitador de fechamento correspondente fazem parte da string:

PYHTON

```Python
>>> print("I am a string.")
I am a string.
>>> type("I am a string.")
<class 'str'>

>>> print('I am too.')
I am too.
>>> type('I am too.')
<class 'str'>
```

Uma string em Python pode conter quantos caracteres você desejar. O único limite são os recursos de memória da sua máquina. Uma string também pode estar vazia:

PYHTON

```Python
>>> ''
''
```

E se você quiser incluir um caractere de aspas como parte da própria string? Seu primeiro impulso pode ser tentar algo assim:

PYHTON

```Python
>>> print('This string contains a single quote (') character.')
SyntaxError: invalid syntax
```

Como você pode ver, isso não funciona tão bem. A string neste exemplo abre com aspas simples, então o Python assume que a próxima aspas simples, aquela entre parênteses que deveria fazer parte da string, é o delimitador de fechamento. A aspa simples final fica perdida e causa o [erro de sintaxe](https://realpython.com/invalid-syntax-python/) mostrado.

Se você quiser incluir qualquer tipo de caractere de aspas na string, a maneira mais simples é delimitar a string com o outro tipo. Se uma string deve conter aspas simples, delimite-a com aspas duplas e vice-versa:

PYHTON

```Python
>>> print("This string contains a single quote (') character.")
This string contains a single quote (') character.

>>> print('This string contains a double quote (") character.')
This string contains a double quote (") character.
```

### Sequências de escape em strings

Às vezes, você deseja que o Python interprete um caractere ou sequência de caracteres dentro de uma string de maneira diferente. Isso pode ocorrer de duas maneiras:

* Você pode querer suprimir a interpretação especial que certos caracteres geralmente recebem em uma string.
* Você pode querer aplicar uma interpretação especial aos caracteres em uma string que normalmente seria interpretada literalmente.

Você pode fazer isso usando um `\`caractere de barra invertida ( ). Um caractere de barra invertida em uma string indica que um ou mais caracteres que o seguem devem ser tratados de maneira especial. (Isso é chamado de sequência de escape, porque a barra invertida faz com que a sequência de caracteres subsequente “escapa” de seu significado usual.)

Vamos ver como isso funciona.

#### Suprimindo o significado de caracteres especiais

Você já viu os problemas que pode encontrar ao tentar incluir caracteres de aspas em uma string. Se uma string for delimitada por aspas simples, você não poderá especificar diretamente um caractere de aspas simples como parte da string porque, para essa string, as aspas simples têm um significado especial – ela encerra a string:

PYHTON

```Python
>>> print('This string contains a single quote (') character.')
SyntaxError: invalid syntax
```

Especificar uma barra invertida na frente do caractere de aspas em uma string “escapa” dela e faz com que o Python suprima seu significado especial usual. Em seguida, é interpretado simplesmente como um caractere literal de aspas simples:

PYHTON

```Python
>>> print('This string contains a single quote (\') character.')
This string contains a single quote (') character.
```

O mesmo funciona em uma string delimitada por aspas duplas:

PYHTON

```Python
>>> print("This string contains a double quote (\") character.")
This string contains a double quote (") character.
```

A seguir está uma tabela de sequências de escape que fazem com que o Python suprima a interpretação especial usual de um caractere em uma string:

| ``Sequência de fuga | Interpretação usual de``caractere(s) após barra invertida     | Interpretação “escapada”                                                                                                     |
| ------------------- | ------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `\'`                | Termina a string com delimitador de abertura de aspas simples | Caractere literal de aspas simples (`'`)                                                                                     |
| `\"`                | Termina a string com delimitador de abertura de aspas duplas  | Caractere literal de aspas duplas (`"`)                                                                                      |
| `\<newline>`        | Termina a linha de entrada                                    | [A nova linha é ignorada](https://stackoverflow.com/questions/48693600/what-does-the-newline-escape-sequence-mean-in-python) |
| `\\`                | Apresenta sequência de escape                                 | Caractere literal de barra invertida (`\`)                                                                                   |

Normalmente, um caractere de nova linha encerra a entrada de linha. Portanto, pressionar Enterno meio de uma string fará com que o Python pense que ela está incompleta:

PYHTON

```Python
>>> print('a

SyntaxError: EOL while scanning string literal
```

Para dividir uma string em mais de uma linha, inclua uma barra invertida antes de cada nova linha e as novas linhas serão ignoradas:

PYHTON

```Python
>>> print('a\
... b\
... c')
abc
```

Para incluir uma barra invertida literal em uma string, escape-a com uma barra invertida:

PYHTON

```Python
>>> print('foo\\bar')
foo\bar
```

#### Aplicando significado especial aos personagens

A seguir, suponha que você precise criar uma string que contenha um caractere de tabulação. Alguns editores de texto podem permitir que você insira um caractere de tabulação diretamente em seu código. Mas muitos programadores consideram essa prática inadequada, por vários motivos:

* O computador consegue distinguir entre um caractere de tabulação e uma sequência de caracteres de espaço, mas você não. Para um ser humano que lê o código, os caracteres de tabulação e espaço são visualmente indistinguíveis.
* Alguns editores de texto são configurados para eliminar automaticamente caracteres de tabulação, expandindo-os para o número apropriado de espaços.
* Alguns ambientes Python REPL não inserem guias no código.

Em Python (e em quase todas as outras linguagens de computador comuns), um caractere de tabulação pode ser especificado pela sequência de escape `\t`:

PYHTON

```Python
>>> print('foo\tbar')
foo     bar
```

A sequência de escape `\t`faz com que o `t`caractere perca seu significado usual, o de literal `t`. Em vez disso, a combinação é interpretada como um caractere de tabulação.

Aqui está uma lista de sequências de escape que fazem com que o Python aplique um significado especial em vez de interpretá-lo literalmente:

| Sequência de fuga | Interpretação “escapada”                                      |
| ----------------- | ------------------------------------------------------------- |
| `\a`              | `BEL`Caractere ASCII Bell ( )                                 |
| `\b`              | `BS`Caractere ASCII Backspace ( )                             |
| `\f`              | `FF`Caractere ASCII Formfeed ( )                              |
| `\n`              | `LF`Caractere ASCII Linefeed ( )                              |
| `\N{<name>}`      | Caractere do banco de dados Unicode com determinado `<name>`  |
| `\r`              | `CR`Caractere ASCII Carriage Return ( )                       |
| `\t`              | Caractere de guia horizontal ASCII (`TAB`)                    |
| `\uxxxx`          | Caractere Unicode com valor hexadecimal de 16 bits `xxxx`     |
| `\Uxxxxxxxx`      | Caractere Unicode com valor hexadecimal de 32 bits `xxxxxxxx` |
| `\v`              | Caractere de guia vertical ASCII (`VT`)                       |
| `\ooo`            | Caractere com valor octal `ooo`                               |
| `\xhh`            | Caractere com valor hexadecimal `hh`                          |

Exemplos:

PYHTON

```Python
>>> print("a\tb")
a    b
>>> print("a\141\x61")
aaa
>>> print("a\nb")
a
b
>>> print('\u2192\N{rightwards arrow}')
→ →
```

Esse tipo de sequência de escape é normalmente usado para inserir caracteres que não são gerados prontamente no teclado ou que não são facilmente legíveis ou imprimíveis.

### Cordas brutas

Uma string literal bruta é precedida por `r`ou `R`, que especifica que as sequências de escape na string associada não são traduzidas. O caractere de barra invertida é deixado na string:

PYHTON

```Python
>>> print('foo\nbar')
foo
bar
>>> print(r'foo\nbar')
foo\nbar

>>> print('foo\\bar')
foo\bar
>>> print(R'foo\\bar')
foo\\bar
```

### Strings com aspas triplas

Existe ainda outra maneira de delimitar strings em Python. Strings com aspas triplas são delimitadas por grupos correspondentes de três aspas simples ou três aspas duplas. As sequências de escape ainda funcionam em strings com aspas triplas, mas aspas simples, aspas duplas e novas linhas podem ser incluídas sem escapar delas. Isso fornece uma maneira conveniente de criar uma string com aspas simples e duplas:

PYHTON

```Python
>>> print('''This string has a single (') and a double (") quote.''')
This string has a single (') and a double (") quote.
```

Como novas linhas podem ser incluídas sem escapar delas, isso também permite strings multilinhas:

PYHTON

```Python
>>> print("""This is a
string that spans
across several lines""")
This is a
string that spans
across several lines
```

Você verá no próximo tutorial sobre Estrutura do Programa Python como strings entre aspas triplas podem ser usadas para adicionar um comentário explicativo ao código Python.

## Tipo booleano, contexto booleano e “veracidade”

Python 3 fornece um [tipo de dados booleano](https://realpython.com/python-boolean/) . Objetos do tipo booleano podem ter um de dois valores, `True`ou `False`:

PYHTON

```Python
>>> type(True)
<class 'bool'>
>>> type(False)
<class 'bool'>
```

Como você verá nos próximos tutoriais, as expressões em Python são frequentemente avaliadas no contexto booleano, o que significa que são interpretadas para representar verdade ou falsidade. Às vezes, um valor verdadeiro no contexto booleano é considerado “verdadeiro”, e um valor falso no contexto booleano é considerado “falso”. (Você também pode ver “falsy” escrito “falsey”.)

A “veracidade” de um objeto do tipo booleano é evidente: objetos booleanos iguais a são `True`verdadeiros (verdadeiros) e aqueles iguais a `False`são falsos (falso). Mas objetos não booleanos também podem ser avaliados no contexto booleano e determinados como verdadeiros ou falsos.

Você aprenderá mais sobre avaliação de objetos no contexto booleano ao encontrar operadores lógicos no próximo tutorial sobre operadores e expressões em Python.

## Funções integradas

O interpretador Python suporta muitas funções integradas: sessenta e oito, a partir do Python 3.6. Você abordará muitos deles nas discussões a seguir, à medida que surgirem no contexto.

Por enquanto, segue uma breve visão geral, apenas para dar uma ideia do que está disponível. Consulte a [documentação do Python sobre funções integradas](https://docs.python.org/3.6/library/functions.html) para obter mais detalhes. Muitas das descrições a seguir referem-se a tópicos e conceitos que serão discutidos em tutoriais futuros.

### Matemática

| Função                                                                                                | Descrição                                                         |
| ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| [`abs()`](https://realpython.com/python-absolute-value/#using-the-built-in-abs-function-with-numbers) | Retorna o valor absoluto de um número                             |
| `divmod()`                                                                                            | Retorna o quociente e o resto da divisão inteira                  |
| [`max()`](https://realpython.com/python-min-and-max/)                                                 | Retorna o maior dos argumentos ou itens fornecidos em um iterável |
| [`min()`](https://realpython.com/python-min-and-max/)                                                 | Retorna o menor dos argumentos ou itens fornecidos em um iterável |
| `pow()`                                                                                               | Eleva um número a uma potência                                    |
| `round()`                                                                                             | Arredonda um valor de ponto flutuante                             |
| [`sum()`](https://realpython.com/python-sum-function/)                                                | Soma os itens de um iterável                                      |

### Conversão de tipo

| Função      | Descrição                                                                       |
| ----------- | ------------------------------------------------------------------------------- |
| `ascii()`   | Retorna uma string contendo uma representação imprimível de um objeto           |
| `bin()`     | Converte um número inteiro em uma string binária                                |
| `bool()`    | Converte um argumento em um valor booleano                                      |
| `chr()`     | Retorna a representação em string do caractere fornecido pelo argumento inteiro |
| `complex()` | Retorna um número complexo construído a partir de argumentos                    |
| `float()`   | Retorna um objeto de ponto flutuante construído a partir de um número ou string |
| `hex()`     | Converte um número inteiro em uma string hexadecimal                            |
| `int()`     | Retorna um objeto inteiro construído a partir de um número ou string            |
| `oct()`     | Converte um número inteiro em uma string octal                                  |
| `ord()`     | Retorna a representação inteira de um caractere                                 |
| `repr()`    | Retorna uma string contendo uma representação imprimível de um objeto           |
| `str()`     | Retorna uma versão string de um objeto                                          |
| `type()`    | Retorna o tipo de um objeto ou cria um novo tipo de objeto                      |

### Iteráveis e Iteradores

| Função                                                       | Descrição                                                             |
| ------------------------------------------------------------ | --------------------------------------------------------------------- |
| [`all()`](https://realpython.com/python-all/)                | Retorna `True`se todos os elementos de um iterável forem verdadeiros  |
| [`any()`](https://realpython.com/any-python/)                | Retorna `True`se algum elemento de um iterável for verdadeiro         |
| [`enumerate()`](https://realpython.com/python-enumerate/)    | Retorna uma lista de tuplas contendo índices e valores de um iterável |
| [`filter()`](https://realpython.com/python-filter-function/) | Filtra elementos de um iterável                                       |
| `iter()`                                                     | Retorna um objeto iterador                                            |
| [`len()`](https://realpython.com/len-python-function/)       | Retorna o comprimento de um objeto                                    |
| [`map()`](https://realpython.com/python-map-function/)       | Aplica uma função a cada item de um iterável                          |
| `next()`                                                     | Recupera o próximo item de um iterador                                |
| `range()`                                                    | Gera um intervalo de valores inteiros                                 |
| `reversed()`                                                 | Retorna um iterador reverso                                           |
| `slice()`                                                    | Retorna um `slice`objeto                                              |
| [`sorted()`](https://realpython.com/python-sort/)            | Retorna uma lista ordenada de um iterável                             |
| [`zip()`](https://realpython.com/python-zip-function/)       | Cria um iterador que agrega elementos de iteráveis                    |

### Tipo de dados compostos

| Função        | Descrição                                                                                                                       |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `bytearray()` | Cria e retorna um objeto da[`bytearray`](https://realpython.com/python-strings/#bytearray-objects)classe                        |
| `bytes()`     | Cria e retorna um[`bytes`](https://realpython.com/python-strings/#bytes-objects)objeto (semelhante a `bytearray`, mas imutável) |
| `dict()`      | Cria um[`dict`](https://realpython.com/python-dicts/)objeto                                                                     |
| `frozenset()` | Cria um[`frozenset`](https://realpython.com/python-sets/#frozen-sets)objeto                                                     |
| `list()`      | Cria um[`list`](https://realpython.com/python-lists-tuples/)objeto                                                              |
| `object()`    | Cria um novo objeto sem características                                                                                         |
| `set()`       | Cria um[`set`](https://realpython.com/python-sets/)objeto                                                                       |
| `tuple()`     | Cria um[`tuple`](https://realpython.com/python-lists-tuples/)objeto                                                             |

### Classes, atributos e herança

| Função                                            | Descrição                                                                         |
| ------------------------------------------------- | --------------------------------------------------------------------------------- |
| `classmethod()`                                   | Retorna um método de classe para uma função                                       |
| `delattr()`                                       | Exclui um atributo de um objeto                                                   |
| `getattr()`                                       | Retorna o valor de um atributo nomeado de um objeto                               |
| `hasattr()`                                       | Retorna `True`se um objeto possui um determinado atributo                         |
| `isinstance()`                                    | Determina se um objeto é uma instância de uma determinada classe                  |
| `issubclass()`                                    | Determina se uma classe é uma subclasse de uma determinada classe                 |
| `property()`                                      | Retorna um valor de propriedade de uma classe                                     |
| `setattr()`                                       | Define o valor de um atributo nomeado de um objeto                                |
| [`super()`](https://realpython.com/python-super/) | Retorna um objeto proxy que delega chamadas de método para uma classe pai ou irmã |

### Entrada/Saída

| Função     | Descrição                                        |
| ---------- | ------------------------------------------------ |
| `format()` | Converte um valor em uma representação formatada |
| `input()`  | Lê a entrada do console                          |
| `open()`   | Abre um arquivo e retorna um objeto de arquivo   |
| `print()`  | Imprime em um fluxo de texto ou no console       |

### Variáveis, referências e escopo

| Função      | Descrição                                                                                                       |
| ----------- | --------------------------------------------------------------------------------------------------------------- |
| `dir()`     | Retorna uma lista de nomes no escopo local atual ou uma lista de atributos de objetos                           |
| `globals()` | Retorna um dicionário que representa a tabela de símbolos globais atual                                         |
| `id()`      | Retorna a identidade de um objeto                                                                               |
| `locals()`  | Atualiza e retorna um dicionário que representa a tabela de símbolos locais atual                               |
| `vars()`    | Retorna `__dict__`atributo para um [módulo](https://realpython.com/python-modules-packages/) , classe ou objeto |

### Diversos

| Função                                                   | Descrição                                     |
| -------------------------------------------------------- | --------------------------------------------- |
| `callable()`                                             | Retorna `True`se o objeto parecer chamável    |
| `compile()`                                              | Compila a fonte em um código ou objeto AST    |
| [`eval()`](https://realpython.com/python-eval-function/) | Avalia uma expressão Python                   |
| `exec()`                                                 | Implementa execução dinâmica de código Python |
| `hash()`                                                 | Retorna o valor hash de um objeto             |
| `help()`                                                 | Invoca o sistema de ajuda integrado           |
| `memoryview()`                                           | Retorna um objeto de visualização de memória  |
| `staticmethod()`                                         | Retorna um método estático para uma função    |
| `__import__()`                                           | Invocado pela `import`declaração              |

## Conclusão

**Neste tutorial, você aprendeu sobre os tipos de dados** e **funções** integrados que o Python fornece.

Os exemplos dados até agora foram todos manipulados e exibidos apenas com valores constantes. Na maioria dos programas, você normalmente desejará criar objetos que mudam de valor à medida que o programa é executado.
