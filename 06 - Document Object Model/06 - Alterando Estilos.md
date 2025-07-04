# Alterando Estilos de Elementos com JavaScript

## Introdução

Você já aprendeu a selecionar elementos e a manipular seu conteúdo. Nesta aula, vamos dar um passo adiante e aprender a **manipular os estilos** dos elementos diretamente com o JavaScript.

Vamos explorar duas abordagens principais: a primeira e mais recomendada é a manipulação de classes CSS, e a segunda é a alteração direta de estilos em linha (inline styles).

## Método 1: Manipulando Classes com `classList`

A maneira mais organizada e comum de alterar a aparência de um elemento é adicionando ou removendo classes CSS que já foram previamente definidas no seu arquivo de estilos. Para isso, usamos a propriedade `classList`.

Vamos usar o campo `<input>` do nosso formulário como exemplo. Em nosso CSS, já existe uma classe chamada `.input-error` que adiciona uma borda vermelha.

**JavaScript (Selecionando o Elemento)**

**JavaScript**

```
// Primeiro, selecionamos o input pelo seu ID 'name'
const input = document.querySelector('#name');
```

Agora que temos o elemento, podemos gerenciar suas classes.

### Adicionando uma Classe com `.add()`

Para adicionar a classe `.input-error` ao nosso input, usamos o método `add()`.

**JavaScript**

**JavaScript**

```
input.classList.add('input-error');
```

### Removendo uma Classe com `.remove()`

De forma semelhante, para remover uma classe, usamos o método `remove()`.

**JavaScript**

**JavaScript**

```
input.classList.remove('input-error');
```

### Alternando uma Classe com `.toggle()`

O método `toggle()` é extremamente útil. Ele verifica se a classe existe no elemento:

* Se a classe  **não existe** , ele a  **adiciona** .
* Se a classe  **já existe** , ele a  **remove** .

É perfeito para funcionalidades como abrir/fechar um menu ou uma janela modal.

**JavaScript**

**JavaScript**

```
// Se a classe 'input-error' não estiver no elemento, esta linha irá adicioná-la.
// Se já estiver, esta mesma linha irá removê-la.
input.classList.toggle('input-error');
```

---

## Método 2: Alterando Estilos em Linha com a Propriedade `style`

Às vezes, você pode querer aplicar um estilo específico que não está definido em uma classe, ou um valor que é calculado dinamicamente. Para isso, podemos alterar os estilos em linha (inline) de um elemento através da propriedade `style`.

Vamos usar o botão do nosso formulário como exemplo.

**JavaScript (Alterando o Estilo do Botão)**

**JavaScript**

```
// Selecionamos o botão pela sua tag (como só há um, isso funciona bem)
const button = document.querySelector('button');

// Acessamos a propriedade 'style' para modificar seu CSS
button.style.backgroundColor = 'red';
```

**Observação Importante:** Propriedades CSS que usam hífen (como `background-color` ou `font-size`) são escritas em JavaScript no formato **camelCase** (como `backgroundColor` ou `fontSize`).

## Resumo da Aula

Você aprendeu as duas principais formas de manipular estilos de elementos com JavaScript.

| Método                         | Descrição                                                                                                             | Uso Recomendado                                                                                                 |
| ------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| **`element.classList`** | Gerencia as classes CSS de um elemento com métodos como `.add()`,`.remove()`e `.toggle()`.                       | **A forma preferida** . Mantém os estilos organizados no arquivo CSS e apenas alterna as classes via JS. |
| **`element.style`**     | Altera diretamente os estilos em linha (inline) de um elemento. Propriedades CSS com hífen são escritas em camelCase. | Para aplicar estilos específicos e dinâmicos que não fazem parte de uma classe predefinida.                  |

Dominar essas duas técnicas lhe dará controle total sobre a aparência da sua página, permitindo a criação de interfaces dinâmicas e interativas.
