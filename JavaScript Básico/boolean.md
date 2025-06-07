

## 🧠 Resumo da Aula: Foco no Tipo de Dado `BOOLEAN` em JavaScript

Esta aula explica o tipo de dado **`BOOLEAN`** em JavaScript, essencial para lógica de programação, pois representa valores de **verdadeiro** ou  **falso** .

### ⚖️ O que é o Tipo `BOOLEAN`?

O tipo de dado **`BOOLEAN`** armazena apenas dois valores possíveis: **`true`** (verdadeiro) ou **`false`** (falso). Ele é fundamental para tomar decisões e controlar o fluxo do seu código.

* **Valores Exclusivos** : Uma variável booleana pode ser `true` ou `false`, mas nunca ambos ao mesmo tempo.
* **Exemplos Básicos** :

  **JavaScript**

```
  console.log(true);  // Exibe: true
  console.log(false); // Exibe: false
```

* **Verificação de Tipo** : Assim como outros tipos, você pode usar o operador **`typeof`** para confirmar que um valor é do tipo `boolean`.

  **JavaScript**

```
  let isConnected = true;
  console.log(typeof isConnected); // Exibe: "boolean"
```

---

### 💡 Uso Comum de Booleanos na Programação

Booleanos são amplamente utilizados para representar estados, condições ou resultados de verificações.

* **Variáveis de Estado** : É muito comum usar variáveis booleanas para indicar se algo está "ligado/desligado", "ativo/inativo" ou "carregando/concluído". Uma convenção comum é prefixar o nome da variável com "is" ou "has" (ex: `isLoading`, `hasPermission`).

  **JavaScript**

```
  let isLoading = true; // Indica que algo está carregando
  console.log(isLoading); // Exibe: true

  // Mais tarde no código, quando o carregamento terminar:
  isLoading = false;
  console.log(isLoading); // Exibe: false
```

* **Lógica Condicional** : Booleanos são a base de estruturas condicionais (como `if/else`) e laços de repetição, permitindo que o programa execute diferentes blocos de código com base em uma condição ser verdadeira ou falsa.

---

### 📜 Origem do Nome: George Boole

O nome "boolean" é uma homenagem ao matemático e filósofo britânico  **George Boole** . Ele foi o criador da  **Álgebra Booleana** , um sistema de lógica matemática que lida com valores de verdadeiro e falso, e que forma a base de toda a computação digital.

---

Compreender o tipo `BOOLEAN` é um passo crucial para escrever código JavaScript que possa tomar decisões e responder dinamicamente a diferentes situações.
