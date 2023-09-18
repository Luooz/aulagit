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






Cenario Validar cancelamento de ravAuto com sucesso 

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

Cenario Validar cancelamento de ravAuto com sucesso sem campo "daysToBeCancelled" 

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
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 400 Bad Request
Via: 1.1 27a40883692bd2d0fc9f21eedec9bbce.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:57:57 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: PMFsLHwf6lzBXVelIRJ3nk4IAwWrld3UGI2OaFDyTUR3sAGyqJzzQg==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e51345-4aeb7b51185be1ff0db700c9
Content-Length: 118
x-amz-apigw-id: KE_y6EIPIAMEltQ=
x-amzn-RequestId: a6d222ac-21ba-4237-bfa7-29998eea002d
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:57:57 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 118

{
    "errors": {
        "code": "1002",
        "message": "daysToBeCancelled: must be a valid value or attribute is required.",
        "status": 400
    }
}

Validar cancelamento de ravAuto com sucesso sem campo "reasonExclusion" 

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
    "daysToBeCancelled": 1
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 200 OK
Via: 1.1 cf4c5c0d1e9f7f2fe3fd71e902b923a0.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:02 GMT
X-Cache: Miss from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: 23BEQ8o-F9xP28Y43JUJVJiaBTKiPl9crGB79Y7QyGGf1F3M5rGJAg==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e51346-00baeed82b8ae2c24c69eee6
Content-Length: 867
x-amz-apigw-id: KE_zCG7koAMEKOA=
x-amzn-RequestId: d363a691-c93f-428d-8e0f-227b05ebddf0
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:57:58 GMT
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

Cenario Validar cancelamento de ravAuto com campo "companyNumber" com valor alfabetico inválido

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
    "companyNumber": "ABC",
    "codeExclusion": 1,
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 422 unknown
Via: 1.1 ac6d83e68fe20e1748535144bdfba004.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:02 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: EeAqbdzaHY4k9A-IBm_3cDHly8diyvDcLTY4BpBHPSP9hMi4HrOhxw==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e5134a-1e724a3a2509caab60921faa
Content-Length: 42
x-amz-apigw-id: KE_zvHj5oAMENvQ=
x-amzn-RequestId: 09736b44-a85c-42b5-90b3-569457d2b53a
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:02 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 42

{
    "companyNumber": [
        "Not a valid integer."
    ]
}

Cenario Validar cancelamento de ravAuto com campo "companyNumber" com valor em branco

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
    "companyNumber": " ",
    "codeExclusion": 1,
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 422 unknown
Via: 1.1 1771886d2860f832da6663a86b97d96a.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:03 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: NkOvIDE-6mNsPEFVhN7F5ksg4w_vH0w1aE5tYI-OIb5JmTd_B0nf0A==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e5134b-0b9f04ef35625fe718958f8f
Content-Length: 42
x-amz-apigw-id: KE_zzHmloAMEkmg=
x-amzn-RequestId: 47c7a513-b806-43fe-886f-b83ea64b1bdd
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:02 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 42

{
    "companyNumber": [
        "Not a valid integer."
    ]
}

Cenario Validar cancelamento de ravAuto com campo "companyNumber" com valor vazio

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
    "companyNumber": "",
    "codeExclusion": 1,
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 422 unknown
Via: 1.1 1f885eb623f2401ecf9e53f5bdb7e1b4.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:04 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: qxZ6sjYpdEm4cLpynDEaRYQs94T-_Fg-VGvxZ_zz9fAGgJiT8plzUw==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e5134c-51c02db013314a247d2fefe8
Content-Length: 42
x-amz-apigw-id: KE_z8EJ-IAMERbg=
x-amzn-RequestId: 1ba2aa47-d1b3-411f-821d-9264ec67a05b
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:03 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 42

{
    "companyNumber": [
        "Not a valid integer."
    ]
}

Cenario Validar cancelamento de ravAuto sem campo "companyNumber"

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
    "codeExclusion": 1,
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 422 unknown
Via: 1.1 ac4e6581409ee543d30418bc80eff8a8.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:04 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: L0Og1M1PgDp4Nu7IEcTf4umQEEf7q08ko_hNMDNgzt7KiR3G8gj2kw==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e5134c-58f1a9c7261045d246c604f2
Content-Length: 54
x-amz-apigw-id: KE_0CGN5IAMEGFw=
x-amzn-RequestId: 35b581fa-25a4-4918-bfb2-c428535f2e0a
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:04 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 54

{
    "companyNumber": [
        "Missing data for required field."
    ]
}

Cenario Validar cancelamento de ravAuto com campo "codeExclusion" com valor alfabetico inválido

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
    "codeExclusion": "ABC",
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 422 unknown
Via: 1.1 f32d2bdd5c2020bad0a252a6b7deb9b2.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:05 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: G42JkCY-fpnnUfAAIpiFseXSqjvZoMH7xFyhA9JFvDLhjIWX77RsdA==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e5134d-63d7f7e543e247fb73ee8f5f
Content-Length: 42
x-amz-apigw-id: KE_0IEf-IAMEbjg=
x-amzn-RequestId: ad593943-8c23-41b9-a724-b161aeb223f3
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:05 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 42

