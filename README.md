# 📘 Documentação das Rotas do Sandbox

Bem-vindo à documentação das rotas do ambiente Sandbox! Aqui, você encontrará informações detalhadas sobre as várias rotas disponíveis.

## 📚 Índice

## [Rotas](#rotas)

### 1. RavAuto
- Cancelamento
    - 1.1. [Cancelamento de ravAuto](#cancelamento-de-ravauto) 
- Contratação
    - 1.2. [Contratação de ravAuto](#contratação-de-ravauto)
- Consulta
    - 1.3. [Consulta de Contrato ravAuto](#consulta-de-contrato-ravauto)

### 2. RavAuto Avulso
- Contratação
    - 2.1. [Contratação de Antecipação Zenite](#contratação-de-antecipação-zenite)
    - 2.2. [Contratação de Antecipação Zenite Docimile](#contratação-de-antecipação-zenite-domicile)

- Simulação
    - 2.3. [Simulação de Antecipação Zenite](#simulação-de-antecipação-zenite)
    - 2.4. [Simulação de Antecipação Zenite Domicile](#simulação-de-antecipação-zenite-domicile)

### 3. Consulta de Saldo (Balance)
- [Consulta de Saldo Antecipação Zenite](#consulta-de-saldo-antecipação-zenite)
   - 3.2. Free
   - 3.3. Compan

### 4. Consulta de Operações
- Operations
   - 4.1. [Consulta de Operação Zenite](#consulta-de-operação-zenite)
- Last-operations
   - 4.2. [Consulta de Última Operação Zenite](#consulta-de-última-operação-zenite)
- Status-operations
   - 4.3. [Consulta de Status de Operações Zenite](#consulta-de-status-de-operações-zenite)

---

### 🗂️ Tabela de Rotas

| Rotas | Nomes sugeridos para Pastas | Método |
|---|---|---|
| Cancelamento de ravAuto | --- | --- |
| Consulta de saldo antecipação Zenite | get-balance | `GET` |
| Consulta de última operação Zenite | get-consult-operations-last-operation | `GET` |
| Consulta de status de operações Zenite | get-consult-operations-status | `GET` |
| Consulta de operação Zenite | get-consult-operations | `GET` |
| Consulta de contrato ravAuto | get-consult-contract-ravAuto | `GET` |
| Contratacao de antecipação Zenite | post-hire | `POST` |
| Contratação de ravAuto | post-hire-ravAuto | `POST` |
| Contratação a antecipação Zenite Domicile | post-hire-domicile | `POST` |
| Simulação de antecipação Zenite | post-simulate | `POST` |
| Simulação de antecipação Zenite Domicile | post-simulate-domicile | `POST` |

## Rotas

### Cancelamento de ravAuto

- **Endpoint:** /anticipation/zenite/rav-auto
- **Método:** `POST`

---

### Consulta de Saldo Antecipação Zenite
`get-balance`
- **Endpoint:** /anticipation/zenite/balance/{companyNumber}
- **Método:** `GET`

<b> Parâmetros de entrada </b>

Request URI: `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/{XXXX}`

- {XXXX} : Substituir pelo valor ou nome específico.

### Cenários de Teste
Aqui estão os cenários que você pode usar para testar esta rota no Insomnia:

| Cenários | Request URI/urlPathPattern | Response |
|---|---|---|
| Validar header 'Autorization' com valor inválido ou vazio | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/([1-9][0-9]{9,})` | `{ "code": "0000", "message": "Unauthorized" }`
| Parametro 'companyNumber' com valor inexistente | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/0.*` | `{ "pathParameters": { "companyNumber": [ "Must be greater than or equal to 1 and less than or equal to 999999999." ] } }`
| Parametro 'companyNumber' com valor alfabetico | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/([A-Z]\|[a-z])*` | `{ "pathParameters": { "companyNumber": [ "Must be greater than or equal to 1 and less than or equal to 999999999." ] } } `
| Validar get sem header 'Autorization' | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/([1-9]\|[1-9][0-9]{0,7})` | `{ "code": "0000", "message": "Unauthorized" }`
| Retorno sucesso | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/([1-9]\|[1-9][0-9]{0,7})` | `{ "code": "0000", "message": "consult", "object": { "totalNegotiatedGravame": 0.0, "totalRevolving": 0.0, "brands": [ { "balance": 647777.04, "code": 1 } ], "totalFree": 647777.04, "totalBlockedAnticipation": 0.0, "totalCreditAssignment": 0.0, "totalAmountInstallments": 647777.04, "grossTotal": 647777.04 } }`

#### 🚀 Testando no Insomnia

1. Abra o Insomnia.
2. Importe o arquivo JSON de configuração.
3. Antes de iniciar os testes, vá para a pasta `RL7 > HOM > RL7 LOGIN` e clique no botão "Send" na cor roxa.
4. Copie o resultado amarelo da chave "access_token" (sem as aspas).
5. Vá para a pasta `RL7 CLOUDFRONT Copy > ZENITE - BALANCE`.
6. Dentro desta pasta, vá a seção "Bearer" e cole no campo Token.
7. Agora, coloque o Request URI/urlPathPattern do cenário que deseja testar no URL.
8. Clique em "Send" na cor roxa para enviar a request.
9. A resposta esperada será exibida no painel.

**Nota:** Continue o padrão acima para as demais rotas, ajustando o nome da pasta conforme a rota que está sendo testada.

#### Exemplos para Rotas GET:

- Para a rota **Consulta de última operação Zenite**, altere para `RL7 - last-operation`.
- Para a rota **Consulta de status de operações Zenite**, altere para `RL7 - operation-status`.
* Para a rota **Consulta de operação Zenite**, altere `RL7 - operations`.
* Para a rota **Consulta de contrato ravAuto**, altere para `RL7 - consult-anticipation-window`.

#### Exemplos para Rotas POST:
- Para a rota **Contratacao de antecipação Zenite**, altere `ZENITE - hire`	
- Para a rota **Contratação de ravAuto**, altere para `New Request`
- Para a rota **Contratação a antecipação Zenite Kosmo**, altere para `ZENITE - hire - kosmo`
- Para a rota **Simulação de antecipação Zenite**, altere para `ZENITE - simulate`	
- Para a rota **Simulação de antecipação Zenite Kosmo**, altere para `ZENITE - simulate - kosmo`

**❗ IMPORTANTE:** Se a resposta não for exibida conforme esperado ou encontrar algum problema, repita o 3º passo para garantir que o "access_token" está atualizado e tente novamente.

---

## Consulta de última operação Zenite
`get-consult-operations-last-operation`

- **Endpoint:** /anticipation/zenite/last-operation

- **Método:** `GET`

### Cenários de Teste
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

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Consulta de status de operações Zenite
`get-consult-operations-status`

- **Endpoint:** /anticipation/zenite/operation-status

- **Método:** `GET`

### Cenários de Teste
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

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Consulta de operação Zenite
`get-consult-operations`

- **Endpoint:** /anticipation/zenite/operations

- **Método:** `GET`

### Cenários de Teste
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

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Consulta de contrato ravAuto 
`get-consult-contract-ravAuto`

Endpoint: /anticipation/zenite/rav-auto

- **Método:** `GET`

### Cenários de Teste
| CT-NCA-XXX | Cenários | Request URI/urlPathPattern | Response |
|---|---|---|---|
| CT-NCA-271 | Validar consulta de ravAuto com sucesso | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto?companyNumber=41211` | `{ "message": "consult", "code": "0000", "object": { "changeOperator": "CISIMIS", "deletionScheduledDate": "", "anticipationProductCode": 1, "changeHour": "13:04", "headquarterNumber": 41211, "loyaltyFee": 0.0, "pendingStatusCode": 0, "anticipationProductName": "RAV", "returnDescripton": "OK", "companyNumber": 41211, "anticipationRavFee": 0.0, "rateCategoryCode": "XV", "loyaltyStartDate": "", "anticipationBaseDate": "08/08/2023", "loyaltyEndDate": "", "reserveExit": "", "documentNumber": 49190309000180, "authorizationDate": "07/08/2023", "contractDate": "07/08/2023", "authorizationHour": "13:04:14", "rateCategory": 2.5, "authorizationOperator": "CISIMIS", "nextAnticipationDate": "08/08/2023", "nameCategory": "AUTOMATICO (2,50%)", "nameEstablishment": "", "returnCode": 0, "anticipationProductDescripton": "RV", "changeDate": "07/08/2023", "brandSelectedDescription": "TODAS", "brands": [ { "selIndicator": "", "brandCode": 1, "brandDescripton": "MASTERCARD" }, { "selIndicator": "", "brandCode": 2, "brandDescripton": "DINERS CLUB" }, { "selIndicator": "", "brandCode": 5, "brandDescripton": "VISA" }, { "selIndicator": "", "brandCode": 51, "brandDescripton": "CABAL" }, { "selIndicator": "", "brandCode": 60, "brandDescripton": "HIPERCARD" }, { "selIndicator": "", "brandCode": 61, "brandDescripton": "SOROCRED" }, { "selIndicator": "", "brandCode": 63, "brandDescripton": "CUP" }, { "selIndicator": "", "brandCode": 64, "brandDescripton": "SICREDI" }, { "selIndicator": "", "brandCode": 66, "brandDescripton": "CALCARD" }, { "selIndicator": "", "brandCode": 67, "brandDescripton": "AVISTA" }, { "selIndicator": "", "brandCode": 68, "brandDescripton": "CREDSYSTEM" }, { "selIndicator": "", "brandCode": 69, "brandDescripton": "AMERICAN EXPRES" }, { "selIndicator": "", "brandCode": 70, "brandDescripton": "ELO" }, { "selIndicator": "", "brandCode": 72, "brandDescripton": "NOVA BANDEIRA" }, { "selIndicator": "", "brandCode": 74, "brandDescripton": "BANESCARD" }, { "selIndicator": "", "brandCode": 76, "brandDescripton": "JCB" }, { "selIndicator": "", "brandCode": 77, "brandDescripton": "CREDZ" } ], "loyaltyLockIndicator": "", "descriptonPendedingRate": "" } }` |
| CT-NCA-272 | Validar consulta de ravAuto com query param "companyNumber" com valor alfabetico inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto?companyNumber=ABC` | `{ "queryStringParameters": { "companyNumber": [ "Not a valid integer." ] } }` | 
| CT-NCA-273 | Validar consulta de ravAuto com query param "companyNumber" com valor inexistente | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto?companyNumber=90016267` | `{ "errors": { "code": "1019", "message": "Company does dot exist.", "status": 422 } }` |

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Contratação de antecipação Zenite
`post-hire`
- **Endpoint:** /anticipation/zenite/hire/domicile

- **Método:** `POST`

### Cenários de Teste
| CT-NCA-XXX | Cenários | Request | Response |
| --- | --- | --- | --- |
| CT-NCA-056 | Validar post hire domicílio com sucesso | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "create", "code": "0000", "object": { "creditAgency": 0, "dateTimeProcessing": "", "minimumValueAnticipateChannel": 0.0, "endPeriodAnticipation": "", "freeGrossValue": 0.0, "gravameGrossValue": 0.0, "startPeriodAnticipation": "", "codeDomicilePayment": 0.0, "domicile": null, "totalAmountAvailableAnticipate": 0.0, "creditBank": 0, "nameProductAnticipation": "", "gravameNetValue": 0.0, "operationNumber": 0, "anticipationDataGravame": null, "discountRate": 0.0, "codeProductAnticipation": 0, "freeNetValue": 0.0 } }` |
| CT-NCA-063 | Validar post hire domicílio com header "Authorization" com valor inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "Unauthorized" }` |
| CT-NCA-064 | Validar post hire domicílio com header "Authorization" com valor em branco | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "Unauthorized" }` |
| CT-NCA-065 | Validar post hire domicílio com header "Authorization" com token inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "Unauthorized" }` |
| CT-NCA-066 | Validar post hire domicílio sem header "Authorization" | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "Unauthorized" }` |
| CT-NCA-072 | Validar post hire domicílio com campo companyNumber com valor inválido zenite | `{ "companyNumber": "ABC", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "companyNumber": [ "Not a valid integer." ] }` |
| CT-NCA-073 | Validar post hire domicílio com campo companyNumber com valor numerico negativo | `{ "companyNumber": "-12", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "companyNumber": [ "Must be greater than or equal to 1 and less than or equal to 999999999." ] }` |
| CT-NCA-074 | Validar post hire domicílio com campo companyNumber com valor vazio | `{ "companyNumber": "", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "companyNumber": [ "Not a valid integer." ] }` |
| CT-NCA-075 | Validar post hire domicílio com campo companyNumber com valor em branco | `{ "companyNumber": " ", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "companyNumber": [ "Not a valid integer." ] }` |
| CT-NCA-076 | Validar post hire domicílio sem campo companyNumber | `{ "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "companyNumber": [ "Missing data for required field." ] }` |
| CT-NCA-077 | Validar post hire domicílio com campo workingDaysToPayment com valor inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": "%#[,%", "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "workingDaysToPayment": [ "Not a valid integer." ] }` |
| CT-NCA-078 | Validar post hire domicílio com campo workingDaysToPayment com valor numerico negativo | `{ "companyNumber": "90078837", "workingDaysToPayment": "-12", "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "workingDaysToPayment: must be no less than 0.", "status": 400 } }` |
| CT-NCA-079 | Validar post hire domicílio com campo workingDaysToPayment com valor vazio | `{ "companyNumber": "90078837", "workingDaysToPayment": "", "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "workingDaysToPayment": [ "Not a valid integer." ] }` |
| CT-NCA-080 | Validar post hire domicílio com campo workingDaysToPayment com valor em branco | `{ "companyNumber": "90078837", "workingDaysToPayment": " ", "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "workingDaysToPayment": [ "Not a valid integer." ] }` |
| CT-NCA-082 | Validar post hire domicílio com campo anticipationType com valor inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "#+,=#", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "anticipationType: must be a valid value.", "status": 400 } }` |
| CT-NCA-083 | Validar post hire domicílio com campo anticipationType com valor vazio | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "anticipationType: attribute is required.", "status": 400 } }` |
| CT-NCA-084 | Validar post hire domicílio com campo anticipationType com valor em branco | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": " ", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "anticipationType: must be a valid value.", "status": 400 } }` |
| CT-NCA-085 | Validar post hire domicílio sem campo anticipationType | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "anticipationType: attribute is required.", "status": 400 } }` |
| CT-NCA-086 | Validar post hire domicílio com campo anticipationAmount com valor inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": "^:_.}", "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "anticipationAmount": [ "Not a valid number." ] }` |
| CT-NCA-087 | Validar post hire domicílio com campo anticipationAmount com valor zerado e campo anticipationType com valor "P" | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": "0", "anticipationType": "P", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1008", "message": "Requested amount out of range: 1.00, 1000000000.00", "status": 422 } }` |
| CT-NCA-088 | Validar post hire domicílio com campo anticipationAmount com valor zerado e campo anticipationType com valor "T" | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": "0", "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "create", "code": "0000", "object": { "creditAgency": 0, "dateTimeProcessing": "", "minimumValueAnticipateChannel": 0.0, "endPeriodAnticipation": "", "freeGrossValue": 0.0, "gravameGrossValue": 0.0, "startPeriodAnticipation": "", "codeDomicilePayment": 0.0, "domicile": null, "totalAmountAvailableAnticipate": 0.0, "creditBank": 0, "nameProductAnticipation": "", "gravameNetValue": 0.0, "operationNumber": 0, "anticipationDataGravame": null, "discountRate": 0.0, "codeProductAnticipation": 0, "freeNetValue": 0.0 } }` |
| CT-NCA-089 | Validar post hire domicílio com campo anticipationAmount com valor vazio | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": "", "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "anticipationAmount": [ "Not a valid number." ] }` |
| CT-NCA-090 | Validar post hire domicílio com campo anticipationAmount com valor em branco | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": " ", "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "anticipationAmount": [ "Not a valid number." ] }` |
| CT-NCA-091 | Validar post hire domicílio sem campo anticipationAmount | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "create", "code": "0000", "object": { "creditAgency": 0, "dateTimeProcessing": "", "minimumValueAnticipateChannel": 0.0, "endPeriodAnticipation": "", "freeGrossValue": 0.0, "gravameGrossValue": 0.0, "startPeriodAnticipation": "", "codeDomicilePayment": 0.0, "domicile": null, "totalAmountAvailableAnticipate": 0.0, "creditBank": 0, "nameProductAnticipation": "", "gravameNetValue": 0.0, "operationNumber": 0, "anticipationDataGravame": null, "discountRate": 0.0, "codeProductAnticipation": 0, "freeNetValue": 0.0 } }` |
| CT-NCA-092 | Validar post hire domicílio com campo selectionType com valor inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": ",}]-+", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "selectionType: must be a valid value.", "status": 400 } }` |
| CT-NCA-093 | Validar post hire domicílio com campo selectionType com valor vazio | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "create", "code": "0000", "object": { "creditAgency": 0, "dateTimeProcessing": "", "minimumValueAnticipateChannel": 0.0, "endPeriodAnticipation": "", "freeGrossValue": 0.0, "gravameGrossValue": 0.0, "startPeriodAnticipation": "", "codeDomicilePayment": 0.0, "domicile": null, "totalAmountAvailableAnticipate": 0.0, "creditBank": 0, "nameProductAnticipation": "", "gravameNetValue": 0.0, "operationNumber": 0, "anticipationDataGravame": null, "discountRate": 0.0, "codeProductAnticipation": 0, "freeNetValue": 0.0 } }` |
| CT-NCA-094 | Validar post hire domicílio com campo selectionType com valor em branco | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": " ", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "selectionType: must be a valid value.", "status": 400 } }` |
| CT-NCA-097 | Validar post hire domicílio com campo product com valor inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "(!)]|", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "product: must be a valid value.", "status": 400 } }` |
| CT-NCA-098 | Validar post hire domicílio com campo product com valor vazio | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "product: attribute is required.", "status": 400 } }` |
| CT-NCA-099 | Validar post hire domicílio com campo product com valor em branco | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": " ", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "product: must be a valid value.", "status": 400 } }` |
| CT-NCA-100 | Validar post hire domicílio sem campo product | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "product: attribute is required.", "status": 400 } }` |
| CT-NCA-101 | Validar post hire domicílio com campo anticipationGravame com valor inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "((+{+", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "anticipationGravame: must be a valid value.", "status": 400 } }` |
| CT-NCA-102 | Validar post hire domicílio com campo anticipationGravame com valor vazio | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "anticipationGravame: attribute is required.", "status": 400 } }` |
| CT-NCA-103 | Validar post hire domicílio com campo anticipationGravame com valor em branco | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": " ", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "anticipationGravame: must be a valid value.", "status": 400 } }` |
| CT-NCA-104 | Validar post hire domicílio sem campo anticipationGravame | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "anticipationGravame: attribute is required.", "status": 400 } }` |
| CT-NCA-105 | Validar post hire domicílio com campo desiredDiscountPercentage com valor inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "739347", "endSelectionDate": "2023-12-31", "partnerNumber": 2, "desiredDiscountPercentage": -15 }` | `{ "message": "create", "code": "0000", "object": { "creditAgency": 0, "dateTimeProcessing": "", "minimumValueAnticipateChannel": 0.0, "endPeriodAnticipation": "", "freeGrossValue": 0.0, "gravameGrossValue": 0.0, "startPeriodAnticipation": "", "codeDomicilePayment": 0.0, "domicile": null, "totalAmountAvailableAnticipate": 0.0, "creditBank": 0, "nameProductAnticipation": "", "gravameNetValue": 0.0, "operationNumber": 0, "anticipationDataGravame": null, "discountRate": 0.0, "codeProductAnticipation": 0, "freeNetValue": 0.0 } }` |
| CT-NCA-106 | Validar post hire domicílio com campo operationUser com valor inválido | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "1234567890", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "errors": { "code": "1002", "message": "operationUser: the length must be no more than 9.", "status": 400 } }` |
| CT-NCA-107 | Validar post hire domicílio com campo operationUser com valor fora do padrão | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": "123", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "create", "code": "0000", "object": { "creditAgency": 0, "dateTimeProcessing": "", "minimumValueAnticipateChannel": 0.0, "endPeriodAnticipation": "", "freeGrossValue": 0.0, "gravameGrossValue": 0.0, "startPeriodAnticipation": "", "codeDomicilePayment": 0.0, "domicile": null, "totalAmountAvailableAnticipate": 0.0, "creditBank": 0, "nameProductAnticipation": "", "gravameNetValue": 0.0, "operationNumber": 0, "anticipationDataGravame": null, "discountRate": 0.0, "codeProductAnticipation": 0, "freeNetValue": 0.0 } }` |
| CT-NCA-108 | Validar post hire domicílio com campo operationUser com valor em branco | `{ "companyNumber": "90078837", "workingDaysToPayment": 1, "channel": 15, "anticipationAmount": 0, "anticipationType": "T", "selectionType": "V", "product": "A", "codeProduct": 201, "anticipationGravame": "N", "startSelectionDate": "2022-08-23", "operationUser": " ", "endSelectionDate": "2023-12-31", "partnerNumber": 2 }` | `{ "message": "create", "code": "0000", "object": { "creditAgency": 0, "dateTimeProcessing": "", "minimumValueAnticipateChannel": 0.0, "endPeriodAnticipation": "", "freeGrossValue": 0.0, "gravameGrossValue": 0.0, "startPeriodAnticipation": "", "codeDomicilePayment": 0.0, "domicile": null, "totalAmountAvailableAnticipate": 0.0, "creditBank": 0, "nameProductAnticipation": "", "gravameNetValue": 0.0, "operationNumber": 0, "anticipationDataGravame": null, "discountRate": 0.0, "codeProductAnticipation": 0, "freeNetValue": 0.0 } }`

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Contratação de ravAuto
`post-hire-ravAuto`
- **Endpoint:** /anticipation/zenite/rav-auto

