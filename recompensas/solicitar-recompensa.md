# Recompensas

#### Solicitar recompensa a um colaborador

<span style="color: #00C853">**[POST]**</span> ```https://app.wecarecorp.com.br/api/v1/users/:id/orders```

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
  "order": {
    "reward_id": id_da_recompensa (inteiro)
  }
}
```

---

**Resposta bem sucedida:**

**Código:** 201 Created

**Conteúdo:**

```json
{
  "sucesso": "Recompensa solicitada com sucesso"
}
```

---

**Resposta mal sucedida:** o colaborador não possui saldo suficiente

**Código:** 400 Bad Request

**Conteúdo:**

```json
{
  "erro": "O colaborador não possui saldo suficiente"
}
```

---

**Resposta mal sucedida:** solicitar uma recompensa que não existe

**Código:** 404 Not Found

**Conteúdo:**

```json
{
  "erro": "Não existe recompensa com este id"
}
```

---

**Resposta mal sucedida:** solicitar recompensa a um colaborador que não existe

**Código:** 404 Not Found

**Conteúdo:**

```json
{
  "erro": "o colaborador não existe"
}
```

---

**Resposta mal sucedida:** solicitar recompensa a um colaborador que não seja da sua empresa

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
  "url": "https://app.wecarecorp.com.br/api/v1/users/1/orders",
  "method": "POST",
  "headers": {
    "authorization": "Basic Token-de-Autenticacao",
    "content-type": "application/json",
    "cache-control": "no-cache"
  },
  "processData": false,
  "data": "{\n\t\"order\": {\n\t\t\"reward_id\": 1\n\t}\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```