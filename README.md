# 🌐 Consumindo API Externa com JavaScript

Projeto de estudo desenvolvido para praticar o consumo de APIs externas utilizando requisições HTTP com o método `fetch` nativo do JavaScript.

---

## 📋 Sobre o Projeto

Esta aplicação realiza uma requisição HTTP do tipo **GET** para uma API pública de posts, retorna os dados em formato JSON e os renderiza dinamicamente no DOM, exibindo título, imagem de capa e subtítulo de cada post em uma lista.

---

## 🚀 Tecnologias Utilizadas

- **HTML5** — estrutura semântica da página
- **CSS3** — estilização e layout com Flexbox
- **JavaScript (ES6+)** — lógica, manipulação do DOM e requisições HTTP

---

## 🔗 API Utilizada

| Campo       | Valor                                              |
|-------------|---------------------------------------------------|
| Endpoint    | `https://sujeitoprogramador.com/rn-api/?api=posts` |
| Método      | `GET`                                             |
| Formato     | `JSON`                                            |

**Exemplo de estrutura retornada:**
```json
[
  {
    "titulo": "Título do post",
    "subtitulo": "Subtítulo do post",
    "capa": "https://url-da-imagem.jpg"
  }
]
```

---

## 📁 Estrutura de Arquivos

```
projeto/
├── index.html
├── css/
│   └── style.css
└── js/
    └── script.js
```

---

## 🧠 Conceitos Praticados

### `fetch()` — Requisição HTTP
O método `fetch()` é nativo do JavaScript e retorna uma **Promise**. É utilizado para fazer requisições a servidores externos.

```js
fetch("https://url-da-api.com/endpoint")
  .then((response) => response.json())  // converte a resposta para JSON
  .then((data) => {
    // utiliza os dados recebidos
  })
  .catch(() => {
    console.log("Erro na requisição!");
  });
```

### Encadeamento de Promises (`.then` / `.catch`)
- `.then()` — executado quando a Promise é resolvida com sucesso
- `.catch()` — executado quando ocorre algum erro na requisição

### Manipulação do DOM
Os dados recebidos da API são utilizados para criar elementos HTML dinamicamente:

```js
let liElement = document.createElement("li");
let titleElement = document.createElement("strong");
titleElement.appendChild(document.createTextNode(item.titulo));
liElement.appendChild(titleElement);
document.querySelector("#app").appendChild(liElement);
```

### `Array.map()`
Utilizado para percorrer o array de posts retornado pela API e renderizar cada item na tela.

---

## ▶️ Como Executar

1. Clone ou baixe este repositório
2. Abra o arquivo `index.html` diretamente no navegador
   > ⚠️ Recomenda-se usar uma extensão como **Live Server** (VS Code) para evitar bloqueios de CORS em ambiente local.

---

## 📌 Fluxo da Aplicação

```
Página carrega
     ↓
nutriApp() é chamada
     ↓
fetch() dispara requisição GET para a API
     ↓
Resposta convertida para JSON
     ↓
Array de posts percorrido com .map()
     ↓
Elementos HTML criados e inseridos no DOM
     ↓
Posts exibidos na tela
```

---

## 📚 O que aprendi

- Como realizar requisições HTTP com `fetch()`
- Como tratar respostas assíncronas com Promises (`.then`, `.catch`)
- Como converter a resposta da API para JSON com `.json()`
- Como criar e inserir elementos HTML dinamicamente no DOM
- Como iterar sobre arrays com `.map()` para renderizar listas de dados

---

## 👨‍💻 Autor

Dev Souza
