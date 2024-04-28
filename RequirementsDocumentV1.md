# Documento dei Requisiti - EZElectronics corrente

Data:

Versione: V1 - descrizione di EZElectronics nella sua forma corrente

| Numero della versione | Cambiamenti            |
| :------------: | :---------------: |
|        V1      | versione iniziale |

# Contenuti

- [Documento dei Requisiti - EZElectronics corrente](#documento-dei-Requisiti---EZElectronics-corrente)
- [Contentenuti](#contenuti)
- [Descrizione Informale](#descrizione-informale)
- [Stakeholders](#stakeholders)
- [Diagramma del contesto e Interfacce](#diagramma-del-contesto-e-interfacce)
  - [Diagramma del Contesto](#diagramma-del-contesto)
  - [Interfacce](#interfacce)
- [Stories and personas](#stories-and-personas)
- [Requisiti Funzionali e non Funzionali](#requisiti-funzionali-e-non-funzionali)
  - [Requisiti Funzionali](#requisiti-funzionali)
  - [Non Functional Requirements](#non-functional-requirements)
- [Casi d'Uso e Diagrammi dei Casi d'Uso](#casi-d'uso-e-diagrammi-dei-casi-d'uso)
  - [Diagrammi dei Casi d'Uso](#diagrammi-dei-casi-d'uso)
    - [Use case 1, UC1](#use-case-1-uc1)
      - [Scenario 1.1](#scenario-11)
      - [Scenario 1.2](#scenario-12)
      - [Scenario 1.3](#scenario-13)
    - [Use case 2, UC2](#use-case-2-uc2)
    - [Use case 3, UC3](#use-case-x-uc3)
      - [Scenario 3.1](#scenario-31)
- [Glossario](#glossario)
- [System Design](#system-design)
- [Deployment Diagram](#deployment-diagram)

# Descrizione Informale

EZElectronics (letto EaSy Electronics) è una applicazione software fatta per aiutare i manager di piccoli negozi di elettronica a gestire i loro prodotti e a offrirli ai clienti tramite un sito dedicato. I Manager possono vedere i prodotti disponibili, aggiungerne di nuovi e confermare gli acquisti. I Clienti possono vedere i prodotti disponibili, aggiungerli al loro carrello e vedere lo storico dei loro acquisti.

# Stakeholders

| Stakeholder name | Description |
| :--------------: | :---------: |
| Manager | Gestore del negozio di elettronica. Gestisce l'inserzione e la modifica dei prodotti e le operazioni di vendita. |
| Cliente | Cliente che visita il sito web. Visualizza i prodotti, gestisce il carrello ed acquista. |

# Diagramma del contesto e Interfacce

## Diagramma del contesto


 
## Interfaces

|   Actor   | Interfaccia Logica | Interfaccia Fisica |
| :-------: | :----------------: | :----------------: |
| Manager   | GUI Manager        | PC/Internet        |
| Cliente   | GUI Cliente        | PC/Smartphone      |


# Stories and personas

### Manager
- Luigi - Manager (40 anni)
  Lui può creare un account, accedere ad un account esistente o effettuare logout. Può registrare uno o più prodotti di uno stesso modello, smarcarli come venduti o cancellarli. Può visualizzare tutti i prodotti, filtrando eventualmente quelli già venduti o non ancora venduti e/o filtrando per categoria o modello. Può cercare un prodotto per codice identificativo.

  Obiettivi: Offrire e mantenere un servizio di qualità per i clienti e fornire un catalogo aggiornato.
  
- Sara - customer (25 anni)
  Lei può creare un account, accedere ad un account esistente o effettuare logout. Può visualizzare tutti i prodotti, filtrando eventualmente quelli già venduti o non ancora venduti e/o filtrando per categoria o modello. Può cercare un prodotto per codice identificativo. Può gestire un carrello di prodotti: può visualizzarlo, può aggiungere o rimuovere un singolo prodotto, svuotare l'intero carrello e confermare l'acquisto dei prodotti. Può visualizzare la lista degli ordini effettuati.

  Obiettivi: acquistare prodotti in modo semplice.

# Requisiti Funzionali e non Funzionali #

## Requisiti Funzionali ##

|  ID   | Description |
| --- | --------- |
|  **FR1**  |      **Gestione Accesso**    |
|FR1.1| Accesso previo credenziali|
|FR1.2| Logout utente|
|FR1.3| Informazioni utente loggato|
|FR1.4| Registrazione di un nuovo User|
| --- | --------- |
|  **FR2**  |    **Funzionalità sugli utenti**   |
|FR2.2| Restituisce lista di tutti gli utenti|
|FR2.3| Restituisce una lista di utenti filtrata per ruolo|
|FR2.4| Restituisce un utente specifico per cognome|
|FR2.5| Eimina un determinato utente identificato per cognome|
|FR2.6| Elimina tutti gli utenti registrati **SOLO TESTING**|
| --- | --------- |
|**FR3**| **Funzionalità dei prodotti**|
|FR3.1| Crea un nuovo prodotto|
|FR3.2| Registra l'arrivo dei prodotti|
|FR3.3| Segna un prodotto come venduto|
|FR3.4| Restituisce una lista dei prodotti del database|
|FR3.5| Restituisce un singolo prodotto da codice specifico|
|FR3.6| Restituisce i prodotti di una specifica categoria|
|FR3.7| Restituisce i prodotti di un modello specifico|
|FR3.8| Elimina un prodotto specifico dal database|
|FR3.8| Elimina tutti i prodotti dal database **SOLO TESTING**|
| --- | --------- |
|**FR4**| **Funzionalità del carrello**|
|FR4.1| Restituisce il carrello dell'utente loggato|
|FR4.2| Aggiunge un prodotto al carrello dell'utente loggato|
|FR4.3| Paga per il carrello dell'utente loggato|
|FR4.4| Restituisce l'elenco dei pagamenti effettuati dall'utente loggato|
|FR4.5| Rimuove un prodotto dal carrello dell'utente|
|FR4.6| Elimina il carrello attuale dell'utente|
|FR4.7| Elimina tutti i carrelli dell'utente loggato **SOLO TESTING**|

## Requisiti non funzionali ##

|   ID    | Tipo                               | Descrizionw | Riferimenti |
| :-----: | :--------------------------------: | :---------: | :-------: |
|  NFR1   | Efficienza | Il sistema deve garantire un tempo di risposta di massimo un secondo. Deve garantire meno del 25% delle risorse di cpu. | FR2, FR3, FR4 |
|  NFR2   | Affidabilità | Gli utenti non devono riferire più di un bag al'anno a testa. Il sistema deve essere dispondibile per il 95% del tempo operativo. Il 100% degli errori devone essere espressi nel modo corretto fornendo messaggi e codici specifici. | FR1, FR2, FR3, FR4 |
|  NFR3   | Sicurezza | Protezione dei dati sensibili degli utenti. Gestione delle transazioni | FR1, FR2, FR3, FR4 |
|  NFR4   | Usabilità | Gli utenti non devono imparare a usare il sito. Facilità d'uso: tempo d'apprendimento tendente a 0. Accessibilità: il sistema deve aderire al 100% degli standard web per l'accessibilità | FR1, FR2, FR3, FR4 |
|  NFR5   | Scalabilità | Gestione di un aumento del carico utente maggiore della media senza perdita di prestazioni. | FR2, FR3, FR4 |


# Casi d'Uso e Diagrammi dei Casi d'Uso #

## Diagrammi dei Casi d'Uso ##

## Casi d'Uso ##
### Use case 1, UC1: Creazione Account ###
| Actors Involved  |  Manager                                                             |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | L'utente non deve essere già registrato                              |
|  Post condition  | L'utente è registrato e autenticato                                  |
| Nominal Scenario | Il cliente si registra e viene salvato e autenticato dal sistema     |
|     Variants     |                      nessuna variante                                |
|    Exceptions    | L'utente annulla: il caso d'uso termina con errore. 
                     L'utente inserisce un username già esistente: il sistema lo avvisa.  |

##### Scenario 1.1 #####
|  Scenario 1.1  |                                                                                                       |
| :------------: | :---------------------------------------------------------------------------------------------------: |
|  Precondition  | L'utente non deve essere già registrato                                                               |
| Post condition | L'utente è registrato e autenticato                                                                   |
|     Step#      |                          Descrizione                                                                  |
|       1        | L'utente inserisce i dati richiesti (username, nome, cognome, password, ruolo)                        |
|       2        | L'utente conferma i dati inseri                                                                       |
|       3        | Il sistema verifica i dati inseriti                                                                   |
|       4        | Il sistema registra l'utente                                                                          |
|       4        | Il sistema autentica l'utente                                                                         |
|       5        | Il caso d'uso termina con successo                                                                    |

##### Scenario 1.2 #####
|  Scenario 1.2  |                                                                                                       |
| :------------: | :---------------------------------------------------------------------------------------------------: |
|  Precondition  | L'utente non deve essere già registrato                                                               |
| Post condition | L'utente è registrato e autenticato                                                                   |
|     Step#      |                          Descrizione                                                                  |
|       1        | L'utente inserisce i dati richiesti (username, nome, cognome, password, ruolo)                        |
|       2        | L'utente conferma i dati inseri                                                                       |
|       3        | Il sistema verifica i dati inseriti e trova che lo user name è già esistente                          |
|       4        | Il sistema avvista l'utente dell'errroe                                                               |
|       4        | L'utente sceglie un nuovo user name, che non è già esistente                                          |
|       4        | Il sistema autentica l'utente                                                                         |
|       5        | Il caso d'uso termina con successo                                                                    |

##### Scenario 1.3 #####
|  Scenario 1.3  |                                                                                                       |
| :------------: | :---------------------------------------------------------------------------------------------------: |
|  Precondition  | L'utente non deve essere già registrato                                                               |
| Post condition | L'utente è registrato e autenticato                                                                   |
|     Step#      |                          Descrizione                                                                  |
|       1        | L'utente inserisce i dati richiesti (username, nome, cognome, password, ruolo)                        |
|       2        | L'utente annulla                                                                                      |
|       3        | Il caso d'uso termina con successo                                                                    |

### Use case 2, UC2: Accesso account ###
| Attori Coinvolti | Cliente                                                                                             |
| :--------------: | :-------------------------------------------------------------------------------------------------: |
|   Precondition   | Il cliente non è autenticato                                                                        |
|  Post condition  | L'utente è autenticato                                                                              |
| Nominal Scenario | Il cliente accede al suo account                                                                    |
|     Variants     |                                    nessuna variante                                                 |
|    Exceptions    | Se il cliente non è registrato viene mostrato un messaggio d'errore                                 |

##### Scenario 2.1 #####
|  Scenario 2.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente non è autenticato                                               |
| Post condition | L'utente è autenticato                                                     |
|     Step#      |                                Descrizione                                 |
|       1        | L'utente inserisce i dati richiesti (username, password)                   |
|       2        | L'utente conferma i dati inseriti                                          |
|       3        | Il sistema verifica i dati inseriti                                        |
|       3        | Il sistema autentica l'utente                                              |
|       4        | Il caso d'uso termina con successo                                         |


##### Scenario 2.2 #####
|  Scenario 2.2  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente non è autenticato                                               |
| Post condition | L'utente è autenticato                                                     |
|     Step#      |                                Descrizione                                 |
|       1        | L'utente inserisce i dati richiesti (username, password)                   |
|       2        | L'utente conferma i dati inseriti                                          |
|       3        | Il sistema verifica i dati inseriti                                        |
|       3        | Il sistema mostra un errore all'utente                                     |
|       4        | Il caso d'uso termina con errore                                           |

### Use case 3, UC3: Logout
| Attori Coinvolti |   Cliente                                                            |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | Il cliente è autenticato                                             |
|  Post condition  | Il cliente non è autenticato                                         |
| Nominal Scenario | Il cliente si disconnette dal suo profilo                            |
|     Variants     |                     nessuna variante                                 |
|    Exceptions    | Nessuna                                                              |

##### Scenario 3.1: 
|  Scenario 3.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | Il cliente non è autenticato                                               |
|     Step#      |                                Descrizione                                 |
|       1        | Selezione del pulsante logout                                              |
|       2        | L'utente conferma di voler effettuare il logout                            |
|       3        | Il sistema effettua il logout                                              |
|       4        | Il caso d'uso termina con successo                                         |

### Use case 4, UC4: Visualizzazione dei dati dell'account
| Attori Coinvolti |   Cliente                                                            |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | Il cliente è autenticato                                             |
|  Post condition  | Nessuna                                                              |
| Nominal Scenario | Il cliente si visualizza i dati del suo profilo                      |
|     Variants     |                     nessuna variante                                 |
|    Exceptions    | Nessuna                                                              |

##### Scenario 4.1: #####
|  Scenario 4.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | Nessuna                                                                    |
|     Step#      |                                Descrizione                                 |
|       1        | Il sistema mostra i dati dell'utente                                       |
|       2        | Il caso d'uso termina con successo                                         |

### Use case 5, UC5: Visualizzazione dei prodotti nel carrello ###
| Actors Coinvolti |   Cliente                                                            |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | Il cliente è autenticato                                             |
|  Post condition  | Nessuna                                                              |
| Nominal Scenario | Il cliente visualizza i dati del suo profilo                         |
|     Variants     |                     nessuna variante                                 |
|    Exceptions    | Nessuna                                                              |

##### Scenario 5.1: #####
|  Scenario 5.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | Nessuna                                                                    |
|     Step#      |                                Descrizione                                 |
|       1        | Il sistema mostra i prodotti presenti nel carrello                         |
|       2        | Il caso d'uso termina con successo                                         |

### Use case 6, UC6: Aggiunta del prodotto al carrello ###
| Attori Coinvolti |   Cliente                                                            |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | Il cliente è autenticato                                             |
|  Post condition  | Il prodotto è stato aggiunto al carrello                             |
| Nominal Scenario | Il cliente aggiunge un prodottto al carrello                         |
|     Variants     |                     nessuna variante                                 |
|    Exceptions    | L'utente annulla: il caso d'uso termina con errore                   |

##### Scenario 6.1: #####
|  Scenario 6.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | Il prodotto è stato aggiunto al carrello                                   |
|     Step#      |                                Descrizione                                 |
|       1        | L'utente seleziona un prodotto                                             |
|       2        | L'utente conferma di voler aggiungere il prodotto al carrello              |
|       3        | Il sistema aggiunge il prodotto al carrello                                |
|       4        | Il caso d'uso termina con successo                                         |

##### Scenario 6.2: #####
|  Scenario 6.2  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | Il prodotto è stato aggiunto al carrello                                   |
|     Step#      |                                Descrizione                                 |
|       1        | L'utente seleziona un prodotto                                             |
|       2        | L'utente annulla                                                           |
|       3        | Il caso d'uso termina con errore                                           |

### Use case 7, UC7: Rimozione del prodotto dal carrello ###
| Attori Coinvolti |   Cliente                                                            |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | Il cliente è autenticato                                             |
|  Post condition  | Il prodotto è stato rimosso dal carrello                             |
| Nominal Scenario | Il cliente rimuove un prodottto dal carrello                         |
|     Variants     |                     nessuna variante                                 |
|    Exceptions    | L'utente annulla: il caso d'uso termina con errore                   |

##### Scenario 7.1: #####
|  Scenario 7.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | Il prodotto è stato rimosso dal carrello                                   |
|     Step#      |                                Descrizione                                 |
|       1        | UC: Visualizzazione prodotti già presenti nel carrello                     |
|       2        | L'utente seleziona un prodotto                                             |
|       3        | L'utente seleziona il pulsante rimuovi                                     |
|       4        | L'utente conferma di voler rimuovere il prodotto dal carrello              |
|       5        | Il sistema rimuove il prodotto dal carrello                                |
|       6        | Il caso d'uso termina con successo                                         |

##### Scenario 7.2: #####
|  Scenario 7.2  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | Il prodotto è stato aggiunto al carrello                                   |
|     Step#      |                                Descrizione                                 |
|       1        | L'utente seleziona un prodotto                                             |
|       2        | L'utente seleziona il pulsante rimuovi                                     |
|       3        | L'utente annulla                                                           |
|       4        | Il caso d'uso termina con errore                                           |

### Use case 8, UC8: Rimozione di tutti i prodotti dal carrello ###
| Attori Coinvolti |   Cliente                                                            |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | Il cliente è autenticato                                             |
|  Post condition  | Il prodotto è vuoto                                                  |
| Nominal Scenario | Il cliente rimuove tutti i prodotti dal carrello                     |
|     Variants     |                     nessuna variante                                 |
|    Exceptions    | L'utente annulla: il caso d'uso termina con errore                   |

##### Scenario 8.1: #####
|  Scenario 8.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | Il prodotto è stato rimosso dal carrello                                   |
|     Step#      |                                Descrizione                                 |
|       1        | UC: Visualizzazione prodotti già presenti nel carrello                     |
|       2        | L'utente seleziona il pulsante svuota                                      |
|       3        | L'utente conferma di voler svuotare il carrello                            |
|       4        | Il sistema rimuove tutti i prodotti dal carrello                           |
|       5        | Il caso d'uso termina con successo                                         |

##### Scenario 8.2: #####
|  Scenario 8.2  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | Il prodotto è stato aggiunto al carrello                                   |
|     Step#      |                                Descrizione                                 |
|       1        | L'utente seleziona un prodotto                                             |
|       2        | L'utente seleziona il pulsante svuota                                      |
|       3        | L'utente annulla                                                           |
|       4        | Il caso d'uso termina con errore                                           |

### Use case 9, UC9: Conferma dell'acquisto ###
| Attori Coinvolti |   Cliente                                                            |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | Il cliente è autenticato                                             |
|  Post condition  | Il prodotto è vuoto                                                  |
| Nominal Scenario | Il cliente rimuove tutti i prodotti dal carrello                     |
|     Variants     |                     nessuna variante                                 |
|    Exceptions    | L'utente annulla: il caso d'uso termina con errore                   |

##### Scenario 9.1: #####
|  Scenario 9.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | L'ordine è stato confermato                                                |
|     Step#      |                                Descrizione                                 |
|       1        | UC: Visualizzazione prodotti già presenti nel carrello                     |
|       2        | L'utente seleziona il pulsante acquista                                    |
|       3        | L'utente conferma di voler acquistare i prodotti nel carrello              |
|       4        | Il sistema registra l'ordine                                               |
|       5        | Il sistema svuota il carrello                                              |
|       6        | Il caso d'uso termina con successo                                         |

##### Scenario 9.1: #####
|  Scenario 9.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | L'ordine è stato confermato                                                |
|     Step#      |                                Descrizione                                 |
|       1        | UC: Visualizzazione prodotti già presenti nel carrello                     |
|       2        | L'utente seleziona il pulsante acquista                                    |
|       3        | L'utente annulla                                                           |
|       6        | Il caso d'uso termina con errore                                           |

# Glossario

- Manager: utente autorizzatto all'applicazione che gestisce i prodotti all'interno del sistema.
- Pannello di amministrazione: interfaccia dell'applicazione riservata al manager.
- Customer/Cliente: utente registrato nell'applicazione che può effettuare acquisti nel sistema.
- Prodotto: articolo visibile sul sito e dispondibile per l'acquisto.
- Carrello: contenitore di articoli da acquistare.
- Autenticazione: processo di verifica dell'identità dell'utente.
- Database dei prodotti: archivio di dati contenente informazioni relativi ai prodotti.
- Database degli utenti: archivio di dati contenente informazioni relative agli utenti.
- Database degli ordini: archivio di dati contenente informazioni relative agli acquisti, mette in relazione prodotti e utenti.
- Sito web dedicato: piattaforma online che ospita l'applicazione.



# System Design

![System Design .png](Files/system_design.png)

# Deployment Diagram

![deployment diagram .png](Files/deployment_diagram.png)
