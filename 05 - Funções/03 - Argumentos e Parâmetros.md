# Argumentos e Parâmetros

## Introdução

Vimos como criar e chamar funções, mas seu verdadeiro poder é desbloqueado quando as tornamos flexíveis. Nesta aula, vamos aprender a passar informações para dentro de uma função usando **parâmetros** e  **argumentos** , permitindo que a mesma função produza resultados diferentes.

Para facilitar, vamos definir os dois termos mais importantes desde o início:

* **Parâmetro** : É a **variável** que declaramos na definição da função. Ela atua como um espaço reservado para um valor que será recebido.
* **Argumento** : É o **valor real** que passamos para a função quando a chamamos.

---

## Parâmetros em Ação

Imagine que queremos uma função que exiba uma saudação, mas de forma personalizada para cada usuário. Sem parâmetros, teríamos que criar uma função para cada pessoa, o que não é prático.

É aqui que os parâmetros entram. Vamos criar uma função `message` que recebe um parâmetro `username`.

**JavaScript (Usando Parâmetros)**

**JavaScript**

```
// 'username' é o PARÂMETRO. É uma variável que só existe dentro desta função.
function message(username) {
  // Usamos o conteúdo do parâmetro para criar uma mensagem dinâmica
  console.log("Olá, " + username + "!");
}

// Ao chamar a função, passamos o ARGUMENTO "Rodrigo".
// O valor "Rodrigo" será atribuído ao parâmetro 'username'.
message("Rodrigo");

// Podemos chamar a mesma função com um argumento diferente.
message("Ana");

// Saída no console:
// Olá, Rodrigo!
// Olá, Ana!
```

Perceba que a função `message` agora é um modelo flexível. O argumento que passamos em cada chamada determina o resultado final.

### O Escopo dos Parâmetros

Uma regra crucial:  **os parâmetros só existem dentro da função onde foram declarados** . Se você tentar usar a variável `username` fora da função `message`, encontrará um erro.

**JavaScript (Escopo)**

**JavaScript**

```
function message(username) {
  console.log("Dentro da função, o valor é:", username);
}

message("Maria");

// A linha abaixo causará um erro, pois 'username' não existe neste escopo global.
// console.log(username); // Uncaught ReferenceError: username is not defined
```

Isso garante que as variáveis de uma função não interfiram com o resto do seu código, tornando-o mais seguro e previsível.

---

## A Ordem dos Argumentos Importa

Quando uma função tem múltiplos parâmetros, a ordem em que você passa os argumentos é fundamental. O primeiro argumento será atribuído ao primeiro parâmetro, o segundo ao segundo, e assim por diante.

Vamos criar uma função para somar dois números para ver isso na prática.

**JavaScript (Múltiplos Parâmetros)**

**JavaScript**

```
// 'numberA' é o primeiro parâmetro, 'numberB' é o segundo.
function sum(numberA, numberB) {
  console.log(numberA + numberB);
}

// A ordem importa: 10 vai para 'numberA', 20 vai para 'numberB'
sum(10, 20); // Saída: 30

// 7 vai para 'numberA', 3 vai para 'numberB'
sum(7, 3); // Saída: 10
```

Se invertêssemos a ordem em uma operação de subtração, por exemplo, o resultado seria completamente diferente. Portanto, sempre respeite a ordem definida na declaração da função.

---

## Definindo Valores Padrão

O que acontece se chamarmos uma função sem passar um dos argumentos? Por padrão, o parâmetro correspondente receberá o valor `undefined`.

**JavaScript (Sem Valor Padrão)**

**JavaScript**

```
function joinText(text1, text2) {
  console.log(text1, text2);
}

joinText("Rodrigo");

// Saída no console:
// Rodrigo undefined
```

Para evitar isso e tornar nossas funções mais robustas, podemos definir um **valor padrão** para os parâmetros usando o sinal de igual (`=`). Esse valor será usado apenas se nenhum argumento for fornecido para aquele parâmetro.

**JavaScript (Com Valor Padrão)**

**JavaScript**

```
// Se 'text2' não for informado, seu valor será uma string vazia ''.
function joinText(text1, text2 = "") {
  console.log(text1, text2);
}

// Chamamos a função sem o segundo argumento.
joinText("Rodrigo");

// Agora, se passarmos o segundo argumento, ele substitui o valor padrão.
joinText("Rodrigo", "Santana");

// Saída no console:
// Rodrigo
// Rodrigo Santana
```

Definir valores padrão é uma excelente prática para evitar erros e comportamentos inesperados.

## Resumo da Aula

Nesta aula, você aprendeu a:

* **Diferenciar `parâmetro`** (a variável na função) de **`argumento`** (o valor passado).
* **Usar parâmetros** para criar funções dinâmicas e flexíveis.
* **Respeitar a ordem** ao passar múltiplos argumentos.
* **Definir valores padrão** para parâmetros, tornando suas funções mais seguras e previsíveis.
