

# Operadores Lógicos: Estritamente Igual a (`===`) e Estritamente Diferente de (`!==`)

Nessa aula, a gente vai se aprofundar nos operadores de comparação e entender o **estritamente igual a (`===`)** e o  **estritamente diferente de (`!==`)** . Eles são essenciais pra fazer comparações mais robustas e seguras no JavaScript.

---

## O Operador "Estritamente Igual a" (`===`)

A grande sacada do operador `===` é que ele verifica se dois valores são iguais  **tanto no conteúdo (o valor em si) quanto no tipo de dado** . Pra que a comparação dê `true` (verdadeiro), os dois critérios precisam bater. Se o tipo for diferente, mesmo que o valor pareça o mesmo, ele já retorna `false`.

Vamos usar as mesmas variáveis que vimos antes pra entender melhor:

**JavaScript**

```
let one = 1; // Tipo: Number
let two = 2; // Tipo: Number

console.log("--- Estritamente Igual a (===) ---");

// Comparando uma variável com um número (mesmo valor e mesmo tipo)
console.log(`one === 1: ${one === 1}`); // Saída: true (1 é um número e é igual a 1)

// Comparando um número com uma string (mesmo valor, mas tipo diferente)
console.log(`one === '1': ${one === '1'}`); // Saída: false (1 é um número, '1' é uma string. Tipos diferentes!)
```

Percebe a diferença? Enquanto `one == '1'` (com dois iguais) retornava `true` por comparar só o conteúdo, `one === '1'` retorna `false` porque `one` é um **Number** e `'1'` é uma  **String** . Pra `===` dar `true`, valor e tipo têm que ser idênticos.

---

## O Operador "Estritamente Diferente de" (`!==`)

O operador `!==` é o oposto do `===`. Ele verifica se dois valores são  **diferentes no valor OU diferentes no tipo** . Se os valores são diferentes, ou se os tipos são diferentes (ou ambos), ele retorna `true`.

Olha só os exemplos:

**JavaScript**

```
let one = 1; // Tipo: Number
let two = 2; // Tipo: Number

console.log("\n--- Estritamente Diferente de (!==) ---");

// Comparando se 'one' é estritamente diferente de 'two' (valores diferentes, mesmos tipos)
console.log(`one !== two: ${one !== two}`); // Saída: true (1 é diferente de 2)

// Comparando se 'one' é estritamente diferente de 1 (mesmo valor, mesmo tipo)
console.log(`one !== 1: ${one !== 1}`);     // Saída: false (1 NÃO é estritamente diferente de 1)

// Comparando um número com uma string (mesmo valor aparente, mas tipos diferentes)
console.log(`one !== '1': ${one !== '1'}`); // Saída: true (1 é um número, '1' é uma string. Tipos diferentes!)
```

No último exemplo, `one !== '1'` retorna `true`. Isso porque, mesmo que o conteúdo seja "1" em ambos os casos, os **tipos são diferentes** (`Number` vs. `String`), e o operador `!==` leva o tipo em consideração.

---

## `===` e `!==` vs. `==` e `!=`: Qual Usar?

É supercomum a pergunta: "Tá, mas qual deles eu devo usar?"

**Minha recomendação clara é: sempre que puder, use o `===` (estritamente igual a) e o `!==` (estritamente diferente de) nas suas comparações em JavaScript.**

### Por que essa preferência?

* **Segurança e Previsibilidade:** Ao verificar valor e tipo, você evita comportamentos inesperados que podem acontecer por causa da "conversão" automática de tipo que o `==` e `!=` fazem.
* **Código Mais Claro:** Seu código fica mais fácil de entender sobre o que está sendo comparado. Não tem ambiguidade se você quer olhar só o conteúdo ou também o tipo.
* **Evita Bugs:** Imagine um número que, sem querer, vira uma string ("10" em vez de 10) num cálculo financeiro. Usando `==`, ele ainda seria considerado "igual" a 10, podendo causar erros graves. Com `===`, a comparação falharia, mostrando que tem um problema de tipo.
* **Cuidado com Concatenação:** Em operações como a adição (`+`), o JavaScript pode juntar strings em vez de somar números se um dos valores for uma string. Usar `===` ou `!==` antes de operar pode ajudar a garantir que você está lidando com os tipos de dados certos.

Em resumo, usar `===` e `!==` te dá mais **controle** e **confiabilidade** nas suas comparações. Você tem certeza que está comparando não só o que parece ser o mesmo valor, mas também que eles são do mesmo "material" (tipo).

---
