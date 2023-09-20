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
Endpoint: /anticipation/zenite/operations

Request method: `GET`

| CT-NCA-XXX | Cenários | Request URI/urlPathPattern | Response |
|---|---|---|---|
| CT-NCA-117 | Validar get consult operation com sucesso | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operations?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "consult", "code": "0000", "object": { "totalPages": 0, "pageNumber": 0, "data": [ ], "pageSize": 0 } }` |
| CT-NCA-118 | Validar get consult operation com parametro de rota companyNumber com valor inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operations?operationDate=2022-09-30&companyNumber=%3F%5B%5E%2C%25&operationNumber=30322` | `{ "queryStringParameters": { "companyNumber": [ "Not a valid integer." ] } }` |
| CT-NCA-119 | Validar get consult operation com parametro de rota companyNumber com valor inexistente | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operations?operationDate=2022-09-30&companyNumber=000&operationNumber=30322` | `{ "queryStringParameters": { "companyNumber": [ "Must be greater than or equal to 1 and less than or equal to 999999999." ] } }` |
| CT-NCA-120 | Validar get consult operation sem parametro de rota companyNumber zenite | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operations?operationDate=2022-09-30` | `{ "queryStringParameters": { "companyNumber": [ "Missing data for required field." ] } }` |
| CT-NCA-121 | Validar get consult operation com header "Autorization" com valor inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operations?operationDate=2022-09-30` | `{ "queryStringParameters": { "companyNumber": [ "Missing data for required field." ] } }` | 
| CT-NCA-122 | Validar get consult operation com header "Autorization" com valor vazio | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operations?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-123 | Validar get consult operation com header "Autorization" com valor em branco | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operations?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-124 | Validar get consult operation com header "Autorization" com token inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operations?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |
| CT-NCA-125 | Validar get consult operation sem header "Autorization" | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/operations?operationDate=2022-09-30&companyNumber=3008550&operationNumber=30322` | `{ "message": "Unauthorized" }` |

## Consulta de contrato ravAuto
Endpoint: /anticipation/zenite/rav-auto

Request method: `GET`

| CT-NCA-XXX | Cenários | Request URI/urlPathPattern | Response |
|---|---|---|---|
| CT-NCA-271 | Validar consulta de ravAuto com sucesso | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto?companyNumber=41211` | `{ "message": "consult", "code": "0000", "object": { "changeOperator": "CISIMIS", "deletionScheduledDate": "", "anticipationProductCode": 1, "changeHour": "13:04", "headquarterNumber": 41211, "loyaltyFee": 0.0, "pendingStatusCode": 0, "anticipationProductName": "RAV", "returnDescripton": "OK", "companyNumber": 41211, "anticipationRavFee": 0.0, "rateCategoryCode": "XV", "loyaltyStartDate": "", "anticipationBaseDate": "08/08/2023", "loyaltyEndDate": "", "reserveExit": "", "documentNumber": 49190309000180, "authorizationDate": "07/08/2023", "contractDate": "07/08/2023", "authorizationHour": "13:04:14", "rateCategory": 2.5, "authorizationOperator": "CISIMIS", "nextAnticipationDate": "08/08/2023", "nameCategory": "AUTOMATICO (2,50%)", "nameEstablishment": "", "returnCode": 0, "anticipationProductDescripton": "RV", "changeDate": "07/08/2023", "brandSelectedDescription": "TODAS", "brands": [ { "selIndicator": "", "brandCode": 1, "brandDescripton": "MASTERCARD" }, { "selIndicator": "", "brandCode": 2, "brandDescripton": "DINERS CLUB" }, { "selIndicator": "", "brandCode": 5, "brandDescripton": "VISA" }, { "selIndicator": "", "brandCode": 51, "brandDescripton": "CABAL" }, { "selIndicator": "", "brandCode": 60, "brandDescripton": "HIPERCARD" }, { "selIndicator": "", "brandCode": 61, "brandDescripton": "SOROCRED" }, { "selIndicator": "", "brandCode": 63, "brandDescripton": "CUP" }, { "selIndicator": "", "brandCode": 64, "brandDescripton": "SICREDI" }, { "selIndicator": "", "brandCode": 66, "brandDescripton": "CALCARD" }, { "selIndicator": "", "brandCode": 67, "brandDescripton": "AVISTA" }, { "selIndicator": "", "brandCode": 68, "brandDescripton": "CREDSYSTEM" }, { "selIndicator": "", "brandCode": 69, "brandDescripton": "AMERICAN EXPRES" }, { "selIndicator": "", "brandCode": 70, "brandDescripton": "ELO" }, { "selIndicator": "", "brandCode": 72, "brandDescripton": "NOVA BANDEIRA" }, { "selIndicator": "", "brandCode": 74, "brandDescripton": "BANESCARD" }, { "selIndicator": "", "brandCode": 76, "brandDescripton": "JCB" }, { "selIndicator": "", "brandCode": 77, "brandDescripton": "CREDZ" } ], "loyaltyLockIndicator": "", "descriptonPendedingRate": "" } }` |
| CT-NCA-272 | Validar consulta de ravAuto com query param "companyNumber" com valor alfabetico inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto?companyNumber=ABC` | `{ "queryStringParameters": { "companyNumber": [ "Not a valid integer." ] } }` | 
| CT-NCA-273 | Validar consulta de ravAuto com query param "companyNumber" com valor inexistente | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto?companyNumber=90016267` | `{ "errors": { "code": "1019", "message": "Company does dot exist.", "status": 422 } }` |

## Contratação de antecipação Zenite
Endpoint: /anticipation/zenite/hire/domicile

Request method: `POST`



## Contratação de ravAuto
Endpoint: /anticipation/zenite/rav-auto

Request method: `POST`

## Contratação de antecipação Zenite Kosmo
Endpoint: /anticipation/zenite/hire

Request method: `POST`

## Simulação de antecipação Zenite
Endpoint: /anticipation/zenite/simulate/domicile

Request method: `POST`

## Simulação de antecipação Zenite Kosmo
Endpoint: /anticipation/zenite/simulate

Request method: `POST`
