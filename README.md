# WeCare API

A plataforma de incentivos WeCare possui uma API aberta aos gestores das empresas. Essa API permite que o gestor integre com diversos serviços, como as aplicações do Google Suite e Trello, por exemplo.

## Autenticação

Para utilizar a API, é preciso fazer a autenticação com um par de chaves: `api_key`, que é encontrado na seção **API e Integrações** na plataforma de gestão da empresa, e um `secret`. Note que nesta seção é possível criar vários _secret_, qualquer par `api_key:secret` servirá para a autenticação na API.

Toda requisição à API tem que ser feita informando o par `key:secret`.