- **Método:** `POST`

### Cenários de Teste
| CT-NCA-XXX | Cenários | Request | Response |
| --- | --- | --- | --- |
| CT-NCA-223 | Validar contratacao de ravAuto com sucesso sem campo "stockBaseDate" e com campo "anticipateStockIndicator" com valor "N" | `{ "companyNumber": "34100", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233" }` | `{ "message": "create", "code": "0000", "object": { "message": "successful hiring", "companyNumber": 34100 } }` |
| CT-NCA-224 | Validar contratacao de ravAuto com campo "companyNumber" com valor inválido | `{ "companyNumber": "ABC",  "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "companyNumber": [ "Not a valid integer." ] }` |
| CT-NCA-225 | Validar contratacao de ravAuto sem campo "companyNumber" | `{ "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "companyNumber": [ "Missing data for required field." ] }` |
| CT-NCA-226 | Validar contratacao de ravAuto com campo "productCode" com quantidade de caracteres acima do permitido | `{ "companyNumber": "90078837", "productCode": "AA", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "productCode: the length must be exactly 1.", "status": 400 } }` |
| CT-NCA-227 | Validar contratacao de ravAuto com campo "productCode" com valor numérico inválido | `{ "companyNumber": "90078837", "productCode": 1, "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "productCode": [ "Not a valid string." ] }` |
| CT-NCA-228 | Validar contratacao de ravAuto com campo "productCode" com valor alfabético inválido | `{ "companyNumber": "90078837", "productCode": "W", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "productCode: must be a valid value.", "status": 400 } }` |
| CT-NCA-229 | Validar contratacao de ravAuto com campo "productCode" com valor em branco | `{ "companyNumber": "90078837", "productCode": " ", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "productCode: the length must be exactly 1.", "status": 400 } }` |
| CT-NCA-230 | Validar contratacao de ravAuto com campo "productCode" com valor vazio | `{ "companyNumber": "90078837", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "productCode: attribute is required.", "status": 400 } }` |
| CT-NCA-231 | Validar contratacao de ravAuto sem campo "productCode" | `{ "companyNumber": "90078837", "firstInstallments": 1, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | 
| CT-NCA-232 | Validar contratacao de ravAuto com campo "firstInstallments" com valor inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": "ABC", "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "firstInstallments": [ "Not a valid integer." ] }` |
| CT-NCA-233 | Validar contratacao de ravAuto com campo "firstInstallments" com valor abaixo do permitido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 0, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "firstInstallments: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-234 | Validar contratacao de ravAuto com campo "firstInstallments" com valor acima do permitido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 100, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "firstInstallments: must be no greater than 99.", "status": 400 } }` |
| CT-NCA-235 | Validar contratacao de ravAuto sem campo "firstInstallments" | `{ "companyNumber": "90078837", "productCode": "A", "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "firstInstallments: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-236 | Validar contratacao de ravAuto com campo "lastInstallments" com valor inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": "ABC", "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "lastInstallments": [ "Not a valid integer." ] }` |
| CT-NCA-237 | Validar contratacao de ravAuto com campo "lastInstallments" com valor abaixo do permitido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 0, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "lastInstallments: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-238 | Validar contratacao de ravAuto com campo "lastInstallments" com valor acima do permitido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 100, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "lastInstallments: must be no greater than 99.", "status": 400 } }` |
| CT-NCA-239 | Validar contratacao de ravAuto sem campo "lastInstallments" | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "lastInstallments: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-240 | Validar contratacao de ravAuto com campo "codeFrequency" com quantidade de caracteres acima do permitido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "DD", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "codeFrequency: the length must be exactly 1.", "status": 400 } }` |
| CT-NCA-241 | Validar contratacao de ravAuto com campo "codeFrequency" com valor numérico inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": 1, "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "codeFrequency": [ "Not a valid string." ] }` |
| CT-NCA-242 | Validar contratacao de ravAuto com campo "codeFrequency" com valor alfabético inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "W", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "codeFrequency: must be a valid value.", "status": 400 } }` |
| CT-NCA-243 | Validar contratacao de ravAuto com campo "codeFrequency" com valor em branco | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": " ", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "codeFrequency: must be a valid value.", "status": 400 } }` |
| CT-NCA-244 | Validar contratacao de ravAuto com campo "codeFrequency" com valor vazio | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "codeFrequency: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-245 | Validar contratacao de ravAuto sem campo "codeFrequency" | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "codeFrequency: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-246 | Validar contratacao de ravAuto com campo "startExpiryDate" com valor alfabético inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "ABC", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "startExpiryDate: must be a valid date.", "status": 400 } }` |
| CT-NCA-247 | Validar contratacao de ravAuto com campo "startExpiryDate" com valor em branco | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": " ", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "startExpiryDate: must be a valid date.", "status": 400 } }` |
| CT-NCA-248 | Validar contratacao de ravAuto com campo "startExpiryDate" com valor vazio | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "startExpiryDate: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-249 | Validar contratacao de ravAuto com campo "startExpiryDate" com valor vazio | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "07.31.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "startExpiryDate: must be a valid date.", "status": 400 } }` |
| CT-NCA-250 | Validar contratacao de ravAuto sem campo "startExpiryDate" | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "startExpiryDate: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-251 | Validar contratacao de ravAuto com campo "endExpiryDate" com valor alfabético inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "ABC", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "endExpiryDate: must be a valid date.", "status": 400 } }` |
| CT-NCA-252 | Validar contratacao de ravAuto com campo "endExpiryDate" com valor em branco | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": " ", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "endExpiryDate: must be a valid date.", "status": 400 } }` |
| CT-NCA-253 | Validar contratacao de ravAuto com campo "endExpiryDate" com valor vazio | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "endExpiryDate: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-254 | Validar contratacao de ravAuto com campo "endExpiryDate" com valor fora do padrão | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "08.31.2023", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "endExpiryDate: must be a valid date.", "status": 400 } }` |
| CT-NCA-255 | Validar contratacao de ravAuto com campo "endExpiryDate" com data menor que data no campo "startExpiryDate" | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "29.07.2023", "endExpiryDate": "01.07.2023", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "endExpiryDate: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-256 | Validar contratacao de ravAuto sem campo "endExpiryDate" | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "endExpiryDate: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-257 | Validar contratacao de ravAuto com campo "anticipationMinValue" com valor numérico inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": -1, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "anticipationMinValue: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-258 | Validar contratacao de ravAuto com campo "anticipationMinValue" com valor alfabético inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": "ABC", "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "anticipationMinValue": [ "Not a valid integer." ] }` |
| CT-NCA-259 | Validar contratacao de ravAuto sem campo "anticipationMinValue" | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "anticipationMinValue: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-260 | Validar contratacao de ravAuto com campo "anticipateStockIndicator" com quantidade de caracteres acima do permitido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "SS", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "anticipateStockIndicator: the length must be exactly 1.", "status": 400 } }` |
| CT-NCA-261 | Validar contratacao de ravAuto com campo "anticipateStockIndicator" com valor numérico inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": 1, "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "anticipateStockIndicator": [ "Not a valid string." ] }` |
| CT-NCA-262 | Validar contratacao de ravAuto com campo "anticipateStockIndicator" com valor alfabético inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "W", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "anticipateStockIndicator: must be a valid value.", "status": 400 } }` |
| CT-NCA-263 | Validar contratacao de ravAuto com campo "anticipateStockIndicator" com valor em branco | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": " ", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "anticipateStockIndicator: must be a valid value.", "status": 400 } }` |
| CT-NCA-264 | Validar contratacao de ravAuto com campo "anticipateStockIndicator" com valor vazio | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "anticipateStockIndicator: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-265 | Validar contratacao de ravAuto sem campo "anticipateStockIndicator" | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "anticipateStockIndicator: must be a valid value or attribute is required.", "status": 400 } }` |
| CT-NCA-266 | Validar contratacao de ravAuto com campo "operatorCode" com quantidade de dígitos acima do permitido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "73823300000", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1002", "message": "operatorCode: the length must be no more than 9.", "status": 400 } }` |
| CT-NCA-267 | Validar contratacao de ravAuto com campo "stockBaseDate" com valor alfabético inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "ABC" }` | `{ "errors": { "code": "1002", "message": "stockBaseDate: must be a valid date.", "status": 400 } }` |
| CT-NCA-268 | Validar contratacao de ravAuto com campo "stockBaseDate" com valor numérico inválido | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": 1 }` | `{ "stockBaseDate": [ "Not a valid string." ] }` |
| CT-NCA-269 | Validar contratacao de ravAuto com campo "stockBaseDate" com valor fora do padrão | `{ "companyNumber": "90078837", "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "07.31.2023" }` | `{ "errors": { "code": "1002", "message": "stockBaseDate: must be a valid date.", "status": 400 } }` |
| CT-NCA-270 | Validar depara das mensagens de erro internas da API ravAuto na rota de contratacao de ravAuto | `{ "companyNumber": 412500213, "productCode": "A", "firstInstallments": 1, "lastInstallments": 99, "codeFrequency": "D", "startExpiryDate": "22.08.2023", "endExpiryDate": "01.01.2099", "anticipationMinValue": 500, "anticipateStockIndicator": "N", "operatorCode": "738233", "stockBaseDate": "01.01.2000" }` | `{ "errors": { "code": "1019", "message": "non-eligible customer, contact the help desk", "status": 422 } }` |

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Contratação de antecipação Zenite Domicile
`post-hire-domicile`
- **Endpoint:** /anticipation/zenite/hire

