# Componentes Reutilizáveis com Vite + React

Atividade prática para demonstrar como um **único componente React** pode ser utilizado várias vezes, recebendo dados diferentes por meio de **props**.

## Requisitos atendidos

- Projeto React configurado com Vite (JavaScript).
- Componente `Header` para o cabeçalho da página.
- Componente **único** `Card` para os cartões.
- Página `App` exibe **1 Header** e **3 Cards**, numerados **1, 2 e 3**.
- Cards renderizados usando `.map()` e `props` (`numero`, `titulo`, `descricao`).
- Estilo limpo e responsivo, sem bibliotecas extras de interface.

## Estrutura

```text
componentes-reutilizaveis-vite-react/
├── src/
│   ├── components/
│   │   ├── Card.jsx
│   │   └── Header.jsx
│   ├── App.jsx
│   ├── main.jsx
│   └── styles.css
├── .gitignore
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

## Como executar

1. Instale o **Node.js 20.19+ ou 22.12+** (requisito do Vite 7).
2. Extraia o ZIP e abra a pasta do projeto no VS Code.
3. No terminal, dentro da pasta do projeto, execute:

```bash
npm install
npm run dev
```

4. Abra o endereço mostrado no terminal (normalmente `http://localhost:5173`).

Para gerar a versão de produção:

```bash
npm run build
```

## Como funciona a reutilização

O `Card.jsx` define a estrutura visual de **um** cartão:

```jsx
export default function Card({ numero, titulo, descricao }) {
  // ... JSX do cartão usando as props ...
}
```

O `App.jsx` reúne os dados e cria as três instâncias do mesmo componente:

```jsx
{cartoes.map((cartao) => (
  <Card key={cartao.numero} {...cartao} />
))}
```

Se for necessário adicionar um quarto cartão, basta adicionar mais um objeto ao array `cartoes`. **Não é necessário criar `Card4.jsx`**.

## Entrega

O arquivo ZIP foi preparado **sem a pasta `node_modules`**, conforme solicitado no enunciado. Depois de extrair, execute `npm install` para baixar as dependências.
