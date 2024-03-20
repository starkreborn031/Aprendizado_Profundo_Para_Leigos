# Python para iniciantes: tipos de dados

Cada valor em Python possui um tipo de dados. É importante conhecer esses tipos de dados e neste post descobriremos o que significam esses tipos de dados.

![Imagem em destaque para: Python para iniciantes: tipos de dados] [def]

 Até agora, suas aventuras com Python giraram em torno de criar coisas. Havia um objetivo, um pequeno aplicativo que você pudesse usar para aprender os meandros da programação básica em Python. É aí que está a diversão. Mas às vezes é preciso dar um passo atrás para seguir em frente. Quando chegar a hora, saiba que você terá que absorver alguns dos aspectos mais chatos da programação. E é aí que nos encontramos agora. Esta etapa é importante porque há certos aspectos da programação que você deve compreender para tirar o máximo proveito dela e entender verdadeiramente o que está fazendo.

Um aspecto do Python que você deve entender são os tipos de dados.

## Quais são os tipos de dados?

Como você provavelmente suspeita, um tipo de dados é um tipo de dados. Mas é um pouco mais profundo do que isso. Quão profundo? Um tipo de dados não é apenas uma categoria de dados, mas também informa quais operações podem ser executadas em um determinado conjunto de dados.

Você já aprendeu como usar variáveis como:

| 1   | **x** = **int.**(**input**(**"Type a number to start the range:"**)) |
| --- | -------------------------------------------------------------------- |
|     |                                                                      |

A instrução acima define a variável x como um número inteiro da entrada obtida de um usuário. Nesse caso, a variável x armazenará um número inteiro que é um tipo de dados específico. Por ser armazenado como um tipo de dados específico, o Python saberá o que pode ser feito com ele. Sem tipos de dados em jogo, você poderia definir uma variável, mas o Python não saberia o que fazer com ela. Por exemplo, se você não tivesse tipos de dados, você poderia definir x = 2 e y = 10, mas se você tentasse adicioná-los com uma função, o Python não saberia que eram números, então não seria capaz para fazer o cálculo.

É por isso que os tipos de dados são importantes.

Python possui alguns tipos de dados integrados. Um pouco de confusão é que você encontrará listas diferentes para esses tipos (portanto, parece não haver nenhum tipo de acordo sobre o que incluir nesta lista ou como chamar os tipos). No entanto, iremos com a seguinte lista (porque é a que mais parece concordar):

* Numérico
* Sequência
* Definir
* Dicionário
* booleano

Alguns desses tipos incluem diferentes “subtipos” (mais sobre isso em breve). E então, quais são os diferentes tipos de dados? Vamos descobrir.

## Numérico

Este é provavelmente o mais fácil de entender porque todos sabemos o que são números. Um tipo de dados numérico é, bem, um número. Em Python, os tipos de dados numéricos podem ser inteiros, números flutuantes ou números complexos.

Pronto para retornar à matemática elementar?

Um **número inteiro** (representado como uma classe por *int* ) é um número inteiro positivo ou negativo, como -1, 2, 3, 4, -10, 20, 3.000 ou 40.000. Os números inteiros não têm ponto decimal e não há limite para o tamanho de um número inteiro. Também é importante entender que Python não permite que a vírgula seja usada como delimitador numérico. Em vez disso, você usa o sublinhado. Para entender isso, faça Acesso no console Python com o comando:

`python3`

No console, digite:

`x=int(867_5309)`

A seguir, digite:

`print(x)`

Você deveria ver:

`8675309`

Você pode deixar de fora a parte *int* porque o Python detectará automaticamente que o número é um inteiro (o mesmo vale para outros tipos de dados).

Um número de classe **flutuante** inclui um ponto decimal e pode ser negativo ou positivo e pode até ser representado por notação científica. Portanto, um número flutuante pode ser -1,5, 3,14159, 30,2 ou 100,7. Ao contrário do inteiro, float tem um tamanho máximo, que é conhecido como *inf* (que significa infinito). Aqui está um exemplo. A notação científica “e” significa “10 elevado a”. Então, se definirmos um valor flutuante de 10e100 (que é 10.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000.000, 000 ,000.000.000.000.000.000.000.000 ou 1e+100) com o comando:

`x=10e100`

