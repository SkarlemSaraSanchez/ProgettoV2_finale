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

### STATISTICHE

|**Tipo**| **Rotta** (/stats/country)                                            | **Descrizione**                   |**Parametri**                                            |
|--------|-----------------------------------------------------------------------|-----------------------------------|---------------------------------------------------------|
|` GET ` | `/{countryCode}`                                                      |Restituisce le statistiche         | `countryCode`,`                                         |
|` GET ` | `/{countryCode}/classification/{nameCat}`                             |Restituisce le statistiche         | `countryCode`,`nameCat`                                 |
|` GET ` | `/{countryCode}/state/{stateCode}/classification/{nameClass}/startdate/{start}/enddate/{end}`|            | `countryCode`,`stateCode`,`nameClass`,`start`,`end`     |
|` GET ` | `/{countryCode}/state/{stateCode}/statsmensili/{anno}`                |Restituisce le statistiche annuali | `countryCode`,`stateCode`,`anno`                        |
  
### ALTRE

|__Tipo__| __Rotta__ (/stats/country)                                            | __Descrizione__                   |__Parametri__                                            |
|--------|-----------------------------------------------------------------------|-----------------------------------|---------------------------------------------------------|
|` GET ` | `/country/{countryCode}`                                              |Restituisce il numero degli eventi | `countryCode`                                           |
|` GET ` | `/country/{countryCode}/state/{stateCode}`                            |Restituisce il numero degli eventi | `countryCode`,`stateCode`                               |
|` GET ` | `/country/{countryCode}/state/{stateCode}/classification/{nameClass}` |Restituisce il numero degli eventi | `countryCode`,`stateCode`,`nameClass`                   |
|` GET ` | `/events/classification`                                              |Restituisce le classificazioni     |                                                         | 


## ESEMPI REQUEST
Paragrafo esempo request
