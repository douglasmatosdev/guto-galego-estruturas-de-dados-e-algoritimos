# BIG O NOTATION
> Fala sobre escalabilidade, e não necessariamente performance

Um algoritmo `O(n)` não necessariamente vai ser mais rápido do que `O(n)`, mas a questão não é essa, para uma estrutura pequena não faz diferença, mas no Big O consideramos a  nálise assintótica, assim faremas a análise
do quão escalável é o algoritmo.

## Complexidade Temporal

Analisamos o tempo gasto

Exemplo, digamos que temos uma lista, onde queremos identificar o indice do maior valor.

```javascript
// Lista de exemplo
[1, 7, 6, 5, 4, 3, 2]
```
1. `1` é maior
2. `7` é maior (***1 passou a não ser maior***)
3. `6` não é maior
4. `5` não é maior
5. `4` não é maior
6. `3` não é maior
7. `2` não é maior

Veja que precisou percorrer todos os itens da lista, ou seja, a complexidade temporal é `O(n)`, onde `n` é o tamanho da lista.


## Complexidade Espacial

Usando como exemplo o caso anterior, note que para sabermos o indice do maior valor, precisamos apenas alocar 1 item na memória, ou seja, o espaço usado na memória é sempre 1, logo a complexidade espacial é `O(1)`.


## O(1) CONSTANTE

`O(1)` é constante, podendo ser **tempo constante** ou **memória constante**.

### Tempo constante

Um exemplo de algoritmo `O(1)` com tempo constate é um algoritmo que pegue apenas o primeiro valor de uma lista, está operação é `O(1)`:

```javascript
const arr = [1, 2, 3, 4, 5]

arr[0] // Já sabemos a posição 0 (zero), o custo de tempo é O(1)
```

### Memória constante

Usando o mesmo exemplo anterior, podemos ver que precisamos alocar na memória apenas 1 item sempre, logo o espaço em memória é constante ou `O(1)`.

```javascript
const arr = [1, 2, 3, 4, 5]

arr[0] // Já sabemos a posição 0 (zero), o custo de espaço é O(1)
```

Lembro, sempre se trata da escalabilidade, então veja o exemplo a seguir, onde temos uma lista com 1.000.000 (um milhão de itens), a mémoria continua constante, pois independente do tamanho, sempre iremos armazenar apenas 1 item na memória.

```javascript
const arr = [1, 2, 3, 4, 5, ...., 1000000]

arr[0] // Já sabemos a posição 0 (zero), o custo de espaço é O(1)
```

## O (Log n)

```txt
Log2 (10) -> 3.321928
Log2 (20) -> 4.321928
Log2 (40) -> 5.321928
```

Veja que dobramos o valor de `10` para `20` e o resulta não dobrou, auemntou apenas `1`, de `3.321928` para `4.321928`.

Exemplo usando o algoritmo `Binary Search`.

Usando o algoritmo `Binary Search` veja quantas etapas são necessárias para encontrar o número `3` em uma lista com `10` ordenados.

```javascript
const list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

// ETAPA 1
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
// Vamos dividir no meio:
// [1, 2, 3, 4, 5]
// [6, 7, 8, 9, 10]

// Veja que 3 é menor que todos os itens da segunda metada de lista, então podemos descartar a segunda metade

// ETAPA 2
// [1, 2, 3, 4, 5]
// Vamos dividir no meio a lista restante, neste caso o meio é o 3, na maioria das implementações de Binary Search é considerado o elemento da esquerda, que no caso é o 2.
// [1, 2] 
// [3, 4, 5]

// ETAPA 3
// [3, 4, 5]
// Vamos dividir no meio novamento
// [3]
// [4, 5]

// Veja que agora temos o elemento 3
```

Foram necessárias 3 etapas para encontrar o valor 3 em uma lista com 10 elementos ordenados.

Agora, se dobrarmos o tamnho da lista? A quantidade de etapas dobra? Vamos testar.


```javascript
const list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]

// ETAPA 1
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20]
// Vamos dividir no meio:
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
// [11, 12, 13, 14, 15, 16, 17, 18, 19, 20]

// ETAPA 2
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
// Vamos dividir no meio.
// [1, 2, 3, 4, 5]
// [6, 7, 8, 9, 10]

// ETAPA 3
// [1, 2, 3, 4, 5]
// Vamos dividir no meio novamento
// [1, 3]
// [3, 4, 5]

// ETAPA 4
// [3, 4, 5]
// Vamos dividir no meio novamento
// [3]
// [4, 5]

// Veja que agora temos o elemento 4
```

O seja, isso é `O Log(n)`, pois o algoritmo está escalando logaritmicamente, aumentando de 1 em 1 e não dobrando o tempo.


## Pessimista

### Conplexidade temporal

Em `O(n)` onde `n` é o tamanho do input de dados, digamos que em uma lista de 10 elementos ordenados nós precisamos encontrar o número 3.
```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
Veja que precisaremos apenas de 3 passos para achar o valor desejado.

Neste caso, podemos dizer que o algoritmo é melhor que `O(n)`, tipo um `O(3)` ???

NÃO!!!

Porque, sempre vamos considerar o pior caso, sempre imaginando que talvez o valor desejado esteja no fim da lista de tamanho `n`, logo temos `O(n)`.

### Complexidade espacial

Em `O(n)` onde `n` é o tamanho do input de dados, digamos que em uma lista de 10 elementos ordenados nós precisamos criar uma nova lista a partir da primeira, onde cada item desta lista tem o seu valor dobrado.
```javascript
// lista inicial
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

// nova lista
[2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
```

Veja que para criarmos uma nova lista, precisamos alocar na memória uma quantidade de espaço exatamento do mesmo tamanho que a lista inicial.

Neste caso, a complexidade espacial é `O(n)` também.
