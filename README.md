# Projeto: Consumo de API de Países

Este projeto faz parte do curso ministrado por [Jonas Schmedtmann](https://www.udemy.com/user/jonasschmedtmann/) na Udemy e tem como objetivo ensinar conceitos fundamentais de **requisições assíncronas** em JavaScript. Utilizamos **AJAX**, **fetch API**, **Promises** e **async/await** para buscar informações de países por meio de uma API.

## Tecnologias Utilizadas
- **JavaScript** (ES6+)
- **Fetch API**
- **AJAX com XMLHttpRequest**
- **Promises**
- **Async/Await**
- **HTML & CSS (para estrutura e estilos básicos)**

## API Utilizada
O projeto consome dados da API **RestCountries**, que fornece informações detalhadas sobre diversos países.

**Nova URL da API:**  
```plaintext
https://restcountries.com/v2/name/{country}
```
Substitua `{country}` pelo nome do país desejado.

## Funcionalidades
- Buscar informações de um país pelo nome.
- Exibir bandeira, nome, região, população, idioma e moeda.
- Identificar e buscar países vizinhos automaticamente.
- Utilização de `fetch()`, `then()`, `catch()`, `async` e `await` para trabalhar com chamadas assíncronas.

## Como Executar o Projeto
1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
   ```
2. Abra o arquivo `index.html` em seu navegador ou utilize uma extensão como **Live Server** no VS Code.
3. Clique no botão para buscar informações do país e visualize os dados na tela.

## Explicação do Código

### **1. Fazendo requisições com AJAX (Método Antigo)**

```javascript
const request = new XMLHttpRequest();
request.open('GET', 'https://restcountries.com/v2/name/brazil');
request.send();

request.addEventListener('load', function () {
  const data = JSON.parse(this.responseText);
  console.log(data);
});
```

### **2. Utilizando Fetch API e Promises**
```javascript
fetch('https://restcountries.com/v2/name/brazil')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(err => console.error('Erro:', err));
```

### **3. Requisições com Async/Await**
```javascript
const getCountryData = async (country) => {
  try {
    const response = await fetch(`https://restcountries.com/v2/name/${country}`);
    const data = await response.json();
    console.log(data);
  } catch (err) {
    console.error('Erro na requisição!', err);
  }
};

getCountryData('brazil');
```

## Conclusão
Este projeto reforça conceitos essenciais para trabalhar com requisições assíncronas e consumo de APIs externas em JavaScript. Ele é uma excelente base para quem deseja aprofundar-se no desenvolvimento web moderno.

## Créditos
Projeto desenvolvido com base no curso de **Jonas Schmedtmann** na Udemy.

