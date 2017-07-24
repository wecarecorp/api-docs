# Colaboradores

#### Visualizar extrato do colaborador

<span style="color: #2196F3">**[GET]**</span> `https://app.wecarecorp.com.br/api/v1/users/:id/transactions`

<br>
**Parâmetros:**

|Parâmetro|Valores aceitos|Descrição|
|:--------|:----|:--------|
|id <span style="color: rgba(0, 0, 0, 0.54)">(string, obrigatório)</span> |Qualquer string|Id do colaborador, email, login alternativo|
|month <span style="color: rgba(0, 0, 0, 0.54)">(inteiro, optativo)</span>|1-12|Mês das transações|
|order_by <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|created_by|Ordena resultados por data de criação|
|reverse <span style="color: rgba(0, 0, 0, 0.54)">(boolean, optativo)</span>|true, false|Reverte um resultado ordenado|
|created_min <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|data (dd-mm-aaaa)|Data de criação mínima|
|created_max <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|data (dd-mm-aaaa)|Data de criação máxima|
|max_results <span style="color: rgba(0, 0, 0, 0.54)">(inteiro, optativo)</span>|Qualquer inteiro|Limite de resultados|

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
    "operation": "+",
    "points": 10000,
    "message": "Parabéns",
    "created_at": "2017-04-21T09:19:45.773-03:00"
  },
  {
    "id": 2,
    "operation": "-",
    "points": 2000,
    "message": "Aquisição da Recompensa Salto de Paraquedas",
    "created_at": "2017-04-22T10:49:41.703-03:00"
  },
  {
    "id": 3,
    "operation": "+",
    "points": 20000,
    "message": "Parabéns",
    "created_at": "2017-04-23T13:20:32.832-03:00"
  }
]
```

---

**Resposta mal sucedida:** visualizar extrato de um colaborador que não existe

**Código:** 404 Not Found

**Conteúdo:**

```json
{
  "erro": "o colaborador não existe"
}
```

---

**Resposta mal sucedida:** visualizar extrato de um colaborador que não seja da sua empresa

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