Poderíamos ver esse valor com:

`print(x)`

Python reportaria:

`1e+100`

No entanto, se definíssemos x como 10e400, o Python reportaria:

`inf`

Por que? Porque o valor estava além do tamanho máximo que pode armazenar.

Um **número complexo** é uma combinação de um número real e um número imaginário, representado pela classe complexa. Um número complexo pode ser algo como 10*2x. Defina essa variável com;

`a=10+3j`

Se então emitirmos:

`print(a)`

Veremos:

`(10+3j)`

## Sequência

Uma sequência é simples porque é uma sequência ordenada de caracteres. Por exemplo, você poderia definir x com a seguinte instrução:

`x=str("Hello, New Stack")`

Digite `print(x)`e Python apresentará:

`Hello, New Stack`

O tipo de dados de sequência inclui strings (uma sequência de caracteres), lista (valores separados por vírgula que podem ser alterados) e tupla (valores separados por vírgula que não podem ser alterados). Outra diferença entre tuplas e listas é que as tuplas usam (), enquanto as listas usam []. Já discutimos [listas em Python][def2] , então leia esse tutorial para entender melhor esse conceito.

## Definir

Um conjunto é uma coleção não ordenada de dados iterável (capaz de retornar seus membros um de cada vez), mutável (o valor pode ser alterado) e não possui elementos duplicados. Os conjuntos são delimitados por vírgulas e colocados entre colchetes. Um conjunto pode ser uma mistura de valores numéricos e de string. Por exemplo, emita o comando (no console Python);

`x={1,2,3,4,5, "New Stack"}`

Se você emitir:

`print(x)`

Python irá imprimir:

`1,2,3,4,5, 'New Stack'`

Uma característica muito importante dos conjuntos é que podemos realizar uniões e interseções. Por exemplo, definiremos x e y como tal:

`x = {"Hello"}y = {"New Stack"}`

Faremos então uma união (unindo os dois) com:

`print(x|y)`

Python irá imprimir:

`{'Hello', 'New Stack'}`

## Dicionário

O tipo de dados de dicionário é o tipo mais flexível que o Python tem a oferecer, pois pode ser usado para armazenar grandes quantidades de dados. Este tipo é uma coleção não ordenada de valores de dados armazenados em pares de valores-chave.

Um aspecto muito útil desse tipo é a capacidade de usar chaves e valores. Aqui está um exemplo simples. Os dicionários são configurados assim:

`{key : value, key : key : value, key : value}`

Deixe-me explicar através de um exemplo. No console Python, digite o seguinte:

| 12345 | **dict** = {**"name"**: **"Jack Wallen"**,**"client"**: **"The New Stack"****"subject"**: **"Python"**} |
| ----- | ------------------------------------------------------------------------------------------------------------------------------------------- |

Com o exposto acima, criamos um dicionário com os pares chave-valor:

* Nome: Jack Wallen
* cliente: A Nova Pilha
* assunto Python

Imprima o dicionário com:

`print(dict)`

A saída seria:

`{'name': 'Jack Wallen', 'client': 'The New Stack', 'subject': 'Python'}`

Agora, e se quiséssemos apenas visualizar o cliente? Para isso, digite:

`print(dict["client"])`

A saída seria:

`The New Stack`

## booleano

Um booleano é uma simples afirmação verdadeira ou falsa, que já discutimos detalhadamente em
[Python para Iniciantes: E/ou Operadores.][def3] Aqui estão alguns exemplos simples de booleanos:

`print(10 > 5)`

O acima irá imprimir *True* .

No entanto, se emitirmos o comando:

`print(5 > 10)`

Python imprimirá *False.*

## Conclusão

E essa é a sua introdução aos tipos de dados. É importante entender esse conceito à medida que você continua sua jornada com Python. Conhecer os fundamentos de uma linguagem de programação é uma maneira infalível de ajudar a garantir uma educação bem-sucedida. E embora você nunca pense conscientemente sobre os tipos de dados, você os usará com cada aplicativo Python que criar.

[def]: https://cdn.thenewstack.io/media/2022/01/42dfb0af-python_1846209262.png
[def2]: https://thenewstack.io/python-for-beginners-lists/
[def3]: https://thenewstack.io/python-for-beginners-and-or-operators/
