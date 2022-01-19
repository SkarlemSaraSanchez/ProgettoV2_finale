# ProgettoV2_finale
Progetto OOP

* [Introduzione](#introduzione)
* [Rotte](#rotte)
* [Esempi Request](#esempi_request)


<div id = introduzione />

## INTRODUZIONE
Paragrafo dell'introduzione

<div id = rotte />

## ROTTE
Paragrafo rotte

|**Tipo**| **Rotta**                                                             | **Descrizione**                   |**Parametri**                                            |
|--------|-----------------------------------------------------------------------|-----------------------------------|---------------------------------------------------------|
|` GET ` | `/country/{countryCode}`                                              |Restituisce il numero degli eventi | `countryCode`                                           |
|` GET ` | `/stats/country/{countryCode}`                                        |Restituisce le statistiche         | `countryCode`,`                                         |
|` GET ` | `/stats/country/{countryCode}/classification/{nameCat}`               |Restituisce le statistiche         | `countryCode`,`nameCat`                                 |
|` GET ` | `/country/{countryCode}/state/{stateCode}`                            |Restituisce il numero degli eventi | `countryCode`,`stateCode`                               |
|` GET ` | `/country/{countryCode}/state/{stateCode}/classification/{nameClass}` |                                   | `countryCode`,`stateCode`,`nameClass`                   |
|` GET ` | `/country/{countryCode}/state/{stateCode}/classification/{nameClass}/startdate/{start}/enddate/{end}`|    | `countryCode`,`stateCode`,`nameClass`,`start`,`end`     |
|` GET ` | `/stats/country/{countryCode}/state/{stateCode}/statsmensili/{anno}`  |Restituisce le statistiche annuali | `countryCode`,`stateCode`,`anno`                        |
|` GET ` | `/events/classification`                                              |Restituisce tutte le classificazioni|                                                        |                    

## ESEMPI REQUEST
Paragrafo esempo request
