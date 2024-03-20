# Tuplas vs listas vs conjuntos em Python

Em Python, existem quatro tipos de dados integrados que podemos usar para armazenar coleções de dados. Com qualidades e características diferentes, esses tipos de dados integrados são Lista ( `list`), Tupla (tupla), Conjunto ( `set`) e Dicionário ( `dict`).

Neste artigo, vamos nos aprofundar nos detalhes de listas, tuplas e conjuntos em Python. Veremos suas diferenças e quando usar esses tipos de dados.

Como o Dicionário associa chaves aos seus respectivos valores, o que é um caso de uso muito diferente em comparação com Lista, Tupla e Conjunto (que simplesmente contêm valores), ele não fará parte desta discussão.

Para simplificar, usarei Set e Dictionary de forma intercambiável, pois são baseados em [Hash Table](https://en.wikipedia.org/wiki/Hash_table) (ou Hash Map).

![Tipos de dados integrados do Python para armazenar coleções de dados](https://res.cloudinary.com/practicaldev/image/fetch/s--IvWvy0_d--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/m19r30nxlkz7mb11dtoi.png)

Tipos de dados integrados do Python para armazenar coleções de dados

## Por que nos importamos?

Na maioria das vezes, esses tipos de dados podem ser usados de forma intercambiável em um aplicativo sem muitos problemas.

No entanto, imagine se nos fosse dada a tarefa de verificar se existe uma agulha num palheiro de tamanho considerável. Qual seria a maneira mais eficiente em termos de velocidade e memória para fazer isso?

O palheiro deveria ser uma lista? E uma tupla? Ou por que não usar sempre um Conjunto (ou um Dicionário)? Quais são as advertências que devemos observar?

Vamos cavar!

---

## Diferenças entre lista, tupla e conjunto

### Duplicatas

Se eu explicasse isso, List e Tuple são como irmãos em Python. Por outro lado, Set (ou Dicionário) é como um primo de ambos.

Ao contrário de uma lista ou tupla, um conjunto não pode conter duplicatas. Em outras palavras, os elementos de um Conjunto são únicos.

```python
set_example = {1, 1, 2, 3, 3, 3}
# {1, 2, 3}

fruit_set = {'🍎', '🍓', '🍐', '🍎', '🍎', '🍓'}
# {'🍎', '🍐', '🍓'}
```

cópia de

Com esse conhecimento em mente, sabemos agora que Set também pode ser usado para remover duplicatas de uma lista!

### Ordem de classificação

Você deve ter ouvido a afirmação “Set e Dictionary não são ordenados em Python”. Bem, isso é apenas metade da verdade hoje, dependendo de qual versão do Python você está usando.

Antes do Python 3.6, dicionários e conjuntos não mantinham sua ordem de inserção. Aqui está um exemplo se você experimentar no Python 3.5:

```python
# Example in Python 3.5

fruit_size = {} 
>>> fruit_size['🍎'] = 12 
>>> fruit_size['🍐'] = 16 
>>> fruit_size['🍇'] = 20 
>>> fruit_size
{'🍎': 12, '🍇': 20, '🍐': 16}
```

cópia de

> Você pode mudar facilmente para diferentes versões do Python usando [pyenv](https://github.com/pyenv/pyenv) . Experimente!

Hoje, essa afirmação está desatualizada há alguns anos. A partir do Python 3.7, Dictionary e Set são ordenados oficialmente no momento da inserção.

De qualquer forma, caso você esteja se perguntando, Listas e Tuplas são sequências ordenadas de objetos.

### Mutabilidade

Quando você descreve um objeto como mutável, é simplesmente uma maneira elegante de dizer que o estado interno do objeto pode ser alterado.

A principal diferença aqui é que Tuple é imutável (não mutável), enquanto List e Set são mutáveis.

Embora os conjuntos sejam mutáveis, não podemos acessar ou alterar qualquer elemento de um conjunto por meio de indexação ou fatiamento. Portanto, só podemos adicionar novos elementos a um conjunto – e não alterá-los.

Observe que o:

![[Update método](https://www.programiz.com/python-programming/methods/set/update)]

Em um Set significa simplesmente a capacidade de adicionar vários elementos de uma vez.

### Indexação

Tanto Tuple quanto List suportam indexação e fatiamento, enquanto Set não.

```python
fruit_list = ['🍎', '🍓', '🍐']
fruit_list[1]
# '🍓'

animal_tuple = ('🐶', '🐱', '🐮')
animal_tuple[2]
# '🐮'

vehicle_set = {'🚐', '🏍', '🚗'}
vehicle_set[0]
# TypeError: 'set' object is not subscriptable
```

cópia de

---

## Quando usar Lista vs. Tupla?

Como mencionamos anteriormente, as tuplas são imutáveis, enquanto as listas são mutáveis. Da mesma forma, as tuplas têm tamanho fixo por natureza, enquanto as listas são dinâmicas.

```python
a_tuple = tuple(range(1000))
a_list = list(range(1000))
a_tuple.__sizeof__()  # 8024 bytes
a_list.__sizeof__()   # 9088 bytes
```

cópia de

### Lista de usos

1. Quando você precisar alterar sua coleção.
2. Quando você precisar remover ou adicionar novos itens à sua coleção de itens.

### Usar tupla

1. Se seus dados devem ou não ser alterados.
2. Tuplas são mais rápidas que listas. Deveríamos usar uma Tupla em vez de uma Lista se estivermos definindo um conjunto constante de valores e tudo o que faremos com ele é iterá-lo.
3. Se precisarmos que um array de elementos seja usado como chaves de dicionário, podemos usar Tuplas. Como as listas são mutáveis (tipo não hash), elas nunca podem ser usadas como chaves de dicionário.

---

## Quando usar Set vs. Lista/Tupla?

Como Set usa Hash Table como estrutura de dados subjacente, Set é extremamente rápido quando se trata de verificar se um elemento está dentro dele (por exemplo, `x in a_set`).

A ideia por trás disso é que procurar um item em uma tabela hash é uma operação O(1) (tempo constante).

"Então, devo sempre usar Set ou Dictionary?"

Essencialmente, se você não precisa armazenar duplicatas, Set será melhor que List. Período.

---

## Resumo

Se você é um geek de números como eu, confira esta [comparação de velocidade entre Tuple, List e Set](https://stackoverflow.com/questions/2831212/python-sets-vs-lists/17945009#17945009) ao iterar ou verificar se um objeto está presente em uma coleção.

Quais são as principais conclusões?

* Se você precisar armazenar duplicatas, escolha Lista ou Tupla.
* Para Lista vs. Tupla, considere a mutabilidade. Se você precisa de imutabilidade, escolha Tuple.
* Se você não precisa armazenar duplicatas, opte sempre por Conjunto ou Dicionário. Os mapas hash são significativamente mais rápidos quando se trata de determinar se um objeto está presente no Conjunto (por exemplo, `x in set_or_dict`).
