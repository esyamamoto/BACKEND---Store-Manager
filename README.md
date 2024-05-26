# Projeto Store Manager


<details>
<summary><strong>👨‍💻 O que foi desenvolvido</strong></summary><br />
Uma API RESTful utilizando a arquitetura em camadas!

A API construída é um sistema de gerenciamento de vendas em que será possível criar, visualizar, deletar e atualizar produtos e vendas. Utilizando o banco de dados MySQL para a gestão de dados.

 </details>

<details>
  <summary><strong>:memo: Tecnologias Utilizadas:</strong></summary><br />

- Javascript
- Docker 
- Node.JS
- Aplicacao em camadas
- Padroes Rest

</details> 

<details>
  <summary><strong>:memo: Habilidades Desenvolvidas:</strong></summary><br />

- Interagir com um banco de dados relacional MySQL;
- Implementar uma API utilizando arquitetura em camadas;
- Criar validações para os dados recebidos pela API;
- Escrever testes para APIs para garantir a implementação dos endpoints;
</details>

<details>
<summary>🎲 Tabelas do banco de dados</summary>

|Diagrama de Entidade-Relacionamento|
|:--:|
|![DER](./public/erStoreManager.png)|

|Tabela|Formato|Notas|
|---|---|---|
|`products`|![Tabela Produtos](./public/tableproducts.png)|O `id` é gerado automaticamente|
|`sales`|![Tabela Vendas](./public/tablesales.png)|O `id` e `date` são gerados automaticamente|
|`sales_products`|![Tabela Vendas-Produtos](./public/tablesalesproducts.png)|Os registros nessa tabela são removidos automaticamente em caso de remoção do produto ou da venda relacionados (`ON DELETE CASCADE`)|

- Os scripts para criar e popular o banco de dados podem ser vistos no diretório [`sql`](./sql);

</details>


<details>
Orientacoes
<details>
<summary>🐳 Iniciando a aplicação no Docker Compose</summary>

```bash
# Instale as dependências
npm install

# Inicie os containers do compose `backend` e `db`
# A aplicação estará disponível em `http://localhost:3001` em modo de desenvolvimento
docker-compose up -d

# É possível ver os logs da aplicação com `docker logs -n 10 -f <nome-do-container>`
docker logs -n 10 -f store_manager
```

</details>
<details>
<summary>🖥️ Iniciando a aplicação localmente</summary>

> ⚠️ Atenção: Ao rodar localmente, a aplicação deverá receber variáveis de ambiente como exemplificado em [`env.example`](./env.example) para poder se comunicar com o serviço de banco de dados.

```bash
# Instale as dependências
npm install

# Inicie apenas o serviço `db` no compose
docker-compose up -d db

# Inicie a aplicação em modo de desenvolvimento
npm run dev:local
```

<summary>🛠 Desenvolvendo a aplicação e rodando testes</summary>
- Antes de rodar os testes do avaliador, garanta que a aplicação esteja executando;
- Desenvolva a aplicação dentro do diretório `backend/src`;
- Desenvolva os testes dentro do diretório `backend/tests`;
    - Os arquivos de testes devem terminar com o sufixo `.test.js`.
  
```bash
#### Comandos dos testes do avaliador
npm run lint     # roda a verificação do linter
npm test         # roda todos os testes no terminal ou
REQ=01 npm test  # rodando apenas o teste do requisito 01 pelo terminal ou
npm run cy:open  # abre a interface gráfica do Cypress para rodar os testes

#### Comandos dos testes com mocha
npm run test:mocha     # roda os testes do mocha
npm run test:coverage  # roda os testes e mostra a cobertura geral
npm run test:mutation  # roda os testes e mostra a cobertura de mutações
```

</details>

</details>

