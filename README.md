**MENU**

_Rotas_
* [Cancelamento de ravAuto](#cancelamento-de-ravAuto)
* [Consulta de saldo antecipação Zenite](#consulta-de-saldo-antecipação-Zenite)
* [Consulta de última operação Zenite](#consulta-de-última-operação-Zenite)
* [Consulta de status de operações Zenite](#consulta-de-status-de-operações-Zenite)
* [Consulta de operação Zenite](#consulta-de-operação-Zenite)
* [Consulta de contrato ravAuto](#consulta-de-contrato-ravAuto)
* [Contratação de antecipação Zenite](#contratação-de-antecipação-Zenite)
* [Contratação de ravAuto](#contratação-de-ravAuto)
* [Contratação a antecipação Zenite Kosmo](#contratação-de-antecipação-zenite-kosmo)
* [Simulação de antecipação Zenite](#simulação-de-antecipação-Zenite)
* [Simulação de antecipação Zenite Kosmo](#simulação-de-antecipação-Zenite-Kosmo)


# Documentação das rotas do Sandbox

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
## Cancelamento de ravAuto
Endpoint: /anticipation/zenite/rav-auto

Descrição: This route is used to cancel a ravAuto operation.

Request method (Método): `POST`

## Consulta de saldo antecipação Zenite
Endpoint: /consulta/saldo/antecipacao/zenite

Description: This route is used to retrieve the balance of a Zenite anticipation operation.

Request method: `GET`

<b> Parâmetros de entrada </b>

Request URI: `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/{XXXX}`

- {XXXX} : Substituir pelo valor

| Cenários | Request URI | Response |
|---|---|---|
| Validar get balance kosmos com sucesso | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/0000` | ``` {"pathParameters": {"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}} ``` |


## Consulta de última operação Zenite
Endpoint: /consulta/ultima-operacao/zenite

Description: This route is used to retrieve the details of the last Zenite operation.

Request method: `GET`

## Consulta de status de operações Zenite
Endpoint: /consulta/status-operacoes/zenite

Description: This route is used to retrieve the status of Zenite operations.

Request method: `GET`

## Consulta de operação Zenite
Endpoint: /consulta/operacao/zenite

Description: This route is used to retrieve the details of a Zenite operation.

Request method: `GET`

## Consulta de contrato ravAuto
Endpoint: /consulta/contrato/ravAuto

Description: This route is used to retrieve the details of a ravAuto contract.

Request method: `GET`

## Contratação de antecipação Zenite
Endpoint: /contratacao/antecipacao/zenite

Description: This route is used to contract a Zenite anticipation operation.

Request method: `POST`

## Contratação de ravAuto
Endpoint: /contratacao/ravAuto

Description: This route is used to contract a ravAuto operation.

Request method: `POST`

## Contratação de antecipação Zenite Kosmo
Endpoint: /contratacao/antecipacao/zenite-kosmo

Description: This route is used to contract a Zenite Kosmo anticipation operation.

Request method: `POST`

## Simulação de antecipação Zenite
Endpoint: /simulacao/antecipacao/zenite

Description: This route is used to simulate a Zenite anticipation operation.

Request method: `POST`

## Simulação de antecipação Zenite Kosmo
Endpoint: /simulacao/antecipacao/zenite-kosmo

Description: This route is used to simulate a Zenite Kosmo anticipation operation.

Request method: `POST`
