# Gestanca

API da aplicação do aplicativo de delivery de pizza.

## Endpoints

- Cardápio
    - Cadastrar produto
    - Apagar produto
    - Alterar produto
    - Listar todos os produtos
- Pedido
    - Cadastrar pedido
    - Apagar pedido
    - Alterar pedido
    - Informações do cliente
- Contas
    - Cadastrar conta
    - Apagar conta
    - Alterar informações do usuário
- Cupons
    - Ativar cupom

---

### Cadastrar Pizza

`POST` /gestanca/api/pizza

| campo | tipo | obrigatório | descrição
|-------|------|:-------------:|----
| nome | string | sim | descrição da pizza (ingredientes)
| tamanho | string | sim | tamanho da pizza (pequena, média e grande)
| preço | big decimal | sim | preço da pizza 
| id | big decimal | sim | id da pizza

  **Exemplo de corpo de requisição**

```js 
{
    nome: Pizza de Calabresa,
    tamanho: 'médio',
    preço: R$ 38.00
}
```

**Respostas**

| código | descrição
|-|-
|201| pizza cadastrada com sucesso
|400| a validação dos campos falhou

---

`DELETE` /gestanca/api/pizza{id}


deleteById = id

**Respostas**

| código | descrição
|-|-
|200| a pizza foi excluida
|404| erro ao deletar 


---
`PATCH`/gestanca/api/pizza{id}

url: "/gestanca/api/pizza{id}"

{
tamanho: "grande"
}

---

**Respostas**

| código | descrição
|-|-
|200| alteração feita com sucesso
|404| não foi possível fazer a alteração


### Listar pizza

`GET` /gestanca/api/pizza/{id}

**Respostas**

| código | descrição
|-|-
|200| aqui está a lista completa de pizzas


**Exemplo de corpo da resposta**
```js 
{
    nome: Pizza de Calabresa,
    tamanho: 'médio',
    preço: R$ 38.00
}
```
