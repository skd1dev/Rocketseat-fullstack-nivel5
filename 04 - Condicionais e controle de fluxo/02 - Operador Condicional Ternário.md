
# Operador Condicional Ternário: Decisões em uma Linha

---

## Introdução

Nesta aula, vamos conhecer o  **operador condicional ternário** . Você já vai entender o porquê do nome "ternário", que remete a três partes essenciais. Este operador é uma forma concisa de escrever uma estrutura de condição `if-else` em uma única linha.

---

## O Que é o Operador Ternário?

O operador ternário é uma expressão que avalia uma condição e retorna um de dois valores possíveis, dependendo se a condição é `true` ou `false`.

**Sintaxe Básica:**

**JavaScript**

```
condição ? valor_se_verdadeiro : valor_se_falso;
```

* **`condição`** : É o teste lógico que será avaliado (`true` ou `false`).
* **`?` (interrogação)** : Separa a condição do valor que será retornado se a condição for verdadeira.
* **`valor_se_verdadeiro`** : É o valor (ou expressão) que será retornado se a `condição` for `true`.
* **`:` (dois pontos)** : Separa o valor verdadeiro do valor falso.
* **`valor_se_falso`** : É o valor (ou expressão) que será retornado se a `condição` for `false`.

---

## Por Que "Ternário"?

Ele se chama "ternário" porque envolve **três partes** ou operandos em sua estrutura:

1. A **Condição**
2. A expressão para o caso **Verdadeiro**
3. A expressão para o caso **Falso**

---

## Exemplo Prático: Verificando Idade para Dirigir

Vamos usar um exemplo comum: verificar se uma pessoa pode dirigir com base na sua idade. A regra é: se a idade for maior ou igual a 18, a pessoa pode dirigir; caso contrário, não pode.

**JavaScript**

```
let age = 16; // Idade da pessoa

// Usamos o console.log para exibir o resultado diretamente da expressão ternária
console.log(
  // PRIMEIRA PARTE: A Condição (Teste Lógico)
  age >= 18          // A idade é maior ou igual a 18?
  ? "Você pode dirigir."  // SE VERDADEIRO (depois da interrogação): Retorna esta mensagem
  : "Você não pode dirigir." // SE FALSO (depois dos dois pontos): Retorna esta mensagem
);
// Saída quando age = 16: "Você não pode dirigir."
```

Vamos alterar o valor da idade para ver a mudança:

**JavaScript**

```
age = 21; // Alterando a idade para 21

console.log(
  age >= 18          // A idade é maior ou igual a 18? (21 >= 18 -> true)
  ? "Você pode dirigir."
  : "Você não pode dirigir."
);
// Saída quando age = 21: "Você pode dirigir."
```

O resultado (a mensagem exibida) mudou porque a condição (`age >= 18`) foi avaliada de forma diferente em cada caso.

---

## Flexibilidade da Condição e Valores

A condição do operador ternário pode usar **qualquer operador lógico** (`&&`, `||`, `!`) ou de **comparação** (`>`, `<`, `===`, `!==`, etc.) que você já aprendeu. Os valores de retorno (`valor_se_verdadeiro` e `valor_se_falso`) podem ser strings, números, outras variáveis, ou até mesmo resultados de outras operações.

### Exemplo: Invertendo a Lógica da Condição

Você também pode inverter a lógica da sua condição, ajustando os resultados de acordo.

**JavaScript**

```
let currentAge = 20; // Idade atual

// Condição: idade é MENOR que 18?
console.log(
  currentAge < 18           // A idade é menor que 18? (20 < 18 -> false)
  ? "Você não pode dirigir." // SE VERDADEIRO (para idade menor que 18)
  : "Você pode dirigir."     // SE FALSO (para idade NÃO menor que 18, ou seja, maior ou igual)
);
// Saída quando currentAge = 20: "Você pode dirigir."
```

---

## Quando Usar o Operador Ternário?

O operador ternário é ideal para **condições simples** que resultam em uma escolha entre dois valores ou ações diretas. Ele é mais conciso que um `if-else` completo, tornando o código mais legível para essas situações.

Para lógicas mais complexas, com múltiplos testes ou blocos de código extensos, as estruturas `if-else if-else` são mais adequadas e fáceis de manter.

---
