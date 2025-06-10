
# Ordem de Precedência em Programação (e Matemática!)

Na programação, assim como na matemática, o conceito de **ordem de precedência** é crucial. Ele nos ajuda a definir qual operação deve ser calculada primeiro quando temos várias juntas em uma expressão. Se você ainda não conhece, não se preocupe, é mais simples do que parece!

---

## O Que é Ordem de Precedência?

Quando uma expressão tem múltiplos **operadores** (como `+`, `-`, `*`, `/`), a ordem de precedência é o que determina qual operação será realizada primeiro. Ela estabelece uma hierarquia entre os operadores.

Imagine que existe uma "tabela" invisível que mostra qual operador tem maior prioridade (nível mais alto) e qual tem menos prioridade. Por exemplo, a **exponenciação** (`**`) geralmente tem prioridade sobre a **multiplicação** (`*`), que por sua vez tem prioridade sobre a **divisão** (`/`), e estas têm prioridade sobre a **adição** (`+`) e a **subtração** (`-`). Outros operadores, como os relacionais (`==`, `>`, `<`) e lógicos (`&&`, `||`), também seguem uma ordem.

---

## Exemplo Prático: Desvendando a Ordem

Vamos pegar um exemplo clássico para entender a ordem de precedência:

`2 + 3 * 4`

Quanto você acha que dá o resultado dessa conta?

Muitos pensariam:

1. `2 + 3 = 5`
2. `5 * 4 = 20`

No entanto, o resultado **não** é `20`. Por quê? Por causa da ordem de precedência!

Lembre-se que a  **multiplicação (`*`) tem mais prioridade que a adição (`+`)** . Portanto, a operação será realizada da seguinte forma:

1. Primeiro, a multiplicação: `3 * 4 = 12`
2. Depois, a adição: `2 + 12 = 14`

O resultado correto é `14`. É por isso que entender a ordem de precedência é tão importante!

---

## Alterando a Ordem com Parênteses `()`

E se quisermos, de fato, que a adição seja feita primeiro no exemplo anterior? Para isso, usamos os  **parênteses `()`** . Os parênteses permitem que a gente defina explicitamente qual conta deve ser feita primeiro,  **sobrepondo a ordem de precedência padrão** .

Veja como o exemplo muda com os parênteses:

`(2 + 3) * 4`

Agora sim, a conta será feita da seguinte maneira:

1. Primeiro, o que está dentro dos parênteses: `2 + 3 = 5`
2. Depois, a multiplicação: `5 * 4 = 20`

Ao usar os parênteses, mudamos o resultado da expressão de `14` para `20`.

Pense nas implicações disso: se você não conhecer a ordem de precedência e estiver criando um sistema financeiro, por exemplo, um cálculo errado pode levar a resultados desastrosos (mais dinheiro para uns, menos para outros, ou vice-versa!).

---
