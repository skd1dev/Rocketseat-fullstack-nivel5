
# Compreendendo Expressões Regulares (Regex)

Nesta aula, desvendamos o conceito de  **expressões regulares** , também conhecidas como  **regex** . Elas são ferramentas poderosas para  **identificar padrões em strings** , sendo amplamente utilizadas para validação de dados, como e-mails, senhas e formatos específicos. O principal objetivo desta aula é que você compreenda a **possibilidade de validação** com regex, não a memorização de suas combinações complexas.

---

## O que são Expressões Regulares?

Expressões regulares são sequências de caracteres que definem um  **padrão de busca** . Imagine que você tem uma string (um texto) e quer verificar se um determinado arranjo de caracteres existe ali, ou se a string inteira segue um formato específico. É aí que as regex entram em ação!

Elas são frequentemente usadas para:

* **Validação de dados** : Verificar se um e-mail, CPF, número de telefone ou senha estão no formato correto.
* **Busca e substituição** : Encontrar e substituir partes de um texto que correspondam a um padrão.
* **Extração de informações** : Retirar dados específicos de grandes volumes de texto.

Uma expressão regular é composta por uma combinação de **caracteres simples** (letras, números) e **caracteres especiais** (como `+`, `*`, `?`, `\`, `[]`, etc.), que juntos definem o padrão.

---

## Exemplo Prático de uma Expressão Regular

Vamos analisar um exemplo para entender como uma regex funciona na prática.

Considere a seguinte string de texto: `"53A7B5C"`

Nosso objetivo é encontrar as **letras** dentro dessa string, ignorando os números. Para isso, podemos usar a seguinte expressão regular:

**Snippet de código**

```
/\D+/g
```

Vamos detalhar cada parte dessa expressão:

### Delimitadores da Expressão

* **`/` (Barra inicial)** : Indica o início da expressão regular.
* **`/` (Barra final)** : Indica o fim da expressão regular.

Tudo o que está entre essas barras define o padrão que será procurado.

### O Caractere Especial `\D`

* **`\D`** : Este é um caractere especial que significa "qualquer caractere que  **não seja um dígito** ".
* Um dígito é um número de 0 a 9.
* Portanto, `\D` vai corresponder a  **letras, símbolos, espaços** , etc.

No nosso exemplo `"53A7B5C"`, o `\D` identificará:

* `A`
* `B`
* `C`

Ele ignorará o `5`, o `3`, o `7` e o `5`.

### O Quantificador `+` (Sinal de Mais)

* **`+` (Sinal de Mais)** : Este é um  **quantificador** . Quando colocado após um caractere ou grupo, ele indica que o padrão anterior deve aparecer  **uma ou mais vezes consecutivas** .

Combinado com `\D`, **`\D+`** significa: "encontre uma ou mais sequências de caracteres que não sejam dígitos".

Por que isso é importante?

Sem o +, a regex /\D/g encontraria cada letra individualmente (A, depois B, depois C). Com o +, se tivéssemos uma sequência como "ABC" (sem números entre elas), a regex \D+ a capturaria como uma única correspondência "ABC", em vez de "A", "B", "C" separadamente. No nosso exemplo "53A7B5C", ele pegaria o A, depois o B, e por fim o C, cada um como uma "sequência" de um caractere.

### O Modificador Global `g`

* **`g` (Global)** : Este é um **modificador (ou flag)** que vem após a barra final da expressão regular. Ele indica que a busca deve ser feita em **toda a string** e encontrar **todas as correspondências** do padrão.

Sem o g: A expressão regular pararia na primeira correspondência encontrada. Por exemplo, em "53A7B5C", ela encontraria apenas o A e pararia.

Com o g: A expressão continua a busca até o final da string, encontrando A, B e C.

---

## Não é Preciso Decorar!

O mais importante é entender o **conceito** e a **possibilidade** que as expressões regulares oferecem para a validação e manipulação de strings. Você não precisa decorar todas as combinações de caracteres e modificadores.

Na prática, quando precisar validar algo específico (como um e-mail ou um CPF), você pode pesquisar pela expressão regular mais adequada. Existem inúmeros recursos e bibliotecas online com padrões de regex prontos para os mais diversos cenários.

O objetivo é adicionar essa poderosa ferramenta ao seu repertório, sabendo que ela existe e como ela pode ser usada para resolver problemas de validação de forma eficiente.

---
