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
    - 2.2. [Contratação de Antecipação Zenite Kosmo](#contratação-de-antecipação-zenite-kosmo)

- Simulação
    - 2.3. [Simulação de Antecipação Zenite](#simulação-de-antecipação-zenite)
    - 2.4. [Simulação de Antecipação Zenite Kosmo](#simulação-de-antecipação-zenite-kosmo)

### 3. Balancer
- [Consulta de Saldo Antecipação Zenite](#consulta-de-saldo-antecipação-zenite)
   - 3.2. Free
   - 3.3. Compan

### 4. Consult
- Operations
   - 4.1. [Consulta de Operação Zenite](#consulta-de-operação-zenite)
- Last-operations
   - 4.2. [Consulta de Última Operação Zenite](#consulta-de-última-operação-zenite)
- Status-operations
   - 4.3.[Consulta de Status de Operações Zenite](#consulta-de-status-de-operações-zenite)

---

### 🗂️ Tabela de Rotas

| Rotas | Nomes sugeridos para Pastas | Método |
|---|---|---|
| Cancelamento de ravAuto | --- | --- |
| Consulta de saldo antecipação Zenite | get-balance-kosmos | `GET` |
| Consulta de última operação Zenite | get-consult-operations-last-operation | `GET` |
| Consulta de status de operações Zenite | get-consult-operations-status | `GET` |
| Consulta de operação Zenite | get-consult-operations | `GET` |
| Consulta de contrato ravAuto | get-consult-contract-ravAuto | `GET` |
| Contratacao de antecipação Zenite | post-hire-domicilio | `POST` |
| Contratação de ravAuto | post-hire-ravAuto | `POST` |
| Contratação a antecipação Zenite Kosmo | post-hire-kosmos | `POST` |
| Simulação de antecipação Zenite | post-simulate-domicilio | `POST` |
| Simulação de antecipação Zenite Kosmo | post-simulate-kosmos | `POST` |

## Rotas

### Cancelamento de ravAuto

- **Endpoint:** /anticipation/zenite/rav-auto
- **Método:** `POST`

---

### Consulta de Saldo Antecipação Zenite
`get-balance-kosmos`
- **Endpoint:** /anticipation/zenite/balance/{companyNumber}
- **Método:** `GET`

<b> Parâmetros de entrada </b>

Request URI: `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/{XXXX}`

- {XXXX} : Substituir pelo valor ou nome específico.

### Cenários de Teste
Aqui estão os cenários que você pode usar para testar esta rota no Insomnia:

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

**❗ Importante:** Se a resposta não for exibida conforme esperado ou encontrar algum problema, repita o 3º passo para garantir que o "access_token" está atualizado e tente novamente.

---

## Consulta de última operação Zenite
`get-consult-operations-last-operation`

- **Endpoint:** /anticipation/zenite/last-operation

- **Método:** `GET`

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

| CT-NCA-XXX | Cenários | Request URI/urlPathPattern | Response |
|---|---|---|---|
| CT-NCA-271 | Validar consulta de ravAuto com sucesso | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto?companyNumber=41211` | `{ "message": "consult", "code": "0000", "object": { "changeOperator": "CISIMIS", "deletionScheduledDate": "", "anticipationProductCode": 1, "changeHour": "13:04", "headquarterNumber": 41211, "loyaltyFee": 0.0, "pendingStatusCode": 0, "anticipationProductName": "RAV", "returnDescripton": "OK", "companyNumber": 41211, "anticipationRavFee": 0.0, "rateCategoryCode": "XV", "loyaltyStartDate": "", "anticipationBaseDate": "08/08/2023", "loyaltyEndDate": "", "reserveExit": "", "documentNumber": 49190309000180, "authorizationDate": "07/08/2023", "contractDate": "07/08/2023", "authorizationHour": "13:04:14", "rateCategory": 2.5, "authorizationOperator": "CISIMIS", "nextAnticipationDate": "08/08/2023", "nameCategory": "AUTOMATICO (2,50%)", "nameEstablishment": "", "returnCode": 0, "anticipationProductDescripton": "RV", "changeDate": "07/08/2023", "brandSelectedDescription": "TODAS", "brands": [ { "selIndicator": "", "brandCode": 1, "brandDescripton": "MASTERCARD" }, { "selIndicator": "", "brandCode": 2, "brandDescripton": "DINERS CLUB" }, { "selIndicator": "", "brandCode": 5, "brandDescripton": "VISA" }, { "selIndicator": "", "brandCode": 51, "brandDescripton": "CABAL" }, { "selIndicator": "", "brandCode": 60, "brandDescripton": "HIPERCARD" }, { "selIndicator": "", "brandCode": 61, "brandDescripton": "SOROCRED" }, { "selIndicator": "", "brandCode": 63, "brandDescripton": "CUP" }, { "selIndicator": "", "brandCode": 64, "brandDescripton": "SICREDI" }, { "selIndicator": "", "brandCode": 66, "brandDescripton": "CALCARD" }, { "selIndicator": "", "brandCode": 67, "brandDescripton": "AVISTA" }, { "selIndicator": "", "brandCode": 68, "brandDescripton": "CREDSYSTEM" }, { "selIndicator": "", "brandCode": 69, "brandDescripton": "AMERICAN EXPRES" }, { "selIndicator": "", "brandCode": 70, "brandDescripton": "ELO" }, { "selIndicator": "", "brandCode": 72, "brandDescripton": "NOVA BANDEIRA" }, { "selIndicator": "", "brandCode": 74, "brandDescripton": "BANESCARD" }, { "selIndicator": "", "brandCode": 76, "brandDescripton": "JCB" }, { "selIndicator": "", "brandCode": 77, "brandDescripton": "CREDZ" } ], "loyaltyLockIndicator": "", "descriptonPendedingRate": "" } }` |
| CT-NCA-272 | Validar consulta de ravAuto com query param "companyNumber" com valor alfabetico inválido | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto?companyNumber=ABC` | `{ "queryStringParameters": { "companyNumber": [ "Not a valid integer." ] } }` | 
| CT-NCA-273 | Validar consulta de ravAuto com query param "companyNumber" com valor inexistente | `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto?companyNumber=90016267` | `{ "errors": { "code": "1019", "message": "Company does dot exist.", "status": 422 } }` |

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Contratação de antecipação Zenite
`post-hire-domicilio`
- **Endpoint:** /anticipation/zenite/hire/domicile

- **Método:** `POST`

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Contratação de ravAuto
`post-hire-ravAuto`
- **Endpoint:** /anticipation/zenite/rav-auto

- **Método:** `POST`

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Contratação de antecipação Zenite Kosmo
`post-hire-kosmos`
- **Endpoint:** /anticipation/zenite/hire

- **Método:** `POST`

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Simulação de antecipação Zenite
`post-simulate-domicilio`
- **Endpoint:** /anticipation/zenite/simulate/domicile

- **Método:** `POST`

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

---

## Simulação de antecipação Zenite Kosmo
`post-simulate-kosmos`
- **Endpoint:** /anticipation/zenite/simulate

- **Método:** `POST`

#### Como Testar
Para testar esta rota, siga os passos em [🚀 Testando no Insomnia](#-testando-no-insomnia).

____

Contratacao de antecipação Zenite

CT-NCA-056 Validar post hire domicílio com sucesso {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "create",
    "code": "0000",
    "object": {
        "creditAgency": 0,
        "dateTimeProcessing": "",
        "minimumValueAnticipateChannel": 0.0,
        "endPeriodAnticipation": "",
        "freeGrossValue": 0.0,
        "gravameGrossValue": 0.0,
        "startPeriodAnticipation": "",
        "codeDomicilePayment": 0.0,
        "domicile": null,
        "totalAmountAvailableAnticipate": 0.0,
        "creditBank": 0,
        "nameProductAnticipation": "",
        "gravameNetValue": 0.0,
        "operationNumber": 0,
        "anticipationDataGravame": null,
        "discountRate": 0.0,
        "codeProductAnticipation": 0,
        "freeNetValue": 0.0
    }
}

CT-NCA-063 Validar post hire domicílio com header "Authorization" com valor inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "Unauthorized"
}

CT-NCA-064 Validar post hire domicílio com header "Authorization" com valor em branco {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "Unauthorized"
}

CT-NCA-065 Validar post hire domicílio com header "Authorization" com token inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "Unauthorized"
}

CT-NCA-066 Validar post hire domicílio sem header "Authorization" {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "Unauthorized"
}

CT-NCA-072 Validar post hire domicílio com campo companyNumber com valor inválido zenite {
    "companyNumber": "ABC",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "companyNumber": [
        "Not a valid integer."
    ]
}

CT-NCA-073 Validar post hire domicílio com campo companyNumber com valor numerico negativo {
    "companyNumber": "-12",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "companyNumber": [
        "Must be greater than or equal to 1 and less than or equal to 999999999."
    ]
}

CT-NCA-074 Validar post hire domicílio com campo companyNumber com valor vazio {
    "companyNumber": "",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "companyNumber": [
        "Not a valid integer."
    ]
} 

CT-NCA-075 Validar post hire domicílio com campo companyNumber com valor em branco {
    "companyNumber": "    ",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "companyNumber": [
        "Not a valid integer."
    ]
}

CT-NCA-076 Validar post hire domicílio sem campo companyNumber {
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "companyNumber": [
        "Missing data for required field."
    ]
} 

CT-NCA-077 Validar post hire domicílio com campo workingDaysToPayment com valor inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": "%#[,%",
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "workingDaysToPayment": [
        "Not a valid integer."
    ]
}

CT-NCA-078 Validar post hire domicílio com campo workingDaysToPayment com valor numerico negativo {
    "companyNumber": "90078837",
    "workingDaysToPayment": "-12",
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "workingDaysToPayment: must be no less than 0.",
        "status": 400
    }
}

CT-NCA-079 Validar post hire domicílio com campo workingDaysToPayment com valor vazio {
    "companyNumber": "90078837",
    "workingDaysToPayment": "",
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "workingDaysToPayment": [
        "Not a valid integer."
    ]
}

CT-NCA-080 Validar post hire domicílio com campo workingDaysToPayment com valor em branco {
    "companyNumber": "90078837",
    "workingDaysToPayment": "   ",
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "workingDaysToPayment": [
        "Not a valid integer."
    ]
}

CT-NCA-082 Validar post hire domicílio com campo anticipationType com valor inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "#+,=#",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "anticipationType: must be a valid value.",
        "status": 400
    }
} 

CT-NCA-083 Validar post hire domicílio com campo anticipationType com valor vazio {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "anticipationType: attribute is required.",
        "status": 400
    }
}

CT-NCA-084 Validar post hire domicílio com campo anticipationType com valor em branco {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "   ",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "anticipationType: must be a valid value.",
        "status": 400
    }
} 

