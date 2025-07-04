# Manipulando o Valor do Input com Expressões Regulares em JavaScript

Nesta aula, aprofundamos o uso de **expressões regulares (regex)** em JavaScript para interagir e validar dados de  **campos de input** . Aprendemos a recuperar o valor digitado pelo usuário, aplicar expressões regulares para identificar padrões específicos, validar se esses padrões são atendidos e até mesmo substituir ou remover partes do texto com base na regex. Além disso, revisitamos eventos importantes como `input` e `submit` para criar interações dinâmicas.

---

## 1. Recuperando e Observando o Valor do Input

Para começar a manipular o valor do input, primeiro precisamos selecionar o elemento no DOM e adicionar um "observador" para capturar o que o usuário digita.

**JavaScript**

```
// Seleciona o elemento input
const input = document.querySelector('input');

// Adiciona um ouvinte para o evento 'input'
input.addEventListener('input', () => {
  // O evento 'input' é disparado a cada alteração no valor do input (enquanto o usuário digita)
  console.log(input.value); // Exibe o valor atual do input no console
});
```

* O evento `input` é ideal para  **capturar o valor em tempo real** , à medida que o usuário digita ou apaga. Isso é diferente do `keydown` ou `keypress`, que focam nas teclas, e do `change`, que só dispara ao perder o foco.
* `input.value` nos dá o conteúdo atual do campo.

---

## 2. Definindo a Expressão Regular

Vamos utilizar a mesma expressão regular das aulas anteriores, que busca por **sequências de caracteres que não são dígitos (letras, símbolos, etc.)** em todo o texto.

**JavaScript**

```
// Define a expressão regular para encontrar sequências de caracteres não-dígitos
const regex = /\D+/g;
// \D: Caractere que não é um dígito (0-9)
// +: Uma ou mais ocorrências consecutivas do padrão anterior
// g: Modificador global, para encontrar todas as correspondências na string
```

---

## 3. Validando Padrões com `match()` e `test()`

O JavaScript oferece métodos built-in para trabalhar com expressões regulares em strings:

### a) `string.match(regex)`: Encontrando Ocorrências

O método `match()` é chamado na string e recebe a regex como argumento. Ele **retorna um array** com todas as correspondências encontradas que atendem ao padrão, ou `null` se nenhuma correspondência for encontrada.

**JavaScript**

```
input.addEventListener('input', () => {
  const value = input.value;
  const foundMatches = value.match(regex);
  console.log(foundMatches); // Retorna um array com as letras encontradas ou null
});
```

* Ao digitar "Rodrigo123", ele retornará `["R", "o", "d", "r", "i", "g", "o"]` (ou `["Rodrigo"]` se o `+` pegar a sequência toda, dependendo do contexto exato da sua regex).
* Se digitar "123", retornará `null`.

### b) `regex.test(string)`: Testando a Validade do Padrão

O método `test()` é chamado na regex e recebe a string como argumento. Ele **retorna `true` ou `false`** indicando se o padrão da regex foi encontrado na string.

**JavaScript**

```
input.addEventListener('input', () => {
  const value = input.value;
  const isValid = regex.test(value);
  console.log(isValid); // Retorna true se encontrar letras, false caso contrário
});
```

* Ao digitar "Rodrigo123", retornará `true`.
* Ao digitar "123", retornará `false`.

---

## 4. Manipulando o Texto com `replace()`

O método `replace()` de strings, em conjunto com regex, é extremamente poderoso para **substituir ou remover partes do texto** que correspondem a um padrão.

Para demonstrar, vamos usar o evento `submit` de um formulário, que é acionado quando o formulário é enviado.

**JavaScript**

```
// Seleciona o elemento do formulário
const form = document.querySelector('form');

// Adiciona um ouvinte para o evento 'submit' do formulário
form.addEventListener('submit', (event) => {
  event.preventDefault(); // Impede o recarregamento da página (comportamento padrão do submit)

  const value = input.value; // Pega o valor atual do input

  // Exemplo: Substituir todas as letras por 'X'
  // const newValue = value.replace(regex, 'X');

  // Exemplo: Remover todas as letras (substituir por uma string vazia)
  const newValue = value.replace(regex, ''); // Substitui todas as letras por nada

  console.log(newValue); // Exibe o valor do input após a manipulação
});
```

* Com `value.replace(regex, '')`, se o usuário digitar "Rodrigo123Gonçalves456", a saída será "123456", pois todas as letras (caracteres não-dígitos) foram substituídas por uma string vazia.
* Esta é uma técnica excelente para **limpar ou formatar dados** antes de enviá-los para um servidor ou processamento.

---

## 5. Cenários de Validação com `if/else` e `alert`

Podemos combinar a validação com regex e condicionais (`if/else`) para fornecer feedback ao usuário.

**JavaScript**

```
form.addEventListener('submit', (event) => {
  event.preventDefault();

  const value = input.value;

  // Verifica se o valor do input contém o padrão definido pela regex (letras)
  // O '!' inverte o resultado: se NÃO encontrar letras, a condição será verdadeira
  if (!regex.test(value)) {
    // Se não encontrar letras (ou seja, só tiver números/símbolos), exibe um alerta
    alert('Valor inválido! Digite corretamente (deve conter letras).');
  } else {
    // Se encontrar letras, significa que o padrão foi atendido
    console.log('Padrão OK! Valor processado:', value);
    // Aqui você faria o envio para o banco de dados, cadastro, etc.
  }
});
```

* Este exemplo simula uma validação de campo: se o campo deve conter letras e não as contiver (ou seja, `regex.test(value)` for `false`, e `!false` for `true`), um alerta é exibido. Caso contrário, o valor é considerado "OK" e pode ser processado.

---

## Conclusão

A manipulação de valores de input com expressões regulares em JavaScript é uma habilidade fundamental para criar interfaces de usuário robustas e seguras. Ao combinar a capacidade das regex de identificar padrões com eventos de input e métodos de manipulação de string, você pode:

* Fornecer feedback instantâneo ao usuário.
* Garantir a integridade dos dados.
* Limpar e formatar informações de forma eficiente.

Experimente estas técnicas em seus próprios projetos para solidificar seu aprendizado! O que mais você gostaria de validar ou manipular usando regex em seus inputs?