{
    "codeExclusion": [
        "Not a valid integer."
    ]
}

Cenario Validar cancelamento de ravAuto com campo "codeExclusion" com valor em branco 

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
    "codeExclusion": " ",
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 422 unknown
Via: 1.1 47a154aa18274fd426bd9733e306788c.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:06 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: amVDjAAPEd9U0jw9rQbPKC_1RFgGkHqOkHvoY0uSyC6vyi1rfZCbzA==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e5134e-1577d1b50c9ab03f13297b9a
Content-Length: 42
x-amz-apigw-id: KE_0PHSjIAMESvg=
x-amzn-RequestId: b6d6b8d2-7b4e-4e70-ac8d-a46b244024b2
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:05 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 42

{
    "codeExclusion": [
        "Not a valid integer."
    ]
}

Cenario Validar cancelamento de ravAuto com campo "codeExclusion" com valor vazio

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
    "codeExclusion": "",
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 422 unknown
Via: 1.1 2c76d08ca890064a1588e6f4501a0576.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:06 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: dUS_rqb3QFzWtxwFR2p7ZDtxZhAF-JqC194Imr_EzoDJOh2pGk0ruQ==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e5134e-1450dcc11a375491082941a1
Content-Length: 42
x-amz-apigw-id: KE_0WHT5oAMEfBg=
x-amzn-RequestId: d01a8016-74b4-4ae9-92b4-baaa88f0c161
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:06 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 42

{
    "codeExclusion": [
        "Not a valid integer."
    ]
}

Cenario Validar cancelamento de ravAuto sem campo "codeExclusion

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
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 400 Bad Request
Via: 1.1 ac6d83e68fe20e1748535144bdfba004.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:07 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: gPENSs3PVPWYGfRKGiFbNQhayif4MWggUBJAFsvNWW6nLsvNBoC1_A==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e5134f-79d2500670af396368d8e281
Content-Length: 114
x-amz-apigw-id: KE_0eF_-oAMESTQ=
x-amzn-RequestId: 1ede54ad-3cf1-43cc-80bb-6e3670394610
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:06 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 114

{
    "errors": {
        "code": "1002",
        "message": "codeExclusion: must be a valid value or attribute is required.",
        "status": 400
    }
}

Cenario Validar cancelamento de ravAuto com campo "daysToBeCancelled" com valor invalido

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
    "daysToBeCancelled": "ABC",
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 422 unknown
Via: 1.1 fb0e71e586369a585a71bf96f3ce2856.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:08 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: jo1gItHXabcEvjdfTGoJY67-4VHOxZGXHgnTODAYdlV6PuYKa-U45A==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e51350-7fc2f6cb38e237b84a46b007
Content-Length: 46
x-amz-apigw-id: KE_0kEGroAMEerw=
x-amzn-RequestId: a84f9380-fbea-462a-b3c0-019376758d2d
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:08 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 46

{
    "daysToBeCancelled": [
        "Not a valid integer."
    ]
}

Cenario Validar cancelamento de ravAuto com campo "companyNumber" com valor inexistente

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
    "companyNumber": 90016267,
    "codeExclusion": 1,
    "daysToBeCancelled": 1,
    "reasonExclusion": "Teste integração Zenite -> RavAuto"
}

[JSON RESPONSE API /anticipation/zenite/rav-auto] 
HTTP/1.1 404 Not Found
Via: 1.1 1e033b63f84574dadc301b3d41a55f6e.cloudfront.net (CloudFront), 1.1 10.225.75.34 (McAfee Web Gateway 11.2.6.43601)
Date: Tue, 22 Aug 2023 19:58:09 GMT
X-Cache: Error from cloudfront
Connection: Keep-Alive
X-Amz-Cf-Id: MnLOCxb5RruNfkUWm5q4Z4hlwHDf1BnNAHDiPnZNR-k1QQT8XK4Q4A==
Content-Type: application/json
X-Amz-Cf-Pop: GRU50-C1
x-b3-traceid: Root=1-64e51350-3ca3ddd938e60c1f2f12b2f2
Content-Length: 86
x-amz-apigw-id: KE_0sGCbIAMEQ_Q=
x-amzn-RequestId: c3a57b56-3e7f-41cc-9e7d-d8e6f2caa4db
x-amzn-Remapped-date: Tue, 22 Aug 2023 19:58:08 GMT
x-amzn-Remapped-server: uvicorn
x-amzn-Remapped-content-length: 86

{
    "errors": {
        "code": "1004",
        "message": "The record entered does not exist.",
        "status": 404
    }
}