CT-NCA-085 Validar post hire domicílio sem campo anticipationType {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "anticipationType: attribute is required.",
        "status": 400
    }
}

CT-NCA-086 Validar post hire domicílio com campo anticipationAmount com valor inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": "^:_.}",
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "anticipationAmount": [
        "Not a valid number."
    ]
} 

CT-NCA-087 Validar post hire domicílio com campo anticipationAmount com valor zerado e campo anticipationType com valor "P" {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": "0",
    "anticipationType": "P",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1008",
        "message": "Requested amount out of range: 1.00, 1000000000.00",
        "status": 422
    }
}

CT-NCA-088 Validar post hire domicílio com campo anticipationAmount com valor zerado e campo anticipationType com valor "T" {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": "0",
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "create",
    "code": "0000",
    "object": {
        "creditAgency": 0,
        "dateTimeProcessing": "",
        "minimumValueAnticipateChannel": 0.0,
        "endPeriodAnticipation": "",
        "freeGrossValue": 0.0,
        "gravameGrossValue": 0.0,
        "startPeriodAnticipation": "",
        "codeDomicilePayment": 0.0,
        "domicile": null,
        "totalAmountAvailableAnticipate": 0.0,
        "creditBank": 0,
        "nameProductAnticipation": "",
        "gravameNetValue": 0.0,
        "operationNumber": 0,
        "anticipationDataGravame": null,
        "discountRate": 0.0,
        "codeProductAnticipation": 0,
        "freeNetValue": 0.0
    }
}

