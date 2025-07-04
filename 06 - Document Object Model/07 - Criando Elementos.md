
# Criando e Adicionando Elementos na DOM com JavaScript

Nesta aula, vamos aprender como criar novos elementos HTML dinamicamente com JavaScript e inseri-los no Document Object Model (DOM). Isso permite manipular o conteúdo de uma página web de forma interativa.

## Estrutura Inicial

Vamos partir de uma lista de convidados simples em nosso HTML. A estrutura consiste em uma lista não ordenada (`<ul>`) com alguns itens de lista (`<li>`), cada um contendo um `<span>` com o nome do convidado.

**HTML:**

**HTML**

```
<ul class="guest-list">
  <li class="guest"><span>Rodrigo</span></li>
  <li class="guest"><span>Mike</span></li>
</ul>
```

O objetivo é adicionar um novo convidado a esta lista usando apenas JavaScript.

## 1. Selecionando o Elemento Pai

Primeiro, precisamos de uma referência ao elemento onde queremos adicionar nosso novo item. Neste caso, é a lista `<ul>`. Usamos `document.querySelector` para selecioná-la.

**JavaScript:**

**JavaScript**

```
const guestsList = document.querySelector('ul');
```

## 2. Criando Novos Elementos com `createElement`

Para criar um novo elemento, usamos o método `document.createElement()`, passando o nome da tag HTML como uma string. Vamos criar um novo `<li>` e um `<span>` para o nome do novo convidado.

**JavaScript**

```
// Cria o elemento <li>
const newGuest = document.createElement('li');

// Cria o elemento <span>
const guestName = document.createElement('span');
```

## 3. Adicionando Conteúdo e Estrutura

Com os elementos criados, eles ainda estão vazios e não conectados à DOM.

* **Adicionar texto:** Usamos a propriedade `.textContent` para definir o conteúdo de texto de um elemento.
  **JavaScript**

  ```
  guestName.textContent = 'Diego';
  ```
* **Adicionar um elemento dentro de outro:** Para colocar o `<span>` dentro do `<li>`, usamos o método `.append()`.
  **JavaScript**

  ```
  // Adiciona o <span> (guestName) dentro do <li> (newGuest)
  newGuest.append(guestName);
  ```

Neste ponto, a variável `newGuest` contém o seguinte elemento em memória: `<li><span>Diego</span></li>`.

## 4. Adicionando Classes para Estilização

O novo elemento `<li>` não possui a classe `"guest"` que os outros itens da lista têm. Podemos adicioná-la usando a propriedade `classList` e seu método `.add()`.

**JavaScript**

```
newGuest.classList.add('guest');
```

Agora, o nosso `newGuest` está completo e estilizado: `<li class="guest"><span>Diego</span></li>`.

## 5. Adicionando o Elemento à DOM

Finalmente, para que o novo convidado apareça na página, adicionamos o elemento `newGuest` à lista `guestsList` que selecionamos no início.

### `append()` vs. `prepend()`

Temos duas opções principais para inserir o elemento:

* **`.append()`** : Adiciona o novo elemento como o **último filho** do elemento pai.
  **JavaScript**

```
  // Adiciona "Diego" no final da lista
  guestsList.append(newGuest);
```

  **Resultado:**

1. Rodrigo
2. Mike
3. Diego

* **`.prepend()`** : Adiciona o novo elemento como o **primeiro filho** do elemento pai.
  **JavaScript**

```
  // Adiciona "Diego" no início da lista
  guestsList.prepend(newGuest);
```

  **Resultado:**

1. Diego
2. Rodrigo
3. Mike

> **Nota:** Tanto `append()` quanto `prepend()` permitem adicionar múltiplos elementos de uma vez, separados por vírgula. Ex: `elementoPai.append(elem1, elem2);`.

### `appendChild()`

Existe um método mais antigo chamado `.appendChild()`. Ele funciona de forma semelhante ao `.append()`, mas com uma limitação principal: ele aceita apenas **um** elemento (nó) por vez.

**JavaScript**

```
// Funciona da mesma forma que append, mas só aceita um argumento
guestsList.appendChild(newGuest);
```

## Código Completo

**JavaScript**

```
// 1. Seleciona a lista pai na DOM
const guestsList = document.querySelector('ul');

// 2. Cria o elemento <li> para o novo convidado
const newGuest = document.createElement('li');

// 3. Adiciona a classe para estilização
newGuest.classList.add('guest');

// 4. Cria o elemento <span> para o nome
const guestName = document.createElement('span');
guestName.textContent = 'Diego';

// 5. Adiciona o <span> dentro do <li>
newGuest.append(guestName);

// 6. Adiciona o novo <li> (com tudo dentro) à lista principal na página
// Use .append() para adicionar no final
guestsList.append(newGuest);

// Ou use .prepend() para adicionar no começo
// guestsList.prepend(newGuest);
```
