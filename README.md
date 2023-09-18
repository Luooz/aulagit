# Documentação das rotas do Sandbox

## Cancelamento de ravAuto
Endpoint: /anticipation/zenite/rav-auto

Descrição: This route is used to cancel a ravAuto operation.

Request method (Método): <b>DELETE</b>

### Parâmetros:

Cenário: *Validar cancelamento de RavAuto com sucesso*

REQUEST

<pre>{
    "companyNumber": 33626,
    "codeExclusion": 1,
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}</pre>

RESPONSE

<pre>{
    "message": "delete",
    "code": "0000",
    "object": {
        "changeOperator": "",
        "deletionScheduledDate": "23/08/2023",
        "anticipationProductCode": 24,
        "changeHour": "",
        "headquarterNumber": 33626,
        "loyaltyFee": 0.0,
        "pendingStatusCode": 0,
        "anticipationProductName": "CESSAO DE CREDITO",
        "returnDescripton": "OK",
        "companyNumber": 33626,
        "anticipationRavFee": 0.0,
        "rateCategoryCode": "YB",
        "loyaltyStartDate": "",
        "anticipationBaseDate": "23/08/2023",
        "loyaltyEndDate": "",
        "reserveExit": "",
        "documentNumber": 77574119000100,
        "authorizationDate": "",
        "contractDate": "21/08/2023",
        "authorizationHour": "",
        "rateCategory": 3.5,
        "authorizationOperator": "",
        "nextAnticipationDate": "23/08/2023",
        "nameCategory": "AUTOMATICO (3,50%)",
        "nameEstablishment": "",
        "returnCode": 0,
        "anticipationProductDescripton": "CS",
        "changeDate": "",
        "brandSelectedDescription": "TODAS",
        "brands": null,
        "loyaltyLockIndicator": "",
        "descriptonPendedingRate": ""
    }
}</pre>

Cenário: *Validar cancelamento de ravAuto com sucesso sem campo "daysToBeCancelled"*

REQUEST

<pre>{
    "companyNumber": 33626,
    "codeExclusion": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}</pre>

RESPONSE

<pre>{
    "errors": {
        "code": "1002",
        "message": "daysToBeCancelled: must be a valid value or attribute is required.",
        "status": 400
    }
}</pre>

## Consulta de saldo antecipação Zenite
Endpoint: /consulta/saldo/antecipacao/zenite

Description: This route is used to retrieve the balance of a Zenite anticipation operation.

Request method: <b>GET</b>

## Consulta de última operação Zenite
Endpoint: /consulta/ultima-operacao/zenite

Description: This route is used to retrieve the details of the last Zenite operation.

Request method: <b>GET</b>

## Consulta de status de operações Zenite
Endpoint: /consulta/status-operacoes/zenite

Description: This route is used to retrieve the status of Zenite operations.

Request method: <b>GET</b>

## Consulta de operação Zenite
Endpoint: /consulta/operacao/zenite

Description: This route is used to retrieve the details of a Zenite operation.

Request method: <b>GET</b>

## Consulta de contrato ravAuto
Endpoint: /consulta/contrato/ravAuto

Description: This route is used to retrieve the details of a ravAuto contract.

Request method: <b>GET</b>

## Contratação de antecipação Zenite
Endpoint: /contratacao/antecipacao/zenite

Description: This route is used to contract a Zenite anticipation operation.

Request method: <b>POST</b>

## Contratação de ravAuto
Endpoint: /contratacao/ravAuto

Description: This route is used to contract a ravAuto operation.

Request method: <b>POST</b>

## Contratação de antecipação Zenite Kosmo
Endpoint: /contratacao/antecipacao/zenite-kosmo

Description: This route is used to contract a Zenite Kosmo anticipation operation.

Request method: <b>POST

## Simulação de antecipação Zenite
Endpoint: /simulacao/antecipacao/zenite

Description: This route is used to simulate a Zenite anticipation operation.

Request method: <b>POST</b>

## Simulação de antecipação Zenite Kosmo
Endpoint: /simulacao/antecipacao/zenite-kosmo

Description: This route is used to simulate a Zenite Kosmo anticipation operation.

Request method: <b>POST</b>
