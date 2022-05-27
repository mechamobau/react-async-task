# React.js Async Task

[🇺🇸 Switch to english version](./README.pt-BR.md)

[![Continuous Integrations](https://github.com/VitorLuizC/react-async-task/actions/workflows/continuous-integrations.yaml/badge.svg?branch=main)](https://github.com/VitorLuizC/react-async-task/actions/workflows/continuous-integrations.yaml)
[![License](https://badgen.net/github/license/VitorLuizC/react-async-task)](./LICENSE)
[![Library minified size](https://badgen.net/bundlephobia/min/react-async-task)](https://bundlephobia.com/result?p=react-async-task)
[![Library minified + gzipped size](https://badgen.net/bundlephobia/minzip/react-async-task)](https://bundlephobia.com/result?p=react-async-task)

React Hooks para gerenciar tarefas assíncronas em componentes React.

## Instalação

Esta biblioteca está publicada no NPM e pode ser instalada usando qualquer gerenciador de pacotes compatível.

```sh
npm install react-async-task --save

# Para Yarn, use o comando abaixo.
yarn add react-async-task
```

### Instalação por CDN

Os pacotes desse módulo IIFE também estão disponíveis nas CDNs JSDelivr e UNPKG.

```html
<!-- Usando o pacote padrão com o UNPKG -->
<script src="https://unpkg.com/react-async-task"></script>

<!-- Usando o pacote padrão com o JSDelivr -->
<script src="https://cdn.jsdelivr.net/npm/react-async-task"></script>

<script>
  function useProductList() {
    // Módulo IIFE está disponível com o objeto global "ReactAsyncTask".
    return ReactAsyncTask.useAsyncTask(fetchProductList);
  }

  // ...
</script>
```

## Como usar

`react-async-task` fornece React Hooks para gerenciar tarefas assíncronas dentro de componentes React. Todos esses Hooks podem ser importados do pacote

```jsx
import { useAsyncTask } from 'react-async-task'

function fetchProductsList() {
  return fetch('/api/v1/products-list')
    .then(response => response.json())
    .then(({ products }) => products);
}

function ProductsList() {
  const { result, pending, error } = useAsyncTask(fetchProductsList);

  if (loading) return <p>Carregando...</p>

  if (error) return <p>Ocorreu um erro durante a busca de produtos</p>

  return (
    <ul>
      {result.map((product) => (
        <li>
          <p>{product.name}</p>
          <p>{product.price}</p>
        </li>
      ))}
    </ul>
  )
}
```

### API

#### `useAsyncTask`

#### `useAsyncTaskLasy`

## License

Lançado sob a licença [MIT](./LICENSE).
