# ProgettoV2_finale
Progetto OOP

* [Introduzione](#introduzione)
* [Rotte](#rotte)
* [Esempi Request](#esempi_request)


<div id = introduzione />

## INTRODUZIONE
L'applicazione consente all'utente di analizzare gli eventi che avreanno luogo in un determinato paese, in particolare in Canada, utilizzando l'API di Ticket Master. Ticket Master si occupa della gestione di eventi appartenenti a varie classificazioni.

<div id = rotte />

## ROTTE
L'applicazione consente di utilizzare 2 diversi tipi di rotte:
* Rotte per le Statistiche (/stats/country/)
* Rotte Varie (/country)
 
Per l'utilizzo delle rotte di seguito troviamo una legenda dei parametri che si possono utilizzare nelle richieste:
- `country` indica la nazione 
- `stateCode` indica lo stato o gli stati (:heavy_exclamation_mark:)
- `nameCat` indica la classificazione o le classificazioni (:heavy_exclamation_mark:)
- `startdate` inidica la data di inizio periodo
- `enddate` indica la data fine periodo

(:heavy_exclamation_mark:) E' possibile inserire più di un valore (basta dividere i valori desiderati con `-`)


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

<div id = esempi_request />

## ESEMPI REQUEST

### /stats/country/{countryCode}
Request URL: __/stats/country/CA__
```json
{
    "Stats": {
        "media eventi nazione ": 540,
        "totale eventi organizzati di ": 6487,
        "statistiche": [
            {
                "statistiche stati con numero maggiore di eventi": [
                    {
                        "stato  ": "ON",
                        "num eventi": 3695
                    }
                ]
            },
            {
                "statistiche stati con numero minore  di eventi": [
                    {
                        "stato  ": "NU",
                        "num eventi": 0
                    },
                    {
                        "stato  ": "YT",
                        "num eventi": 0
                    }
                ]
            }
        ],
        "nazione": "ca"
    }
}
```

### stats/country/{countryCode}/classification/{nameCat}
Request URL: __/stats/country/CA/classification/music__
```json
{
    "Stats": [
        {
            "totale eventi organizzati di music": 2326,
            "statistiche": [
                {
                    "statistiche stati con numero maggiore di eventi": [
                        {
                            "stato  ": "ON",
                            "num eventi": 885
                        }
                    ]
                },
                {
                    "statistiche stati con numero minore  di eventi": [
                        {
                            "stato  ": "NT",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "NU",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "YT",
                            "num eventi": 0
                        }
                    ]
                }
            ],
            "categoria": "music",
            "media eventi per stato  music": 193
        }
    ],
    "nazione": "ca"
}
```
Request URL: __/stats/country/CA/classification/music-sports__
```json
{
    "Stats": [
        {
            "totale eventi organizzati di music": 2326,
            "statistiche": [
                {
                    "statistiche stati con numero maggiore di eventi": [
                        {
                            "stato  ": "ON",
                            "num eventi": 885
                        }
                    ]
                },
                {
                    "statistiche stati con numero minore  di eventi": [
                        {
                            "stato  ": "NT",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "NU",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "YT",
                            "num eventi": 0
                        }
                    ]
                }
            ],
            "categoria": "music",
            "media eventi per stato  music": 193
        },
        {
            "totale eventi organizzati di sports": 783,
            "statistiche": [
                {
                    "statistiche stati con numero maggiore di eventi": [
                        {
                            "stato  ": "ON",
                            "num eventi": 309
                        }
                    ]
                },
                {
                    "statistiche stati con numero minore  di eventi": [
                        {
                            "stato  ": "NT",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "NU",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "YT",
                            "num eventi": 0
                        }
                    ]
                }
            ],
            "media eventi per stato  sports": 65,
            "categoria": "sports"
        }
    ],
    "nazione": "ca"
}
```
