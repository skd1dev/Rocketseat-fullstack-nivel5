# Manipulando o Conteúdo dos Elementos (`textContent`, `innerText`, `innerHTML`)

## Introdução

Agora que você já sabe como selecionar elementos no DOM, nesta aula vamos aprender a **ler e alterar o conteúdo** desses elementos. Vamos continuar usando nosso projeto de lista de convidados para explorar as diferentes propriedades que o JavaScript nos oferece para essa tarefa.

## Lendo e Modificando com `textContent`

A propriedade `.textContent` é uma das formas mais diretas de interagir com o texto de um elemento.

### Lendo o Conteúdo

Primeiro, vamos selecionar nosso primeiro convidado e ler o texto dentro dele.

**JavaScript (Lendo com `.textContent`)**

**JavaScript**

```
// 1. Selecionamos o elemento <li> com id 'guest-1'
const guest = document.querySelector('#guest-1');

// 2. Usamos .textContent para obter apenas o texto, ignorando as tags internas
console.log(guest.textContent);

// Saída no console:
// Rodrigo
```

### Alterando o Conteúdo

Além de ler, podemos usar a mesma propriedade para atribuir um novo valor, alterando o que é exibido na página.

**JavaScript (Alterando com `.textContent`)**

**JavaScript**

```
guest.textContent = 'João';
```

**Atenção:** Ao usar `.textContent` para atribuir um valor, você **substitui todo o conteúdo** do elemento selecionado por um simples texto. No nosso caso, a tag `<span>` que estava dentro do `<li>` foi removida e substituída pelo texto "João".

### Como Manter a Estrutura HTML?

Se o seu objetivo é alterar apenas o texto dentro da `<span>` sem destruir a tag, você deve selecioná-la diretamente. O `querySelector` torna isso fácil.

**JavaScript (Selecionando um Filho Direto)**

**JavaScript**

```
// Agora selecionamos a <span> DENTRO do elemento com id 'guest-1'
const guestSpan = document.querySelector('#guest-1 span');

// Alterar o textContent da <span> preserva a estrutura do <li>
guestSpan.textContent = 'Ana';
```

---

## `textContent` vs. `innerText` vs. `innerHTML`

Existem outras propriedades para manipular conteúdo, e cada uma tem um comportamento específico. Vamos preparar nosso HTML para ver a diferença. Adicionaremos uma `<span>` oculta com CSS:

**HTML:**

**HTML**

```
<li id="guest-1" class="guest">
  <span>Rodrigo</span>
  <span class="hide">0 novas mensagens</span>
</li>
```

**CSS:**

**CSS**

```
.hide {
  display: none;
}
```

Agora, vamos selecionar o `<li>` novamente e comparar as três propriedades:

**JavaScript (Comparando as Propriedades)**

**JavaScript**

```
const guest = document.querySelector('#guest-1');

console.log(guest.textContent);
// Saída: "Rodrigo 0 novas mensagens"

console.log(guest.innerText);
// Saída: "Rodrigo"

console.log(guest.innerHTML);
// Saída: "<span>Rodrigo</span><span class="hide">0 novas mensagens</span>"
```

### Análise da Diferença

1. **`textContent`** : Retorna **todo** o conteúdo de texto do nó e de seus descendentes, incluindo o texto de elementos ocultos (`display: none`). É uma representação "crua" do texto.
2. **`innerText`** : Retorna apenas o texto que está **visível** para o usuário. Ele leva em consideração o estilo CSS e não incluirá o conteúdo de elementos ocultos.
3. **`innerHTML`** : Retorna o conteúdo como uma string de  **HTML** . Em vez de extrair apenas o texto, ele devolve todas as tags, atributos e textos que estão dentro do elemento selecionado. Ele também pode ser usado para *inserir* HTML em um elemento.

## Resumo da Aula

Você aprendeu a ler e modificar o conteúdo dos elementos DOM usando três propriedades diferentes, cada uma com um propósito específico.

| Propriedade               | Leitura                                                         | Escrita                                                 | Considera CSS? |
| ------------------------- | --------------------------------------------------------------- | ------------------------------------------------------- | -------------- |
| **`textContent`** | Retorna todo o texto (visível e oculto), sem tags.             | Substitui todo o conteúdo por texto plano.             | Não           |
| **`innerText`**   | Retorna apenas o texto**visível** , com formatação.    | Substitui o conteúdo por texto plano.                  | **Sim**  |
| **`innerHTML`**   | Retorna o**HTML completo**(tags + texto) como uma string. | Substitui todo o conteúdo por uma nova string de HTML. | Não           |

Saber qual propriedade usar é fundamental para manipular a página da maneira desejada sem quebrar a estrutura HTML.
