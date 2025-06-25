# Documentando Suas Funções com Comentários JSDoc

## Introdução

Você já aprendeu a usar comentários de uma e múltiplas linhas para deixar notas no seu código. Agora, vamos conhecer um tipo especial de comentário, o  **comentário de documentação** . Utilizando uma sintaxe padrão chamada  **JSDoc** , podemos criar documentações que não são apenas legíveis para humanos, mas também interpretadas por editores de código (como o VS Code) para fornecer ajuda interativa.

Esta é uma prática essencial, principalmente quando você cria funções que serão reutilizadas por você ou por outras pessoas no futuro. Com o JSDoc, você pode explicar:

* O que a função faz.
* Quais parâmetros ela espera.
* O tipo de dado de cada parâmetro (`string`, `number`, etc.).
* O que a função retorna.

Vamos ver como isso funciona na prática.

---

## O Cenário: Uma Função Sem Documentação

Imagine que temos uma função para autenticar um usuário. Ela recebe um e-mail e uma senha e, se tudo estiver correto, retorna o ID do usuário.

**JavaScript (Função Simples)**

**JavaScript**

```
function signIn(email, password) {
  // Imagina que aqui existe um fluxo complexo de autenticação...
  // 1. Conecta no banco de dados.
  // 2. Procura pelo usuário com o 'email' informado.
  // 3. Compara a 'password' com a senha armazenada.
  // ... e etc.

  // Se tudo der certo, retornamos o ID do usuário.
  return 7;
}
```

Se tentarmos usar essa função, o editor de código nos dará pouca informação. Ao passar o mouse sobre `signIn`, ele pode mostrar os nomes dos parâmetros (`email`, `password`), mas não nos diz que tipo de dado eles esperam ou o que exatamente a função retorna.

É aqui que a documentação entra para resolver o problema.

---

## Criando Comentários JSDoc

Para criar um comentário de documentação, usamos a sintaxe `/**` (barra e dois asteriscos) para abrir o bloco, logo acima da função.

A maioria dos editores de código modernos oferece um atalho: digite `/**` acima da linha da função e pressione `Enter`. Ele irá gerar automaticamente um modelo com base nos parâmetros e no retorno da sua função.

**JavaScript (Gerando o Template JSDoc)**

**JavaScript**

```
/**
 * * @param {*} email
 * @param {*} password
 * @returns
 */
function signIn(email, password) {
  // ...
  return 7;
}
```

Agora, vamos preencher este modelo com informações úteis.

### Preenchendo a Documentação

Usamos "tags" especiais como `@param` e `@returns` para estruturar a informação.

1. **Descrição Geral:** Na primeira linha, escrevemos um resumo do que a função faz.
2. **`@param {tipo} nome`:** Para cada parâmetro, especificamos o tipo de dado entre chaves (`{string}`, `{number}`, etc.) e adicionamos uma descrição.
3. **`@returns {tipo}`:** Especificamos o tipo do valor retornado e descrevemos o que ele representa.

**JavaScript (Função Documentada)**

**JavaScript**

```
/**
 * Autentica o usuário no sistema.
 * @param {string} email O e-mail do usuário para login.
 * @param {string} password A senha do usuário. Deve conter mais de 6 caracteres.
 * @returns {number} Retorna o ID único do usuário em caso de sucesso.
 */
function signIn(email, password) {
  // ... todo o fluxo de autenticação do usuário
  return 7;
}
```

---

## O Resultado: Uma Experiência Aprimorada

Agora, veja a mágica acontecer. Ao passar o mouse sobre a função `signIn` ou ao começar a digitá-la, o editor de código exibe uma "caixa de ajuda" rica em detalhes:

A ferramenta agora nos informa claramente:

* A descrição: "Autentica o usuário no sistema."
* Que `email` e `password` devem ser do tipo `string`.
* As descrições adicionais para cada parâmetro.
* Que o retorno é um `number` e representa o ID do usuário.

Essa prática transforma a experiência de programar, tornando o código mais fácil de entender, usar e manter.

## Resumo da Aula

Nesta aula, você aprendeu a importância e a prática da documentação de código com JSDoc.

* **Comentários de Documentação** (`/** ... */`) fornecem informações estruturadas sobre suas funções.
* **Tags Principais** : `@param` descreve um parâmetro e seu tipo; `@returns` descreve o valor de retorno e seu tipo.
* **Benefício Imediato** : Editores de código usam essa documentação para fornecer autocompletar e dicas inteligentes (IntelliSense).
* **Boas Práticas** : Documentar funções é um pilar para escrever código limpo, profissional e fácil de colaborar.
