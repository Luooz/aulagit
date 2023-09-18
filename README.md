# Documentação das rotas do Sandbox

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
## Cancelamento de ravAuto
Endpoint: /anticipation/zenite/rav-auto

Descrição: This route is used to cancel a ravAuto operation.

Request method (Método): <b>DELETE</b>
XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

## Consulta de saldo antecipação Zenite
Endpoint: /consulta/saldo/antecipacao/zenite

Description: This route is used to retrieve the balance of a Zenite anticipation operation.

Request method: <b>GET</b>

### Parâmetros:

Cenário: *Validar get balance kosmos com sucesso*

REQUEST
<pre>{
    "scenarioName": "Nome do cenário",
    "priority": 1,
    "request": {
        "method": "GET",
        "urlPathPattern": "/anticipation/zenite/balance/{companyNumber}",
        "headers": {
            "Authorization": {
                "matches": "(Bearer e.*)"
            }
        }</pre>

RESPONSE
<pre>{
    "message": "consult",
    "code": "0000",
    "object": {
        "totalRevolving": 0.0,
        "grossTotal": 15395.43,
        "totalAmountInstallments": 15395.43,
        "totalFree": 15395.43,
        "totalCreditAssignment": 0.0,
        "totalBlockedAnticipation": 0.0,
        "brands": [
            {
                "code": 1,
                "balance": 15395.43
            }
        ],
        "totalNegotiatedGravame": 0.0
    }
}</pre>

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