- **Método:** `POST`

### Cenários de Teste

| Cenários | Request URI/urlPathPattern | Response |
|---|---|---|
| Validar post hire com campo anticipationAmount com valor zerado e campo product com valor 'V' | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post hire com campo anticipationAmount com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"anticipationAmount": ["Not a valid number."]}` |
| Validar post hire com campo anticipationGravame com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"anticipationGravame": ["Not a valid boolean."]}` |
| Validar post hire com campo channel em branco com falha | /anticipation/zenite/hire | `{"channel": ["Not a valid integer."]}` |
| Validar post hire com campo channel com valor inválido | /anticipation/zenite/hire | `{"channel": ["Not a valid integer."]}` |
| Validar post hire com campo companyNumber com valor numérico negativo | /anticipation/zenite/hire | `{"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}` |
| Validar post hire com campo companyNumber com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"companyNumber": ["Not a valid integer."]}` |
| Validar post hire com header 'Authorization' com token inválido | /anticipation/zenite/hire | `{"message": "Unauthorized"}` |
| Validar post hire com header 'Authorization' com valor inválido ou em branco | /anticipation/zenite/hire | `{"message": "Unauthorized"}` |
| Validar post hire com campo operationUser com valor em branco | /anticipation/zenite/hire | `{"operationUser": ["Not a valid integer."]}` |
| Validar post hire com campo operationUser com valor inválido | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "operationUser: the length must be no more than 8.", "status": 400}}` |
| Validar post hire com campo product com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post hire sem campo anticipationGravame | /anticipation/zenite/hire | `{"errors": {"code": "1016", "message": "This partner is inactive.", "status": 422}}` |
| Validar post hire sem campo companyNumber | /anticipation/zenite/hire | `{"companyNumber": ["Missing data for required field."]}` |
| Validar post hire sem campo product | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "product: attribute is required.", "status": 400}}` |
| Validar post hire sem header 'Authorization' | /anticipation/zenite/hire | `{"message": "Unauthorized"}` |
| Validar post hire com sucesso (validar se seria Kosmos) | /anticipation/zenite/hire | `{"object": {"periodRate": 9.223599, "netValue": 119014.56, "totalRotatingAmount": 0.0, "parcelAmount": 131107.38, "effectiveRate": 5.043661, "financialCost": 1.036515, "monthRate": 4.69, "initialDueDate": "23/10/2023", "finalDueDate": "23/10/2023", "averageTerm": 59.0, "product": "CESSAO", "domiciles": [{"companyNumber": 90078837, "creditAgency": 1500, "gravameIndicator": false, "brandNumber": 1, "codeDomicilePayment": "5544191", "creditBank": 341, "accountType": "CC", "accountNumber": "00000000000000738636"}], "operationNumber": 45756, "spread": 3.966, "brands": [1], "grossValue": 131107.38}, "code": "0000", "message": "create"}` |
| Validar post hire com valor acima do estipulado para o canal | /anticipation/zenite/hire | `{"errors": {"code": "1016", "message": "This partner is inactive.", "status": 422}}` |
| Validar post hire com campo workingDaysToPayment com valor numérico negativo | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "workingDaysToPayment: must be no less than 0.", "status": 400}}` |
| Validar post hire com campo workingDaysToPayment com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"workingDaysToPayment": ["Not a valid integer."]}` |


#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Simulação de antecipação Zenite
`post-simulate`
- **Endpoint:** /anticipation/zenite/simulate/domicile

- **Método:** `POST`

### Cenários de Teste
| CT-NCA-XXX | Cenários | Request URI/urlPathPattern | Response |
|---|---|---|---|
| CT-NCA-013 | Validar post simulate domicílio com valor acima do estipulado para o canal | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 999999999, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1016", "message": "This partner is inactive.", "status": 422}}` |
| CT-NCA-019 | Validar post simulate domicílio com campo companyNumber com valor inválido zenite | `{"companyNumber": "ABC", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"companyNumber": ["Not a valid integer."]}` |
| CT-NCA-020 | Validar post simulate domicílio com campo companyNumber com valor numérico negativo | `{"companyNumber": "-12", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}` |
| CT-NCA-021 | Validar post simulate domicílio com campo companyNumber com valor vazio | `{"companyNumber": "", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"companyNumber": ["Not a valid integer."]}` |
| CT-NCA-022 | Validar post simulate domicílio com campo companyNumber com valor em branco | `{"companyNumber": " ", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"companyNumber": ["Not a valid integer."]}` |
| CT-NCA-023 | Validar post simulate domicílio sem campo companyNumber | `{"workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"companyNumber": ["Missing data for required field."]}` |
| CT-NCA-024 | Validar post simulate domicílio com campo workingDaysToPayment com valor inválido | `{"companyNumber": "90078837", "workingDaysToPayment": "@", "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"workingDaysToPayment": ["Not a valid integer."]}` |
| CT-NCA-025 | Validar post simulate domicílio com campo workingDaysToPayment com valor numérico negativo | `{"companyNumber": "90078837", "workingDaysToPayment": "-12", "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "workingDaysToPayment: must be no less than 0.", "status": 400}}` |
| CT-NCA-026 | Validar post simulate domicílio com campo workingDaysToPayment com valor vazio | `{"companyNumber": "90078837", "workingDaysToPayment": "", "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"workingDaysToPayment": ["Not a valid integer."]}` |
| CT-NCA-027 | Validar post simulate domicílio com campo workingDaysToPayment com valor em branco | `{"companyNumber": "90078837", "workingDaysToPayment": " ", "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"workingDaysToPayment": ["Not a valid integer."]}` |
| CT-NCA-029 | Validar post simulate domicílio com campo anticipationType com valor inválido | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "))[$]", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "anticipationType: must be a valid value.", "status": 400}}` |
| CT-NCA-030 | Validar post simulate domicílio com campo anticipationType com valor vazio | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "anticipationType: attribute is required.", "status": 400}}` |
| CT-NCA-031 | Validar post simulate domicílio com campo anticipationType com valor em branco | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": " ", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "anticipationType: must be a valid value.", "status": 400}}` |
| CT-NCA-032 | Validar post simulate domicílio sem campo anticipationType | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "anticipationType: attribute is required.", "status": 400}}` |
| CT-NCA-033 | Validar post simulate domicílio com campo anticipationAmount com valor inválido | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": "+:}{;", "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"anticipationAmount": ["Not a valid number."]}` |
| CT-NCA-034 | Validar post simulate domicílio com campo anticipationAmount com valor zerado e campo anticipationType com valor "P" | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": "0", "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1016", "message": "This partner is inactive.", "status": 422}}` |
| CT-NCA-036 | Validar post simulate domicílio com campo anticipationAmount com valor vazio | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": "", "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"anticipationAmount": ["Not a valid number."]}` |
| CT-NCA-037 | Validar post simulate domicílio com campo anticipationAmount com valor em branco | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": " ", "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"anticipationAmount": ["Not a valid number."]}` |
| CT-NCA-038 | Validar post simulate domicílio sem campo anticipationAmount | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1016", "message": "This partner is inactive.", "status": 422}}` |
| CT-NCA-039 | Validar post simulate domicílio com campo selectionType com valor inválido | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "|!:#%", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "selectionType: must be a valid value.", "status": 400}}` |
| CT-NCA-041 | Validar post simulate domicílio com campo selectionType com valor em branco | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": " ", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "selectionType: must be a valid value.", "status": 400}}` |
| CT-NCA-044 | Validar post simulate domicílio com campo product com valor inválido | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "}]+^,", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| CT-NCA-045 | Validar post simulate domicílio com campo product com valor vazio | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "product: attribute is required.", "status": 400}}` |
| CT-NCA-046 | Validar post simulate domicílio com campo product com valor em branco | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "   ", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| CT-NCA-047 | Validar post simulate domicílio sem campo product | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "operationUser": "739347", "anticipationGravame": "N"}` | `{"errors": {"code": "1002", "message": "product: attribute is required.", "status": 400}}` |
| CT-NCA-048 | Validar post simulate domicílio com campo anticipationGravame com valor inválido | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "#+!<!"}` | `{"errors": {"code": "1002", "message": "anticipationGravame: must be a valid value.", "status": 400}}` |
| CT-NCA-049 | Validar post simulate domicílio com campo anticipationGravame com valor vazio | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": ""}` | `{"errors": {"code": "1002", "message": "anticipationGravame: attribute is required.", "status": 400}}` |
| CT-NCA-050 | Validar post simulate domicílio com campo anticipationGravame com valor em branco | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347", "anticipationGravame": "   "}` | `{"errors": {"code": "1002", "message": "anticipationGravame: must be a valid value.", "status": 400}}` |
| CT-NCA-051 | Validar post simulate domicílio sem campo anticipationGravame | `{"companyNumber": "90078837", "workingDaysToPayment": 1, "anticipationAmount": 100, "anticipationType": "P", "selectionType": "V", "channel": 6, "startSelectionDate": "2022-08-23", "endSelectionDate": "2023-12-31", "product": "A", "operationUser": "739347"}` | `{"errors": {"code": "1002", "message": "anticipationGravame: attribute is required.", "status": 400}}` |

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Simulação de antecipação Zenite Domicile
`post-simulate-domicile`
- **Endpoint:** /anticipation/zenite/simulate

