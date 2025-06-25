# Acessando Elementos no DOM

## Introdução

Muito bem, agora que entendemos o que é o DOM e como inspecioná-lo, vamos dar o próximo passo: acessar os elementos da página utilizando JavaScript. A partir do nosso arquivo `scripts.js` (que já está conectado ao HTML), vamos aprender a selecionar elementos específicos para que possamos, futuramente, manipulá-los.

Nosso ponto de partida para qualquer interação com o DOM é o objeto global `document`.

## O Objeto `document`

O objeto `document` é uma variável especial, sempre disponível para nós no JavaScript quando executado em um navegador. Ele representa toda a página e é a porta de entrada para acessarmos qualquer nó da árvore DOM.

Vamos começar visualizando este objeto.

**JavaScript (Visualizando o Documento)**

**JavaScript**

```
console.log(document);
```

Ao executar este código e abrir o console do navegador, você verá uma representação interativa de toda a sua estrutura HTML. Ao passar o mouse sobre os elementos nesta estrutura, eles serão destacados na página, pois o que vemos no console é uma referência direta aos elementos vivos no DOM.

### Acessando Propriedades Simples: O Título

O objeto `document` tem várias propriedades. Uma bem simples de acessar é o título da página.

**JavaScript (Obtendo o Título)**

**JavaScript**

```
console.log(document.title);

// Saída no console:
// Aulas de Javascript
```

---

## Seletores de Elementos

Para selecionar elementos específicos, usamos métodos disponíveis no objeto `document`. Vamos ver os principais.

### 1. Acessando por ID (`getElementById`)

O ID é um identificador único para um elemento na página. Este é o método mais rápido e direto para selecionar um único elemento.

**JavaScript (Selecionando por ID)**

**JavaScript**

```
// O método getElementById retorna um ÚNICO elemento.
const guestTwo = document.getElementById('guest-2');

console.log(guestTwo);
// Saída: <li id="guest-2" class="guest">Mike</li>
```

> **Dica:** Para inspecionar todas as propriedades de um objeto de elemento, use `console.dir()`. Por exemplo, `console.dir(guestTwo)` mostrará propriedades como `.textContent` ("Mike"), `.tagName` ("LI"), e muitas outras.

### 2. Acessando por Classe (`getElementsByClassName`)

Classes são usadas para agrupar múltiplos elementos que compartilham um estilo ou comportamento. Portanto, este método retorna uma **coleção** de elementos.

**JavaScript (Selecionando por Classe)**

**JavaScript**

```
// Note o plural 'Elements'. Retorna uma HTMLCollection (uma lista de elementos).
const guestsByClass = document.getElementsByClassName('guest');

console.log(guestsByClass);
// Saída: HTMLCollection(2) [li#guest-1.guest, li#guest-2.guest]
```

A `HTMLCollection` é como um array, o que significa que podemos acessar seus itens por um índice, começando do zero.

**JavaScript (Acessando Itens da Coleção)**

**JavaScript**

```
// Exibindo o primeiro elemento da lista (índice 0)
console.log(guestsByClass[0]); // Saída: <li id="guest-1" class="guest">Rodrigo</li>

// Exibindo o segundo elemento da lista (índice 1)
console.log(guestsByClass.item(1)); // Saída: <li id="guest-2" class="guest">Mike</li>
```

Você pode usar tanto a notação de colchetes `[ ]` quanto o método `.item()`.

### 3. Acessando por Tag (`getElementsByTagName`)

Podemos também selecionar todos os elementos que possuem uma determinada tag HTML, como `<li>`, `<h1>`, `<p>`, etc. Este método também retorna uma **coleção** de elementos.

**JavaScript (Selecionando por Nome da Tag)**

**JavaScript**

```
// Seleciona todos os elementos <li> da página
const guestsByTag = document.getElementsByTagName('li');

console.log(guestsByTag);
// Saída: HTMLCollection(2) [li#guest-1.guest, li#guest-2.guest]
```

Assim como no `getElementsByClassName`, você pode acessar os itens individuais da coleção através do seu índice.

## Resumo da Aula

Nesta aula, você aprendeu os métodos fundamentais para selecionar elementos no DOM:

* **`document`** : O objeto global que representa toda a página e é o nosso ponto de partida.
* **`document.getElementById('id-do-elemento')`** : Retorna **um único** elemento. É o seletor mais específico.
* **`document.getElementsByClassName('nome-da-classe')`** : Retorna uma **coleção** de todos os elementos que possuem a classe especificada.
* **`document.getElementsByTagName('nome-da-tag')`** : Retorna uma **coleção** de todos os elementos com a tag especificada.
* **Coleções** : São listas de elementos que se comportam de forma parecida com arrays, permitindo o acesso por índice (ex: `[0]`).
