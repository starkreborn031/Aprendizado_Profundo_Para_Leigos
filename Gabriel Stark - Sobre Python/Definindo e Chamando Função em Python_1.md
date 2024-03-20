# Funções Python – Como definir e chamar uma função

![Funções Python – Como definir e chamar uma função](https://www.freecodecamp.org/news/content/images/size/w2000/2022/03/functions.png)

Na programação, uma função é um bloco de código reutilizável que executa uma determinada funcionalidade quando é chamada.

As funções são partes integrantes de toda linguagem de programação porque ajudam a tornar seu código mais modular e reutilizável.

Neste artigo, mostrarei como definir uma função em Python e chamá-la, para que você possa dividir o código de seus aplicativos Python em partes menores.

Também mostrarei como os argumentos e a palavra-chave return funcionam nas funções Python.

## Sintaxe básica para definir uma função em Python

Em Python, você define uma função com a `def`palavra-chave e, em seguida, escreve o identificador da função (nome) seguido de parênteses e dois pontos.

A próxima coisa que você precisa fazer é recuar com uma tabulação ou 4 espaços e, em seguida, especificar o que deseja que a função faça por você.

```py
def functionName():
    # What to make the function do
```

## Exemplos básicos de uma função em Python

Seguindo a sintaxe básica acima, um exemplo de função básica do Python imprimindo “Hello World” no terminal é assim:

```py
def myfunction():
    print("Hello World")
```

**Para chamar esta função** , escreva o nome da função seguido de parênteses:

```py
myfunction()

```

Em seguida, execute seu código no terminal digitando `python filename.py` para mostrar o que você deseja que a função faça:

![sss-1](https://www.freecodecamp.org/news/content/images/2022/03/sss-1.png)

Outro exemplo básico de subtração de 2 números é assim:

```py
def subtractNum():
    print(34 - 4)

subtractNum()
# Output: 30
```

## Argumentos em funções Python

Ao definir uma função em Python, você pode passar argumentos para a função colocando-os entre parênteses.

A sintaxe básica para fazer isso é mostrada abaixo:

```py
def functionName(arg1, arg2):
    # What to do with function
  
```

Quando a função é chamada, você precisa especificar um valor para os argumentos:

```py
functionName(valueForArg1, valueForArg2)
```

Aqui está um exemplo de argumentos em uma função Python:

```py
def addNum(num1, num2):
    print(num1 + num2)
addNum(2, 4)

# Output: 6
```

No exemplo acima:

* Passei 2 argumentos para a função chamada `addNum`
* Eu disse para imprimir a soma dos 2 argumentos no terminal
* Em seguida, chamei-o com os valores dos 2 argumentos especificados

**NB** : Você pode especificar quantos argumentos desejar.

## Como usar a palavra-chave Return em Python

Em Python, você pode usar a `return`palavra-chave para sair de uma função e voltar para onde foi chamada. Ou seja, envie algo fora da função.

A instrução return pode conter uma expressão a ser executada assim que a função for chamada.

O exemplo abaixo demonstra como a palavra-chave return funciona em Python:

```py
def multiplyNum(num1):
    return num1 * 8

result = multiplyNum(8)
print(result)

# Output: 64
```

**O que o código acima está fazendo?**

* Eu defini uma função chamada `multiplyNum`e a passei `num1`como argumento
* Dentro da função, usei a palavra-chave return para especificar que quero `num1`ser multiplicado por 8
* Depois disso, chamei a função, passei `8`para ela como o valor do `num1`argumento e atribuí a chamada da função a uma variável que nomeei `result`
* Com a variável resultado, consegui imprimir no terminal o que pretendia fazer com a função

## Conclusão

Neste artigo, você aprendeu como definir e chamar funções em Python. Você também aprendeu como passar argumentos para uma função e usar a palavra-chave return, para poder ser mais criativo com as funções que escreve.

Se você achar este artigo útil, não hesite em compartilhá-lo com seus amigos e familiares.
