# Inspecionando o DOM no Navegador

## Introdução

A partir de agora, vamos sair da teoria e começar a interagir com o DOM de verdade. Para isso, utilizaremos uma aplicação de exemplo simples, que contém apenas HTML e CSS.

A estrutura da nossa página de exemplo é a seguinte:

* Um título `<h1>` ("Convidados")
* Um formulário `<form>` com um campo `<input>` e um `<button>`
* Uma lista `<ul>` com alguns itens `<li>`

> **Recomendação:** O código-fonte deste projeto estará disponível junto com a aula. Faça o download para acompanhar os próximos passos e praticar junto.

## Abrindo as Ferramentas de Desenvolvedor

Para visualizar o DOM, usamos as "Ferramentas de Desenvolvedor" (DevTools) que vêm integradas aos navegadores modernos. No Google Chrome (e na maioria dos outros navegadores), o acesso é simples:

1. Clique com o **botão direito** do mouse em qualquer lugar da página.
2. No menu que aparecer, selecione a opção **"Inspecionar"** (Inspect).

Uma nova janela ou painel será aberto na lateral ou na parte inferior da tela. Este painel é a sua central de comando para interagir com a página.

---

## Explorando o DOM na Aba "Elements"

As Ferramentas de Desenvolvedor têm várias abas (`Console`, `Sources`, `Network`, etc.). Nós já usamos bastante a aba `Console`. Agora, nosso foco será na aba  **`Elements`** .

A aba `Elements` nos mostra a estrutura do DOM da página em tempo real. É a mesma árvore que discutimos na aula teórica, mas agora de forma interativa.

### Navegando na Árvore de Nós

Você pode ver a hierarquia completa do seu documento HTML.

* No topo, temos o `<!DOCTYPE html>` e a tag `<html>`.
* Podemos expandir e recolher os nós clicando nas pequenas setas ao lado deles. Ao expandir o `<html>`, vemos seus dois filhos diretos: `<head>` e `<body>`.
* Expandindo o `<body>`, encontramos nossos elementos visíveis, como o `<main>`, que por sua vez contém o `<h1>`, o `<form>` e a `<ul>`.

Perceba a hierarquia: o `<h1>` é um nó filho do `<main>`, que é filho do `<body>`, e assim por diante. É essa estrutura que nos permite navegar e selecionar elementos com precisão.

### Interatividade

A grande vantagem dessa ferramenta é sua interatividade. Conforme você passa o mouse sobre um elemento na aba `Elements`, o navegador irá **destacar o elemento correspondente** na página visual. Isso torna muito fácil identificar qual parte do código corresponde a qual parte da interface.

---

## Conclusão

Isso que você está vendo na aba `Elements`  **é o DOM** . É uma representação viva da sua página.

O que faremos a partir da próxima aula é usar o JavaScript para acessar, ler e modificar esses mesmos elementos que estamos inspecionando agora. Você pode fechar a ferramenta de inspeção clicando no "X" no canto do painel. Vamos começar a manipulação!