CT-NCA-089 Validar post hire domicílio com campo anticipationAmount com valor vazio {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": "",
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "anticipationAmount": [
        "Not a valid number."
    ]
}

CT-NCA-090 Validar post hire domicílio com campo anticipationAmount com valor em branco {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": "   ",
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "anticipationAmount": [
        "Not a valid number."
    ]
}

CT-NCA-091 Validar post hire domicílio sem campo anticipationAmount {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "create",
    "code": "0000",
    "object": {
        "creditAgency": 0,
        "dateTimeProcessing": "",
        "minimumValueAnticipateChannel": 0.0,
        "endPeriodAnticipation": "",
        "freeGrossValue": 0.0,
        "gravameGrossValue": 0.0,
        "startPeriodAnticipation": "",
        "codeDomicilePayment": 0.0,
        "domicile": null,
        "totalAmountAvailableAnticipate": 0.0,
        "creditBank": 0,
        "nameProductAnticipation": "",
        "gravameNetValue": 0.0,
        "operationNumber": 0,
        "anticipationDataGravame": null,
        "discountRate": 0.0,
        "codeProductAnticipation": 0,
        "freeNetValue": 0.0
    }
}

CT-NCA-092 Validar post hire domicílio com campo selectionType com valor inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": ",}]-+",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "selectionType: must be a valid value.",
        "status": 400
    }
}

