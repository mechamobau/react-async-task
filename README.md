# React.js Async Task

[🇧🇷 Trocar para a versão em português](./README.pt-BR.md)

[![Continuous Integrations](https://github.com/VitorLuizC/react-async-task/actions/workflows/continuous-integrations.yaml/badge.svg?branch=main)](https://github.com/VitorLuizC/react-async-task/actions/workflows/continuous-integrations.yaml)
[![License](https://badgen.net/github/license/VitorLuizC/react-async-task)](./LICENSE)
[![Library minified size](https://badgen.net/bundlephobia/min/react-async-task)](https://bundlephobia.com/result?p=react-async-task)
[![Library minified + gzipped size](https://badgen.net/bundlephobia/minzip/react-async-task)](https://bundlephobia.com/result?p=react-async-task)

## Installation

This library is published in the NPM registry and can be installed using any compatible package manager.

```sh
npm install react-async-task --save

# For Yarn, use the command below.
yarn add react-async-task
```

### Installation from CDN

This module has an IIFE bundle available through JSDelivr and Unpkg CDNs.

```html
<!-- For UNPKG use the code below. -->
<script src="https://unpkg.com/react-async-task"></script>

<!-- For JSDelivr use the code below. -->
<script src="https://cdn.jsdelivr.net/npm/react-async-task"></script>

<script>
  function useProductList() {
    // IIFE module is exposed through the "ReactAsyncTask" global variable.
    return ReactAsyncTask.useAsyncTask(fetchProductList);
  }

  // ...
</script>
```


## Usage

`react-async-task` provides React Hooks to deal with async tasks in React components. All those Hooks could be imported from package.

```jsx
import { useAsyncTask } from 'react-async-task'

function fetchProductsList() {
  return fetch('/api/v1/products-list')
    .then(response => response.json())
    .then(({ products }) => products);
}

function ProductsList() {
  const { result, pending, error } = useAsyncTask(fetchProductsList);

  if (loading) return <p>Loading...</p>

  if (error) return <p>An error has occured during products fetch</p>

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

Released under [MIT License](./LICENSE).
