# Criando sua Primeira Função na Prática

## Introdução

Vamos colocar a mão na massa e criar nossa primeira função em JavaScript. Nesta aula rápida, você verá o passo a passo de como **declarar** uma função (ou seja, criá-la) e, em seguida, como **chamar** essa função para que ela execute a tarefa que programamos.

---

## 1. Declarando a Função

Primeiro, precisamos definir nossa função. Para isso, usamos a palavra-chave `function`, seguida por um nome que escolhermos para ela.

A estrutura básica é:

1. A palavra reservada `function`.
2. O nome da função (ex: `exibirMensagem`).
3. Parênteses `()`.
4. Chaves `{}` que delimitam o bloco de código. Tudo o que estiver dentro das chaves é a "tarefa" que a função irá realizar.

**JavaScript (Declaração)**

**JavaScript**

```
// 1. Palavra-chave 'function' seguida do nome 'message'
// 2. Abrimos e fechamos parênteses '()'
// 3. Abrimos e fechamos chaves '{}' para definir o escopo (o corpo da função)
function message() {
  // Todo código aqui dentro será executado quando a função for chamada
  console.log("Olá, é bom ter você aqui!");
}
```

Neste ponto, se você salvar e executar o código,  **nada acontecerá** . Nós apenas criamos a "receita", mas ainda não demos a ordem para prepará-la. A função existe, mas não foi ativada.

---

## 2. Chamando (Executando) a Função

Para que o código dentro da função seja de fato executado, precisamos **chamá-la** ou  **invocá-la** . Fazemos isso simplesmente escrevendo o nome da função seguido de parênteses.

**JavaScript (Chamada)**

**JavaScript**

```
function message() {
  console.log("Olá, é bom ter você aqui!");
}

// Agora, vamos chamar a função para executá-la
message();

// Saída no console:
// Olá, é bom ter você aqui!
```

Agora sim! A mensagem que definimos foi exibida no console.

### A Magia da Reutilização

O grande benefício é que não precisamos reescrever o `console.log` toda vez. Podemos simplesmente chamar a função quantas vezes quisermos.

**JavaScript**

**JavaScript**

```
function message() {
  console.log("Olá, é bom ter você aqui!");
}

// Chamando a mesma função várias vezes
message();
message();
message();

// Saída no console:
// Olá, é bom ter você aqui!
// Olá, é bom ter você aqui!
// Olá, é bom ter você aqui!
```

Nós reaproveitamos o conteúdo e a lógica da função sem esforço, simplesmente chamando-a pelo nome.

## Resumo da Aula

Nesta aula, você aprendeu na prática a:

* **Declarar uma função** usando a sintaxe `function nome() {}`.
* **Chamar uma função** usando seu nome seguido de parênteses, como `nome()`, para executar o código dentro dela.
* **Reaproveitar o código** de uma função, chamando-a múltiplas vezes.

Parabéns, você criou e executou sua primeira função!
