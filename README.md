# Documentação das Rotas API

## Cancelamento de ravAuto
Endpoint: /anticipation/zenite/rav-auto

Descrição: This route is used to cancel a ravAuto operation.

Request method (Método): <b>POST</b>

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

Tags: @CancelRavAuto @Anticipation @Delete @Zenite @RavAuto @CT-NCA-271
8.497
Cenario Validar cancelamento de ravAuto com sucesso 
Hooks 
Before Hooks.init(Scenario)0.206
Steps 
Quando realizo um DELETE com body8.462
Output 1 
[JSON REQUEST API /anticipation/zenite/rav-auto] 
Request method:	DELETE
Request URI:	https://rl7-hom-api.useredecloud.com.br/anticipation/zenite/rav-auto
Proxy:			http://proxy:8080
Request params:	<none>
Query params:	<none>
Form params:	<none>
Path params:	<none>
Headers:		Authorization=Bearer eyJraWQiOiJmMjUyYmMxMi1jZTJkLTQzMDktOGJlYS1hN2UxM2NmMzk4NTIiLCJhbGciOiJSUzI1NiJ9.eyJpc3MiOiJodHRwczovL3JsNy1ob20tYXBpLnVzZXJlZGVjbG91ZC5jb20uYnIvb2F1dGgvdjIiLCJpYXQiOjE2OTI3MzM4NTYsIm5iZiI6MTY5MjczMzg1NiwiYXVkIjoiaHR0cHM6Ly9ybDctaG9tLWFwaS51c2VyZWRlY2xvdWQuY29tLmJyL29hdXRoL3YyIiwiZXhwIjoxNjkyNzM1Mjk2LCJhcHAiOiJyYXZfYW50aWNpcGF0aW9uIiwidmVyIjoiMS4wIiwib3JnIjoiMTM0NWI3ZjgtZDIzYi00NjNmLWI1ODUtMTBhNGIwOTZiNmEwIiwic2NvcGUiOiJtZXJjaGFudC1zdGF0ZW1lbnQgYWZmaWxpYXRlIGZlYXR1cmVfbWVyY2hhbnRfc3RhdGVtZW50IGFudGljaXBhdGlvbiBjdXN0b21lci1zdXBwb3J0IHdlYmhvb2tzIiwicHJpZCI6IjIiLCJjZWxsIjoiMzQxIiwiY2hubCI6IjEiLCJjaWQiOiI0M2NlMWM1My0yZDc5LTRjZWYtOTBlYy0wNWViN2U2NDcwZGQiLCJ1c2lkIjoiNDk5NzhjNGYtODNjMC00MDFlLTgyNmQtMzI4NmJiOGFkY2M5In0.lbxkrv1uCoQcbtiEEiHoXM3GwTNbOuk2nsLO9fNluRaxRsH3z9DP_pr88pDZFZ_XQQQsAQjBXeDkH_mw1d0STeWAV269mSH-k3MTUAUzlW6ZP5xgnOqhw4-o5OSYxTcmOYMeadb7DfWWbNgYc4j8z2a-cqi3B7cti0cutgQ9yUGpM6YssPtFg2sQqcTGCUdQqAcFG4fM7H3q-fGKqoqDpXo0nzRkSc_c3kfVcB7BygWx1Lq6yQ_hLXOO_n2fM1A-eHgfQEA4i5KZOSy6tGfyhPMrNAHnCVgTXGg0L2IFum7X2mbIvnSLv8ha2VyRmww6OTWkc02F-1QdGvaNf3UBKg
				Accept=*/*
				Content-Type=application/json; charset=UTF-8
Cookies:		<none>
Multiparts:		<none>
Body:
{
    "companyNumber": 33626,
    "codeExclusion": 1,
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 200 OK
Via: 1.1 27a40883692bd2d0fc9f21eedec9bbce.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:57:56 GMT
X-Cache: Miss from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: 8pO39uDhd7JHWmjyndjdo8q5NOBsD6jRIrtuz-AKWVPG1oshD03azQ==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e5133d-3375f33346c632652090f825
Content-Length: 867
x-amz-apigw-id: KE_xrG6NoAMEiZA=
x-amzn-RequestId: b7775a45-a26b-4853-a933-af7538cbaab4
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:57:49 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 867

{
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
}


Então o código de retorno é 2000.001
* apresenta a mensagem "33626" no path "object.companyNumber"0.033
Hooks 
After Hooks.afterScenarioExecution(Scenario)0.000
0.040
Contexto 
Steps 
Dado que tenho token de usuário organização com acesso a antecipação de crédito0.036
Output 1 
Utilizado token da memória com titulo: AutenticacaoParceiro com valor: eyJraWQiOiJmMjUyYmMxMi1jZTJkLTQzMDktOGJlYS1hN2UxM2NmMzk4NTIiLCJhbGciOiJSUzI1NiJ9.eyJpc3MiOiJodHRwczovL3JsNy1ob20tYXBpLnVzZXJlZGVjbG91ZC5jb20uYnIvb2F1dGgvdjIiLCJpYXQiOjE2OTI3MzM4NTYsIm5iZiI6MTY5MjczMzg1NiwiYXVkIjoiaHR0cHM6Ly9ybDctaG9tLWFwaS51c2VyZWRlY2xvdWQuY29tLmJyL29hdXRoL3YyIiwiZXhwIjoxNjkyNzM1Mjk2LCJhcHAiOiJyYXZfYW50aWNpcGF0aW9uIiwidmVyIjoiMS4wIiwib3JnIjoiMTM0NWI3ZjgtZDIzYi00NjNmLWI1ODUtMTBhNGIwOTZiNmEwIiwic2NvcGUiOiJtZXJjaGFudC1zdGF0ZW1lbnQgYWZmaWxpYXRlIGZlYXR1cmVfbWVyY2hhbnRfc3RhdGVtZW50IGFudGljaXBhdGlvbiBjdXN0b21lci1zdXBwb3J0IHdlYmhvb2tzIiwicHJpZCI6IjIiLCJjZWxsIjoiMzQxIiwiY2hubCI6IjEiLCJjaWQiOiI0M2NlMWM1My0yZDc5LTRjZWYtOTBlYy0wNWViN2U2NDcwZGQiLCJ1c2lkIjoiNDk5NzhjNGYtODNjMC00MDFlLTgyNmQtMzI4NmJiOGFkY2M5In0.lbxkrv1uCoQcbtiEEiHoXM3GwTNbOuk2nsLO9fNluRaxRsH3z9DP_pr88pDZFZ_XQQQsAQjBXeDkH_mw1d0STeWAV269mSH-k3MTUAUzlW6ZP5xgnOqhw4-o5OSYxTcmOYMeadb7DfWWbNgYc4j8z2a-cqi3B7cti0cutgQ9yUGpM6YssPtFg2sQqcTGCUdQqAcFG4fM7H3q-fGKqoqDpXo0nzRkSc_c3kfVcB7BygWx1Lq6yQ_hLXOO_n2fM1A-eHgfQEA4i5KZOSy6tGfyhPMrNAHnCVgTXGg0L2IFum7X2mbIvnSLv8ha2VyRmww6OTWkc02F-1QdGvaNf3UBKg

E que tenho a url de antecipacao Zenite RavAuto0.004
E que tenho os dados do delete válidos para realizar um cancelamento Zenite RavAuto0.000
