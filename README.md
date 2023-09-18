**MENU**

_Rotas_
* [Cancelamento de ravAuto](Cancelamento-de-ravAuto)
* [Consulta de saldo antecipação Zenite](Consulta-de-saldo-antecipação-Zenite)
* [Validar consulta de última operação Zenite](Validar-consulta-de-última-operação-Zenite)
* [Validar consulta de status de operações Zenite](Validar-consulta-de-status-de-operações-Zenite)
* [Validar consulta de operação Zenite](Validar-consulta-de-operação-Zenite)
* [Validar a consulta de contrato ravAuto](Validar-a-consulta-de-contrato-ravAuto)
* [Validar a contratação de antecipação Zenite](Validar-a-contratação-de-antecipação-Zenite)
* [Validar a contratação de ravAuto](Validar-a-contratação-de-ravAuto)
* [Validar a contratação a antecipação Zenite Kosmo](Validar-a-contratação-a-antecipação-Zenite-Kosmo)
* [Validar a simulação de antecipação Zenite](Validar-a-simulação-de-antecipação-Zenite)
* [Validar a simulação de antecipação Zenite Kosmo](Validar-a-simulação-de-antecipação-Zenite-Kosmo)


# Documentação das rotas do Sandbox

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
## Cancelamento de ravAuto
Endpoint: /anticipation/zenite/rav-auto

Descrição: This route is used to cancel a ravAuto operation.

Request method (Método): <b>DELETE</b>

## Consulta de saldo antecipação Zenite
Endpoint: /consulta/saldo/antecipacao/zenite

Description: This route is used to retrieve the balance of a Zenite anticipation operation.

Request method: `GET`

<b> Parâmetros de entrada </b>

Request URI: `https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/{XXXX}`

- {XXXX} : Substituir pelo valor

### Cenário: *Validar get balance kosmos com sucesso*

Request URI:	https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/balance/0000

Response:
```json
{
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
}
```

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
