# WIP - Roteiro - Como funciona o `fetch` do JS

[Documentação 'Fetch API' no MDN (pt-BR)](https://developer.mozilla.org/pt-BR/docs/Web/API/Fetch_API/Using_Fetch)
[Documentação 'Fetch API' no MDN (en-US)](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)

## Introdução:
1. O `fetch` é uma função em JavaScript que permite fazer requisições de rede para buscar recursos (como dados ou arquivos) em um servidor.
2. O `fetch` é frequentemente usado para interagir com APIs, que são conjuntos de regras e protocolos que permitem que diferentes sistemas se comuniquem entre si.

## Funcionamento básico do `fetch`:
1. O `fetch` retorna uma promessa (Promise) que representa a resposta da requisição.
2. Podemos encadear métodos na promessa retornada pelo `fetch` para lidar com a resposta.
3. Uso básico do `fetch` com um exemplo simples:

```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Ocorreu um erro:', error);
  });
```
> ### Entendendo o exemplo
> - Nesse exemplo, estamos buscando dados de uma API fictícia (`https://api.example.com/data`).
> - O método `.then()` é usado para processar a resposta retornada pelo `fetch`.
> - usamos o método `.json()` para transformar a resposta em um objeto JavaScript utilizável.
> - Note que podemos acessar os dados e fazer o que quisermos com eles, como exibi-los no console.

## Lidando com erros:
1. É importante lidar com erros ao fazer uma requisição `fetch`.
2. O uso do método `.catch()` é uma das formas de capturar erros. Lembre-se de tratá-los adequadamente.

```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Ocorreu um erro:', error);
  });
```

- Se ocorrer um erro durante a requisição, a promessa será rejeitada e o método `.catch()` será chamado para tratar o erro.

## Manipulando cabeçalhos e enviando dados:
1. É possível manipular cabeçalhos (headers) em uma requisição `fetch` e enviar dados para o servidor.
2. É possível adicionar cabeçalhos personalizados usando o parâmetro `headers` no objeto de configuração do `fetch`.
3. É possível enviar dados em diferentes formatos (JSON, formulário) usando o método `POST` do `fetch`.

```javascript
fetch('https://api.example.com/data', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({ name: 'John', age: 30 })
})
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error('Ocorreu um erro:', error);
  });
```
> ### Entendendo o exemplo
> - Nesse exemplo, estamos enviando um objeto como JSON para a API.
> - Usamos o parâmetro `headers` para especificar o tipo de conteúdo que estamos enviando.
> - O método `JSON.stringify()` é usado para converter o objeto em uma string JSON antes de enviá-lo.


<!--
Nota pessoal:

1. Recapitular

Apresentar os pontos principais abordados durante a explicação.
2. Encoraje o aluno a praticar mais e explorar outras funcionalidades do `fetch` por conta própria.
Lembre-se de adaptar e simplificar a explicação de acordo com o nível de conhecimento do aluno.
-->
