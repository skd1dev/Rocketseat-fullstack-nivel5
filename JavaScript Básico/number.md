

## 🧠 Resumo da Aula: Foco no Tipo de Dado `NUMBER` em JavaScript

Esta aula aborda o tipo de dado **`NUMBER`** em JavaScript, que é fundamental para trabalhar com valores numéricos. Compreender suas características e como o JavaScript lida com diferentes representações numéricas é essencial para qualquer desenvolvedor.

### 🔢 O Tipo `NUMBER` no JavaScript

O tipo **`NUMBER`** em JavaScript é usado para representar tanto números inteiros quanto números de ponto flutuante (com casas decimais). O interpretador JavaScript os reconhece e os trata de forma específica.

* **Identificação Visual** : No `console.log()`, números geralmente aparecem em uma cor diferente de strings (que ficam entre aspas), servindo como uma dica visual do seu tipo.
* **Verificação de Tipo** : Você pode usar o operador **`typeof`** para confirmar que um valor é do tipo `NUMBER`.

  **JavaScript**

```
  console.log(typeof 5); // Exibe: "number"
```

---

### 📊 Possibilidades do Tipo `NUMBER`

O tipo `NUMBER` em JavaScript é bastante flexível e pode armazenar diversos formatos de números:

* **Inteiros Positivos** : São números sem casas decimais e maiores que zero.
  **JavaScript**

```
  console.log(5); // Exibe: 5
```

* **Inteiros Negativos** : São números sem casas decimais e menores que zero.
  **JavaScript**

```
  console.log(-5); // Exibe: -5
```

* **Números Reais (Float)** : Também conhecidos como "float", são números com casas decimais. É importante notar que em JavaScript (e na maioria das linguagens de programação), o **ponto (`.`)** é usado como separador decimal, e não a vírgula.
  **JavaScript**

```
  console.log(7.5); // Exibe: 7.5
  console.log(125.70); // Exibe: 125.7
```

* **Atenção** : Usar vírgula (`,`) em vez de ponto (`.`) fará com que o JavaScript interprete os valores como itens separados em uma lista, o que pode levar a erros lógicos.

---

### ⚠️ `NaN` (Not a Number)

Quando uma operação matemática inválida é realizada, o JavaScript retorna um valor especial do tipo `NUMBER` chamado **`NaN`** (Not a Number - Não é um Número).

* **Ocorrência** : Isso acontece, por exemplo, ao tentar dividir um número por um texto, uma operação que não faz sentido matematicamente.

  **JavaScript**

```
  console.log(12.5 / "meu nome"); // Exibe: NaN
```

* **Significado** : `NaN` indica que o resultado da operação não pôde ser representado como um número válido.

---

### ✅ Conclusão

O tipo `NUMBER` é a base para qualquer operação matemática em JavaScript. É crucial entender como ele lida com inteiros, decimais (usando ponto) e o comportamento `NaN` para escrever códigos robustos e evitar surpresas em cálculos e manipulações numéricas.
