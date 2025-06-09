
---

## 📝 Resumo da Aula: Criando Variáveis com Valores Fixos (Constantes)

Nesta aula, exploramos cenários onde precisamos armazenar um valor em uma variável de forma temporária, mas com a garantia de que esse valor **não será alterado** – ou seja, um valor fixo.

---

### 🤔 Quando Usar Valores Fixos?

Haverá momentos em que você precisará ou desejará:

* Guardar um conteúdo específico.
* Garantir que este conteúdo permaneça inalterado durante a execução de uma parte do código.

Para esses casos, em vez de uma variável comum (cujo valor pode mudar), utilizamos  **constantes** .

---

### ✨ O que é uma Constante?

Uma **constante** compartilha o princípio de uma variável: é um espaço na memória que armazena um valor temporariamente. A grande diferença é que, uma vez atribuído,  **seu valor é fixo e não pode ser modificado** .

* **Palavra-chave** : Para criar uma constante, utilizamos a palavra reservada `const`.
* **Nomeação** : Assim como as variáveis, constantes recebem um nome (identificador).
* **Atribuição** : Um valor é atribuído à constante no momento da sua criação.

**Exemplo Básico:**

**JavaScript**

```
const number = 42;
```

Neste exemplo, `number` é uma constante que armazena o valor `42`.

---

### 🔒 A Imutabilidade da Constante

A principal característica de uma constante é que seu valor não pode ser reatribuído após a inicialização.

* **Definição** : Uma constante cria uma "variável" cujo valor é fixo (não pode ser alterado).

**Demonstração Prática:**

1. **Exibindo o valor da constante:**

   **JavaScript**

   ```
   const pi = 3.14159;
   console.log(pi); // Saída: 3.14159
   ```

   O comportamento inicial é similar ao de uma variável, exibindo o valor armazenado.
2. **Tentando alterar o valor da constante:**

   **JavaScript**

   ```
   const meuNumeroFavorito = 7;
   console.log(meuNumeroFavorito); // Saída: 7

   // A linha abaixo irá gerar um erro:
   // meuNumeroFavorito = 10;
   // console.log(meuNumeroFavorito);
   ```

   Se tentarmos atribuir um novo valor a `meuNumeroFavorito` (ex: `meuNumeroFavorito = 10;`), o programa apresentará um  **erro** . A mensagem de erro normalmente indica que uma atribuição a uma variável constante (`assignment to constant variable`) não é permitida.

Comentário no código original:

O instrutor deixou claro que a tentativa de reatribuição "irá gerar um erro, porque o valor não pode ser alterado."

---

### 🎯 Por que e Quando Usar `const`?

Utilizamos `const` quando queremos:

* Armazenar um valor na memória.
* Garantir que esse conteúdo seja **fixo** e não sofra alterações acidentais ou intencionais ao longo do código.

Essa estratégia será útil em diversos cenários, especialmente durante o desenvolvimento de projetos.

---

### 💡 Observação Importante: Objetos e Arrays

O instrutor mencionou que haverá algumas "exceções" ou particularidades quando trabalharmos com tipos de dados mais complexos, como **objetos** e, especificamente,  **arrays** , declarados com `const`.

* **O que isso significa (adiantando um pouco)** : Para objetos e arrays declarados com `const`, a referência ao objeto/array em si não pode ser alterada (você não pode fazer a constante apontar para um *novo* objeto/array). No entanto, o conteúdo *interno* do objeto (suas propriedades) ou do array (seus elementos) geralmente pode ser modificado.

Essas particularidades serão ressaltadas e explicadas em detalhes quando esses tópicos (objetos e arrays) forem abordados.

---

### 🚀 Principal Lição

Por agora, o importante é ter no radar:

> **`const` é utilizada quando queremos criar um identificador para um conteúdo que deve permanecer fixo.**

Isso traz mais segurança e clareza às intenções do seu código.
