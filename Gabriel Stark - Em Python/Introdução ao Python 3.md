# ![Introdução ao Python 3](https://files.realpython.com/media/Introduction-to-Python-3_Watermarked.9d8dfef30c96.jpg)

**Python** é uma linguagem de script interpretada de alto nível desenvolvida no final da década de 1980 por Guido van Rossum no Instituto Nacional de Pesquisa em Matemática e Ciência da Computação na Holanda. A versão inicial foi publicada no [grupo de notícias](https://en.wikipedia.org/wiki/Usenet) alt.sources em 1991, e a versão 1.0 foi lançada em 1994.

Python 2.0 foi lançado em 2000, e as versões 2.x foram os lançamentos predominantes até dezembro de 2008. Naquela época, a equipe de desenvolvimento tomou a decisão de lançar a versão 3.0, que continha algumas mudanças relativamente pequenas, mas significativas, que não eram compatíveis com versões anteriores. com as versões 2.x. Python 2 e 3 são muito semelhantes e alguns recursos do Python 3 foram transferidos para o Python 2. Mas, em geral, eles permanecem não totalmente compatíveis.

Tanto o Python 2 quanto o 3 continuaram a ser mantidos e desenvolvidos, com atualizações periódicas de lançamento para ambos. No momento em que este livro foi escrito, as versões mais recentes disponíveis eram 2.7.15 e 3.6.5. No entanto, uma [data oficial de fim da vida útil de 1º de janeiro de 2020](https://pythonclock.org/) foi estabelecida para Python 2, após o qual ela não será mais mantida. Se você é um iniciante em Python, é recomendável que você se concentre em Python 3, como este tutorial fará.

Python ainda é mantido por uma equipe central de desenvolvimento do Instituto, e Guido ainda está no comando, tendo recebido o título de BDFL (Benevolent Dictator For Life) pela comunidade Python. O nome Python, aliás, não deriva da cobra, mas da trupe de comédia britânica [Monty Python&#39;s Flying Circus](https://en.wikipedia.org/wiki/Monty_Python%27s_Flying_Circus) , da qual Guido era, e provavelmente ainda é, fã. É comum encontrar referências a esquetes e filmes do Monty Python espalhados pela documentação do Python.

**Download grátis de PDF:** [Folha de referências do Python 3](https://realpython.com/bonus/python-cheat-sheet-short/)

## Por que escolher Python?

Se você pretende escrever programas, existem literalmente dezenas de linguagens comumente usadas para você escolher. Por que escolher Python? Aqui estão alguns dos recursos que tornam o Python uma escolha atraente.

### Python é popular

Python tem crescido em popularidade nos últimos anos. A [pesquisa de desenvolvedores Stack Overflow](https://insights.stackoverflow.com/survey/2018) de 2018 classificou o Python como a 7ª tecnologia mais popular e a mais procurada do ano. [Empresas de desenvolvimento de software de classe mundial em todo o mundo usam Python todos os dias.](https://realpython.com/world-class-companies-using-python/)

De acordo com [a pesquisa da Dice,](https://insights.dice.com/2016/02/01/whats-hot-and-not-in-tech-skills/) Python também é uma das habilidades mais interessantes e a linguagem de programação mais popular do mundo, com base no [Índice de Popularidade de Linguagem de Programação](https://pypl.github.io/PYPL.html) .

Devido à popularidade e ao amplo uso do Python como linguagem de programação, os desenvolvedores do Python são procurados e bem pagos. Se quiser se aprofundar nas [estatísticas salariais e oportunidades de emprego do Python, você pode fazê-lo aqui](https://dbader.org/blog/why-learn-python) .

### Python é interpretado

Muitas linguagens são compiladas, o que significa que o código-fonte que você cria precisa ser traduzido em código de máquina, a linguagem do processador do seu computador, antes de poder ser executado. Os programas escritos em uma linguagem interpretada são passados diretamente para um intérprete que os executa diretamente.

Isso torna o ciclo de desenvolvimento mais rápido porque você apenas digita seu código e executa-o, sem a etapa intermediária de compilação.

Uma desvantagem potencial das linguagens interpretadas é a velocidade de execução. Os programas compilados na linguagem nativa do processador do computador tendem a ser executados mais rapidamente do que os programas interpretados. Para alguns aplicativos que são particularmente intensivos em termos computacionais, como processamento gráfico ou processamento intenso de números, isso pode ser limitante.

Na prática, entretanto, para a maioria dos programas, a diferença na velocidade de execução é medida em milissegundos, ou segundos no máximo, e não é perceptível para um usuário humano. A conveniência da codificação em uma linguagem interpretada normalmente vale a pena para a maioria das aplicações.

**Leitura adicional:** Consulte [esta página da Wikipedia](https://en.wikipedia.org/wiki/Interpreted_language) para ler mais sobre as diferenças entre linguagens interpretadas e compiladas.

### Python é grátis

O interpretador Python é desenvolvido sob uma licença de código aberto aprovada pela OSI, tornando-o gratuito para instalação, uso e distribuição, mesmo para fins comerciais.

Uma versão do interpretador está disponível para praticamente qualquer plataforma existente, incluindo todos os tipos de Unix, Windows, macOS, smartphones e tablets e provavelmente qualquer outra coisa que você já tenha ouvido falar. Existe até uma versão para meia dúzia de pessoas restantes que usam o OS/2.

### Python é portátil

Como o código Python é interpretado e não compilado em instruções de máquina nativas, o código escrito para uma plataforma funcionará em qualquer outra plataforma que tenha o interpretador Python instalado. (Isso se aplica a qualquer linguagem interpretada, não apenas ao Python.)

### Python é simples

No que diz respeito às linguagens de programação, o Python é relativamente organizado e os desenvolvedores o mantiveram deliberadamente assim.

Uma estimativa aproximada da complexidade de um idioma pode ser obtida a partir do número de palavras-chave ou palavras reservadas no idioma. Estas são palavras reservadas para um significado especial pelo compilador ou intérprete porque designam funcionalidades internas específicas da linguagem.

Python 3 tem 33 [palavras-chave](https://realpython.com/python-keywords/) e Python 2 tem 31. Por outro lado, C++ tem 62, Java tem 53 e Visual Basic tem mais de 120, embora esses últimos exemplos provavelmente variem um pouco de acordo com a implementação ou o dialeto.

O código Python tem uma estrutura simples e limpa, fácil de aprender e ler. Na verdade, como você verá, a definição da linguagem impõe uma estrutura de código fácil de ler.

[Remover propagandas](https://realpython.com/account/join/)

### Mas não é tão simples

Apesar de toda a sua simplicidade sintática, Python suporta a maioria das construções que seriam esperadas em uma linguagem de altíssimo nível, incluindo tipos de dados dinâmicos complexos, programação estruturada e funcional e [programação orientada a objetos](https://realpython.com/python3-object-oriented-programming/) .

Além disso, está disponível uma biblioteca muito extensa de classes e funções que fornece recursos muito além do que está embutido na linguagem, como manipulação de banco de dados ou programação GUI.

Python realiza o que muitas linguagens de programação não conseguem: a linguagem em si é projetada de forma simples, mas é muito versátil em termos do que você pode realizar com ela.

## Conclusão

Esta seção forneceu uma visão geral da linguagem de programação **Python** , incluindo:

* Uma breve história do desenvolvimento do Python
* Alguns motivos pelos quais você pode selecionar Python como sua linguagem preferida

Python é uma ótima opção, seja você um programador iniciante procurando aprender o básico, um programador experiente projetando um aplicativo grande ou qualquer outro lugar. Os fundamentos do Python são facilmente compreendidos e, ainda assim, seus recursos são vastos.
