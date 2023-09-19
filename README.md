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

Request method (Método): `POST`

## Consulta de saldo antecipação Zenite
Endpoint: /anticipation/zenite/balance/{companyNumber}

Request method: `GET`

<b> Parâmetros de entrada </b>

Request URI: `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/{XXXX}`

- {XXXX} : Substituir pelo valor ou nome desejado.

| CT-NCA-XXX | Cenários | Request URI | Response |
|---|---|---|---|
| CT-NCA-109 | Validar get balance kosmos com sucesso | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/0000` | `{"pathParameters": {"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}}` |
| CT-NCA-110 | Validar get balance kosmos com header "Autorization" com valor inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/90085329` | ` {"message": "Unauthorized"} ` |
| CT-NCA-111 | Validar get balance kosmos com header "Autorization" com valor vazio | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/90085329` | ` {"message": "Unauthorized"} ` |
| CT-NCA-112 | Validar get balance kosmos com header "Autorization" com valor em branco | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/90085329` | ` {"message": "Unauthorized"} ` |
| CT-NCA-113 | Validar get balance kosmos com header "Autorization" com token inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/90085329` | ` {"message": "Unauthorized"} ` |
| CT-NCA-114 | Validar get balance kosmos sem header "Autorization" | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/90085329` | ` {"message": "Unauthorized"} ` |
| CT-NCA-115 | Validar get balance kosmos com parametro de rota "companyNumber" com valor alfabetico | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/alfabetico` | `{"pathParameters": {"companyNumber": ["Not a valid integer."]}}` |
| CT-NCA-115 | Validar get balance kosmos com parametro de rota "companyNumber" com valor inexistente | ` https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/0000 ` | `{"pathParameters": {"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}}`


## Consulta de última operação Zenite
Endpoint: /consulta/ultima-operacao/zenite

Request method: `GET`

## Consulta de status de operações Zenite
Endpoint: /consulta/status-operacoes/zenite

Request method: `GET`

## Consulta de operação Zenite
Endpoint: /consulta/operacao/zenite

Request method: `GET`

## Consulta de contrato ravAuto
Endpoint: /consulta/contrato/ravAuto

Request method: `GET`

## Contratação de antecipação Zenite
Endpoint: /contratacao/antecipacao/zenite

Request method: `POST`

## Contratação de ravAuto
Endpoint: /contratacao/ravAuto

Request method: `POST`

## Contratação de antecipação Zenite Kosmo
Endpoint: /contratacao/antecipacao/zenite-kosmo

Request method: `POST`

## Simulação de antecipação Zenite
Endpoint: /simulacao/antecipacao/zenite

Request method: `POST`

## Simulação de antecipação Zenite Kosmo
Endpoint: /simulacao/antecipacao/zenite-kosmo

Request method: `POST`
