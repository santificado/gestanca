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

### Detalhar despesa

`GET` /gestanca/api/despesa/{id}

**Respostas**

| código | descrição
|-|-
|200| os dados da despesa foram retornados no corpo da resposta
|404| não existe despesa com o id informado

**Exemplo de corpo da resposta**
```js 
{
    valor: 100.00,
    data: '2023-01-27',
    categoria: {
        categoria_id: 1,
        nome: 'lazer',
    }
    conta: {
        conta_id: 1,
        nome: 'itaú',
    },
    descricao: 'cinema com os amigos'
}
```
