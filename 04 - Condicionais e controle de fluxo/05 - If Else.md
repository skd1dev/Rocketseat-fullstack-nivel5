
# Estrutura de Condição `else`: O "Senão" do Seu Código

---

## Introdução

Nesta aula, vamos expandir o que aprendemos sobre o `if` e introduzir o  **`else` (que significa "senão")** . Com ele, você pode criar uma lógica onde seu programa executa uma ação **se** uma condição for verdadeira, **E uma ação diferente** se a condição for falsa. É a estrutura ideal para situações de "ou isso, ou aquilo".

---

## O `else` em Ação: Idade para Dirigir

Vamos usar um exemplo prático: determinar se uma pessoa pode dirigir com base na idade dela.

Primeiro, vamos lembrar como o `if` sozinho se comporta:

**JavaScript**

```
// Definimos a variável 'age' (idade)
let age = 17;

// SE a idade for menor que 18, exibe uma mensagem
if (age < 18) { // Condição: 17 é menor que 18? -> true
  console.log("Você não pode dirigir."); // Saída: Você não pode dirigir.
}
// Se a idade fosse 20, nada seria exibido aqui, pois a condição seria falsa e não haveria alternativa.
```

No cenário acima, se `age` fosse `20`, o programa não faria nada. Mas, e se você quiser que ele diga "Você pode dirigir" quando a idade for maior ou igual a 18?

É aí que o **`else`** entra!

### Usando o `if-else`

O `else` complementa o `if`. Ele não precisa de uma condição própria, pois ele  **só é executado se a condição do `if` anterior for falsa** .

**Sintaxe:**

**JavaScript**

```
if (condição) {
  // Código a ser executado SE a condição for verdadeira
} else {
  // Código a ser executado SE a condição do 'if' for falsa
}
```

Vamos aplicar isso ao nosso exemplo da idade para dirigir:

**JavaScript**

```
let age = 23; // Idade da pessoa

// PRIMEIRO: Testa a condição do IF
if (age < 18) { // Condição: 23 é menor que 18? -> false
  console.log("Você não pode dirigir."); // Este bloco NÃO é executado
}
// SEGUNDO: Se a condição do IF for falsa, o ELSE é executado
else {
  console.log("Você pode dirigir."); // Este bloco É executado
}
// Saída quando age = 23: Você pode dirigir.
```

Agora, vamos testar com uma idade menor que 18 novamente:

**JavaScript**

```
age = 15; // Idade da pessoa

// PRIMEIRO: Testa a condição do IF
if (age < 18) { // Condição: 15 é menor que 18? -> true
  console.log("Você não pode dirigir."); // Este bloco É executado
}
// SEGUNDO: Se a condição do IF for verdadeira, o ELSE é IGNORADO
else {
  console.log("Você pode dirigir."); // Este bloco NÃO é executado
}
// Saída quando age = 15: Você não pode dirigir.
```

---

## Como o `if-else` Funciona

* O JavaScript avalia a  **condição do `if`** .
* **Se a condição do `if` for `true`** : O código dentro do bloco `if` é executado, e todo o bloco `else` é  **pulado** .
* **Se a condição do `if` for `false`** : O código dentro do bloco `if` é  **pulado** , e o código dentro do bloco `else` é  **executado** .

Isso garante que **apenas um dos dois blocos** (`if` ou `else`) será executado, criando um fluxo de decisão claro: ou uma coisa acontece, ou a outra acontece.

---

## Conclusão

O `else` é um complemento muito útil para o `if`, permitindo que você lide com os dois resultados possíveis de uma condição booleana (verdadeiro ou falso) de forma estruturada. Ele é perfeito para situações onde você precisa executar uma ação padrão caso a condição principal não seja atendida.