CT-NCA-093 Validar post hire domicílio com campo selectionType com valor vazio {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "create",
    "code": "0000",
    "object": {
        "creditAgency": 0,
        "dateTimeProcessing": "",
        "minimumValueAnticipateChannel": 0.0,
        "endPeriodAnticipation": "",
        "freeGrossValue": 0.0,
        "gravameGrossValue": 0.0,
        "startPeriodAnticipation": "",
        "codeDomicilePayment": 0.0,
        "domicile": null,
        "totalAmountAvailableAnticipate": 0.0,
        "creditBank": 0,
        "nameProductAnticipation": "",
        "gravameNetValue": 0.0,
        "operationNumber": 0,
        "anticipationDataGravame": null,
        "discountRate": 0.0,
        "codeProductAnticipation": 0,
        "freeNetValue": 0.0
    }
}

CT-NCA-094 Validar post hire domicílio com campo selectionType com valor em branco {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "   ",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "selectionType: must be a valid value.",
        "status": 400
    }
}

CT-NCA-097 Validar post hire domicílio com campo product com valor inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "(!)]|",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "product: must be a valid value.",
        "status": 400
    }
}

CT-NCA-098 Validar post hire domicílio com campo product com valor vazio {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "product: attribute is required.",
        "status": 400
    }
} 

CT-NCA-099 Validar post hire domicílio com campo product com valor em branco {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "   ",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "product: must be a valid value.",
        "status": 400
    }
} 

CT-NCA-100 Validar post hire domicílio sem campo product {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "product: attribute is required.",
        "status": 400
    }
}

CT-NCA-101 Validar post hire domicílio com campo anticipationGravame com valor inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "((+{+",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "anticipationGravame: must be a valid value.",
        "status": 400
    }
} 

