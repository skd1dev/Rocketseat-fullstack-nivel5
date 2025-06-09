

## 🧠 Resumo da Aula: Operadores Aritméticos em JavaScript

Esta aula detalha os **operadores aritméticos** em JavaScript, que são símbolos utilizados para realizar operações matemáticas. Entender cada um deles é fundamental para efetuar cálculos e manipular valores numéricos em seu código.

### ➕ Adição (`+`)

O operador de adição (`+`) é usado para somar números.

* **Soma de Números** :

  **JavaScript**

```
  console.log("Soma: ", 12 + 8); // Exibe: "Soma: 20"
  console.log("Soma com float: ", 12.5 + 8); // Exibe: "Soma com float: 20.5"
```

* **CUIDADO: Concatenação com Strings** : Se um dos operandos (ou ambos) for uma  **string** , o operador `+` realizará uma **concatenação** (união de textos) em vez de uma soma aritmética. Isso ocorre devido à coerção de tipos do JavaScript.

  **JavaScript**

```
  console.log("Concatenação: ", "12" + "8"); // Exibe: "Concatenação: 128"
  console.log("Coerção (string + number): ", "12" + 8); // Exibe: "Coerção (string + number): 128"
  // O número 8 é convertido para string "8" e concatenado com "12".
```

  Para operações aritméticas, sempre garanta que os operandos sejam do tipo `NUMBER`.

---

### ➖ Subtração (`-`)

O operador de subtração (`-`) é usado para diminuir um número de outro.

**JavaScript**

```
console.log("Subtração: ", 12 - 8); // Exibe: "Subtração: 4"
console.log("Subtração: ", 12 - 10); // Exibe: "Subtração: 2"
```

---

### ✖️ Multiplicação (`*`)

O operador de multiplicação (`*`, o asterisco) é usado para multiplicar números.

**JavaScript**

```
console.log("Multiplicação: ", 3 * 5.5); // Exibe: "Multiplicação: 16.5"
```

---

### ➗ Divisão (`/`)

O operador de divisão (`/`, a barra) é usado para dividir números.

**JavaScript**

```
console.log("Divisão: ", 12 / 2); // Exibe: "Divisão: 6"
```

---

### ➗ Resto da Divisão (`%`)

O operador de resto da divisão (`%`, o símbolo de porcentagem) retorna o resto de uma operação de divisão.

* **Exemplo** :
  **JavaScript**

```
  console.log("Resto da divisão (12 por 2): ", 12 % 2); // Exibe: "Resto da divisão (12 por 2): 0" (não sobrou nada)
  console.log("Resto da divisão (13 por 2): ", 13 % 2); // Exibe: "Resto da divisão (13 por 2): 1" (sobra 1)
```

* **Uso Comum** : Esse operador é muito útil para verificar se um número é  **par ou ímpar** . Se o resto da divisão de um número por `2` for `0`, o número é par; caso contrário, é ímpar.

---

### 📈 Exponenciação (`**`)

O operador de exponenciação (`**`, dois asteriscos) é usado para calcular a potência de um número (um número elevado a outro).

**JavaScript**

```
console.log("Exponencial (3 elevado a 3): ", 3 ** 3); // Exibe: "Exponencial (3 elevado a 3): 27" (3 * 3 * 3)
```

---

Esses operadores aritméticos são as ferramentas básicas para realizar qualquer cálculo em JavaScript, permitindo desde somas simples até operações mais complexas.
