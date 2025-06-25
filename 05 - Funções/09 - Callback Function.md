# Trabalhando com Callback Functions

## Introdução

Até agora, passamos textos e números como argumentos para nossas funções. Nesta aula, vamos explorar uma técnica fundamental e poderosa em JavaScript: passar  **uma função como argumento para outra função** .

O nome disso é **Callback Function** (ou "função de callback"). Em termos simples, um callback é uma função que é "chamada de volta" (executada) em um momento posterior, de dentro da função que a recebeu. Isso nos permite criar códigos muito mais flexíveis e lidar com tarefas assíncronas (que veremos no futuro).

## Cenário: Executando uma Tarefa

Vamos começar com uma função simples que simula a execução de uma tarefa e exibe seu nome.

**JavaScript (Função Base)**

**JavaScript**

```
function execute(taskName) {
  console.log(`Executando a tarefa: ${taskName}`);
}

execute("Download do arquivo...");

// Saída no console:
// Executando a tarefa: Download do arquivo...
```

Até aqui, nenhuma novidade. Agora, vamos adicionar a capacidade de executar uma ação *após* a conclusão dessa tarefa, usando um callback.

## Implementando um Callback

Vamos modificar nossa função `execute` para aceitar um segundo parâmetro, que será a nossa função de callback. A função `execute` terá o controle de *quando* chamar esse callback.

### Maneira 1: Passando uma Função Nomeada

Primeiro, podemos criar uma função separada e depois passá-la como argumento.

**JavaScript (Passando Função Nomeada)**

**JavaScript**

```
// 1. Nossa função principal agora espera um 'callback'.
function execute(taskName, callback) {
  console.log(`Executando a tarefa: ${taskName}`);

  // 3. Após a tarefa principal, executamos o callback.
  callback();
}

// 2. Criamos uma função separada para ser nosso callback.
function tarefaFinalizada() {
  console.log("Tarefa finalizada!");
}

// Passamos o nome da nossa função 'tarefaFinalizada' como o segundo argumento.
execute("Download do arquivo...", tarefaFinalizada);

// Saída no console:
// Executando a tarefa: Download do arquivo...
// Tarefa finalizada!
```

Note que passamos `tarefaFinalizada` sem os parênteses `()`, pois estamos passando a referência da função em si, e não o resultado da sua execução.

---

## Flexibilidade: Criando Callbacks "On-the-Fly"

Embora a maneira anterior funcione, é muito mais comum criar a função de callback diretamente na chamada da função principal. Isso é geralmente feito com Funções Anônimas ou Arrow Functions.

### Maneira 2: Usando uma Função Anônima

Podemos criar uma função anônima diretamente no lugar do segundo argumento.

**JavaScript (Callback com Função Anônima)**

**JavaScript**

```
execute("Upload do arquivo...", function() {
  console.log("Callback executado com função anônima.");
});

// Saída no console:
// Executando a tarefa: Upload do arquivo...
// Callback executado com função anônima.
```

### Maneira 3: Usando uma Arrow Function (Mais Comum)

A forma mais moderna e legível de fazer isso é com uma Arrow Function.

**JavaScript (Callback com Arrow Function)**

**JavaScript**

```
execute("Excluindo o arquivo...", () => {
  console.log("Arquivo excluído.");
});

// Saída no console:
// Executando a tarefa: Excluindo o arquivo...
// Arquivo excluído.
```

**Observação importante:** A ordem da execução é controlada pela função `execute`. Se movermos a chamada do `callback()` para o início da função, o resultado será invertido, provando que é a função `execute` quem decide quando "chamar de volta".

---

## Dica Extra: Sintaxe Curta para Arrow Functions

Quando seu callback de Arrow Function contém apenas  **uma única linha de código** , você pode omitir as chaves `{}` para uma sintaxe ainda mais limpa e curta.

**JavaScript (Arrow Function Curta)**

**JavaScript**

```
execute("Salvando arquivo...", () => console.log("Arquivo salvo."));

// Saída no console:
// Executando a tarefa: Salvando arquivo...
// Arquivo salvo.
```

## Resumo da Aula

Nesta aula, você aprendeu o que é e como usar uma das técnicas mais importantes do JavaScript.

* **Callback Function** : É uma função que é passada como argumento para outra função.
* **Controle de Execução** : A função principal decide quando executar o callback.
* **Implementação** : Você pode passar uma função nomeada já existente, mas é mais comum criar o callback no momento da chamada usando:
* **Funções Anônimas** : `function() { ... }`
* **Arrow Functions** : `() => { ... }` (forma mais moderna e preferida).
* **Flexibilidade** : Callbacks permitem que você escreva um código mais dinâmico e prepare o terreno para lidar com operações que não terminam imediatamente.
