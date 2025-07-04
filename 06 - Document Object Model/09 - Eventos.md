# Lidando com Eventos em JavaScript

Eventos são as ações que o usuário realiza em uma página web, como clicar em um botão, mover o mouse, pressionar uma tecla ou carregar a página. Com JavaScript, podemos "ouvir" esses eventos e executar um código específico em resposta a eles, tornando nossas aplicações interativas.

## `addEventListener`: O Ouvinte de Eventos

A principal ferramenta para lidar com eventos é o método `.addEventListener()`. Ele "anexa" uma função a um elemento, que será executada sempre que um evento específico ocorrer naquele elemento.

A sintaxe básica é:

elemento.addEventListener('tipoDoEvento', funcaoParaExecutar);

### 1. Evento de Carregamento da Página (`load`)

Um evento comum é o `load`, que é disparado no objeto `window` quando a página e todos os seus recursos (imagens, scripts, etc.) foram completamente carregados.

**JavaScript**

```
window.addEventListener('load', () => {
  console.log('A página foi carregada com sucesso!');
});
```

Sempre que a página for recarregada, essa mensagem aparecerá no console assim que o carregamento for concluído.

### 2. Evento de Clique (`click`)

O evento de clique é um dos mais utilizados. Podemos adicioná-lo a um elemento específico (como um botão) ou ao documento inteiro para capturar qualquer clique na página.

**JavaScript**

```
// Adiciona um ouvinte de clique ao documento inteiro
addEventListener('click', (event) => {
  console.log('Um clique foi detectado na página!');
});
```

## O Objeto `event`

Quando um evento é disparado, a função que o manipula (conhecida como *callback* ou  *handler* ) recebe automaticamente um objeto como argumento. Por convenção, chamamos este objeto de `event` ou `e`. Ele contém informações valiosas sobre a interação que acabou de ocorrer.

### Acessando Informações do Evento

O objeto `event` possui muitas propriedades úteis. Duas das mais importantes são:

* **`event.target`** : Retorna a referência exata do elemento HTML que foi clicado. Isso é extremamente útil para saber onde o usuário interagiu.
* **`event.target.textContent`** : Acessa o conteúdo de texto do elemento que foi clicado.

**JavaScript**

```
addEventListener('click', (event) => {
  // Mostra qual elemento foi clicado
  console.log('Elemento clicado:', event.target);

  // Mostra o texto do elemento clicado
  console.log('Texto do elemento:', event.target.textContent);
});
```

Se você clicar em um `<h1>` com o texto "Minha Lista", `event.target` será o elemento `<h1>` e `event.target.textContent` será "Minha Lista".

## Prevenindo o Comportamento Padrão

Alguns elementos HTML têm comportamentos padrão. Por exemplo, um `<button>` dentro de uma tag `<form>` ou um link `<a>` com um atributo `href` executam uma ação padrão (recarregar a página ou navegar para um novo URL, respectivamente).

Podemos impedir esse comportamento padrão usando o método `event.preventDefault()`.

#### Exemplo: Impedir Recarregamento de Formulário

Imagine um botão de envio em um formulário. Por padrão, ele recarrega a página ao ser clicado. Para evitar isso e manipular os dados com JavaScript, fazemos o seguinte:

**JavaScript**

```
const meuBotao = document.querySelector('button');

meuBotao.addEventListener('click', (event) => {
  // Impede que o botão recarregue a página
  event.preventDefault();

  console.log('O formulário não foi enviado. O comportamento padrão foi prevenido.');
});
```

Agora, ao clicar no botão, a página não será mais recarregada, permitindo que você execute outras lógicas, como validar campos ou enviar dados de forma assíncrona.

## Resumo

* **Eventos** são ações do usuário (clique, envio de formulário, etc.).
* **`addEventListener(tipo, funcao)`** é usado para "ouvir" e reagir a esses eventos.
* A função de callback recebe um objeto **`event`** com detalhes sobre a interação.
* **`event.target`** nos diz qual elemento originou o evento.
* **`event.preventDefault()`** nos permite cancelar o comportamento padrão do navegador para um evento.
