# Colaboradores

#### Visualizar todos os colaboradores

<span style="color: #2196F3">**[GET]**</span> `https://app.wecarecorp.com.br/api/v1/users`

<br>
Esta ação não exige nenhum parâmetro.

<br>
**Cabeçalhos:**

|Cabeçalho|Valor|
|:--------|:--------|
|Authorization|Basic Token-de-Autenticação <span style="color: rgba(0, 0, 0, 0.54)">(Autenticação a partir do par `api_key:secret`)</span>|
---

**Resposta bem sucedida:**

**Código:** 200 OK

**Conteúdo:**

```json
[
  {
    "id": 1,
    "name": "Colaborador 1",
    "email": "colaborador1@gmail.com",
    "points": 10000,
    "function": "Cargo do colaborador 1",
    "created_at": "2017-02-03T10:55:28.911-02:00"
  },
  {
    "id": 2,
    "name": "Colaborador 2",
    "email": "colaborador2@gmail.com",
    "points": 20000,
    "function": "Cargo do colaborador 2",
    "created_at": "2017-02-03T10:55:28.911-02:00"
  },
  {
    "id": 3,
    "name": "Colaborador 3",
    "email": "colaborador3@gmail.com",
    "points": 30000,
    "function": "Cargo do colaborador 3",
    "created_at": "2017-02-03T10:55:28.911-02:00"
  }
]
```

---

**Exemplo de requisição:**

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://app.wecarecorp.com.br/api/v1/users",
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
