# 0.1 Autômatos, Computabilidade e Complexidade

- **Teoria da complexidade**: objetivo é classificar os problemas como fáceis e difíceis. A questão central é "*O que faz alguns problemas computacionalmente difíceis e outros fáceis?*".
- **Teoria da computabilidade**: o objetivo é classificar os problemas como solúveis e insolúveis. Kurt Gödel, Alan Turing e Alonzo Church descobriram que certos problemas básicos não podiam ser resolvidos por computadores. Um exemplo desse fenômeno é o problema de se determinar se um enunciado matemático é verdadeiro ou falso. Entre as consequências desse resultado profundo estava o desenvolvimento de ideias concernentes a modelos teóricos de computadores que, em algum momento, ajudariam a levar à construção de computadores reais.
- **Teoria dos autômatos**: lida com as definições e propriedades de modelos matemáticos de computação. Esses modelos desempenham um papel em diversas áreas aplicadas da ciência da computação.

# 0.2 Noções e Terminologia Matemáticas

## Conjuntos

## Sequências e Uplas

- **Sequência**: uma sequência de objetos é uma lista desses objetos na mesma ordem. Geralmente designamos uma sequência escrevendo a lista entre parênteses. Por exemplo, a sequência 7, 21, 57 seria escrita como (7, 21, 57). (**ORDEM E REPETIÇÕES IMPORTAM**).
- **Uplas**: sequências finitas. Uma sequência com *k* elementos é uma **k-upla**.

## Funções e Relações

- **Funções**: objeto que estabelece um relacionamento de entrada-saída. 
	- Conjunto de entradas é o **domínio**, já o as saídas vem de um conjunto denominado **contradomínio**. 
	- Uma função com **k** argumentos é denominada **função k-ária**, e k é chamada a **aridade** da função. 
	- **Predicado** ou **propriedade** é uma função cujo contradomínio é { VERDADEIRO, FALSO }. 
	- Uma propriedade cujo domínio é um conjunto de k-uplas A x ... x A é chamada **relação**, **relação k-ária**. Um caso comum é uma relação 2-ária, denominada uma **relação binária**. 
	- Um tipo especial de relação binária, chamada de **relação de equivalência**, captura a noção de dois objetos serem iguais com respeito a alguma característica. Uma relação binária R é uma relação de equivalência se R satisfazer três condições.
		1. R é **reflexiva**, se para todo x, xRx;
		2. R é **simétrica**, se para todo x e y, xRy implica yRx; e
		3. R é **transitiva**, se para toxo x, y, e z, xRy e yRz implica xRz.

## Grafos

## Cadeias e Linguagens

- Cadeias de caracteres são blocos básicos fundamentais em ciência da computação. O alfabeto sobre o qual as cadeias são definidas pode variar com a aplicação. Para nossos propósitos, definimos um **alfabeto** como podendo ser qualquer conjunto finito não vazio. Os membros do alfabeto são os **símbolos** do alfabeto. 
- Uma **cadeia sobre um alfabeto** é uma sequência finita de símbolos daquele alfabeto, geralmente escritos um seguido do outro e não separados por vírgulas. 
- Se *w* é uma cadeia sobre Σ, o **comprimento** de *w*, escrito |w|, é o número de símbolos que ela contém. A cadeia de comprimento zero é chamada **cadeia vazia** e é escrita ε. (desempenha o papel do 0 em um sistema numérico).
- A **ordenação lexicográfica** de cadeias é a mesma que a ordenação familiar do dicionário, exceto que as cadeias mais curtas precedem as cadeias mais longas. Por conseguinte, a ordenação lexicográfica de todas as cadeias sobre o alfabeto {0, 1} é (ε, 0, 1, 00, 01, 10, 11, 000, ...).
- Uma **linguagem** é um conjunto de cadeias.

## Lógica Booleana

## Resumo dos Termos Matemáticos

- **Alfabeto**: um conjunto finito de objetos chamados símbolos;
- **Aresta**: uma linha em um grafo;
- **Argumento**: uma entrada para uma função;
- **Árvore**: um grafo conexo sem ciclos simples;
- **Cadeia**: uma lista finita de símbolos de um alfabeto;
- **Cadeia vazia**: a cadeia de comprimento zero;
- **Caminho**: uma sequência de nós em um grafo conectados por arestas;
- **Caminho simples**: um caminho sem repetição;
- **Ciclo**: um caminho que começa e termina no mesmo nó;
- **Complemento**: uma operação sobre um conjunto, formando o conjunto de todos os elementos não presentes;
- **Concatenação**: uma operação que junta cadeias de um conjunto, com cadeias de um outro conjunto.
- **Conjunção**: operação booleana E;
- **Conjunto**: um grupo de objetos;
- **Conjunto vazio**: o conjunto sem membros;
- **Contradomínio**: o conjunto do qual as saídas de uma função são retiradas;
- **Disjunção**: operação booleana OU;
- **Domínio**: o conjunto de possíveis entradas para um função;
- **Elemento**: um objeto em um conjunto;
- **Função**: uma operação que traduz entradas em saídas;
- **Grafo**: uma coleção de pontos e linhas conectando alguns pares de pontos;
- **Grafo conexo**: um grafo com caminhos conectando cada dois nós;
- **Grafo direcionado**: uma coleção de pontos e setas conectando alguns pares de pontos;
- **Interseção**: uma operação sobre conjuntos formando o conjunto de elementos comuns;
- ***k*-upla**: uma lista de *k* objetos;
- **Linguagem**: um conjunto de cadeias;
- **Membro**: um objeto em um conjunto;
- **Nó**: um ponto em um grafo;
- **Operação booleana:** uma operação sobre valores booleanos;
- **Par**: uma lista de dois elementos, também chamada 2-upla;
- **Predicado**: uma função cujo contradomínio é { VERDADEIRO, FALSO };
- **Produto cartesiano**: uma operação sobre conjuntos formando um conjunto de todas as uplas de elementos dos respectivos conjuntos;
- **Propriedade**: um predicado;
- **Relação**: um predicado, mais tipicamente quando o domínio é um conjunto de k-uplas;
- **Relação binária**: uma relação cujo domínio é um conjunto de pares;
- **Relação de equivalência**: uma relação binária que é reflexiva, simétrica e transitiva;
- **Sequência**: uma lista de objetos;
- **Símbolo**: um membro de um alfabeto;
- **União**: uma operação sobre conjuntos combinando todos os elementos em um único conjunto;
- **Valor booleano**: os valores VERDADEIRO ou FALSO, frequentemente representados por 1 ou 0;
- **Vértice**: um ponto em um grafo;