CT-NCA-102 Validar post hire domicílio com campo anticipationGravame com valor vazio {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "anticipationGravame: attribute is required.",
        "status": 400
    }
} 

CT-NCA-103 Validar post hire domicílio com campo anticipationGravame com valor em branco {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "   ",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "anticipationGravame: must be a valid value.",
        "status": 400
    }
}

CT-NCA-104 Validar post hire domicílio sem campo anticipationGravame {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "anticipationGravame: attribute is required.",
        "status": 400
    }
}

CT-NCA-105 Validar post hire domicílio com campo desiredDiscountPercentage com valor inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "739347",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2,
    "desiredDiscountPercentage": -15
} {
    "message": "create",
    "code": "0000",
    "object": {
        "creditAgency": 0,
        "dateTimeProcessing": "",
        "minimumValueAnticipateChannel": 0.0,
        "endPeriodAnticipation": "",
        "freeGrossValue": 0.0,
        "gravameGrossValue": 0.0,
        "startPeriodAnticipation": "",
        "codeDomicilePayment": 0.0,
        "domicile": null,
        "totalAmountAvailableAnticipate": 0.0,
        "creditBank": 0,
        "nameProductAnticipation": "",
        "gravameNetValue": 0.0,
        "operationNumber": 0,
        "anticipationDataGravame": null,
        "discountRate": 0.0,
        "codeProductAnticipation": 0,
        "freeNetValue": 0.0
    }
}

CT-NCA-106 Validar post hire domicílio com campo operationUser com valor inválido {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "1234567890",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "errors": {
        "code": "1002",
        "message": "operationUser: the length must be no more than 9.",
        "status": 400
    }
}

CT-NCA-107 Validar post hire domicílio com campo operationUser com valor fora do padrao {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "123",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "create",
    "code": "0000",
    "object": {
        "creditAgency": 0,
        "dateTimeProcessing": "",
        "minimumValueAnticipateChannel": 0.0,
        "endPeriodAnticipation": "",
        "freeGrossValue": 0.0,
        "gravameGrossValue": 0.0,
        "startPeriodAnticipation": "",
        "codeDomicilePayment": 0.0,
        "domicile": null,
        "totalAmountAvailableAnticipate": 0.0,
        "creditBank": 0,
        "nameProductAnticipation": "",
        "gravameNetValue": 0.0,
        "operationNumber": 0,
        "anticipationDataGravame": null,
        "discountRate": 0.0,
        "codeProductAnticipation": 0,
        "freeNetValue": 0.0
    }
}

CT-NCA-108 Validar post hire domicílio com campo operationUser com valor em branco {
    "companyNumber": "90078837",
    "workingDaysToPayment": 1,
    "channel": 15,
    "anticipationAmount": 0,
    "anticipationType": "T",
    "selectionType": "V",
    "product": "A",
    "codeProduct": 201,
    "anticipationGravame": "N",
    "startSelectionDate": "2022-08-23",
    "operationUser": "   ",
    "endSelectionDate": "2023-12-31",
    "partnerNumber": 2
} {
    "message": "create",
    "code": "0000",
    "object": {
        "creditAgency": 0,
        "dateTimeProcessing": "",
        "minimumValueAnticipateChannel": 0.0,
        "endPeriodAnticipation": "",
        "freeGrossValue": 0.0,
        "gravameGrossValue": 0.0,
        "startPeriodAnticipation": "",
        "codeDomicilePayment": 0.0,
        "domicile": null,
        "totalAmountAvailableAnticipate": 0.0,
        "creditBank": 0,
        "nameProductAnticipation": "",
        "gravameNetValue": 0.0,
        "operationNumber": 0,
        "anticipationDataGravame": null,
        "discountRate": 0.0,
        "codeProductAnticipation": 0,
        "freeNetValue": 0.0
    }
}

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

