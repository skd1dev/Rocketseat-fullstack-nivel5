
---

# Aula: Tipos de Dados em JavaScript

## A Importância dos Tipos de Dados

Os **tipos de dados** são fundamentais em programação, pois definem o conteúdo de uma variável. Para a linguagem, é crucial saber se está lidando com um número, um texto ou outro tipo de dado. Isso garante que operações, como cálculos matemáticos, sejam realizadas corretamente (números com números, e não com textos).

Entender os tipos de dados nos permite manipular as variáveis da maneira correta e executar as operações desejadas.

---

## JavaScript: Uma Linguagem de Tipos Dinâmicos

O JavaScript é uma linguagem com  **tipos dinâmicos** . Isso significa que o tipo de uma variável é definido dinamicamente pelo valor que lhe é atribuído. Diferente de outras linguagens, em JavaScript não declaramos o tipo de dado ao criar uma variável.

Por ser dinâmica, uma mesma variável pode ter seu tipo alterado ao longo do código. Por exemplo, uma variável que armazena um número pode, posteriormente, receber um texto.

> analogy  **Analogia do Copo** : Pense em uma variável como um copo. O objetivo do copo é sempre o mesmo: armazenar um conteúdo. No entanto, o conteúdo que você coloca dentro dele pode mudar – pode ser água agora e refrigerante depois. A variável (o copo) continua a mesma, mas o seu conteúdo (o valor e, consequentemente, o tipo) pode ser alterado.

---

## Tipos Primitivos

Tipos primitivos são os tipos de dados básicos já disponíveis na própria linguagem. Embora seja possível criar tipos próprios, o foco inicial é nos primitivos mais comuns em JavaScript.

### Principais Tipos Primitivos

* **String** : Usado para representar  **texto** .
* **Number** : Usado para representar **números** (inteiros ou de ponto flutuante).
* **Boolean** : Representa um valor lógico, que pode ser **verdadeiro (`true`)** ou  **falso (`false`)** .
* **Null** : Indica que uma variável possui um valor **vazio** ou nulo intencionalmente.
* **Undefined** : Atribuído automaticamente pelo JavaScript a uma variável que foi declarada, mas que  **ainda não recebeu um valor** . Um exemplo disso ocorre com o  *hoisting* , onde uma variável pode ser acessada antes de sua atribuição, resultando em `undefined`.

### Próximos Passos

Outros tipos importantes como **Object** e **Array** serão estudados em detalhes mais à frente. Por agora, o foco é entender e praticar o uso dos tipos primitivos.
