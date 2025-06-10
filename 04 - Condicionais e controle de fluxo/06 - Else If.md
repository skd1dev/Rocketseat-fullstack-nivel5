
# Estruturas de Condição Aninhadas: `if`, `else if`, `else`

---

## Introdução

Nesta aula, vamos aprofundar nosso conhecimento em estruturas de condição, aprendendo a utilizar o  **`if` encadeado com `else if` e `else`** . Essa combinação nos permite criar fluxos de decisão mais complexos, onde o programa testa múltiplas condições em sequência e executa apenas o bloco de código correspondente à primeira condição verdadeira que encontrar.

---

## O Problema dos `if` Independentes

Primeiro, vamos relembrar como múltiplos `if` separados funcionam e por que, às vezes, isso não é o ideal para todos os cenários.

Imagine que queremos exibir uma mensagem de saudação (Bom dia, Boa tarde, Boa noite) baseada na hora do dia.

**JavaScript**

```
let hour = 19; // Hora atual

// Exemplo com IFs independentes:
if (hour <= 12) { // 19 <= 12? -> false
  console.log("Bom dia!");
}
if (hour > 18) { // 19 > 18? -> true
  console.log("Boa noite!"); // Esta linha será executada
}
if (hour > 12) { // 19 > 12? -> true
  console.log("Boa tarde!"); // Esta linha também será executada
}
// Saída quando hour = 19:
// Boa noite!
// Boa tarde!
```

Neste exemplo, com `hour = 19`, o JavaScript exibiu "Boa noite!" E "Boa tarde!". Isso aconteceu porque:

1. O primeiro `if` (`hour <= 12`) foi avaliado como `false`.
2. O segundo `if` (`hour > 18`) foi avaliado como `true`, e "Boa noite!" foi exibido.
3. O terceiro `if` (`hour > 12`) também foi avaliado como `true`, e "Boa tarde!" foi exibido.

**Comportamento:** Quando você usa `if`s separados,  **cada `if` é verificado independentemente** . Mesmo que uma condição seja atendida e seu bloco de código seja executado, o JavaScript (e outras linguagens) continuará verificando todos os outros `if`s que vêm depois. Para o cenário de saudação, isso não é o que queremos; a hora é "Boa noite" *ou* "Boa tarde", não as duas.

---

## O `if-else if-else` Encadeado: Um Fluxo de Decisão Único

Para resolver o problema dos `if`s independentes e garantir que **apenas um bloco de código seja executado** (o da primeira condição verdadeira), usamos o encadeamento com `else if` e `else`.

A ideia é: "SE esta condição for verdadeira, faça isso. SENÃO, SE esta outra condição for verdadeira, faça aquilo. SENÃO (se nenhuma das anteriores for verdadeira), faça aquilo outro."

**Sintaxe:**

**JavaScript**

```
if (condição1) {
  // Bloco de código se condição1 for verdadeira
} else if (condição2) {
  // Bloco de código se condição1 for falsa E condição2 for verdadeira
} else if (condição3) {
  // Bloco de código se condição1 e condição2 forem falsas E condição3 for verdadeira
} else {
  // Bloco de código se TODAS as condições anteriores forem falsas
}
```

### Exemplo: Saudação Correta com `if-else if-else`

Vamos refazer o exemplo da saudação usando a estrutura encadeada. É crucial que a ordem das condições faça sentido para a sua lógica (do mais específico para o mais geral, ou em uma ordem cronológica).

**JavaScript**

```
let hour = 19; // Hora atual

// Estrutura IF-ELSE IF-ELSE encadeada:
if (hour <= 12) { // Primeira tentativa: 19 <= 12? -> false. Não executa.
  console.log("Bom dia!");
} else if (hour > 18) { // Segunda tentativa: 19 > 18? -> true. Executa este bloco.
  console.log("Boa noite!");
} else if (hour > 12) { // Esta condição NEM SERÁ VERIFICADA se a anterior for verdadeira!
  console.log("Boa tarde!");
} else { // Este 'else' final é opcional, executa se NENHUMA das condições anteriores for true.
  console.log("Olá!"); // Uma saudação genérica
}
// Saída quando hour = 19:
// Boa noite!
```

No exemplo acima, com `hour = 19`:

1. `if (hour <= 12)` é `false`.
2. `else if (hour > 18)` é `true`. O bloco "Boa noite!" é executado.
3. **Importante:** Após a execução do `else if (hour > 18)`, o JavaScript **ignora** as condições restantes (`else if (hour > 12)`) e o `else` final. O fluxo da decisão é encerrado.

### Outros Casos para Testar

Vamos testar com outras horas:

**JavaScript**

```
hour = 11; // Hora da manhã
if (hour <= 12) { // 11 <= 12? -> true. Executa "Bom dia!".
  console.log("Bom dia!");
} else if (hour > 18) {
  console.log("Boa noite!");
} else if (hour > 12) {
  console.log("Boa tarde!");
} else {
  console.log("Olá!");
}
// Saída: Bom dia! (As outras condições não são sequer olhadas)

console.log('---'); // Separador

hour = 15; // Hora da tarde
if (hour <= 12) { // 15 <= 12? -> false.
  console.log("Bom dia!");
} else if (hour > 18) { // 15 > 18? -> false.
  console.log("Boa noite!");
} else if (hour > 12) { // 15 > 12? -> true. Executa "Boa tarde!".
  console.log("Boa tarde!");
} else {
  console.log("Olá!");
}
// Saída: Boa tarde!
```

---

## Quando Usar `if` Separados vs. `if-else if-else`

* **`if`s Separados:** Use quando você precisa que  **todas as condições sejam avaliadas independentemente** , e múltiplos blocos de código podem ser executados. (Ex: um sistema de alertas onde várias condições podem ser verdadeiras e acionar alertas diferentes e não mutuamente exclusivos).
* **`if-else if-else` Encadeado:** Use quando as condições são **mutuamente exclusivas** e você quer que **apenas um bloco de código seja executado** após a primeira condição verdadeira ser encontrada. (Ex: classificação de notas, saudação do dia, categorias de idade).

A escolha entre essas estruturas depende diretamente da **lógica que você quer implementar** e do **comportamento desejado** para o seu programa. Entender essa diferença é crucial para escrever um código eficiente e sem surpresas!

---
