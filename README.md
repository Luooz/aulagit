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

| CT-NCA-XXX | Cenários | Request URI/urlPathPattern | Response |
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
Endpoint: /anticipation/zenite/last-operation

Request method: `GET`

| CT-NCA-XXX | Cenários | Request URI/urlPathPattern | Response |
|---|---|---|---|
| CT-NCA-140 | Validar get consult operations last operation com sucesso zenite | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/last-operation?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "consult", "code": "0000", "object": { "periodRate": 0.126599, "companyNumber": 3008550, "operationStatusUpdate": "2022-09-30T15:05:06", "liquidationDate": "2022-10-03T00:00:00", "historic": [ { "operationStatusCode": 1, "operationStatusUpdate": "2022-09-30T15:00:04", "operationStatusDescription": "Pendente processamento" }, { "operationStatusCode": 3, "operationStatusUpdate": "2022-09-30T15:05:06", "operationStatusDescription": "Acatado pela CIP" } ], "netRevenueAmount": 106.0, "monthRate": 3.8, "modalityDescription": "Ambos", "indicatedAutomaticAnticipation": false, "descriptionProductAnticipation": "0001", "operationStatusDescription": "Acatado pela CIP", "operatorCode": "CISIMIS", "operationNumber": 30322, "operationStatusCode": 3, "mediumTerm": 1, "grossRevenueAmount": 178.24, "operationDate": "2022-09-30T00:00:00" } }` |
| CT-NCA-141 | Validar get consult operations last operation com header "Autorization" com valor inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/last-operation?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-142 | Validar get consult operations last operation com header "Autorization" com valor vazio | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/last-operation?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-143 | Validar get consult operations last operation com header "Autorization" com valor em branco | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/last-operation?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-144 | Validar get consult operations last operation com header "Autorization" com token inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/last-operation?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-145 | Validar get consult operations last operation sem header "Autorization" | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/last-operation?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-146 | Validar get consult operations last operation com queryString operationNumber com valor inválido zenite | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/last-operation?operationDate=2022-09-30&companyNumber=3008550&operationNumber=%24%3E%23%29%28` | `{ "queryStringParameters": { "operationNumber": [ "Not a valid integer." ] } }` |
| CT-NCA-147 | Validar get consult operations last operation com queryString companyNumber com valor inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/last-operation?operationDate=2022-09-30&companyNumber=%25%2C%3E%3C%7B&operationNumber=30322` | `{ "queryStringParameters": { "companyNumber": [ "Not a valid integer." ] } }` |
| CT-NCA-148 | Validar get consult operations last operation com queryString operationDate com valor inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/last-operation?operationDate=%23%3C%25%21%3F&companyNumber=3008550&operationNumber=30322` | `{ "errors": { "code": "1012", "message": "operationDate invalid value in the path variable", "status": 400 } }` |

## Consulta de status de operações Zenite
Endpoint: /anticipation/zenite/operation-status

Request method: `GET`

| CT-NCA-XXX | Cenários | Request URI/urlPathPattern | Response |
|---|---|---|---|
| CT-NCA-131 | Validar get consult operations last operation com sucesso | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operation-status?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "consult", "code": "0000", "object": { "operationStatusCode": 3, "operationStatusUpdate": "2022-09-30T15:05:06", "operationStatusDescription": "Acatado pela CIP" } }` |
| CT-NCA-132 | Validar get consult operations status com header "Autorization" com valor inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operation-status?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-133 | Validar get consult operations status com header "Autorization" com valor vazio | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operation-status?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` | 
| CT-NCA-134 | Validar get consult operations status com header "Autorization" com valor em branco | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operation-status?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-135 | Validar get consult operations status com header "Autorization" com token inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operation-status?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` | 
| CT-NCA-136 | Validar get consult operations status sem header "Autorization" | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operation-status?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` | 
| CT-NCA-137 | Validar get consult operations status com queryString operationNumber com valor inválido | `https://rl7-hom- api.useredecloud.com.br/anticipation/zenite/operation-status?operationDate=2022-09-30&companyNumber=3008550&operationNumber=%2C%5B%7B%3C_` | `{ "queryStringParameters": { "operationNumber": [ "Not a valid integer." ] } }` |
| CT-NCA-138 | Validar get consult operations status com queryString companyNumber com valor inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operation-status?operationDate=2022-09-30&companyNumber=%3A%21%28%3B_&operationNumber=30322` | `{ "queryStringParameters": { "companyNumber": [ "Not a valid integer." ] } }` |
| CT-NCA-139 | Validar get consult operations status com queryString operationDate com valor inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operation-status?operationDate=%3F%7B%3D%23.&companyNumber=3008550&operationNumber=30322` | `{ "errors": { "code": "1012", "message": "operationDate invalid value in the path variable", "status": 400 } }` |

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
