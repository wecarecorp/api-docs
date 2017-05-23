# Recompensas

#### Visualizar uma única recompensa

<span style="color: #2196F3">**[GET]**</span> `https://app.wecarecorp.com.br/api/v1/rewards/:id`

<br>
**Parâmetros:**

|Parâmetro|Descrição|
|:--------|:--------|
|id <span style="color: rgba(0, 0, 0, 0.54)">(inteiro, obrigatório)</span> |Identificador da recompensa|

<br>
**Cabeçalhos:**

|Cabeçalho|Valor|
|:--------|:--------|
|Authorization|Basic Token-de-Autenticação <span style="color: rgba(0, 0, 0, 0.54)">(Autenticação a partir do par `api_key:secret`)</span>|

---

**Resposta bem sucedida:** buscar por uma recompensa que exista

**Código:** 200 OK

**Conteúdo:**

```json
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
```

---

**Resposta mal sucedida:** buscar por uma recompensa que não existe

**Código:** 404 Not Found

**Conteúdo:**

```json
{
  "erro": "Não existe recompensa com este id"
}
```

---

**Exemplo de requisição:**

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://app.wecarecorp.com.br/api/v1/rewards/1",
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