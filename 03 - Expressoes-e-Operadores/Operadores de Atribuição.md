
# Operadores de Atribuição

---

## Introdução

Nessa aula, vamos focar nos  **operadores de atribuição** , que são fundamentais para manipular valores em variáveis. Você já usa um deles o tempo todo: o sinal de  **igual (`=`)** , que é o operador de atribuição básico. Ele serve para "colocar" um valor dentro de uma variável.

**JavaScript**

```
let value; // Variável declarada, mas sem valor inicial.

// Operador de atribuição simples: =
value = 1; // Atribuindo o valor 1 à variável 'value'
console.log(value); // Saída: 1
```

Além da atribuição simples, o JavaScript oferece operadores de atribuição compostos, que combinam uma operação matemática (ou outra) com a atribuição. Isso torna seu código mais conciso e legível.

---

## Operadores de Atribuição Composta

Os operadores de atribuição composta realizam uma operação e, em seguida, atribuem o resultado de volta à variável. Eles são uma forma abreviada de escrever `variável = variável [operador] valor`.

### Atribuição com Adição (`+=`)

O operador `+=` adiciona o valor à direita ao valor atual da variável e atribui o resultado de volta à variável.

**JavaScript**

```
value = 1; // Resetando o valor para 1
value += 2; // Equivalente a: value = value + 2;
console.log(value); // Saída: 3
```

### Atribuição com Subtração (`-=`)

O operador `-=` subtrai o valor à direita do valor atual da variável e atribui o resultado de volta à variável.

**JavaScript**

```
value = 3; // Valor atual é 3 (do exemplo anterior)
value -= 2; // Equivalente a: value = value - 2;
console.log(value); // Saída: 1
```

### Atribuição com Multiplicação (`*=`)

O operador `*=` multiplica o valor atual da variável pelo valor à direita e atribui o resultado de volta à variável.

**JavaScript**

```
value = 2; // Definindo um novo valor para melhor visualização
value *= 3; // Equivalente a: value = value * 3;
console.log(value); // Saída: 6
```

### Atribuição com Divisão (`/=`)

O operador `/=` divide o valor atual da variável pelo valor à direita e atribui o resultado de volta à variável.

**JavaScript**

```
value = 6; // Valor atual é 6
value /= 2; // Equivalente a: value = value / 2;
console.log(value); // Saída: 3
```

### Atribuição com Resto da Divisão (`%=`)

O operador `%=` calcula o resto da divisão do valor atual da variável pelo valor à direita e atribui o resto de volta à variável.

**JavaScript**

```
value = 3; // Valor atual é 3
value %= 2; // Equivalente a: value = value % 2; (3 dividido por 2, sobra 1)
console.log(value); // Saída: 1
```

### Atribuição com Exponenciação (`**=`)

O operador `**=` eleva o valor atual da variável à potência do valor à direita e atribui o resultado de volta à variável.

**JavaScript**

```
value = 3; // Definindo um novo valor para melhor visualização
value **= 2; // Equivalente a: value = value ** 2; (3 elevado a 2 = 9)
console.log(value); // Saída: 9
```

---

## Conclusão

Os operadores de atribuição composta são uma forma eficiente e elegante de modificar o valor de uma variável e reatribuir o resultado na mesma linha. Eles tornam seu código mais limpo e direto, combinando uma operação com a própria atribuição.
