# O que é a instrução If do Python?

**A instrução if do Python** é usada para operações de tomada de decisão. Ele contém um corpo de código que é executado somente quando a condição fornecida na instrução if for verdadeira. Se a condição for falsa, a instrução else opcional será executada, contendo algum código para a condição else.

Quando você deseja justificar uma condição enquanto a outra não é verdadeira, você usa a instrução if else do Python.

## Sintaxe da instrução if do Python

    **Fluxograma if…else do Python**

[![Declaração If do Python](https://www.guru99.com/images/2013/04/if_then_flowchart.png)](https://www.guru99.com/images/2013/04/if_then_flowchart.png)

Vamos ver um exemplo de instrução if else em Python:

[![Declaração If do Python](https://www.guru99.com/images/Pythonnew/Python11.1.png)](https://www.guru99.com/images/Pythonnew/Python11.1.png)

* Linha de código 5: definimos duas variáveis x, y = 2, 8
* Linha de código 7: a instrução if em Python verifica a condição x<y, que é **verdadeira** neste caso
* Linha de código 8: A variável st é definida como “x é menor que y”.
* Linha de código 9: A linha print st produzirá o valor da variável st que é “x é menor que y”,

## O que acontece quando “se a condição” não for atendida

Nesta etapa, veremos o que acontece quando a condição if em Python não é atendida.

[![Quando se a condição não for atendida](https://www.guru99.com/images/Pythonnew/Python11.2.png)](https://www.guru99.com/images/Pythonnew/Python11.2.png)

* Linha de código 5: definimos duas variáveis x, y = 8, 4
* Linha de código 7: a instrução if em Python verifica a condição x<y, que é **falsa** neste caso
* Linha de código 8: A variável st **NÃO** está definida como “x é menor que y”.
* Linha de código 9: A linha print st – está tentando imprimir o valor de uma variável que nunca foi declarada. Portanto, obtemos um erro.

## Como usar a “condição else”

A “condição else” geralmente é usada quando você tem que julgar uma afirmação com base em outra. Se uma condição der errado, então deverá haver outra condição que justifique a afirmação ou lógica.

**Exemplo** :

[![Como usar a condição else](https://www.guru99.com/images/Pythonnew/Python11.3.png)](https://www.guru99.com/images/Pythonnew/Python11.3.png)

* Linha de código 5: definimos duas variáveis x, y = 8, 4
* Linha de código 7: a instrução if em Python verifica a condição x<y, que é **falsa** neste caso
* Linha de código 9: O fluxo de controle do programa vai para a condição else
* Linha de código 10: A variável st é definida como “x é **maior** que y”.
* Linha de código 11: A linha print st produzirá o valor da variável st que é “x é maior que y”,

## Quando “outra condição” não funciona

Pode haver muitos casos em que sua “condição else” não fornecerá o resultado desejado. Irá imprimir o resultado errado porque há um erro na lógica do programa. Na maioria dos casos, isso acontece quando você precisa justificar mais de duas declarações ou condições em um programa.

Um **exemplo** ajudará você a entender melhor esse conceito.

Aqui ambas as variáveis são iguais (8,8) e a saída do programa é **“x é maior que y”,** o que é **ERRADO** . Isso ocorre porque ele verifica a primeira condição (se a condição em Python) e, se falhar, imprime a segunda condição (outra condição) como padrão. Na próxima etapa, veremos como podemos corrigir esse erro.

[![Quando mais a condição não funciona](https://www.guru99.com/images/Pythonnew/Python11.4.png)](https://www.guru99.com/images/Pythonnew/Python11.4.png)

## Como usar a condição “elif”

Para corrigir o erro anterior cometido pela “condição else”, podemos usar a instrução **“elif”** . Ao usar a condição “ **elif** ”, você está dizendo ao programa para imprimir a terceira condição ou possibilidade quando a outra condição der errado ou incorreta.

    **Exemplo**

[![Como usar a condição Elif](https://www.guru99.com/images/Pythonnew/Python11.5.jpg)](https://www.guru99.com/images/Pythonnew/Python11.5.jpg)

* Linha de código 5: definimos duas variáveis x, y = 8, 8
* Linha de código 7: a instrução if verifica a condição x<y, que é **falsa** neste caso
* Linha de código 10: O fluxo de controle do programa vai para a condição elseif. Ele verifica se x==y o que é verdade
* Linha de código 11: A variável st é definida como “x é **igual a** y”.
* Linha de código 15: O **fluxo de controle do programa sai da instrução if (não chegará à instrução else).** E imprima a variável st. A saída é “x é igual a y”, o que está correto

## Como executar instrução condicional com código mínimo

Nesta etapa, veremos como podemos condensar a declaração condicional. Em vez de executar o código para cada condição separadamente, podemos usá-los com um único código.

Sintaxe

    **Exemplo**

[![executar instrução condicional com código mínimo](https://www.guru99.com/images/Pythonnew/Python11.6.jpg)](https://www.guru99.com/images/Pythonnew/Python11.6.jpg)

* Linha de código 2: definimos duas variáveis x, y = 10, 8
* Linha de código 3: A variável st é definida como “x é menor que y” se x<y ou então é definida como “x é maior ou igual a y”. Nesta variável x>y, st é definido como **“x é maior ou igual a y”.**
* Linha de código 4: imprime o valor de st e fornece a saída correta
* Em vez de escrever código longo para instruções condicionais, Python oferece a liberdade de escrever código de forma curta e concisa.

## Instrução if aninhada em Python

O exemplo a seguir demonstra a instrução if aninhada Python

## Instrução Switch Case em Python

**O que é a declaração Switch?**

Uma instrução switch é uma instrução de ramificação multidirecional que compara o valor de uma variável com os valores especificados nas instruções case.

A linguagem Python não possui uma instrução switch.

[Python usa](https://www.guru99.com/python-dictionary-beginners-tutorial.html) mapeamento de dicionário para implementar Switch Case em Python

## Resumo

Uma instrução condicional em Python é tratada por instruções if e vimos várias outras maneiras de usar instruções condicionais como Python if else aqui.

* “if condição” - É usado quando você precisa imprimir o resultado quando uma das condições é verdadeira ou falsa.
* “outra condição” - é usado quando você deseja imprimir a declaração quando sua única condição não atende ao requisito
* “condição elif” – É usado quando você tem uma terceira possibilidade como resultado. Você pode usar várias condições Elif para verificar a 4ª ^,^ 5ª ^,^ 6ª ^possibilidades^ em seu código
* Podemos usar código mínimo para executar instruções condicionais, declarando todas as condições em uma única instrução para executar o código
* A instrução Python If pode ser aninhada
