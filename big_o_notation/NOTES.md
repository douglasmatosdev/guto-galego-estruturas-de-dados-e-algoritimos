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

# > Em breve ...
