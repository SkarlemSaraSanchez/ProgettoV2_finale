# ProgettoV2_finale
Progetto OOP

* [Introduzione](#introduzione)
* [Rotte](#rotte)
* [Esempi Request](#esempi_request)


<div id = introduzione />

## INTRODUZIONE
Paragrafo dell'introduzione
L'applicazione consente all'utente di analizzare gli eventi che avreanno luogo in un determinato paese, in particolare in Canada, utilizzando l'API di Ticket Master. Ticket Master si occupa della gestione di eventi appartenenti a varie classificazioni.

<div id = rotte />

## ROTTE
Paragrafo rotte
L'applicazione consente di utilizzare 2 diversi tipi di rotte:
* Rotte (/stats/country/)
* Rotte (/country)
 
Per l'utilizzo delle rotte di seguito troviamo una legenda dei parametri che si possono utilizzare nelle richieste:
- `country` indica la nazione 
- `stateCode` indica lo stato o gli stati (<b color=red>*</b>)
- `nameCat` indica la classificazione o le classificazioni
- `startdate` inidica la data di inizio periodo
- `enddate` indica la data fine periodo

### STATISTICHE

|**Tipo**| **Rotta** (/stats/country)                                                                   |**Parametri**                                            |
|--------|----------------------------------------------------------------------------------------------|---------------------------------------------------------|
|` GET ` | `/{countryCode}`                                                                             | `countryCode`                                         |
|` GET ` | `/{countryCode}/classification/{nameCat}`                                                    | `countryCode`,`nameCat`                                 |
|` GET ` | `/{countryCode}/state/{stateCode}/classification/{nameClass}/startdate/{start}/enddate/{end}`| `countryCode`,`stateCode`,`nameClass`,`start`,`end`     |
|` GET ` | `/{countryCode}/state/{stateCode}/statsmensili/{anno}`                                       | `countryCode`,`stateCode`,`anno`                        |
  
### ALTRE

|__Tipo__| __Rotta__ (/stats/country)                                            |__Parametri__                                            |
|--------|-----------------------------------------------------------------------|---------------------------------------------------------|
|` GET ` | `/country/{countryCode}`                                              | `countryCode`                                           |
|` GET ` | `/country/{countryCode}/state/{stateCode}`                            | `countryCode`,`stateCode`                               |
|` GET ` | `/country/{countryCode}/state/{stateCode}/classification/{nameClass}` | `countryCode`,`stateCode`,`nameClass`                   |
|` GET ` | `/events/classification`                                              |                                                         | 


## ESEMPI REQUEST
Paragrafo esempo request
