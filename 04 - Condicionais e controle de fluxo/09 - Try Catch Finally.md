# Tratamento de Exceções na Prática: `try`, `catch`, `finally` e `throw`

## Introdução

Nesta aula, vamos aplicar os conceitos de tratamento de exceções na prática. Veremos como a estrutura `try...catch` impede que nossa aplicação quebre, como o bloco `finally` garante a execução de código essencial e como podemos criar e lançar nossas próprias exceções personalizadas com `throw`.

---

## O `try...catch` em Ação

Primeiro, vamos ver o que acontece quando um erro ocorre sem nenhum tratamento. Vamos tentar exibir o conteúdo de uma variável que não existe.

**JavaScript (Sem Tratamento)**

**JavaScript**

```
console.log(result); // A variável 'result' não foi declarada

// Saída no console:
// Uncaught ReferenceError: result is not defined
```

O resultado é um erro "agressivo" e em vermelho no console. Mais importante: a execução do script é **interrompida** nesse ponto.

Agora, vamos colocar esse mesmo código dentro de um bloco `try...catch` para ver a diferença.

**JavaScript (Com Tratamento)**

**JavaScript**

```
try {
  // Tentamos executar o código que pode falhar
  console.log(result);
} catch (error) {
  // Se um erro ocorrer no 'try', o fluxo é desviado para cá
  console.log("Capturamos o erro!");
}

console.log("O programa continua...");

// Saída no console:
// Capturamos o erro!
// O programa continua...
```

Perceba duas coisas:

1. A aplicação  **não travou** . A mensagem "O programa continua..." foi exibida.
2. O erro vermelho e agressivo sumiu. Nós controlamos o que acontece.

### Capturando e Exibindo o Erro

O bloco `catch` pode receber o objeto do erro como um parâmetro. É comum chamá-lo de `error` ou `e`, mas você pode usar o nome que quiser, pois é apenas uma variável temporária.

**JavaScript**

**JavaScript**

```
try {
  console.log(result);
} catch (error) {
  // Exibindo o objeto de erro capturado
  console.log(error);

  // Exibindo uma mensagem amigável para o usuário
  console.log("Não foi possível processar sua requisição. Tente novamente mais tarde.");
}

// Saída no console:
// ReferenceError: result is not defined
// Não foi possível processar sua requisição. Tente novamente mais tarde.
```

Agora, temos o melhor dos dois mundos: podemos registrar o erro técnico para a equipe de desenvolvimento e exibir uma mensagem amigável para o usuário final.

---

## O Bloco `finally`

E se houver um código que precisa ser executado  **independentemente de ter ocorrido um erro ou não** ? Para isso, usamos o bloco `finally`. Ele é opcional, mas muito útil para tarefas de "limpeza".

O `finally` executa sempre, seja após a conclusão bem-sucedida do `try` ou após a execução do `catch`.

**Exemplo de Uso:** Um ótimo exemplo é o gerenciamento de conexões com um banco de dados.

1. **`try`** : Você abre a conexão com o banco e tenta enviar os dados.
2. **`catch`** : Se o envio falhar, você trata o erro.
3. **`finally`** : Você **fecha a conexão** com o banco. Isso é crucial para não deixar conexões abertas, consumindo recursos desnecessariamente.

**JavaScript**

**JavaScript**

```
try {
  console.log("Abrindo conexão com o BD...");
  // console.log(result); // Descomente esta linha para simular um erro
  console.log("Enviando dados...");

} catch (error) {
  console.log("Ocorreu um erro:", error.message);

} finally {
  // Este bloco será executado SEMPRE
  console.log("Fechando a conexão com o BD. Fim.");
}

// Saída (sem erro):
// Abrindo conexão com o BD...
// Enviando dados...
// Fechando a conexão com o BD. Fim.

// Saída (com erro):
// Abrindo conexão com o BD...
// Ocorreu um erro: result is not defined
// Fechando a conexão com o BD. Fim.
```

Como pode ver, o `finally` é a garantia de que a limpeza será feita.

---

## Lançando Suas Próprias Exceções com `throw`

Às vezes, um erro não é um problema técnico do JavaScript (como uma variável indefinida), mas sim um **erro lógico** da sua aplicação. Por exemplo, o usuário tentou sacar um valor maior do que o saldo. Nesses casos, você pode **lançar sua própria exceção** usando a palavra-chave `throw`.

Quando você usa `throw`, você está manualmente gerando um erro, que pode ser capturado por um bloco `catch`.

**JavaScript**

**JavaScript**

```
let result = 0;

try {
  console.log("Iniciando processamento...");

  if (result === 0) {
    // Se a condição lógica de erro for atendida, lançamos uma nova exceção.
    throw new Error("O valor não pode ser 0.");
  }

  console.log("Processamento concluído com sucesso."); // Não executa se o erro for lançado

} catch (error) {
  // Capturamos o erro que NÓS lançamos
  console.log("Erro capturado:", error.message);

} finally {
  console.log("Fim do processamento.");
}

// Saída:
// Iniciando processamento...
// Erro capturado: O valor não pode ser 0.
// Fim do processamento.
```

Neste exemplo, `throw new Error(...)` cria um objeto de erro com uma mensagem personalizada. Isso nos dá um controle fino sobre os fluxos de erro da nossa aplicação.

> **Nota:** A sintaxe `new Error()` está relacionada à criação de objetos a partir de classes. Veremos isso em detalhes mais adiante. Por enquanto, saiba que este é o comando para gerar um erro padrão com uma mensagem personalizada.

## Resumo da Aula

Nesta aula prática, você aprendeu a:

* **Usar `try...catch`** para capturar erros de tempo de execução e evitar que a aplicação trave.
* **Usar `finally`** para executar código de limpeza essencial, independentemente do sucesso ou falha.
* **Usar `throw`** para gerar suas próprias exceções personalizadas e lidar com erros lógicos específicos da sua aplicação.

Com o domínio dessas ferramentas, você está pronto para construir aplicações muito mais seguras e confiáveis. Vamos usar esses conceitos extensivamente nos projetos que desenvolveremos juntos!
