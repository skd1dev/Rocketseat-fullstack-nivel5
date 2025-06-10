

# Operadores de Comparação em JavaScript

---

## Introdução

Nesta aula, vamos ver os **operadores de comparação** em JavaScript. Eles são essenciais pra você verificar se um valor é maior, menor, igual ou diferente de outro. O resultado dessas comparações é sempre um valor  **booleano** : `true` (verdadeiro) ou `false` (falso).

---

## Exemplo Prático: Saldo e Pagamento

Vamos usar um exemplo simples pra entender como esses operadores funcionam. Imagine que você tem:

**JavaScript**

```
let balance = 500; // O saldo atual na conta do usuário
let payment = 120; // O valor de um pagamento que precisa ser feito
```

Nossa meta é usar esses operadores pra checar se o `balance` é suficiente pra cobrir o `payment`.

---

### Maior Que (`>`)

O operador `>` verifica se o valor à esquerda é **maior que** o valor à direita.

**JavaScript**

```
console.log("--- Maior Que (>) ---");
console.log(`O saldo (${balance}) é maior que o pagamento (${payment})?`);
console.log(balance > payment); // Saída: true (500 é maior que 120)
```

Como `500` é maior que `120`, o resultado é `true`.

---

### Menor Que (`<`)

O operador `<` verifica se o valor à esquerda é **menor que** o valor à direita.

**JavaScript**

```
console.log("\n--- Menor Que (<) ---");
console.log(`O saldo (${balance}) é menor que o pagamento (${payment})?`);
console.log(balance < payment); // Saída: false (500 NÃO é menor que 120)
```

Neste caso, `500` não é menor que `120`, então o resultado é `false`.

---

### Maior ou Igual a (`>=`)

E se o saldo for exatamente igual ao valor do pagamento? O operador `>` sozinho retornaria `false`, o que não seria o ideal se o saldo é suficiente. Pra isso, usamos o operador `>=` (maior ou igual a).

Ele verifica se o valor à esquerda é **maior ou igual a** o valor à direita.

Vamos mudar o cenário um pouco:

**JavaScript**

```
console.log("\n--- Maior ou Igual a (>=) ---");

let currentBalance = 120; // Novo cenário: saldo exatamente igual ao pagamento
let currentPayment = 120;

console.log(`O saldo (${currentBalance}) é maior ou igual ao pagamento (${currentPayment})?`);
console.log(currentBalance >= currentPayment); // Saída: true (120 é igual a 120)
```

Com `currentBalance` sendo `120` e `currentPayment` também `120`, a comparação retorna `true` porque `120` é igual a `120`. Se `currentBalance` fosse `121`, também seria `true`.

---

### Menor ou Igual a (`<=`)

De forma similar, o operador `<=` (menor ou igual a) verifica se o valor à esquerda é **menor ou igual a** o valor à direita.

**JavaScript**

```
console.log("\n--- Menor ou Igual a (<=) ---");

// Voltando aos valores iniciais para um exemplo mais claro
balance = 500;
payment = 120;

console.log(`O saldo (${balance}) é menor ou igual ao pagamento (${payment})?`);
console.log(balance <= payment); // Saída: false (500 NÃO é menor nem igual a 120)

let anotherBalance = 100; // Outro cenário: saldo menor que o pagamento
console.log(`Outro saldo (${anotherBalance}) é menor ou igual ao pagamento (${payment})?`);
console.log(anotherBalance <= payment); // Saída: true (100 é menor que 120)
```

---

## Conclusão

Dominar esses operadores de comparação é fundamental para construir a lógica nos seus programas. Eles permitem que seu código tome decisões e reaja de formas diferentes, dependendo dos valores das variáveis.

Você consegue pensar em outras situações do dia a dia onde esses operadores seriam úteis?
