# Progetto OOP Celozzi - Sanchez

![ticket_master_official](https://user-images.githubusercontent.com/95294283/150121832-d316b42a-4142-4ee5-bcb7-aa17ec900ea4.jpg)

# SOMMARIO
* [Introduzione](#introduzione)
* [Rotte](#rotte)
* [Esempi Request](#esempi_request)
   * [Esempi Stats](#esempi_stats)
   * [Altri Esempi](#esempi_altri)


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
- `startdate` inidica la data di inizio periodo  (:grey_exclamation:)
- `enddate` indica la data fine periodo  (:grey_exclamation:)

(:heavy_exclamation_mark:)  E' possibile inserire più di un valore (basta dividere i valori desiderati con `-`)
(:grey_exclamation:)  La data deve essere inserita in formato data italiano __gg/mm/aaaa__

### Stats

|**Tipo**| **Rotta** (/stats/country)                                                                   |**Parametri**                                            |
|--------|----------------------------------------------------------------------------------------------|---------------------------------------------------------|
|` GET ` | `/{countryCode}`                                                                             | `countryCode`                                           |
|` GET ` | `/{countryCode}/classification/{nameCat}`                                                    | `countryCode`,`nameCat`                                 |
|` GET ` | `/{countryCode}/state/{stateCode}/classification/{nameClass}/startdate/{start}/enddate/{end}`| `countryCode`,`stateCode`,`nameClass`,`start`,`end`     |
|` GET ` | `/{countryCode}/state/{stateCode}/statsmensili/{anno}`                                       | `countryCode`,`stateCode`,`anno`                        |
  
### Altre

|__Tipo__| __Rotta__                                                             |__Parametri__                                            |
|--------|-----------------------------------------------------------------------|---------------------------------------------------------|
|` GET ` | `/country/{countryCode}`                                              | `countryCode`                                           |
|` GET ` | `/country/{countryCode}/state/{stateCode}`                            | `countryCode`,`stateCode`                               |
|` GET ` | `/country/{countryCode}/state/{stateCode}/classification/{nameClass}` | `countryCode`,`stateCode`,`nameClass`                   |
|` GET ` | `/events/classification`                                              |                                                         | 

<br>
<div id = esempi_request />
<div id = esempi_stats />

## ESEMPI STATS REQUEST

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
Request URL: __/stats/country/CA/classification/music-sports-film__
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
        },
        {
            "media eventi per stato  film": 0,
            "statistiche": [
                {
                    "statistiche stati con numero maggiore di eventi": [
                        {
                            "stato  ": "BC",
                            "num eventi": 6
                        }
                    ]
                },
                {
                    "statistiche stati con numero minore  di eventi": [
                        {
                            "stato  ": "AB",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "MB",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "NB",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "NL",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "NT",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "NS",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "NU",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "PE",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "QC",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "SK",
                            "num eventi": 0
                        },
                        {
                            "stato  ": "YT",
                            "num eventi": 0
                        }
                    ]
                }
            ],
            "categoria": "film",
            "totale eventi organizzati di film": 10
        }
    ],
    "nazione": "ca"
}
```

### stats/country/{countryCode}/state/{stateCode}/classification/{nameClass}/startdate/{start}/enddate/{end}
Request URL: __/stats/country/CA/state/QC-ON/classification/music-sports/startdate/22-2-2022/enddate/14-5-2022__
```json
{
    "categorie": [
        {
            "categoria": "music",
            "stati": [
                {
                    "numero eventi": 283,
                    "media mensile eventi": "141,5",
                    "stateCode": "QC"
                },
                {
                    "numero eventi": 497,
                    "media mensile eventi": "248,5",
                    "stateCode": "ON"
                }
            ]
        },
        {
            "categoria": "sports",
            "stati": [
                {
                    "numero eventi": 76,
                    "media mensile eventi": "38",
                    "stateCode": "QC"
                },
                {
                    "numero eventi": 134,
                    "media mensile eventi": "67",
                    "stateCode": "ON"
                }
            ]
        }
    ],
    "Periodo": [
        {
            "Start Date": "22-2-2022",
            "End Date": "14-5-2022"
        }
    ],
    "contryCode": "CA"
}
```

### stats/country/{countryCode}/state/{stateCode}/statsmensili/{anno}
Request URL: __/stats/country/CA/state/ON/statsmensili/2022__
```json
{
    "Anno": "2022",
    "Stats Mensili": [
        {
            "Gennaio": 523
        },
        {
            "Febbraio": 1540
        },
        {
            "Marzo": 499
        },
        {
            "Aprile": 456
        },
        {
            "Maggio": 343
        },
        {
            "Giugno": 114
        },
        {
            "Luglio": 82
        },
        {
            "Agosto": 63
        },
        {
            "Settembre": 42
        },
        {
            "Ottobre": 23
        },
        {
            "Novembre": 14
        },
        {
            "Dicembre": 7
        }
    ],
    "MIN,MAX,MEDIA": [
        {
            "Mese con numero minimo di eventi": "Dicembre(7)",
            "Mese con numero massimo di eventi": "Febbraio(1540)",
            "Media Mensile": 308
        }
    ],
    "State": "ON",
    "Country": "CA",
    "TOT EVENTI": 3706,
    "Stats Classificazioni": [
        {
            "Numero Eventi": 419,
            "Nome": "Miscellaneous"
        },
        {
            "Numero Eventi": 309,
            "Nome": "Sports"
        },
        {
            "Numero Eventi": 880,
            "Nome": "Music"
        },
        {
            "Numero Eventi": 2067,
            "Nome": "Arts % Theatre"
        },
        {
            "Numero Eventi": 8,
            "Nome": "Undefined"
        },
        {
            "Numero Eventi": 4,
            "Nome": "Film"
        }
    ]
}
```
<div id = esempi_altri />

## ESEMPI ALTRE REQUEST

### /country/{countryCode}
Request URL: __/country/CA__
```json
{
    "numero eventi": 6414,
    "contryCode": "ca"
}
```
### /country/{countryCode}/state/{stateCode}
Request URL: __/country/CA/state/ON__
```json
{
    "numero eventi": 3696,
    "contryCode": "CA",
    "stati": [
        {
            "numero eventi": 3696,
            "stateCode": "ON"
        }
    ]
}
```
Request URL: __/country/CA/state/ON-QC-PE-NU__
```json
{
    "numero eventi": 4868,
    "contryCode": "CA",
    "stati": [
        {
            "numero eventi": 3696,
            "stateCode": "ON"
        },
        {
            "numero eventi": 1159,
            "stateCode": "QC"
        },
        {
            "numero eventi": 13,
            "stateCode": "PE"
        },
        {
            "numero eventi": "0",
            "stateCode": "NU"
        }
    ]
}
```
### /country/{countryCode}/state/{stateCode}/classification/{nameClass}
Request URL: __/country/CA/state/QC/classification/music__
```json
{
    "categorie": [
        {
            "categoria": "music",
            "stati": [
                {
                    "numero eventi": 556,
                    "stateCode": "QC"
                }
            ]
        }
    ],
    "contryCode": "CA"
}
```
Request URL: __/country/CA/state/QC-ON-NU/classification/music-sports__
```json
{
    "categorie": [
        {
            "categoria": "music",
            "stati": [
                {
                    "numero eventi": 556,
                    "stateCode": "QC"
                },
                {
                    "numero eventi": 886,
                    "stateCode": "ON"
                },
                {
                    "numero eventi": "0",
                    "stateCode": "NU"
                }
            ]
        },
        {
            "categoria": "sports",
            "stati": [
                {
                    "numero eventi": 143,
                    "stateCode": "QC"
                },
                {
                    "numero eventi": 309,
                    "stateCode": "ON"
                },
                {
                    "numero eventi": "0",
                    "stateCode": "NU"
                }
            ]
        }
    ],
    "contryCode": "CA"
}
```



