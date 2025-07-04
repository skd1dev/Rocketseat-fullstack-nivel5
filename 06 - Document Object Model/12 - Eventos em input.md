# Eventos em Input no JavaScript

Neste vídeo, exploramos os **eventos de input** em JavaScript, essenciais para interagir com campos de entrada de dados. Demonstramos como capturar eventos como `keydown`, `keypress` e `change`, destacando suas diferenças e aplicações. Compreender esses eventos amplia suas possibilidades de programação e o ajuda a se tornar um especialista em JavaScript, permitindo escolher a melhor abordagem para cada situação.

---

## Selecionando o Input

Para começar, selecionamos o elemento input no DOM. Usamos `document.querySelector('input')` para obter a referência do campo onde o usuário digitará.

**JavaScript**

```
const input = document.querySelector('input');
```

---

## Evento `keydown`

O evento `keydown` é disparado quando uma tecla é pressionada. Sua principal característica é que ele  **captura tudo** , incluindo teclas especiais como `CTRL`, `SHIFT` e outras, antes mesmo do caractere ser exibido no campo.

**JavaScript**

```
input.addEventListener('keydown', (event) => {
  console.log(event); // Exibe todas as informações do evento
  console.log(event.key); // Exibe a tecla pressionada
});
```

**Características:**

* Disparado ao pressionar qualquer tecla.
* Captura teclas de controle (Ctrl, Shift, Alt, etc.).
* Pode ser usado para validar entradas em tempo real ou para criar atalhos de teclado.

Exemplo Prático:

Se você digitar "Rodrigo" e usar SHIFT para o "R" maiúsculo, o keydown capturará tanto o SHIFT quanto as letras digitadas.

---

## Evento `keypress`

O evento `keypress` é disparado quando uma tecla que produz um **valor do tipo caractere** é pressionada. Isso significa que ele foca em letras, números, pontos, espaços e outros caracteres visíveis.

**JavaScript**

```
// Comentando o keydown para testar o keypress
/*
input.addEventListener('keydown', (event) => {
  console.log(event.key);
});
*/

input.addEventListener('keypress', (event) => {
  console.log(event); // Exibe as informações do evento
  console.log(event.key); // Exibe a tecla caractere pressionada
});
```

**Características:**

* Disparado ao pressionar uma tecla que gera um caractere.
* **Ignora** teclas como `Ctrl`, `Shift`, `Alt`, `Home`, `End`, etc.
* Ideal para capturar o valor que o usuário está digitando em tempo real, sem se preocupar com teclas de modificação.
* Espaços também são considerados caracteres.

Exemplo Prático:

Se você digitar "Rodrigo Gonçalves", o keypress capturará cada letra e o espaço, mas ignorará se você pressionar SHIFT ou CTRL.

---

## Evento `change`

O evento `change` é acionado quando o conteúdo de um input é  **alterado e o foco sai do campo** . Ele não dispara a cada tecla digitada, mas sim quando o usuário termina de interagir com o campo (por exemplo, clicando fora ou pressionando `Tab`).

Existem duas formas principais de utilizá-lo:

### 1. Usando `addEventListener`

**JavaScript**

```
input.addEventListener('change', () => {
  console.log('O conteúdo do input mudou!');
});
```

### 2. Atribuindo uma função diretamente (mais comum para uso em HTML)

**JavaScript**

```
// Criando uma função separada
function inputChanged() {
  console.log('O input mudou (função separada)!');
}

// Atribuindo a função ao evento change
// Nota: Em um ambiente de framework ou diretamente no HTML, você poderia fazer input.onchange = inputChanged;
// Para este exemplo em addEventListener, a estrutura é ligeiramente diferente, mas o conceito é o mesmo.
input.addEventListener('change', inputChanged);
```

**Características:**

* Disparado apenas quando o valor do input é modificado e o campo perde o foco.
* Útil para validações que precisam ocorrer após o usuário completar a entrada, ou para sincronizar dados após a finalização da digitação.

Exemplo Prático:

Você digita "Rodrigo" no campo e, enquanto está digitando, nada acontece. Somente quando você clica fora do input ou pressiona Tab é que o evento change é disparado.

---

## Conclusão

Dominar os eventos de input como `keydown`, `keypress` e `change` é fundamental para qualquer desenvolvedor JavaScript. Cada evento possui um comportamento único e é adequado para diferentes cenários:

* Use **`keydown`** quando precisar capturar *qualquer* pressionamento de tecla, incluindo teclas de controle.
* Use **`keypress`** quando precisar captar *caracteres* digitados, ignorando teclas de controle.
* Use **`change`** quando quiser reagir a uma alteração no valor do input  *após o usuário sair do campo* .

Conhecer essas estruturas e suas nuances adiciona ferramentas valiosas ao seu arsenal de programação, permitindo que você escolha a melhor abordagem para cada situação e se torne um especialista em JavaScript.

---
