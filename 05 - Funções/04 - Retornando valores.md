# Retornando Valores de Funções com `return`

## Introdução

Uma função pode operar de duas maneiras principais: ela pode executar um conjunto de instruções e encerrar seu trabalho ali mesmo (como exibir algo na tela), ou pode calcular um valor e **devolvê-lo** para quem a chamou.

Nesta aula, vamos focar nesta segunda abordagem, que é extremamente poderosa. Aprenderemos a usar a palavra-chave `return` para que nossas funções possam produzir resultados que podem ser armazenados em variáveis e usados em outras partes do nosso código.

---

## Cenário 1: Resolvendo Tudo Dentro da Função

Primeiro, vamos relembrar o modelo que já vimos. Criamos uma função `sum` que recebe dois números, calcula a soma e ela mesma se encarrega de exibir o resultado no console.

**JavaScript (Sem Retorno)**

**JavaScript**

```
function sum(a, b) {
  let result = a + b;
  // A própria função exibe o resultado. Ela não devolve nada.
  console.log(result);
}

// Nós apenas chamamos a função e ela faz todo o trabalho.
sum(7, 3);   // Saída: 10
sum(7, 7);   // Saída: 14
```

Neste caso, a função é uma "caixa-preta" que executa uma tarefa do início ao fim. Nós não temos acesso ao valor `14` fora da função; ele apenas é exibido e "desaparece".

---

## Cenário 2: Usando `return` para Devolver um Valor

Mas e se precisarmos usar o resultado dessa soma em outro cálculo? Para isso, usamos o `return`. A palavra `return` faz duas coisas:

1. Encerra a execução da função imediatamente.
2. Envia um valor de volta para a linha de código que chamou a função.

Vamos modificar nossa função `sum`:

**JavaScript (Com Retorno)**

**JavaScript**

```
function sum(a, b) {
  let result = a + b;
  // A função agora DEVOLVE o valor contido em 'result'.
  return result;
}

// Se apenas chamarmos a função, nada aparece no console.
// O valor 14 foi retornado, mas não fizemos nada com ele.
sum(7, 7);

// Para usar o valor, precisamos capturá-lo em uma variável.
let response = sum(7, 7);

// Agora a variável 'response' contém o valor 14.
console.log("O resultado capturado foi:", response);

// Saída no console:
// O resultado capturado foi: 14
```

Agora, o resultado da soma está disponível fora da função, guardado na variável `response`, e podemos usá-lo como quisermos.

### E se não houver `return`?

Se uma função não tiver uma instrução `return` explícita, ela, por padrão, retorna `undefined`.

**JavaScript**

```
function sumWithoutReturn(a, b) {
  let result = a + b;
  // Sem 'return' aqui!
}

let response = sumWithoutReturn(7, 7);

console.log("Conteúdo de 'response':", response);

// Saída no console:
// Conteúdo de 'response': undefined
```

---

## Usando o Valor Retornado Diretamente

Você não precisa sempre armazenar o valor retornado em uma variável. É muito comum usar o retorno de uma função diretamente como argumento para outra função ou em uma expressão matemática.

**JavaScript (Uso Direto)**

**JavaScript**

```
function sum(a, b) {
  return a + b;
}

// O JavaScript primeiro executa sum(5, 6), que retorna 11.
// Em seguida, ele executa console.log(11).
console.log(sum(5, 6));

// Também podemos usar em uma expressão
let newResult = sum(10, 10) * 2; // será 20 * 2
console.log("Novo resultado:", newResult);

// Saída no console:
// 11
// Novo resultado: 40
```

## Resumo da Aula

Nesta aula, você aprendeu a diferença fundamental entre uma função que apenas executa uma tarefa e uma que retorna um valor.

* **`return`** é a palavra-chave usada para enviar um valor de volta de uma função.
* Você pode **capturar o valor retornado** em uma variável para uso posterior (`let resultado = minhaFuncao();`).
* Uma função sem um `return` explícito devolve  **`undefined`** .
* É possível **usar o retorno de uma função diretamente** em outras partes do seu código, como dentro de `console.log()` ou em cálculos.

Dominar o `return` é essencial para construir programas complexos, onde os resultados de uma parte do código alimentam as outras.
