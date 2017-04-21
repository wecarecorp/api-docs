# Colaboradores

#### Visualizar um único colaborador

<span style="color: #2196F3">**[GET]**</span> `https://app.wecarecorp.com.br/api/v1/users/:id`

<br>
**Parâmetros:**

|Parâmetro|Descrição|
|:--------|:--------|
|id <span style="color: rgba(0, 0, 0, 0.54)">(inteiro, obrigatório)</span> |Identificador do colaborador|

<br>
**Cabeçalhos:**

|Cabeçalho|Valor|
|:--------|:--------|
|Authorization|Basic Token-de-Autenticação <span style="color: rgba(0, 0, 0, 0.54)">(Autenticação a partir do par `api_key:secret`)</span>|
---

**Resposta bem sucedida:** buscar por um colaborador que existe e é da sua empresa

**Código:** 200 OK

**Conteúdo:**

```json
{
  "id": 1,
  "name": "Colaborador 1",
  "email": "colaborador1@gmail.com",
  "points": 10000,
  "function": "Cargo do colaborador 1",
  "created_at": "2017-02-03T10:55:28.911-02:00"
}
```

---

**Resposta mal sucedida:** buscar por um colaborador que não existe

**Código:** 404 Not Found

**Conteúdo:**

```json
{
  "erro": "Não existe colaborador com este id"
}
```

---

**Resposta mal sucedida:** buscar por um colaborador que não seja da sua empresa

**Código:** 403 Forbidden

**Conteúdo:**

```json
{
  "erro": "O colaborador não pertence à sua empresa"
}
```

---

**Exemplo de requisição:**

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://app.wecarecorp.com.br/api/v1/users/1",
  "method": "GET",
  "headers": {
    "authorization": "Basic Token-de-Autenticacao",
    "cache-control": "no-cache"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```