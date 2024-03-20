# ![Declarações condicionais em Python](https://files.realpython.com/media/Conditional-Statements-in-Python_Watermarked.b6b7d30ff62b.jpg)

## Declarações condicionais em Python

Assista agoraEste tutorial tem um curso em vídeo relacionado criado pela equipe Real Python. Assista junto com o tutorial escrito para aprofundar sua compreensão: [**Declarações Condicionais em Python (if/elif/else)**](https://realpython.com/courses/python-conditional-statements/)

Dos tutoriais anteriores desta série, agora você tem bastante código Python em seu currículo. Tudo o que você viu até agora consistiu em **execução sequencial** , em que as instruções são sempre executadas uma após a outra, exatamente na ordem especificada.

Mas o mundo muitas vezes é mais complicado do que isso. Frequentemente, um programa precisa pular algumas instruções, executar uma série de instruções repetidamente ou escolher entre conjuntos alternativos de instruções para executar.

É aí que entram **as estruturas de controle** . Uma estrutura de controle direciona a ordem de execução das instruções em um programa (referida como [fluxo de controle](https://en.wikipedia.org/wiki/Control_flow) do programa ).

**Aqui está o que você aprenderá neste tutorial:** Você encontrará sua primeira estrutura de controle Python, a `if`instrução.

No mundo real, normalmente devemos avaliar as informações ao nosso redor e depois escolher um curso de ação ou outro com base no que observamos:

> Se o tempo estiver bom, cortarei a grama. (Está implícito que se o tempo não estiver bom, não cortarei a grama.)

Em um programa Python, a `if`afirmação é como você executa esse tipo de tomada de decisão. Permite a execução **condicional** de uma instrução ou grupo de instruções com base no valor de uma expressão.

O esboço deste tutorial é o seguinte:

* Primeiro, você terá uma visão geral rápida da `if`declaração em sua forma mais simples.
* A seguir, usando a `if`instrução como modelo, você verá por que as estruturas de controle exigem algum mecanismo para agrupar instruções em instruções ou blocos **compostos** . Você aprenderá como isso é feito em Python.
* Por fim, você reunirá tudo e aprenderá como escrever códigos complexos para tomada de decisões.

## Introdução à `if`Declaração

Começaremos examinando o tipo mais básico de `if`declaração. Na sua forma mais simples, fica assim:

PYTHON

```Python
if <expr>:
    <statement>
```

No formulário mostrado acima:

* `<expr>`é uma expressão avaliada em um contexto [booleano](https://realpython.com/python-boolean/) , conforme discutido na seção [Operadores Lógicos](https://realpython.com/python-operators-expressions/#logical-operators) no tutorial Operadores e Expressões em Python.
* `<statement>`é uma instrução Python válida, que deve ser indentada. (Você verá o porquê muito em breve.)

Se `<expr>`for verdadeiro (avaliado como um valor “verdadeiro”), então `<statement>`será executado. Se `<expr>`for falso, `<statement>`será ignorado e não executado.

Observe que os dois pontos ( `:`) a seguir `<expr>`são obrigatórios. Algumas linguagens de programação precisam `<expr>`ser colocadas entre parênteses, mas o Python não.

Aqui estão vários exemplos desse tipo de `if`declaração:

PYTHON

```Python
>>> x = 0
>>> y = 5

>>> if x < y:                            # Truthy
...     print('yes')
...
yes
>>> if y < x:                            # Falsy
...     print('yes')
...

>>> if x:                                # Falsy
...     print('yes')
...
>>> if y:                                # Truthy
...     print('yes')
...
yes

>>> if x or y:                           # Truthy
...     print('yes')
...
yes
>>> if x and y:                          # Falsy
...     print('yes')
...

>>> if 'aul' in 'grault':                # Truthy
...     print('yes')
...
yes
>>> if 'quux' in ['foo', 'bar', 'baz']:  # Falsy
...     print('yes')
...
```

**Nota:** Se você estiver tentando esses exemplos interativamente em uma sessão REPL, descobrirá que, ao clicar Enter após digitar a `print('yes')`instrução, nada acontece.

Como esta é uma instrução multilinha, você precisa clicar Enter uma segunda vez para informar ao intérprete que terminou com ela. Essa nova linha extra não é necessária no código executado a partir de um arquivo de script.

## Instruções de agrupamento: recuo e blocos

Até agora tudo bem.

Mas digamos que você queira avaliar uma condição e então fazer mais de uma coisa se ela for verdadeira:

> Se o tempo estiver bom, então irei:
>
> * Cortar a grama
> * Capine o jardim
> * Leve o cachorro para passear
>
> (Se o tempo não estiver bom, não farei nenhuma dessas coisas.)

Em todos os exemplos mostrados acima, cada um `if <expr>:`foi seguido por apenas um único `<statement>`. Deve haver alguma maneira de dizer “Se `<expr>`for verdade, faça todas as coisas a seguir”.

A abordagem usual adotada pela maioria das linguagens de programação é definir um dispositivo sintático que agrupe múltiplas instruções em uma **instrução** ou **bloco** composto . Um bloco é considerado sintaticamente como uma entidade única. Quando é o alvo de uma `if`instrução e `<expr>`é verdadeiro, todas as instruções do bloco são executadas. Se `<expr>`for falso, então nenhum deles é.

Praticamente todas as linguagens de programação oferecem a capacidade de definir blocos, mas nem todas oferecem isso da mesma maneira. Vamos ver como o Python faz isso.

### Python: é tudo uma questão de recuo

Python segue uma convenção conhecida como [regra do impedimento](https://en.wikipedia.org/wiki/Off-side_rule) , um termo cunhado pelo cientista da computação britânico Peter J. Landin. (O termo é retirado da lei do impedimento no futebol.) Os idiomas que aderem à regra do impedimento definem os bloqueios por recuo. Python faz parte de um conjunto relativamente pequeno de [linguagens de regras off-side](https://en.wikipedia.org/wiki/Off-side_rule#Off-side_rule_languages) .

Lembre-se do tutorial anterior sobre a estrutura do programa Python, que [o recuo tem um significado especial](https://realpython.com/python-program-structure/#whitespace-as-indentation) em um programa Python. Agora você sabe por quê: a indentação é usada para definir instruções ou blocos compostos. Em um programa Python, instruções contíguas recuadas no mesmo nível são consideradas parte do mesmo bloco.

Assim, uma `if`instrução composta em Python se parece com isto:

PYTHON

```Python
 1if <expr>:
 2    <statement>
 3    <statement>
 4    ...
 5    <statement>
 6<following_statement>
```

Aqui, todas as instruções no nível de indentação correspondente (linhas 2 a 5) são consideradas parte do mesmo bloco. O bloco inteiro é executado se `<expr>`for verdadeiro ou ignorado se `<expr>`for falso. De qualquer forma, a execução prossegue com `<following_statement>`(linha 6) posteriormente.

[![Declaração condicional Python](https://files.realpython.com/media/t.78f3bacaa261.png)](https://files.realpython.com/media/t.78f3bacaa261.png)
Instrução if composta em Python

Observe que não há nenhum token que indique o fim do bloco. Em vez disso, o final do bloco é indicado por uma linha com recuo menor que as linhas do próprio bloco.

**Nota:** Na documentação do Python, um grupo de instruções definido por indentação é frequentemente chamado de **suite** . Esta série de tutoriais usa os termos bloco e suíte de forma intercambiável.

Considere este arquivo de script `foo.py`:

PYTHON

```Python
 1 if 'foo' in ['bar', 'baz', 'qux']:
 2    print('Expression was true')
 3    print('Executing statement in suite')
 4    print('...')
 5    print('Done.')
 6 print('After conditional')
```

A execução `foo.py`produz esta saída:

Prompt de comando do Windows

```Python
C:\> python foo.py
After conditional
```

As quatro [`print()`](https://realpython.com/python-print/)declarações nas linhas 2 a 5 são recuadas no mesmo nível uma da outra. Eles constituem o bloco que seria executado se a condição fosse verdadeira. Mas é falso, então todas as declarações do bloco são ignoradas. Depois que o final da `if`instrução composta for alcançado (sejam as instruções do bloco nas linhas 2 a 5 executadas ou não), a execução prossegue para a primeira instrução com menor nível de indentação: a [`print()`](https://realpython.com/courses/python-print/)instrução na linha 6.

Os blocos podem ser aninhados em profundidade arbitrária. Cada recuo define um novo bloco e cada recuo termina o bloco anterior. A estrutura resultante é direta, consistente e intuitiva.

Aqui está um arquivo de script mais complicado chamado `blocks.py`:

PYTHON

```Python
# Does line execute?                        Yes    No
#                                           ---    --
if 'foo' in ['foo', 'bar', 'baz']:        #  x
    print('Outer condition is true')      #  x

    if 10 > 20:                           #  x
        print('Inner condition 1')        #        x

    print('Between inner conditions')     #  x

    if 10 < 20:                           #  x
        print('Inner condition 2')        #  x

    print('End of outer condition')       #  x
print('After outer condition')            #  x
```

A saída gerada quando este script é executado é mostrada abaixo:

Prompt de comando do Windows

```Python
C:\> python blocks.py
Outer condition is true
Between inner conditions
Inner condition 2
End of outer condition
After outer condition
```

**Nota:** Caso você esteja se perguntando, a regra off-side é o motivo da necessidade da nova linha extra ao inserir instruções multilinhas em uma sessão REPL. Caso contrário, o intérprete não terá como saber que a última instrução do bloco foi inserida.

### O que outras línguas fazem?

Talvez você esteja curioso para saber quais são as alternativas. Como os blocos são definidos em idiomas que não aderem à regra do impedimento?

A tática usada pela maioria das linguagens de programação é designar tokens especiais que marcam o início e o fim de um bloco. Por exemplo, em Perl os blocos são definidos com pares de chaves ( `{}`) assim:

Perl

```Python
# (This is Perl, not Python)
if(<expr>){
<statement>;
<statement>;
...
<statement>;
}
<following_statement>;
```

C/C++, [Java](https://realpython.com/oop-in-python-vs-java/) e uma série de [outras linguagens](https://en.wikipedia.org/wiki/List_of_programming_languages_by_type#Curly-bracket_languages) usam chaves dessa maneira.

[![Declaração condicional Perl](https://files.realpython.com/media/t.7dbd895afc69.png)](https://files.realpython.com/media/t.7dbd895afc69.png)
Instrução if composta em C/C++, Perl e Java

Outras linguagens, como Algol e Pascal, usam palavras-chave `begin`e `end`delimitam blocos.

### Qual é melhor?

O melhor está nos olhos de quem vê. No geral, os programadores tendem a ter uma opinião bastante forte sobre como fazem as coisas. O debate sobre os méritos da regra do impedimento pode ser bastante acalorado.

Do lado positivo:

* O uso de indentação em Python é limpo, conciso e consistente.
* Em linguagens de programação que não usam a regra off-side, o recuo do código é completamente independente da definição do bloco e da função do código. É possível escrever código recuado de uma maneira que na verdade não corresponde à forma como o código é executado, criando assim uma impressão equivocada quando uma pessoa apenas olha para ele. Esse tipo de erro é virtualmente impossível de cometer em Python.
* O uso de recuo para definir blocos força você a manter padrões de formatação de código que você provavelmente deveria usar de qualquer maneira.

Do lado negativo:

* Muitos programadores não gostam de ser forçados a fazer as coisas de uma determinada maneira. Eles tendem a ter opiniões fortes sobre o que parece bom e o que não parece, e não gostam de ser forçados a fazer uma escolha específica.
* Alguns editores inserem uma mistura de caracteres de espaço e tabulação à esquerda das linhas recuadas, o que torna difícil para o interpretador Python determinar os níveis de indentação. Por outro lado, frequentemente é possível configurar editores para não fazerem isso. Geralmente não é considerado desejável ter uma mistura de tabulações e espaços no código-fonte, independentemente do idioma.

Goste ou não, se você estiver programando em Python, estará preso à regra do impedimento. Todas as estruturas de controle em Python o utilizam, como você verá em vários tutoriais futuros.

Pelo que vale a pena, muitos programadores que estavam acostumados com linguagens com meios mais tradicionais de definição de blocos inicialmente recuaram diante do método Python, mas ficaram confortáveis com ele e até passaram a preferi-lo.

## As cláusulas `else`e `elif`

Agora você sabe como usar uma `if`instrução para executar condicionalmente uma única instrução ou um bloco de várias instruções. É hora de descobrir o que mais você pode fazer.

Às vezes, você deseja avaliar uma condição e seguir um caminho se for verdadeira, mas especificar um caminho alternativo se não for. Isso é feito com uma `else`cláusula:

PYTHON

```Python
if <expr>:
    <statement(s)>
else:
    <statement(s)>
```

Se `<expr>`for verdade, o primeiro conjunto será executado e o segundo será ignorado. Se `<expr>`for falso, o primeiro conjunto será ignorado e o segundo será executado. De qualquer forma, a execução será retomada após o segundo conjunto. Ambos os conjuntos são definidos por recuo, conforme descrito acima.

Neste exemplo, `x`é menor que `50`, então o primeiro conjunto (linhas 4 a 5) é executado e o segundo conjunto (linhas 7 a 8) é ignorado:

PYTHON

```Python
 1>>> x = 20
 2
 3>>> if x < 50:
 4...     print('(first suite)')
 5...     print('x is small')
 6... else:
 7...     print('(second suite)')
 8...     print('x is large')
 9...
10(first suite)
11x is small
```

Aqui, por outro lado, `x`é maior que `50`, então o primeiro conjunto é ignorado e o segundo conjunto é executado:

PYTHON

```Python
 1>>> x = 120
 2>>>
 3>>> if x < 50:
 4...     print('(first suite)')
 5...     print('x is small')
 6... else:
 7...     print('(second suite)')
 8...     print('x is large')
 9...
10(second suite)
11x is large
```

Também existe sintaxe para execução de ramificação baseada em diversas alternativas. Para isso, use uma ou mais cláusulas `elif`(abreviação de *else if* ). Python avalia cada um `<expr>`deles e executa o conjunto correspondente ao primeiro que for verdadeiro. Se nenhuma das expressões for verdadeira e uma `else`cláusula for especificada, então seu conjunto será executado:

PYTHON

```Python
if <expr>:
    <statement(s)>
elif <expr>:
    <statement(s)>
elif <expr>:
    <statement(s)>
    ...
else:
    <statement(s)>
```

Um número arbitrário de `elif`cláusulas pode ser especificado. A `else`cláusula é opcional. Se estiver presente, só pode haver um e deve ser especificado por último:

PYTHON

```Python
>>> name = 'Joe'
>>> if name == 'Fred':
...     print('Hello Fred')
... elif name == 'Xander':
...     print('Hello Xander')
... elif name == 'Joe':
...     print('Hello Joe')
... elif name == 'Arnold':
...     print('Hello Arnold')
... else:
...     print("I don't know who you are!")
...
Hello Joe
```

No máximo, um dos blocos de código especificados será executado. Se uma `else`cláusula não for incluída e todas as condições forem falsas, nenhum dos blocos será executado.

**Nota:** Usar uma série `if`// `elif`longa `else`pode ser um pouco deselegante, especialmente quando as ações são declarações simples como `print()`. Em muitos casos, pode haver uma maneira mais pitônica de realizar a mesma coisa.

Aqui está uma alternativa possível ao exemplo acima usando o `dict.get()`método:

PYTHON

```Python
>>> names = {
...     'Fred': 'Hello Fred',
...     'Xander': 'Hello Xander',
...     'Joe': 'Hello Joe',
...     'Arnold': 'Hello Arnold'
... }

>>> print(names.get('Joe', "I don't know who you are!"))
Hello Joe
>>> print(names.get('Rick', "I don't know who you are!"))
I don't know who you are!
```

Lembre-se do tutorial sobre dicionários Python que o [`dict.get()`](https://realpython.com/python-dicts/#built-in-dictionary-methods)método pesquisa a chave especificada em um dicionário e retorna o valor associado, se for encontrado, ou o valor padrão fornecido, se não for.

Uma `if`instrução com `elif`cláusulas utiliza avaliação de curto-circuito, análoga ao que você viu com os operadores `and` and. `or` Uma vez que uma das expressões é verdadeira e seu bloco é executado, nenhuma das expressões restantes é testada. Isso é demonstrado abaixo:

PYTHON

```Python
>>> var  # Not defined
Traceback (most recent call last):
  File "<pyshell#58>", line 1, in <module>
var
NameError: name 'var' is not defined

>>> if 'a' in 'bar':
...     print('foo')
... elif 1/0:
...     print("This won't happen")
... elif var:
...     print("This won't either")
...
foo
```

A segunda expressão contém uma divisão por zero e a terceira faz referência a uma [variável](https://realpython.com/python-variables/) `var` indefinida . Qualquer um dos dois geraria um erro, mas nenhum deles será avaliado porque a primeira condição especificada é verdadeira.

[Remover propagandas](https://realpython.com/account/join/)

## `if`Declarações de uma linha

É comum escrever `if <expr>`em uma linha e `<statement>`recuar na linha seguinte assim:

PYTHON

```Python
if <expr>:
    <statement>
```

Mas é permitido escrever uma `if`declaração inteira em uma linha. O seguinte é funcionalmente equivalente ao exemplo acima:

PYTHON

```Python
if <expr>: <statement>
```

Pode até haver mais de um `<statement>`na mesma linha, separados por ponto e vírgula:

PYTHON

```Python
if <expr>: <statement_1>; <statement_2>; ...; <statement_n>
```

Mas o que isso significa? Existem duas interpretações possíveis:

1. Se `<expr>`for verdade, execute `<statement_1>`.
   Em seguida, execute `<statement_2> ... <statement_n>`incondicionalmente, independentemente de `<expr>`ser verdadeiro ou não.
2. Se `<expr>`for verdade, execute todos os `<statement_1> ... <statement_n>`. Caso contrário, não execute nenhum deles.

Python adota a última interpretação. O ponto e vírgula que separa o `<statements>`tem maior precedência do que os dois pontos seguintes `<expr>`- no jargão da informática, diz-se que o ponto e vírgula se liga mais firmemente do que os dois pontos. Assim, os `<statements>`são tratados como um conjunto, e ou todos são executados, ou nenhum deles é:

PYTHON

```Python
>>> if 'f' in 'foo': print('1'); print('2'); print('3')
...
1
2
3
>>> if 'z' in 'foo': print('1'); print('2'); print('3')
...
```

Várias instruções também podem ser especificadas na mesma linha como uma cláusula `elif`ou :`else`

PYTHON

```Python
>>> x = 2
>>> if x == 1: print('foo'); print('bar'); print('baz')
... elif x == 2: print('qux'); print('quux')
... else: print('corge'); print('grault')
...
qux
quux

>>> x = 3
>>> if x == 1: print('foo'); print('bar'); print('baz')
... elif x == 2: print('qux'); print('quux')
... else: print('corge'); print('grault')
...
corge
grault
```

Embora tudo isso funcione, e o intérprete permita, geralmente é desencorajado, alegando que leva a uma legibilidade deficiente, especialmente para `if`declarações complexas. [O PEP 8](https://www.python.org/dev/peps/pep-0008/#other-recommendations) não recomenda especificamente isso.

Como sempre, é uma questão de gosto. A maioria das pessoas acharia o seguinte visualmente mais atraente e mais fácil de entender à primeira vista do que o exemplo acima:

PYTHON

```Python
>>> x = 3
>>> if x == 1:
...     print('foo')
...     print('bar')
...     print('baz')
... elif x == 2:
...     print('qux')
...     print('quux')
... else:
...     print('corge')
...     print('grault')
...
corge
grault
```

Porém, se uma `if`declaração for bastante simples, colocar tudo em uma linha pode ser razoável. Algo assim provavelmente não irritaria muito ninguém:

PYTHON

```Python
debugging = True  # Set to True to turn debugging on.

    .
    .
    .

if debugging: print('About to call function foo()')
foo()
```

## Expressões Condicionais (Operador Ternário do Python)

Python oferece suporte a uma entidade adicional de tomada de decisão chamada expressão condicional. (Também é referido como operador condicional ou operador ternário em vários lugares na documentação do Python.) Expressões condicionais foram propostas para adição à linguagem no [PEP 308](https://www.python.org/dev/peps/pep-0308) e receberam luz verde por Guido em 2005.

Na sua forma mais simples, a sintaxe da expressão condicional é a seguinte:

PYTHON

```Python
<expr1> if <conditional_expr> else <expr2>
```

Isto é diferente dos `if`formulários de instrução listados acima porque não é uma estrutura de controle que direciona o fluxo de execução do programa. Ele atua mais como um operador que define uma expressão. No exemplo acima, `<conditional_expr>`é avaliado primeiro. Se for verdade, a expressão será avaliada como `<expr1>`. Se for falso, a expressão será avaliada como `<expr2>`.

Observe a ordem não óbvia: a expressão do meio é avaliada primeiro e, com base nesse resultado, uma das expressões nas extremidades é retornada. Aqui estão alguns exemplos que esperamos ajudar a esclarecer:

PYTHON

```Python
>>> raining = False
>>> print("Let's go to the", 'beach' if not raining else 'library')
Let's go to the beach
>>> raining = True
>>> print("Let's go to the", 'beach' if not raining else 'library')
Let's go to the library

>>> age = 12
>>> s = 'minor' if age < 21 else 'adult'
>>> s
'minor'

>>> 'yes' if ('qux' in ['foo', 'bar', 'baz']) else 'no'
'no'
```

**Nota:** a expressão condicional do Python é semelhante à `<conditional_expr> ? <expr1> : <expr2>`sintaxe usada por muitas outras linguagens – C, Perl e Java, para citar algumas. Na verdade, o `?:`operador é comumente chamado de operador ternário nessas linguagens, o que provavelmente é o motivo pelo qual a expressão condicional do Python às vezes é chamada de operador ternário do Python.

Você pode ver no PEP 308 que a `<conditional_expr> ? <expr1> : <expr2>`sintaxe foi considerada para Python, mas acabou rejeitada em favor da sintaxe mostrada acima.

Um uso comum da expressão condicional é selecionar a atribuição de variáveis. Por exemplo, suponha que você queira encontrar o maior de dois números. Claro, existe uma função interna, [`max()`](https://realpython.com/python-min-and-max/)que faz exatamente isso (e muito mais) que você pode usar. Mas suponha que você queira escrever seu próprio código do zero.

Você poderia usar uma `if`instrução padrão com uma `else`cláusula:

PYTHON

```PYTHON
>>> if a > b:
...     m = a
... else:
...     m = b
...
```

Mas uma expressão condicional é mais curta e possivelmente mais legível também:

PYTHON

```PYTHON
>>> m = a if a > b else b
```

Lembre-se de que a expressão condicional se comporta sintaticamente como uma expressão. Pode ser usado como parte de uma expressão mais longa. A expressão condicional tem precedência mais baixa do que praticamente todos os outros operadores, portanto são necessários parênteses para agrupá-la sozinha.

No exemplo a seguir, o `+`operador se vincula com mais força do que a expressão condicional, portanto, `1 + x`e `y + 2`são avaliados primeiro, seguidos pela expressão condicional. Os parênteses no segundo caso são desnecessários e não alteram o resultado:

PYTHON

```PYTHON
>>> x = y = 40

>>> z = 1 + x if x > y else y + 2
>>> z
42

>>> z = (1 + x) if x > y else (y + 2)
>>> z
42
```

Se quiser que a expressão condicional seja avaliada primeiro, você precisará colocá-la entre parênteses de agrupamento. No próximo exemplo, `(x if x > y else y)`é avaliado primeiro. O resultado é `y`, que é `40`, então `z`é atribuído `1 + 40 + 2`= `43`:

PYTHON

```PYTHON
>>> x = y = 40

>>> z = 1 + (x if x > y else y) + 2
>>> z
43
```

Se você estiver usando uma expressão condicional como parte de uma expressão maior, provavelmente será uma boa ideia usar parênteses de agrupamento para esclarecimento, mesmo que eles não sejam necessários.

Expressões condicionais também usam [avaliação de curto-circuito](https://realpython.com/python-operators-expressions/#compound-logical-expressions-and-short-circuit-evaluation) como expressões lógicas compostas. Partes de uma expressão condicional não serão avaliadas se não for necessário.

Na expressão `<expr1> if <conditional_expr> else <expr2>`:

* Se `<conditional_expr>`for verdadeiro, `<expr1>`será retornado e `<expr2>`não será avaliado.
* Se `<conditional_expr>`for falso, `<expr2>`será retornado e `<expr1>`não será avaliado.

Como antes, você pode verificar isso usando termos que gerariam um erro:

PYTHON

```PYTHON
>>> 'foo' if True else 1/0
'foo'
>>> 1/0 if False else 'bar'
'bar'
```

Em ambos os casos, os `1/0`termos não são avaliados, portanto nenhuma exceção é levantada.

Expressões condicionais também podem ser encadeadas, como uma espécie de estrutura `if`// `elif`alternativa `else`, como mostrado aqui:

PYTHON

```PYTHON
>>> s = ('foo' if (x == 1) else
...      'bar' if (x == 2) else
...      'baz' if (x == 3) else
...      'qux' if (x == 4) else
...      'quux'
... )
>>> s
'baz'
```

Não está claro se isso tem alguma vantagem significativa sobre a instrução // correspondente , `if`mas é Python sintaticamente correto.`elif``else`

## `pass`A declaração Python

Ocasionalmente, você pode querer escrever o que é chamado de stub de código: um espaço reservado para onde você eventualmente colocará um bloco de código que ainda não implementou.

Em linguagens onde delimitadores de token são usados para definir blocos, como as chaves em Perl e C, delimitadores vazios podem ser usados para definir um stub de código. Por exemplo, o seguinte é um código Perl ou C legítimo:

Perl

```PYTHON
# This is not Python
if(x)
{
}
```

Aqui, as chaves vazias definem um bloco vazio. Perl ou C avaliarão a expressão `x`e, mesmo que seja verdadeira, não farão nada silenciosamente.

Como o Python usa recuo em vez de delimitadores, não é possível especificar um bloco vazio. Se você introduzir uma `if`instrução com `if <expr>:`, algo deverá vir depois dela, na mesma linha ou recuado na linha seguinte.

Considere este roteiro `foo.py`:

PYTHON

```PYTHON
if True:

print('foo')
```

Se você tentar executar `foo.py`, você obterá isto:

Prompt de comando do Windows

```PYTHON
C:\> python foo.py
  File "foo.py", line 3
    print('foo')
        ^
IndentationError: expected an indented block
```

A instrução [Python `pass`](https://realpython.com/python-pass/) resolve esse problema. Isso não altera em nada o comportamento do programa. Ele é usado como um espaço reservado para manter o intérprete feliz em qualquer situação onde uma declaração é sintaticamente necessária, mas você realmente não quer fazer nada:

PYTHON

```PYTHON
if True:
    pass

print('foo')
```

Agora `foo.py`é executado sem erros:

Prompt de comando do Windows

```PYTHON
C:\> python foo.py
foo
```

## Conclusão

Ao concluir este tutorial, você estará começando a escrever código Python que vai além da simples execução sequencial:

* Você conheceu o conceito de **estruturas de controle** . Estas são instruções compostas que alteram **o fluxo de controle** do programa – a ordem de execução das instruções do programa.
* Você aprendeu como agrupar instruções individuais em um **bloco** ou **conjunto** .
* Você encontrou sua primeira estrutura de controle, a **`if`**instrução, que torna possível executar **condicionalmente** uma instrução ou bloco com base na avaliação dos dados do programa.

Todos esses conceitos são cruciais para o desenvolvimento de código Python mais complexo.