# 0.3 Definições, Teoremas e Provas

"Os teoremas ea as provas são o coração e a alma da matemática, e as definições são seu espírito. Essas três entidades são centrais para todo assunto matemático, incluindo o nosso."

- **Definições**: descrevem os objetos e noções que usamos. Uma definição pode ser simples ou complexa. Precisão é essencial a qualquer definição matemática. Ao definir algum objeto temos que deixar claro o que constitui aquele objeto e o que não constitui.
- **Enunciados matemáticos**: expressa que algum objeto tem uma certa propriedade. Pode ser verdadeiro ou falso, mas deve ser, obrigatoriamente, preciso, não havendo nenhuma ambiguidade sobre seu significado.
- **Prova**: argumento lógico convincente de que um enunciado é verdadeiro.
- **Teorema**: enunciado matemático demonstrado como verdadeiro. Geralmente reservamos o uso dessa palavra para os enunciados de especial interesse.
	- Ocasionalmente provamos enunciados que são interessantes somente porque ajudam na prova de outro enunciado mais significativo. Esses enunciados são chamados de **lemas**.
	- Ocasionalmente um teorema ou sua prova podem nos permitir concluir facilmente que outros enunciados relacionados são verdadeiros. Esses enunciados são denominados **corolários** do teorema.

## Encontrado Provas

Não há fórmula secreta. Aqui estão algumas dicas:

- Leia cuidadosamente o enunciado, você entende toda a notação? Reescreva-o com suas palavras.
- Decomponha-o em partes e considere cada parte separadamente.
- Em enunciados de "P se e somente se Q", é necessário provar as duas partes, a **direção de ida**: P => Q; e a **direção reversa**: Q => P.
- Em enunciados que afirmam que dois conjuntos A e B são iguais. A primeira parte afirma que A é um subconjunto de B, e a segunda parte afirma que B é um subconjunto de A.
- Experimentar com exemplos é útil. Assim, se o enunciado diz que todos os objetos de um certo tipo têm uma propriedade específica, escolha alguns objetos daquele tipo e observe se eles têm mesmo aquela propriedade. Após fazer isso, tente encontrar um objeto que falha em ter a propriedade, chamado **contra-exemplo**. Obs: se o enunciado for de fato verdadeiro, você não achará um **contra-exemplo**.

# 0.4 Tipos de Prova

Vários tipos de argumentos surgem frequentemente em provas matemáticas. Aqui, descrevemos alguns que normalmente ocorrem na teoria da computação. Note que uma prova pode conter mais que um tipo de argumento, porque pode conter várias subprovas diferentes.

- **Prova por Construção**: muitos teoremas enunciam que um tipo particular de objeto existe. Uma maneira de provar um teorema desse é demonstrar como construir o objeto.
- **Prova por Contradição**: é uma forma comum de argumento para se provar um teorema, assumimos que o teorema é falso e em seguida mostramos que essa suposição leva a uma consequência obviamente falsa, chamada de contradição. Usamos esse tipo de raciocínio frequentemente no cotidiano.
- **Prova por Indução**: método avançado usado para mostrar que todos os elementos de um conjunto infinito têm uma propriedade especificada. Por exemplo, podemos usar uma prova por indução para mostrar que uma expressão aritmética computa uma quantidade desejada para toda atribuição a suas variáveis ou que um programa funciona corretamente em todos os passos ou para todas as entradas.
	- Toda prova por indução é constituída de duas partes, o **passo da indução** e a **base**. Cada parte é uma prova individual em si própria. O passo da indução demonstra que para cada *i* >= 1, se *P(i)* é verdadeiro, então *P(i + 1)* também é. A base prova que *P(1)* é verdadeiro.
	- No passo da indução, a suposição de que *P(i)* seja verdadeiro é chamada **hipótese da indução**. Às vezes, ter a hipótese da indução mais forte de que *P(j)* é verdadeiro para todo *j* <= *i* é útil.


