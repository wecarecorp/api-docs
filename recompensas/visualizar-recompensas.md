# Recompensas

#### Visualizar todos as recompensas

<span style="color: #2196F3">**[GET]**</span> `https://app.wecarecorp.com.br/api/v1/rewards`

<br>
**Parâmetros:**

|Parâmetro|Valores aceitos|Descrição|
|:--------|:----|:--------|
|name <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|-|Nome do colaborador|
|categoria <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|-|Nome da categoria|
|order_by <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|created_by|Ordena resultados por data de criação|
|reverse <span style="color: rgba(0, 0, 0, 0.54)">(boolean, optativo)</span>|true, false|Reverte um resultado ordenado|
|created_min <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|data (dd-mm-aaaa)|Data de criação mínima|
|created_max <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|data (dd-mm-aaaa)|Data de criação máxima|
|expiration_min <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|data (dd-mm-aaaa)|Data de expiração mínima|
|expiration_max <span style="color: rgba(0, 0, 0, 0.54)">(string, optativo)</span>|data (dd-mm-aaaa)|Data de expiração máxima|
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
    "id": 241,
    "name": "Clube de Cerveja",
    "reward_type": "experience",
    "category": {
      "name": "Gourmet"
    },
    "cost": 6500,
    "provider": "WBeer",
    "location": "Todas",
    "description": "O Clubeer oferece para os sócios um serviço de seleção criteriosa de cervejas feita pelo nosso Beerhunter, que viaja o mundo a fora para trazer dois dos rótulos mais relevantes a serem entregues, mensalmente, nas quantidades que é desejada: 02, 04 ou 06 garrafas.",
    "what_is_valid": "Uma assinatura trimestral no clubeer, onde você ganha 4 garrafas de cervejas artesanais + 1 revista durante 3 meses em sua casa.",
    "about_enterprise": "",
    "stock": 50,
    "expiration_date": "2017-07-31",
    "steps": [
      {
        "number": 4,
        "description": "Pronto! Agora é só curtir sua experiência."
      },
      {
        "number": 3,
        "description": "Responde o e-mail com as informações necessárias;"
      },
      {
        "number": 1,
        "description": "Adquira o produto utilizando seus pontos WeCare na plataforma;"
      },
      {
        "number": 2,
        "description": "Você receberá seu cupom por e-mail junto com as instruções de uso do produto;"
      }
    ],
    "specifications": [
      {
        "number": 1,
        "description": "Código virtual"
      },
      {
        "number": 2,
        "description": "10 dias úteis"
      },
      {
        "number": 3,
        "description": "6 meses após a entrega do código"
      }
    ],
    "created_at": "2017-01-16T13:48:06.056-02:00"
  },
  {
    "id": 232,
    "name": "Vale Cinema",
    "reward_type": "incentive",
    "category": {
      "name": "Lazer"
    },
    "cost": 1500,
    "provider": "Cinemark",
    "location": "Todas",
    "description": "",
    "what_is_valid": "2 ingressos eletrônicos válidos para todos os dias para filmes 2D e 3D da rede CINEMARK\r\n\r\n",
    "about_enterprise": "Maior rede de cinemas do Brasil, a Cinemark está no país desde 1997, e hoje opera 540 salas em 37 cidades brasileiras. Durante o ano de 2013, mais de 42 milhões de espectadores passaram pelos complexos para assistir aos filmes nacionais e estrangeiros. Multinacional com sede nos Estados Unidos, a empresa é a segunda maior cadeia exibidora do mundo e está presente em outros 12 países, como México, Chile e Argentina. Precursora e especializada em complexos multiplex no Brasil, a Cinemark projeta seus espaços de cinema com o objetivo de oferecer conforto e alta tecnologia para seu público e, por isso, conta com salas com melhor visibilidade e som mais nítido.",
    "stock": 50,
    "expiration_date": "2017-06-30",
    "steps": [
      {
        "number": 1,
        "description": "Adquira o produto utilizando seus pontos WeCare na plataforma;"
      },
      {
        "number": 2,
        "description": "Você receberá seu cupom por e-mail junto com as instruções de uso do produto;"
      },
      {
        "number": 3,
        "description": " Acesse: www.cinemark.com.br; "
      },
      {
        "number": 4,
        "description": "Escolha o cinema e o filme de sua preferência (não é valido para filmes 3D/XD) ;"
      },
      {
        "number": 5,
        "description": "Clique no botão “Comprar ingresso” ao lado do filme escolhido; "
      },
      {
        "number": 6,
        "description": "Você será redirecionado ao site “ingresso.com” e confirme o horário escolhido;"
      },
      {
        "number": 7,
        "description": "No carrinho selecione a opção “Super Saver Eletrônico - R$ 0,00”;  "
      },
      {
        "number": 8,
        "description": "Coloque o código recebido no campo de “Senha de validação”;"
      },
      {
        "number": 9,
        "description": "Escolha a forma de entrega e clique em continuar para pagamento;"
      },
      {
        "number": 10,
        "description": "Confira os dados e finalize sua compra."
      }
    ],
    "specifications": [
      {
        "number": 1,
        "description": " Ingresso Virtual"
      },
      {
        "number": 2,
        "description": "Até 2 dias úteis"
      },
      {
        "number": 3,
        "description": "Cupom válido para resgate por 45 dias após o recebimento*"
      }
    ],
    "created_at": "2016-12-28T03:32:14.857-02:00"
  }
]
```

---

**Exemplo de requisição:**

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://app.wecarecorp.com.br/api/v1/rewards",
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
