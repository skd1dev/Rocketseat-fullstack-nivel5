# Selecionando Elementos com `querySelector`

## Introdução

Na aula anterior, vimos os métodos `getElementsBy...` para acessar elementos no DOM. Nesta aula, vamos aprender uma maneira mais moderna e, muitas vezes, mais poderosa de fazer a mesma coisa: utilizando o **`querySelector`** e o  **`querySelectorAll`** .

A grande vantagem desses métodos é que eles utilizam a mesma sintaxe de **seletores CSS** que você já usa para estilizar suas páginas, tornando a seleção de elementos mais intuitiva e flexível.

## 1. Acessando um Único Elemento com `querySelector`

O método `querySelector()` retorna o **primeiro elemento** do documento que corresponde ao seletor CSS especificado. Se nenhum elemento for encontrado, ele retorna `null`.

### Selecionando por ID

Para selecionar um elemento por ID com CSS, usamos o caractere `#` (cerquilha).

**JavaScript (Selecionando por ID com `querySelector`)**

**JavaScript**

```
// Usamos a sintaxe de seletor CSS '#guest-2'
const guestTwo = document.querySelector('#guest-2');

console.log(guestTwo);
// Saída: <li id="guest-2" class="guest">Mike</li>
```

Isso é muito parecido com o `getElementById()`, mas aqui precisamos especificar que estamos buscando um ID através do `#`.

### Selecionando por Classe

Para selecionar por classe, usamos o caractere `.` (ponto). Lembre-se: `querySelector` sempre retornará apenas o **primeiro** elemento que encontrar, mesmo que vários elementos compartilhem a mesma classe.

**JavaScript (Selecionando por Classe com `querySelector`)**

**JavaScript**

```
// Existem dois elementos com a classe 'guest', mas este método pegará apenas o primeiro.
const firstGuest = document.querySelector('.guest');

console.log(firstGuest);
// Saída: <li id="guest-1" class="guest">Rodrigo</li>
```

Para resolver isso e pegar todos os elementos, usamos a variação `querySelectorAll`.

---

## 2. Acessando Múltiplos Elementos com `querySelectorAll`

O método `querySelectorAll()` é a contraparte do `querySelector`. Ele retorna uma **`NodeList`** (uma lista de nós) estática com **todos** os elementos do documento que correspondem ao seletor CSS especificado.

**JavaScript (Selecionando Todos os Elementos por Classe)**

**JavaScript**

```
// Agora, selecionamos TODOS os elementos que têm a classe 'guest'
const allGuests = document.querySelectorAll('.guest');

console.log(allGuests);
// Saída: NodeList(2) [li#guest-1.guest, li#guest-2.guest]
```

O resultado é uma `NodeList`, que funciona de forma muito parecida com um array. Podemos acessar seus itens por índice e ver seu comprimento (`.length`). Ao inspecionar no console, você pode passar o mouse sobre cada item da lista para vê-lo destacado na página.

## Resumo da Aula

Nesta aula, você aprendeu a usar os seletores modernos e versáteis do JavaScript para interagir com o DOM.

* **`document.querySelector('seletor-css')`** :
* Utiliza a sintaxe de seletores CSS (`#id`, `.classe`, `tag`, etc.).
* Retorna **apenas o primeiro** elemento encontrado que corresponde ao seletor.
* **`document.querySelectorAll('seletor-css')`** :
* Também utiliza a sintaxe de seletores CSS.
* Retorna uma **`NodeList`** com **todos** os elementos encontrados que correspondem ao seletor.

Estes dois métodos são extremamente poderosos e são os mais utilizados no desenvolvimento moderno para selecionar elementos na DOM.
