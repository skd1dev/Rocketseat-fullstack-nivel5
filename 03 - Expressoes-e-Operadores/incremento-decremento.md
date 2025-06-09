# Operadores de Incremento e Decremento em JavaScript

Nesta aula, vamos explorar os **operadores de incremento e decremento** em JavaScript, que nos permitem adicionar ou subtrair valores de variáveis de forma concisa.

## Cenário Inicial

Vamos começar com um cenário simples. Imagine que temos uma variável chamada `number` que inicia com o valor `10`:

**JavaScript**

```
let number = 10;
console.log(number); // Saída: 10
```

Se quisermos adicionar `1` ao conteúdo de `number`, poderíamos fazer da seguinte forma:

**JavaScript**

```
number = number + 1;
console.log(number); // Saída: 11
```

---

## Operador de Incremento (`++`)

O JavaScript oferece uma forma mais elegante de fazer isso usando o **operador de incremento** (`++`).

### Incremento Pós-fixado (`number++`)

Quando o `++` é colocado **depois** da variável (`number++`), o valor é incrementado **após** a linha de código ser executada. Isso significa que se você tentar exibir o valor na mesma linha, ele ainda mostrará o valor original antes do incremento.

**JavaScript**

```
let number = 10;
console.log(number++); // Saída: 10 (o incremento ocorre depois que o valor é exibido)
console.log(number);   // Saída: 11 (agora o valor já está incrementado)
```

**Lembre-se:** O incremento ocorre **após** a operação na linha em que `number++` é usado.

### Incremento Pré-fixado (`++number`)

Quando o `++` é colocado **antes** da variável (`++number`), o valor é incrementado **antes** da linha de código ser executada. Isso significa que o valor já estará atualizado quando a linha for processada.

**JavaScript**

```
let number = 10;
console.log(++number); // Saída: 11 (o incremento ocorre antes que o valor seja exibido)
console.log(number);   // Saída: 11 (o valor já está incrementado)
```

---

## Operador de Decremento (`--`)

Assim como o incremento, temos o **operador de decremento** (`--`) para subtrair `1` de uma variável. Ele segue a mesma lógica do incremento em relação à sua posição (pré ou pós-fixada).

### Decremento Pós-fixado (`number--`)

O decremento ocorre **após** a execução da linha.

**JavaScript**

```
let number = 12; // Supondo que 'number' seja 12
console.log(number--); // Saída: 12 (o decremento ocorre depois)
console.log(number);   // Saída: 11 (agora o valor já está decrementado)
```

### Decremento Pré-fixado (`--number`)

O decremento ocorre **antes** da execução da linha.

**JavaScript**

```
let number = 12; // Supondo que 'number' seja 12
console.log(--number); // Saída: 11 (o decremento ocorre antes)
console.log(number);   // Saída: 11 (o valor já está decrementado)
```

---

## Incremento/Decremento de Múltiplos Valores

Os operadores `++` e `--` são excelentes para adicionar ou subtrair `1`. No entanto, e se você quiser adicionar ou remover valores maiores (ex: `2`, `10`, etc.)?

Para isso, usamos os  **operadores de atribuição composta** :

### Adicionar Valores (`+=`)

O operador `+=` permite que você adicione um valor específico à variável.

**JavaScript**

```
let number = 12; // Supondo que 'number' seja 12
number += 10; // Equivalente a: number = number + 10;
console.log(number); // Saída: 22
```

### Remover Valores (`-=`)

O operador `-=` permite que você subtraia um valor específico da variável.

**JavaScript**

```
let number = 22; // Supondo que 'number' seja 22
number -= 2; // Equivalente a: number = number - 2;
console.log(number); // Saída: 20
```

Esses operadores (`+=`, `-=`) são variações mais concisas de `number = number + valor` ou `number = number - valor`, tornando seu código mais legível e eficiente.

---

### Exemplo Final

Vamos observar a sequência de operações para ver como os valores se alteram:

**JavaScript**

```
let number = 10;
console.log(`Initial: ${number}`); // Initial: 10

// Incremento Pós-fixado
console.log(`Post-increment: ${number++}`); // Post-increment: 10
console.log(`After post-increment: ${number}`); // After post-increment: 11

// Incremento Pré-fixado
console.log(`Pre-increment: ${++number}`); // Pre-increment: 12
console.log(`After pre-increment: ${number}`); // After pre-increment: 12

// Decremento Pós-fixado
console.log(`Post-decrement: ${number--}`); // Post-decrement: 12
console.log(`After post-decrement: ${number}`); // After post-decrement: 11

// Decremento Pré-fixado
console.log(`Pre-decrement: ${--number}`); // Pre-decrement: 10
console.log(`After pre-decrement: ${number}`); // After pre-decrement: 10

// Adicionando múltiplos valores
number += 20;
console.log(`Add 20: ${number}`); // Add 20: 30

// Removendo múltiplos valores
number -= 10;
console.log(`Subtract 10: ${number}`); // Subtract 10: 20
```

---
