

# Entendendo o Escopo de Funções e Hoisting

## Introdução

Nesta aula, vamos explorar dois comportamentos importantes das funções em JavaScript: o **hoisting** (içamento) e o conceito de  **escopo** . Entender como o escopo funciona é crucial para saber onde suas funções podem ou não ser acessadas, evitando erros comuns.

Vamos ver como o hoisting nos permite chamar uma função antes mesmo de declará-la e como o escopo de uma função aninhada (uma função dentro de outra) a torna "privada" e protegida do mundo exterior.

---

## Hoisting (Içamento) de Funções

Lembra que o JavaScript "iça" (move) certas declarações para o topo do código antes da execução? As funções declaradas com a palavra-chave `function` também têm esse comportamento.

Na prática, isso significa que você pode chamar uma função em uma linha de código e declará-la mais abaixo, e tudo funcionará perfeitamente.

**JavaScript (Hoisting em Ação)**

**JavaScript**

```
// 1. Chamamos a função ANTES de ela ser declarada no código
showMessage("Olá, Rodrigo!");

// 2. A declaração da função aparece depois da sua chamada
function showMessage(message) {
  console.log(message);
}

// Saída no console:
// Olá, Rodrigo!
```

**Por que isso funciona?** Porque, durante a fase de compilação, o JavaScript move a declaração da função `showMessage` para o topo do seu escopo. Para o interpretador, o código é lido como se a função tivesse sido declarada primeiro.

Claro, a ordem "normal" (declarar e depois chamar) também funciona e é frequentemente considerada mais legível.

**JavaScript**

```
// Ordem convencional
function showMessage(message) {
  console.log(message);
}

showMessage("Funciona também!"); // Saída: Funciona também!
```

---

## Funções Aninhadas (Funções Dentro de Funções)

O JavaScript permite que você declare uma função dentro de outra. Isso é muito útil para criar funções "auxiliares" que só fazem sentido no contexto da função principal.

A função interna fica protegida e só pode ser acessada de dentro da função "mãe".

**JavaScript (Função Aninhada)**

**JavaScript**

```
function showMessage(message) {
  // Chamando a função interna
  endLine();

  console.log(message);

  // Chamando a função interna de novo
  endLine();

  // A função 'endLine' está declarada dentro de 'showMessage'.
  // Ela pertence somente a este escopo.
  function endLine() {
    console.log("--------------------");
  }
}

showMessage("Testando funções aninhadas");

// Saída no console:
// --------------------
// Testando funções aninhadas
// --------------------
```

Note que, assim como a função externa, a função aninhada `endLine` também sofre hoisting dentro do seu próprio escopo (o escopo de `showMessage`), por isso pudemos chamá-la antes de sua declaração.

### O Escopo Protege a Função Interna

Agora, o ponto mais importante: o que acontece se tentarmos chamar `endLine()` fora da função `showMessage`?

**JavaScript (Tentando Acessar Fora do Escopo)**

**JavaScript**

```
function showMessage(message) {
  // ... código da função ...
  function endLine() {
    console.log("--------------------");
  }
}

// A linha abaixo vai gerar um erro.
endLine();

// Saída no console:
// Uncaught ReferenceError: endLine is not defined
```

O erro acontece porque a função `endLine` **não existe** no escopo global. Seu "universo" começa e termina dentro das chaves `{}` da função `showMessage`. Isso é uma ferramenta poderosa para evitar que funções auxiliares poluam o escopo global e entrem em conflito com outras partes do seu programa.

## Resumo da Aula

Nesta aula, você aprendeu conceitos fundamentais sobre o comportamento das funções:

* **Hoisting** : Declarações de função são "içadas" para o topo do seu escopo, o que permite que elas sejam chamadas antes de serem escritas no código.
* **Funções Aninhadas** : É possível e útil declarar funções dentro de outras para organizar a lógica e criar helpers privados.
* **Escopo de Função** : Uma função declarada dentro de outra é limitada ao escopo da função "mãe" e não pode ser acessada de fora, o que previne erros e conflitos.
