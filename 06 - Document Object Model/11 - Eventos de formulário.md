# Aula: Eventos de Formulário no JavaScript

## 📌 Objetivo

Entender como capturar e tratar eventos de formulário, especialmente o evento `submit`, utilizando tanto a propriedade `onsubmit` quanto o método `addEventListener`.

---

## 🧠 Conceitos Abordados

- Seleção de elementos do DOM com `document.querySelector`
- Evento `submit` em formulários
- Diferença entre `onsubmit` e `addEventListener`
- Prevenção do comportamento padrão com `event.preventDefault()`
- A importância da ordem e quantidade de listeners nos eventos

---

## 🔎 Diferenças entre `onsubmit` e `addEventListener`

| Critério                           | `onsubmit`                           | `addEventListener`                           |
| ----------------------------------- | -------------------------------------- | ---------------------------------------------- |
| Quantidade de listeners             | Apenas o**último** é executado | **Todos** os listeners são executados   |
| Substituição de função anterior | **Sim**, substitui a anterior    | **Não**, adiciona à fila de execução |
| Flexibilidade                       | Menor                                  | Maior                                          |

---

## 🧪 Exemplos Práticos

### 🎯 Usando `onsubmit` diretamente

```javascript
const form = document.querySelector("form");

form.onsubmit = (event) => {
  event.preventDefault();
  console.log("Você fez Submit no formulário - 1");
};

form.onsubmit = (event) => {
  event.preventDefault();
  console.log("Você fez Submit no formulário - 2");
};
```

➡️ Apenas a **mensagem 2** será exibida, pois `onsubmit` ignora a primeira função.

---

### ✅ Usando `addEventListener`

```javascript
form.addEventListener("submit", (event) => {
  event.preventDefault();
  console.log("Você fez Submit no formulário - 3");
});

form.addEventListener("submit", (event) => {
  event.preventDefault();
  console.log("Você fez Submit no formulário - 4");
});
```

➡️ Ambas as mensagens (3 e 4) serão exibidas ao submeter o formulário.

---

## 📌 Observações

* O evento `submit` é disparado tanto ao clicar no botão dentro do formulário quanto ao pressionar **Enter** em um input.
* Usar `event.preventDefault()` é essencial para evitar o recarregamento da página em um formulário HTML padrão.
* Prefira `addEventListener` quando:
  * Precisa adicionar múltiplos comportamentos.
  * Quer manter a modularidade do código.
  * Está desenvolvendo código reutilizável.

---

## 📝 Conclusão

O `submit` é um evento fundamental para trabalhar com formulários em JavaScript. Entender a diferença entre `onsubmit` e `addEventListener` permite criar aplicações mais robustas, flexíveis e controladas. Saber qual técnica utilizar pode evitar bugs e comportamentos inesperados.

---
