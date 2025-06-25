# Funções Anônimas: Funções Sem Nome em JavaScript

## Introdução

Até agora, todas as funções que criamos tinham um nome. Nesta aula, vamos explorar um conceito muito comum em JavaScript: a  **função anônima** , que, como o nome sugere, é uma função declarada sem um nome.

Você pode se perguntar: "Por que eu criaria uma função sem nome? Como vou chamá-la?". A resposta está no seu uso mais comum:  **atribuir uma função diretamente a uma variável ou constante** . Em vez de guardar o *retorno* de uma função, nós guardamos a *própria função* para executá-la mais tarde.

## Criando e Usando uma Função Anônima

Diferente de uma função nomeada que pode ser declarada de forma independente, a função anônima é criada para ser usada imediatamente, geralmente sendo atribuída a uma variável.

Vamos ver a sintaxe.

**JavaScript (Atribuindo uma Função Anônima)**

**JavaScript**

```
// Declaramos uma constante 'showMessage'
// e atribuímos a ela uma função sem nome.
const showMessage = function() {
  return "Olá, Rodrigo!";
};

// Vamos verificar o que há dentro da constante 'showMessage'
console.log(showMessage);
// Saída: [Function: showMessage] (ou algo similar, indicando que é uma função)

// Para executar a função, usamos o nome da constante seguido de parênteses
console.log(showMessage());
// Saída: Olá, Rodrigo!
```

Perceba que a constante `showMessage` não guarda o texto `"Olá, Rodrigo!"`, mas sim a própria função. Nós a executamos como faríamos com uma função normal, usando `()`, e só então obtemos o valor retornado.

> **Nota:** Embora tenhamos usado `const`, também é possível usar `let`. Usamos `const` porque, na maioria das vezes, não temos a intenção de reatribuir uma nova função à mesma variável.

---

## Passando Parâmetros para Funções Anônimas

Funções anônimas funcionam como qualquer outra função e podem, claro, receber parâmetros. A declaração dos parâmetros ocorre entre os parênteses da função anônima.

**JavaScript (Função Anônima com Parâmetros)**

**JavaScript**

```
const showMessageWithName = function(name) {
  return "Olá, " + name;
};

// Agora, passamos o argumento ao chamar a função através da variável
console.log(showMessageWithName("João"));
console.log(showMessageWithName("Ana"));

// Saída no console:
// Olá, João
// Olá, Ana
```

A lógica é exatamente a mesma de uma função nomeada: o valor que passamos como argumento (`"João"`) é atribuído ao parâmetro (`name`) dentro da função.

### Múltiplos Parâmetros

Para passar mais de um parâmetro, basta separá-los por vírgula, como já aprendemos.

**JavaScript (Múltiplos Parâmetros)**

**JavaScript**

```
const createGreeting = function(message, name) {
  return message + ", " + name + "!";
};

console.log(createGreeting("Seja bem-vindo", "Carlos"));

// Saída no console:
// Seja bem-vindo, Carlos!
```

## Resumo da Aula

Nesta aula, você aprendeu uma nova maneira de criar e utilizar funções.

* **Função Anônima** : É uma função declarada sem um nome, geralmente para ser atribuída a uma variável.
* **Sintaxe** : `const minhaVariavel = function(param1, param2) { /* ... */ };`.
* **Execução** : A função é chamada através do nome da variável que a armazena (`minhaVariavel()`).
* **Flexibilidade** : Elas podem receber parâmetros e retornar valores, sendo uma ferramenta poderosa e extremamente comum no dia a dia do desenvolvimento com JavaScript.