- **Método:** `POST`

### Cenários de Teste
| Cenários | Request URI/urlPathPattern | Response |
|---|---|---|
| Validar post simulate com amount fora do range mínimo de 100 | /anticipation/zenite/simulate | `{"code": "1016", "message": "This partner is inactive.", "status": 422}` |
| Validar post simulate com campo anticipationAmount com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"anticipationAmount": ["Not a valid number."]}` |
| Validar post simulate com campo anticipationAmount com valor zerado e campo product com valor inválido 'G' | /anticipation/zenite/simulate | `{"code": "0000", "message": "create", "object": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post simulate com campo anticipationGravame com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"anticipationGravame": ["Not a valid boolean."]}` |
| Validar channel null | /anticipation/zenite/simulate | `{"channel": ["Not a valid integer."]}` |
| Validar campo channel inválido | /anticipation/zenite/simulate | `{"channel": ["Not a valid integer."]}` |
| Validar post simulate com campo companyNumber com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"companyNumber": ["Not a valid integer."]}` |
| Validar post simulate com campo companyNumber com valor numérico negativo | /anticipation/zenite/simulate | `{"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}` |
| Validar post simulate com campo operationUser com valor em branco e inválido | /anticipation/zenite/simulate | `{"operationUser": ["Not a valid integer."]}` |
| Validar post simulate com campo operationUser com valor maior que 8 caracteres | /anticipation/zenite/simulate | `{"code": "1002", "message": "operationUser: the length must be no more than 8.", "status": 400}` |
| Validar post simulate com campo product com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post simulate sem campo anticipationGravame | /anticipation/zenite/simulate | `{"code": "1016", "message": "This partner is inactive.", "status": 422}` |
| Validar post simulate sem campo companyNumber | /anticipation/zenite/simulate | `{"companyNumber": ["Missing data for required field."]}` |
| Validar post simulate sem campo product | /anticipation/zenite/simulate | `{"code": "1002", "message": "product: attribute is required.", "status": 400}` |
| Validar post simulate com sucesso | /anticipation/zenite/simulate | `{"object": {"periodRate": 13.913596, "netValue": 50341.03, "totalRotatingAmount": 0.0, "parcelAmount": 58477.33, "effectiveRate": 5.179788, "financialCost": 0.981939, "monthRate": 4.69, "initialDueDate": "22/11/2023", "finalDueDate": "22/11/2023", "averageTerm": 89.0, "product": "CESSAO", "domiciles": [{"companyNumber": 90078837, "creditAgency": 1500, "gravameIndicator": false, "brandNumber": 1, "codeDomicilePayment": "5544191", "creditBank": 341, "accountType": "CC", "accountNumber": "00000000000000738636"}], "spread": 4.157, "brands": [1], "grossValue": 58477.33}, "code": "0000", "message": "create"}` |
| Validar post simulate com valor acima do estipulado para o canal | /anticipation/zenite/simulate | `{"code": "1016", "message": "This partner is inactive.", "status": 422}` |
| Validar post simulate com campo workingDaysToPayment com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"workingDaysToPayment": ["Not a valid integer."]}` |
| Validar post simulate com campo workingDaysToPayment com valor numérico negativo | /anticipation/zenite/simulate | `{"code": "1002", "message": "workingDaysToPayment: must be no less than 0.", "status": 400}` |

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

___

## `get-balance`
| Cenários | Request URI/urlPathPattern | Response |
|---|---|---|
| Validar header 'Autorization' com valor inválido ou vazio | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/([1-9][0-9]{9,})` | `{ "code": "0000", "message": "Unauthorized" }`
| Parametro 'companyNumber' com valor inexistente | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/0.*` | `{ "pathParameters": { "companyNumber": [ "Must be greater than or equal to 1 and less than or equal to 999999999." ] } }`
| Parametro 'companyNumber' com valor alfabetico | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/([A-Z]\|[a-z])*` | `{ "pathParameters": { "companyNumber": [ "Must be greater than or equal to 1 and less than or equal to 999999999." ] } } `
| Validar get sem header 'Autorization' | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/([1-9]\|[1-9][0-9]{0,7})` | `{ "code": "0000", "message": "Unauthorized" }`
| Retorno sucesso | `https://rl7-sandbox-api.useredecloud.com.br/anticipation/zenite/balance/([1-9]\|[1-9][0-9]{0,7})` | `{ "code": "0000", "message": "consult", "object": { "totalNegotiatedGravame": 0.0, "totalRevolving": 0.0, "brands": [ { "balance": 647777.04, "code": 1 } ], "totalFree": 647777.04, "totalBlockedAnticipation": 0.0, "totalCreditAssignment": 0.0, "totalAmountInstallments": 647777.04, "grossTotal": 647777.04 } }`

