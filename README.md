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
| tamanho | enum | sim | tamanho da pizza (pequena, média e grande)
| preco | big decimal | sim | preço da pizza 
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

| codigo | descricao
|-|-
|201| pizza cadastrada com sucesso
|400| a validação dos campos falhou

---
### Deletar pizza

`DELETE` /gestanca/api/pizza{id}


deleteById = id

**Respostas**

| código | descrição
|-|-
|200| a pizza foi excluida
|404| erro ao deletar 


---
### Atualizar pizza

`PATCH`/gestanca/api/pizza{id}

url: "/gestanca/api/pizza{id}"

{
tamanho: "grande"
}

---

**Respostas**

| codigo | descricao
|-|-
|200| alteração feita com sucesso
|404| não foi possível fazer a alteração


### Listar pizza

`GET` /gestanca/api/pizza/{id}

**Respostas**

| código | descricao
|-|-
|200| aqui está a lista completa de pizzas


**Exemplo de corpo da resposta**
```js 
{
    nome: Pizza de Calabresa,
    tamanho: 'médio',
    preco: "R$ 38.00"
}
```

-----------------------
### Cadastrar Pedido
`POST` /gestanca/api/pedido

| campo | tipo | obrigatório | descrição
|-------|------|:-------------:|----
| nome | string | sim | descrição da pizza (ingredientes)
| tamanho | string | sim | tamanho da pizza (pequena, média e grande)
| preco | big decimal | sim | preço da pizza 
| entrega | boolean | sim | método de entrega (0 = retirada / 1 = entrega)
| observacoes | string | não | observações do cliente

  **Exemplo de corpo de requisição**

```js 
{
    nome: Pizza de Calabresa,
    tamanho: 'médio',
    preco: R$ 38.00
}
{
    nome: Pizza de marguerita,
    tamanho: 'grande',
    preço: R$ 51.00,
    entrega: 0, 
    observações: 'null'
}
```
**Respostas**

| codigo | descricao
|-|-
|201| pedido concluído
|400| faltam informações nos campos obrigatórios

---
### Informações do cliente
`POST` /gestanca/api/pedido
| campo | tipo | obrigatório | descrição
|-------|------|:-------------:|----
| nome | string | sim | nome do cliente
| endereco | string | sim | endereço do cliente
| telefone | big decimal | sim | telefone do cliente 

  **Exemplo de corpo de requisição**

```js 
{
    nome: 'João',
    endereço: 'rua das laranjeiras',
    telefone: '(11)94356-2345'
    id: '5'
}
```

-----------------------
### Cadastrar contas
`GET`/gestanca/api/conta
| campo | tipo | obrigatório | descrição
|-------|------|:-------------:|----
| nome | string | sim | nome do cliente
| endereço | string | sim | endereço do cliente
| telefone | big decimal | sim | telefone do cliente 
| id | big decimal | sim | id do usuário

  **Exemplo de corpo de requisição**

```js 
{
    nome: 'Pedro',
    endereço: 'rua das parreiras',
    telefone: '(11)94556-2345'
    id: '6'
}
```
---
### Deletar conta
`DELETE` /gestanca/api/conta


deleteById = id

**Respostas**

| código | descricao
|-|-
|200| a conta foi deletada com sucesso
|404| erro ao deletar 

---
### Atualizar conta

`PATCH`/gestanca/api/conta{id}

url: "/gestanca/api/conta{id}"

{
endereço: 'rua dos limoeiros'
}

---

**Respostas**

| código | descricao
|-|-
|200| alteração feita com sucesso
|404| não foi possível fazer a alteração

---
### Cupom

`PATCH`/gestanca/api/pizza{id}

url: "/gestanca/api/pizza{id}"

{
    valor_desconto = (0.x * preço) - preço
    valor_total = valor_desconto - preço
}
