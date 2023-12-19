# Projeto Node.js - receber requisições HTTP GET e POST

##Configurações

1. **Certifique-se de ter o Node.js instalado no seu sistema.**

   Se você ainda não tem o Node.js instalado, você pode baixá-lo [aqui](https://nodejs.org/). Escolha a versão recomendada para a sua plataforma e siga as instruções de instalação.

2. Instale o pacote Express usando o npm:

    ```bash
    npm install express
    ```

## Iniciando o Servidor

1. Crie um arquivo chamado `server.js` e adicione o seguinte código:

    ```javascript
    // Importando o módulo Express
    const express = require('express');
    const app = express();
    const port = 8080;

    // Configuração para lidar com JSON nos dados das requisições
    app.use(express.json());

    // Rota para requisições HTTP GET
    app.get('/', (req, res) => {
      res.send('Rota GET: Olá, mundo!');
    });

    // Rota para requisições HTTP POST
    app.post('/', (req, res) => {
      // Acessando os dados do corpo da requisição POST
      const data = req.body;

      res.json({ message: 'Rota POST: Dados recebidos com sucesso!', data });
    });

    // Iniciando o servidor na porta especificada
    app.listen(port, () => {
      console.log(`Servidor rodando na porta ${port}`);
    });
    ```

2. No terminal, execute o seguinte comando para iniciar o servidor:

    ```bash
    node server.js
    ```

3. Pronto! Agora você deverá ver a mensagem "Servidor rodando na porta 8080" no console.

## Testando o Servidor

Você pode testar as rotas acessando `http://localhost:8080` no seu navegador ou usando ferramentas como o [Postman](https://www.postman.com/) para enviar requisições GET e POST.
