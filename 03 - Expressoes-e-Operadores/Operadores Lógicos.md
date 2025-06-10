
# Operadores Lógicos em JavaScript

---

## Introdução

Nesta aula, vamos nos aprofundar nos **operadores lógicos** do JavaScript. Eles são ferramentas cruciais para a **tomada de decisões** e para controlar o fluxo das suas aplicações, baseando-se em testes lógicos. Embora ainda não estejamos diretamente em estruturas de condição, entender esses operadores é fundamental, pois eles serão a base de muitas verificações que faremos em breve.

---

## Preparando o Cenário

Para nossos exemplos, vamos criar duas variáveis booleanas. Elas simularão a verificação de um e-mail e uma senha em um processo de login:

**JavaScript**

```
let emailCorreto = true;    // Indica se o e-mail inserido está correto
let senhaCorreta = false;   // Indica se a senha inserida está correta
```

Com essas variáveis, podemos simular diferentes situações de login.

---

## O Operador Lógico "E" (`&&` - AND)

O operador  **AND** , representado por dois "e comerciais" (`&&`), retorna `true` (verdadeiro)  **apenas se todas as condições avaliadas forem verdadeiras** . Se ao menos uma das condições for `false` (falsa), o resultado de toda a expressão será `false`.

Imagine que, para liberar o acesso a um usuário, **tanto o e-mail QUANTO a senha** devem estar corretos.

### Tabela Verdade do `&&` (AND)

| **Condição 1** | **Condição 2** | **Resultado (Condição 1 && Condição 2)** |
| ---------------------- | ---------------------- | -------------------------------------------------- |
| `true`               | `true`               | `true`                                           |
| `true`               | `false`              | `false`                                          |
| `false`              | `true`               | `false`                                          |
| `false`              | `false`              | `false`                                          |

### Exemplos com `&&`

**JavaScript**

```
console.log("--- Operador E (&& - AND) ---");

// Cenário 1: Email correto (true), Senha correta (true)
emailCorreto = true;
senhaCorreta = true;
console.log(`Email correto (${emailCorreto}) E Senha correta (${senhaCorreta}): ${emailCorreto && senhaCorreta}`);
// Saída: true (Acesso liberado, ambos são verdadeiros)

// Cenário 2: Email correto (true), Senha incorreta (false)
emailCorreto = true;
senhaCorreta = false;
console.log(`Email correto (${emailCorreto}) E Senha correta (${senhaCorreta}): ${emailCorreto && senhaCorreta}`);
// Saída: false (Acesso negado, pois a senha está incorreta)
```

No exemplo de login, se o e-mail e a senha estiverem corretos (`true`), o acesso é liberado. Mas se a senha estiver incorreta (`false`), mesmo que o e-mail esteja certo, o acesso é negado.

---

## O Operador Lógico "OU" (`||` - OR)

O operador  **OR** , representado por dois "pipes" (`||`), retorna `true` (verdadeiro)  **se pelo menos uma das condições avaliadas for verdadeira** . Ele só retorna `false` (falso) se **todas** as condições forem falsas.

Imagine que, para um usuário participar de uma promoção, ele precisa ser VIP **OU** ter feito uma compra recente. Basta que uma dessas condições seja verdadeira.

### Tabela Verdade do `||` (OR)

| Condição 1 | Condição 2 | Resultado (`Condição 1 || Condição 2`) |
| :--------: | :--------: | :------------------------------------: |
| `true`     | `true`     | `true`                                 |
| `true`     | `false`    | `true`                                 |
| `false`    | `true`     | `true`                                 |
| `false`    | `false`    | `false`                                |

### Exemplos com `||`

**JavaScript**

```
console.log("\n--- Operador OU (|| - OR) ---");

// Cenário 1: Email correto (true), Senha incorreta (false)
emailCorreto = true;
senhaCorreta = false;
console.log(`Email correto (${emailCorreto}) OU Senha correta (${senhaCorreta}): ${emailCorreto || senhaCorreta}`);
// Saída: true (Basta um ser verdadeiro para o OR retornar verdadeiro)

// Cenário 2: Email incorreto (false), Senha incorreta (false)
emailCorreto = false;
senhaCorreta = false;
console.log(`Email correto (${emailCorreto}) OU Senha correta (${senhaCorreta}): ${emailCorreto || senhaCorreta}`);
// Saída: false (Ambos são falsos, então o OR retorna falso)
```

---

## O Operador Lógico de Negação (`!` - NOT)

O operador  **NOT** , representado por um ponto de exclamação (`!`), simplesmente **inverte o valor booleano** da condição que o segue. Se a condição for `true`, `!` a torna `false`, e vice-versa. Ele é um operador unário, ou seja, opera sobre um único valor.

### Tabela Verdade do `!` (NOT)

| **Condição** | **Resultado (!Condição)** |
| -------------------- | --------------------------------- |
| `true`             | `false`                         |
| `false`            | `true`                          |

### Exemplos com `!`

**JavaScript**

```
console.log("\n--- Operador Negação (! - NOT) ---");

senhaCorreta = false; // A senha está incorreta

console.log(`O valor original de senhaCorreta é: ${senhaCorreta}`); // Saída: false
console.log(`Invertendo o valor de senhaCorreta: ${!senhaCorreta}`); // Saída: true (transformou o false em true)

emailCorreto = true; // O email está correto
console.log(`O valor original de emailCorreto é: ${emailCorreto}`); // Saída: true
console.log(`Invertendo o valor de emailCorreto: ${!emailCorreto}`); // Saída: false (transformou o true em false)
```

É importante notar que o operador `!`  **não altera o valor da variável original** . Ele apenas inverte o seu valor booleano no momento da avaliação da expressão.

---

## Combinando Operadores Lógicos

Você pode combinar múltiplos operadores lógicos em uma mesma expressão e até mesmo misturar `&&`, `||` e `!`. Lembre-se de usar **parênteses `()`** para controlar a  **ordem de precedência** , assim como fazemos com os operadores aritméticos.

**Exemplo:**

**JavaScript**

```
let isAdmin = true;
let hasPermission = false;

// O usuário é um administrador E (tem o email correto OU tem permissão)
let podeAcessarFuncionalidade = isAdmin && (emailCorreto || hasPermission);
console.log(`\nAcesso à funcionalidade (isAdmin && (emailCorreto || hasPermission)): ${podeAcessarFuncionalidade}`);
// Saída: true (true && (true || false) -> true && true -> true)
```

Dominar esses três operadores lógicos (`&&`, `||`, `!`) é fundamental, pois eles são a base para construir a inteligência e o comportamento dinâmico de suas aplicações.

---
