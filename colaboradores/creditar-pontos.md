# Colaboradores

#### Creditar pontos a um colaborador

<span style="color: #00C853">**[POST]**</span> ```https://app.wecarecorp.com.br/api/v1/users/:id/transactions```

<br>
**Parâmetros:**

|Parâmetro|Descrição|
|:--------|:--------|
|id <span style="color: rgba(0, 0, 0, 0.54)">(string, obrigatório)</span>|Identificador do colaborador, email ou login alternativo|

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
  "transaction": {
    "points": quantidade de pontos (inteiro),
    "message": mensagem de feedback (string, opcional)
  }
}
```

---

**Resposta bem sucedida:**

**Código:** 201 Created

**Conteúdo:**

```json
{
  "sucesso": "Pontos adicionados com sucesso"
}
```

---

**Resposta mal sucedida:** creditar pontos negativos ou nulos

**Código:** 400 Bad Request

**Conteúdo:**

```json
{
  "points": [
    "tem que ser maior ou igual a 1"
  ]
}
```

---

**Resposta mal sucedida:** creditar pontos como uma string

**Código:** 400 Bad Request

**Conteúdo:**

```json
{
  "points": [
    "não é um inteiro"
  ]
}
```

---

**Resposta mal sucedida:** creditar pontos a um colaborador que não existe

**Código:** 404 Not Found

**Conteúdo:**

```json
{
  "erro": "o colaborador não existe"
}
```

---

**Resposta mal sucedida:** creditar pontos a um colaborador que não seja da sua empresa

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
  "url": "https://app.wecarecorp.com.br/api/v1/users/1/transactions",
  "method": "POST",
  "headers": {
    "authorization": "Basic Token-de-Autenticacao",
    "content-type": "application/json",
    "cache-control": "no-cache"
  },
  "processData": false,
  "data": "{\n\t\"transaction\": {\n\t\t\"points\": 4000,\n\t\t\"message\": \"Parabéns\"\n\t}\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```