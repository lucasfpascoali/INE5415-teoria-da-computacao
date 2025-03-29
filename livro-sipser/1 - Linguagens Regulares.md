"A teoria da computação começa com uma pergunta: O que é um computador? É, talvez, uma questão tola, pois todos sabem que essa coisa sobre a qual estou teclando é um computador. Porém, esses computadores reais são bastante complicados — demasiadamente complicados para nos permitir construir uma teoria matemática manejável sobre eles diretamente. Em vez disso, usamos um computador idealizado chamado um **modelo computacional**. Como qualquer modelo em ciência um modelo computacional pode ser preciso em alguns detalhes, mas talvez não em outros. Assim, utilizaremos vários modelos computacionais diferentes, dependendo das características que desejemos focalizar. Começaremos com o modelo mais simples, denominado máquina de **estados finitos** ou **autômato finito**."

# 1.1 Autômatos Finitos

- São bons modelos para computadores com uma quantidade extremamente limitada de memória. 

## Definição Formal

Um **autômato finito** é uma 5-upla (*Q*, Σ, δ, q₀, *F*) onde

1. *Q* é um conjunto finito não-vazio conhecido como os **estados**,
2. Σ é um conjunto finito não vazio chamado o **alfabeto**,
3. δ: *Q* × Σ -> *Q* é a **função de transição**,
4. q₀ ∈ *Q* é o **estado inicial**, e
5. *F* ⊆ *Q* é o **conjunto de estados de aceitação** (às vezes são chamados **estados finais**)

Uma linguagem é chamada de uma **linguagem regular** se algum autômato finito a reconhece.

## As Operações Regulares

"Em aritmética, os objetos básicos são números e as ferramentas são operações para manipulá-los, tais como + e ×. Na teoria da computação os objetos são linguagens e as ferramentas incluem operações especificamente projetadas para manipulá-las. Definimos três operações sobre linguagens, chamadas **operações regulares**, e as usamos para estudar propriedades de linguagens regulares."

Sejam *A* e *B* linguagens. Definimos as operações regulares **união**, **concatenação** e **estrela** da seguinte forma.
- **União**: A U B = { x | x  ∈ A ou x ∈ B }
- **Concatenação**: A · B = { xy | x ∈ A e y ∈ B }
- **Estrela**: A* = { x₁, x₂ . . . xₖ | k >= 0 e cada xᵢ ∈ A }.

**OBS**: A classe de linguagens regulares é **fechada** sobre as três operações e as provas são relativamente simples. Você pode conferir isso usando os respectivos teoremas do livro: 1.25 e 1.26.

# 1.2 Não-Determinismo

"Não determinismo é um conceito útil que tem tido grande impacto sobre a teoria da computação. Até agora em nossa discussão, todo passo de uma computação segue de uma maneira única do passo precedente. Quando a máquina está em um dado estado e lê o próximo símbolo de entrada, sabemos qual será o próximo estado — está determinado. Chamamos isso de computação **determinística**. Em uma máquina **não-determinística**, várias escolhas podem existir para o próximo estado em qualquer ponto."

"Não-determinismo é uma generalização de determinismo; portanto, todo autômato finito determinístico é automaticamente um autômato finito não-determinístico.

"O não-determinismo pode ser visto como uma espécie de computação paralela na qual múltiplos e independentes 'processos' ou '*threads*' podem estar rodando concorrentemente. Quando o AFN se divide para seguir as diversas escolhas, isso corresponde a um processo 'bifurcar' em vários filhos, cada um procedendo separadamente. **Se pelo menos um desses processos aceita, então a computação inteira aceita.**"

"Outra maneira de pensar em uma computação não-determinística é como uma árvore de possibilidades. A raiz da árvore corresponde ao início da computação. Todo ponto de ramificação na árvore corresponde a um ponto na computação no qual a máquina tem múltiplas escolhas. A máquina aceita se pelo menos um dos ramos da computação termina em um estado de aceitação."

## Definição Formal de um Autômato Finito Não-determinístico

"A definição formal de um autômato finito não-determinístico é similar àquela de um autômato finito determinístico. Ambos têm estados, um alfabeto de entrada, uma função de transição, um estado inicial e uma coleção de estados de aceitação. Entretanto, eles diferem de uma maneira essencial: no tipo de função de transição. Em um AFD a função de transição toma um estado e um símbolo de entrada e produz o próximo estado. Em um AFN a função de transição toma um estado e um símbolo de entrada **ou a cadeia vazia** e produz o **conjunto de próximos estados possíveis**."

Para escrever a definição formal, precisamos fixar alguma notação adicional. Para qualquer conjunto *Q* escrevemos *P(Q)* como sendo a coleção de todos os subconjuntos de *Q*. Aqui *P(Q)* é chamado **conjunto das partes** de *Q*. Para qualquer alfabeto Σ escrevemos Σₑ como sendo Σ ∪ {ε}. Agora podemos escrever a definição formal do tipo de função de transição em um AFN como δ: *Q* × Σₑ -> *P(Q)*.

Um **autômato finito não-determinístico** é uma 5-tupla (*Q*, Σ, δ, q₀, *F*), onde
1. *Q* é um conjunto finito de estados,
2. Σ é um alfabeto finito,
3. δ: *Q* × Σₑ -> *P(Q)* é a função de transição,
4. q₀ ∈ *Q* é o estado inicial, e
5. *F* ⊆ *Q* é o conjunto de estados de aceitação.

"A definição formal de computação para um AFN é similar àquela para um AFD. Seja *N* = (*Q*, Σ, δ, q₀, *F*) um AFN e *w* uma cadeia sobre o alfabeto Σ. Então dizemos que *N* **aceita** *w* se podemos escrever *w* como *w* = y₁, y₂, . . ., yₘ, onde cada yᵢ é um membro de Σₑ, e existe uma sequência de estados r₀, r₁, . . ., rₘ em *Q* com três condições:"

1. r₀ = q₀,
2. rᵢ₊₁ ∈ δ(rᵢ, yᵢ₊₁),  para i = 0, ..., m - 1, e
3. rₘ ∈ *F*

"A condição 1 diz que a máquina começa no estado inicial. A condição 2 diz que o estado rᵢ₊₁ é um dos próximos estados permissíveis quando *N* está no estado rᵢ e lendo yᵢ₊₁. Observe que δ(rᵢ, yᵢ₊₁) é o **conjunto** de próximos estados permissíveis e portanto dizemos que rᵢ₊₁ é um membro desse conjunto. Finalmente, a condição 3 diz que a máquina aceita sua entrada se o último estado é um estado de aceitação."

## Equivalência de AFNs e AFDs

"Os autômatos finitos determinísticos e não-determinísticos reconhecem a mesma classe de linguagens. Essa equivalência é, ao mesmo tempo, surpreendente e útil. É surpreendente porque AFNs parecetem ter mais poder que AFDs e, portanto, poderíamos esperar que AFNs reconhecessem mais linguagens. É útil porque descrever um AFN para uma dada linguagem às vezes é muito mais fácil que descrever um AFD para essa linguagem. Dizemos que duas máquinas são **equivalentes** se elas reconhecem a mesma linguagem."

