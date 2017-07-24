# Colaboradores

#### Atualizar senha de um colaborador

<span style="color: #ffc107">**[PUT]**</span> ```https://app.wecarecorp.com.br/api/v1/users/:id```

<br>
**Parâmetros:**

|Parâmetro|Descrição|
|:--------|:--------|
|id <span style="color: rgba(0, 0, 0, 0.54)">(string, obrigatório)</span> |Identificador do colaborador, email, login alternativo|

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
    "current_password": senha atual (string),
    "new_password": nova senha (string)
  }
}
```

---

**Resposta bem sucedida:**

**Código:** 200 OK

**Conteúdo:**

```json
{
  "sucesso": "A senha foi atualizada com sucesso"
}
```

---

**Resposta mal sucedida:** atualizar a senha de um colaborador que não existe

**Código:** 404 Not Found

**Conteúdo:**

```json
{
  "erro": "o colaborador não existe"
}
```

---

**Resposta mal sucedida:** atualizar a senha de um colaborador que não seja da sua empresa

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
  "method": "PUT",
  "headers": {
    "authorization": "Basic Token-de-Autenticacao",
    "content-type": "application/json",
    "cache-control": "no-cache"
  },
  "processData": false,
  "data": "{\n  \"user\": {\n  \t\"current_password\": \"teste\",\n\t\"new_password\": \"teste\"\n  }\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```