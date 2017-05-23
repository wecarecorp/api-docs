# Empresas

#### Visualizar extrato da empresa

<span style="color: #2196F3">**[GET]**</span> `https://app.wecarecorp.com.br/api/v1/transactions`

<br>
**Parâmetros:**

|Parâmetro|Valores aceitos|Descrição|
|:--------|:----|:--------|
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
    "user": {
      "id": 1,
      "name": "Colaborador 1",
      "email": "colaborador1@email.com"
    },
    "operation": "+",
    "points": 3000,
    "message": "Parabéns!",
    "created_at": "2017-05-03T16:32:21.758-03:00"
  },
  {
    "id": 2,
    "user": {
      "id": 2,
      "name": "Colaborador 2",
      "email": "colaborador2@email.com"
    },
    "operation": "+",
    "points": 500,
    "message": "Parabéns!",
    "created_at": "2017-05-03T16:15:14.456-03:00"
  }
]
```

---

**Exemplo de requisição:**

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://app.wecarecorp.com.br/api/v1/transactions",
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