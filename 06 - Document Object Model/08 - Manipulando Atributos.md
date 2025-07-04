# Manipulando Atributos de Elementos com JavaScript

Com JavaScript, além de criar e mover elementos, você também pode manipular os atributos dos elementos HTML que compõem a sua página. Atributos são as propriedades que definem o comportamento ou a configuração de uma tag, como `id`, `class`, `type`, `disabled`, `src`, etc.

Nesta aula, usaremos um campo de `<input>` como exemplo.

**HTML de Referência:**

**HTML**

```
<input type="text" id="name" placeholder="Digite um nome...">
```

## 1. Selecionando o Elemento

Primeiro, precisamos obter uma referência ao elemento que desejamos manipular. Faremos isso usando `document.querySelector`.

**JavaScript**

```
const input = document.querySelector('input');
```

## 2. Adicionando ou Atualizando um Atributo com `setAttribute`

O método `.setAttribute()` permite definir o valor de um atributo em um elemento. Se o atributo já existir, seu valor será atualizado. Se não existir, ele será criado.

A sintaxe é: `elemento.setAttribute('nomeDoAtributo', 'valorDoAtributo');`

#### Exemplo 1: Desabilitando um Input

Podemos desabilitar um campo de formulário dinamicamente adicionando o atributo `disabled`. Isso é útil quando uma ação do usuário (como marcar um checkbox de "aceito os termos") deve liberar o formulário.

**JavaScript**

```
// Adiciona o atributo 'disabled' com o valor 'true'
input.setAttribute('disabled', 'true');
```

Após executar este código, o campo de input ficará cinza e não poderá ser clicado ou editado.

#### Exemplo 2: Alterando o Tipo do Input

Também podemos alterar o comportamento fundamental de um elemento mudando seus atributos. Por exemplo, podemos transformar nosso input de texto (`type="text"`) em um seletor de arquivos (`type="file"`).

**JavaScript**

```
// Altera o valor do atributo 'type' para 'file'
input.setAttribute('type', 'file');
```

O elemento, que antes era um campo de texto, agora se transforma em um botão para escolher arquivos.

## 3. Removendo um Atributo com `removeAttribute`

Para remover completamente um atributo de um elemento, usamos o método `.removeAttribute()`.

A sintaxe é: `elemento.removeAttribute('nomeDoAtributo');`

#### Exemplo: Removendo o Atributo `id`

Nosso input original possui o atributo `id="name"`. Podemos removê-lo da seguinte forma:

**JavaScript**

```
// Remove o atributo 'id' do elemento input
input.removeAttribute('id');
```

Se você inspecionar o elemento no navegador após a execução do código, verá que o atributo `id` não existe mais.

## Resumo dos Métodos

* **`setAttribute(atributo, valor)`** : Adiciona um novo atributo ou atualiza um existente.
* **`removeAttribute(atributo)`** : Remove um atributo de um elemento.

Essas ferramentas são extremamente poderosas para criar páginas dinâmicas e interativas, respondendo às ações do usuário em tempo real.