## `post-hire`

| Cenários | Request URI/urlPathPattern | Response |
|---|---|---|
| Validar post hire com campo anticipationAmount com valor zerado e campo product com valor 'V' | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post hire com campo anticipationAmount com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"anticipationAmount": ["Not a valid number."]}` |
| Validar post hire com campo anticipationGravame com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"anticipationGravame": ["Not a valid boolean."]}` |
| Validar post hire com campo channel em branco com falha | /anticipation/zenite/hire | `{"channel": ["Not a valid integer."]}` |
| Validar post hire com campo channel com valor inválido | /anticipation/zenite/hire | `{"channel": ["Not a valid integer."]}` |
| Validar post hire com campo companyNumber com valor numérico negativo | /anticipation/zenite/hire | `{"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}` |
| Validar post hire com campo companyNumber com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"companyNumber": ["Not a valid integer."]}` |
| Validar post hire com header 'Authorization' com token inválido | /anticipation/zenite/hire | `{"message": "Unauthorized"}` |
| Validar post hire com header 'Authorization' com valor inválido ou em branco | /anticipation/zenite/hire | `{"message": "Unauthorized"}` |
| Validar post hire com campo operationUser com valor em branco | /anticipation/zenite/hire | `{"operationUser": ["Not a valid integer."]}` |
| Validar post hire com campo operationUser com valor inválido | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "operationUser: the length must be no more than 8.", "status": 400}}` |
| Validar post hire com campo product com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post hire sem campo anticipationGravame | /anticipation/zenite/hire | `{"errors": {"code": "1016", "message": "This partner is inactive.", "status": 422}}` |
| Validar post hire sem campo companyNumber | /anticipation/zenite/hire | `{"companyNumber": ["Missing data for required field."]}` |
| Validar post hire sem campo product | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "product: attribute is required.", "status": 400}}` |
| Validar post hire sem header 'Authorization' | /anticipation/zenite/hire | `{"message": "Unauthorized"}` |
| Validar post hire com sucesso (validar se seria Kosmos) | /anticipation/zenite/hire | `{"object": {"periodRate": 9.223599, "netValue": 119014.56, "totalRotatingAmount": 0.0, "parcelAmount": 131107.38, "effectiveRate": 5.043661, "financialCost": 1.036515, "monthRate": 4.69, "initialDueDate": "23/10/2023", "finalDueDate": "23/10/2023", "averageTerm": 59.0, "product": "CESSAO", "domiciles": [{"companyNumber": 90078837, "creditAgency": 1500, "gravameIndicator": false, "brandNumber": 1, "codeDomicilePayment": "5544191", "creditBank": 341, "accountType": "CC", "accountNumber": "00000000000000738636"}], "operationNumber": 45756, "spread": 3.966, "brands": [1], "grossValue": 131107.38}, "code": "0000", "message": "create"}` |
| Validar post hire com valor acima do estipulado para o canal | /anticipation/zenite/hire | `{"errors": {"code": "1016", "message": "This partner is inactive.", "status": 422}}` |
| Validar post hire com campo workingDaysToPayment com valor numérico negativo | /anticipation/zenite/hire | `{"errors": {"code": "1002", "message": "workingDaysToPayment: must be no less than 0.", "status": 400}}` |
| Validar post hire com campo workingDaysToPayment com valor em branco, inválido ou vazio | /anticipation/zenite/hire | `{"workingDaysToPayment": ["Not a valid integer."]}` |

## `post-simulate`

| Cenários | Request URI/urlPathPattern | Response |
|---|---|---|
| Validar post simulate com amount fora do range mínimo de 100 | /anticipation/zenite/simulate | `{"code": "1016", "message": "This partner is inactive.", "status": 422}` |
| Validar post simulate com campo anticipationAmount com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"anticipationAmount": ["Not a valid number."]}` |
| Validar post simulate com campo anticipationAmount com valor zerado e campo product com valor inválido 'G' | /anticipation/zenite/simulate | `{"code": "0000", "message": "create", "object": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post simulate com campo anticipationGravame com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"anticipationGravame": ["Not a valid boolean."]}` |
| Validar channel null | /anticipation/zenite/simulate | `{"channel": ["Not a valid integer."]}` |
| Validar campo channel inválido | /anticipation/zenite/simulate | `{"channel": ["Not a valid integer."]}` |
| Validar post simulate com campo companyNumber com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"companyNumber": ["Not a valid integer."]}` |
| Validar post simulate com campo companyNumber com valor numérico negativo | /anticipation/zenite/simulate | `{"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}` |
| Validar post simulate com campo operationUser com valor em branco e inválido | /anticipation/zenite/simulate | `{"operationUser": ["Not a valid integer."]}` |
| Validar post simulate com campo operationUser com valor maior que 8 caracteres | /anticipation/zenite/simulate | `{"code": "1002", "message": "operationUser: the length must be no more than 8.", "status": 400}` |
| Validar post simulate com campo product com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post simulate sem campo anticipationGravame | /anticipation/zenite/simulate | `{"code": "1016", "message": "This partner is inactive.", "status": 422}` |
| Validar post simulate sem campo companyNumber | /anticipation/zenite/simulate | `{"companyNumber": ["Missing data for required field."]}` |
| Validar post simulate sem campo product | /anticipation/zenite/simulate | `{"code": "1002", "message": "product: attribute is required.", "status": 400}` |
| Validar post simulate com sucesso | /anticipation/zenite/simulate | `{"object": {"periodRate": 13.913596, "netValue": 50341.03, "totalRotatingAmount": 0.0, "parcelAmount": 58477.33, "effectiveRate": 5.179788, "financialCost": 0.981939, "monthRate": 4.69, "initialDueDate": "22/11/2023", "finalDueDate": "22/11/2023", "averageTerm": 89.0, "product": "CESSAO", "domiciles": [{"companyNumber": 90078837, "creditAgency": 1500, "gravameIndicator": false, "brandNumber": 1, "codeDomicilePayment": "5544191", "creditBank": 341, "accountType": "CC", "accountNumber": "00000000000000738636"}], "spread": 4.157, "brands": [1], "grossValue": 58477.33}, "code": "0000", "message": "create"}` |
| Validar post simulate com valor acima do estipulado para o canal | /anticipation/zenite/simulate | `{"code": "1016", "message": "This partner is inactive.", "status": 422}` |
| Validar post simulate com campo workingDaysToPayment com valor em branco, inválido ou vazio | /anticipation/zenite/simulate | `{"workingDaysToPayment": ["Not a valid integer."]}` |
| Validar post simulate com campo workingDaysToPayment com valor numérico negativo | /anticipation/zenite/simulate | `{"code": "1002", "message": "workingDaysToPayment: must be no less than 0.", "status": 400}` |

{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": "0",
                    "channel": 6,
                    "product": "V",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": "   ",
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": "   ",
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                "equalToJson": {
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": "NULL",
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 1940
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": "ABC",
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": "-12",
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": "    ",
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                "equalToJson": {
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                "equalToJson": {
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                "equalToJson": {
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": "   ",
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                "equalToJson": {
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": "1234567890",
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "   ",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                "equalToJson": {
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                "equalToJson": {
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 15,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 999999,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": "-12",
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": "   ",
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }

post-hire
| Cenários | Request | Response |
|---|---|---|
| Validar post hire com campo anticipationAmount com valor zerado e campo product com valor 'V' | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": "0", "channel": 6, "product": "V", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post hire com campo anticipationAmount com valor em branco, inválido ou vazio | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": "   ", "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"anticipationAmount": ["Not a valid number."]}` |
| Validar post hire com campo anticipationGravame com valor em branco, inválido ou vazio | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": "   ", "codeProduct": 301, "partnerNumber": 2}` | `{"anticipationGravame": ["Not a valid boolean."]}` |
| Validar post hire com campo channel em branco com falha | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": "NULL", "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 1940}` | `{"channel": ["Not a valid integer."]}` |
| Validar post hire com campo channel com valor inválido | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": "ABC", "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"channel": ["Not a valid integer."]}` |
| Validar post hire com campo companyNumber com valor numérico negativo | `{"companyNumber": "-12", "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}` |
| Validar post hire com campo companyNumber com valor em branco, inválido ou vazio | `{"companyNumber": "    ", "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"companyNumber": ["Not a valid integer."]}` |
| Validar post hire com header 'Authorization' com token inválido | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"message": "Unauthorized"}` |
| Validar post hire com header 'Authorization' com valor inválido ou em branco | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"message": "Unauthorized"}` |
| Validar post hire com campo operationUser com valor em branco | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": "   ", "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"operationUser": ["Not a valid integer."]}` |
| Validar post hire com campo operationUser com valor inválido | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": "1234567890", "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"errors": {"code": "1002", "message": "operationUser: the length must be no more than 8.", "status": 400}}` |
| Validar post hire com campo product com valor em branco, inválido ou vazio | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "   ", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post hire sem campo anticipationGravame | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"errors": {"code": "1016", "message": "This partner is inactive.", "status": 422}}` |
| Validar post hire sem campo companyNumber | `{"workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"companyNumber": ["Missing data for required field."]}` |
| Validar post hire com campo workingDaysToPayment com valor numérico negativo | `{"companyNumber": 90078837, "workingDaysToPayment": "-12", "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"workingDaysToPayment": ["Must be greater than or equal to 1."]}` |
| Validar post hire com campo workingDaysToPayment em branco, inválido ou vazio | `{"companyNumber": 90078837, "workingDaysToPayment": "   ", "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"workingDaysToPayment": ["Not a valid integer."]}` |

post-simulate
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": "50",
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": "   ",
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": "0",
                    "channel": 6,
                    "product": "G",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": "   ",
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": null,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "expression": "$.channel",
                    "matches": "(|[A-Za-z. ]+)",
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": "    ",
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": "   ",
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": "123456789",
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "   ",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 6,
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 100,
                    "channel": 15,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": 1,
                    "anticipationAmount": 999999999,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": "   ",
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }
{
                    "companyNumber": 90078837,
                    "workingDaysToPayment": "-12",
                    "anticipationAmount": 100,
                    "channel": 6,
                    "product": "A",
                    "operationUser": 739347,
                    "anticipationGravame": false,
                    "codeProduct": 301,
                    "partnerNumber": 2
                }

post-simulate
| Cenários | Request | Response |
|---|---|---|
| Validar post simulate com amount fora do range mínimo de 100 | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": "50", "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"code": "1016", "message": "This partner is inactive.", "status": 422}` |
| Validar post simulate com campo anticipationAmount com valor em branco, inválido ou vazio | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": " ", "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"anticipationAmount": ["Not a valid number."]}` |
| Validar post simulate com campo anticipationAmount com valor zerado e campo product com valor inválido 'G' | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": "0", "channel": 6, "product": "G", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"code": "0000", "message": "create", "object": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post simulate com campo anticipationGravame com valor em branco, inválido ou vazio | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": " ", "codeProduct": 301, "partnerNumber": 2}` | `{"anticipationGravame": ["Not a valid boolean."]}` |
| Validar channel null | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": null, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"channel": ["Not a valid integer."]}` |
| Validar campo channel inválido | `{"expression": "$.channel", "matches": "(\|[A-Za-z. ]+)", "companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"channel": ["Not a valid integer."]}` |
| Validar post simulate com campo companyNumber com valor em branco, inválido ou vazio | `{"companyNumber": " ", "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"companyNumber": ["Not a valid integer."]}` |
| Validar post simulate com campo companyNumber com valor numérico negativo | `{"companyNumber": "-12", "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"companyNumber": ["Must be greater than or equal to 1 and less than or equal to 999999999."]}` |
| Validar post simulate com campo operationUser com valor em branco e inválido | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": " ", "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"operationUser": ["Not a valid integer."]}` |
| Validar post simulate com campo operationUser com valor maior que 8 caracteres | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": "123456789", "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"code": "1002", "message": "operationUser: the length must be no more than 8.", "status": 400}` |
| Validar post simulate com campo product com valor em branco, inválido ou vazio | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": " ", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"errors": {"code": "1002", "message": "product: must be a valid value.", "status": 400}}` |
| Validar post simulate sem campo anticipationGravame | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "codeProduct": 301, "partnerNumber": 2}` | `{"code": "1016", "message": "This partner is inactive.", "status": 422}` |
| Validar post simulate sem campo companyNumber | `{"workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"companyNumber": ["Missing data for required field."]} ` |
| Validar post simulate sem campo product | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"code": "1002", "message": "product: attribute is required.", "status": 400}` |
| Validar post simulate com sucesso | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"object": {"periodRate": 13.913596, "netValue": 50341.03, "totalRotatingAmount": 0.0, "parcelAmount": 58477.33, "effectiveRate": 5.179788, "financialCost": 0.981939, "monthRate": 4.69, "initialDueDate": "22/11/2023", "finalDueDate": "22/11/2023", "averageTerm": 89.0, "product": "CESSAO", "domiciles": [{"companyNumber": 90078837, "creditAgency": 1500, "gravameIndicator": false, "brandNumber": 1, "codeDomicilePayment": "5544191", "creditBank": 341, "accountType": "CC", "accountNumber": "00000000000000738636"}], "spread": 4.157, "brands": [1], "grossValue": 58477.33}, "code": "0000", "message": "create"}` |
| Validar post simulate com valor acima do estipulado para o canal | `{"companyNumber": 90078837, "workingDaysToPayment": 1, "anticipationAmount": 100, "channel": 15, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"code": "1016", "message": "This partner is inactive.", "status": 422}` |
| Validar post simulate com campo workingDaysToPayment com valor em branco, inválido ou vazio | `{"companyNumber": 90078837, "workingDaysToPayment": " ", "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"workingDaysToPayment": ["Not a valid integer."]}` |
| Validar post simulate com campo workingDaysToPayment com valor numérico negativo | `{"companyNumber": 90078837, "workingDaysToPayment": "-12", "anticipationAmount": 100, "channel": 6, "product": "A", "operationUser": 739347, "anticipationGravame": false, "codeProduct": 301, "partnerNumber": 2}` | `{"code": "1002", "message": "workingDaysToPayment: must be no less than 0.", "status": 400}` |
