# Colaboradores

#### Criar um colaborador

<span style="color: #00C853">**[POST]**</span> ```https://app.wecarecorp.com.br/api/v1/users```

<br>
Esta ação não exige nenhum parâmetro.

<br>
**Cabeçalhos:**

|Cabeçalho|Valor|
|:--------|:--------|
|Authorization|Basic Token-de-Autenticação <span style="color: rgba(0, 0, 0, 0.54)">(Autenticação a partir do par `api_key:secret`)</span>|
|Content-Type|application/json|

<br>
**Corpo da requisição:**

```json
{
  "user": {
    "name": nome (string),
    "email": email (string),
    "sector": setor (string, opcional),
    "function": cargo (string, opcional),
    "cpf": cpf (string),
    "alternative_login": login alternativo (string, opcional)
  }
}
```

---

**Resposta bem sucedida:**

**Código:** 201 Created

**Conteúdo:**

```json
{
  "id": 1275,
  "email": "teste@email.com",
  "created_at": "2017-07-24T15:08:48.715-03:00",
  "updated_at": "2017-07-24T15:08:49.151-03:00",
  "company_id": 8,
  "name": "Teste Usuário",
  "cpf": "019.983.234-12",
  "address": null,
  "sector": null,
  "function": null,
  "points": 0,
  "user_list_id": null,
  "wishlist_id": 123,
  "alternative_login": "teste"
}
```

---

**Exemplo de requisição:**

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://app.wecarecorp.com.br/api/v1/users",
  "method": "POST",
  "headers": {
    "authorization": "Basic Token-de-Autenticacao",
    "content-type": "application/json",
    "cache-control": "no-cache"
  },
  "processData": false,
  "data": "{\n  \"user\": {\n  \t\"name\": \"Teste Usuário\",\n    \"email\": \"teste@email.com\",\n    \"alternative_login\": \"teste\",\n    \"cpf\": \"019.983.234-12\"\n  }\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```