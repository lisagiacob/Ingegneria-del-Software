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
### Use case 1, UC1: Creazione Account

| Actors Involved  |  Manager                                                             |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | L'utente non deve essere già registrato                              |
|  Post condition  | L'utente è registrato e autenticato                                  |
| Nominal Scenario | Il manager accede, visualizza i prodotti, modifica le informazioni dei prodotti esistenti oppure aggiunge o elimina prodotti. |
|     Variants     |                      nessuna variante                                |
|    Exceptions    | L'utente annulla: il caso d'uso termina con errore. 
                     L'utente inserisce un username già esistente: il sistema lo avvisa.  |

##### Scenario 1.1: Registrazione e autenticazione dell'utente #####

|  Scenario 1.1  |                                                                                                       |
| :------------: | :---------------------------------------------------------------------------------------------------: |
|  Precondition  | L'utente non deve essere già registrato                                                               |
| Post condition | L'utente è registrato e autenticato                                                                   |
|     Step#      |                          Description                                                                  |
|       1        | L'utente inserisce i dati richiesti (username, nome, cognome, password, ruolo)                        |
|       2        | L'utente conferma i dati inseri                                                                       |
|       3        | Il sistema verifica i dati inseriti                                                                   |
|       4        | Il sistema registra l'utente                                                                          |
|       4        | Il sistema autentica l'utente                                                                         |
|       5        | Il caso d'uso termina con successo                                                                    |

### Use case 2, UC2: Accesso account
| Attori Coinvolti | Cliente                                                                                             |
| :--------------: | :-------------------------------------------------------------------------------------------------: |
|   Precondition   | Il cliente non è autenticato                                                                        |
|  Post condition  | L'utente è autenticato                                                                              |
| Nominal Scenario | Il cliente accede al suo carrello, visualizza gli articoli, aggiunge/rimuove, il sistema aggiorna   |
|     Variants     | Il cliente modifica della quantità di un prodotto / svuota il carrello                              |
|    Exceptions    | Se il cliente non è autenticato viene mostrato un messaggio d'errore                                |

##### Scenario 2.1: Aggiunta di un articolo al carrello
|  Scenario 2.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition | L'aggiunta è andata a buon fine                                            |
|     Step#      |                                Description                                 |
|       1        | Accesso al sito                                                            |
|       2        | Visualizzazione degli articoli                                             |
|       3        | Selezione tasto per aggiungere un prodotto al carrello                     |
|       4        | Conferma dell'inserimento                                                  |

##### Scenario 2.2: Aumentare quantità di un articolo al carrello
|  Scenario 2.2  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato, l'articolo è già nel carrello                    |
| Post condition | L'aggiunta è andato a buon fine                                            |
|     Step#      |                                Description                                 |
|       1        | Accesso al sito                                                            |
|       2        | Visualizzazione degli articoli                                             |
|       3        | Selezione tasto per aumentare la quantità del prodotto nel carrello        |
|       4        | Conferma dell'aumento                                                      |

##### Scenario 2.3: Rimozione di un articolo dal carrelloo
|  Scenario 2.3  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente è autenticato                                                   |
| Post condition |  La rimozione è andata a buon fine                                         |
|     Step#      |                                Description                                 |
|       1        | Accesso alla sezione del carrello del sito                                 |
|       2        | Visualizzazione dei prodotti                                               |
|       3        | Selezione del prodotto da rimuovere dal carrello                           |
|       4        | Conferma della rimozione                                                   |

### Use case 3, UC3: Login 
| Actors Involved  |   Cliente                                                            |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | Il cliente non è autenticato                                         |
|  Post condition  | Il cliente è autenticato                                             |
| Nominal Scenario | Il cliente accede alla sua pagina personale                          |
|     Variants     | Il cliente è già autenticao, credenzili errate                       |
|    Exceptions    | Se il cliente non è autenticato viene mostrato un messaggio d'errore |

##### Scenario 3.1: 
|  Scenario 3.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente non è autenticato                                               |
| Post condition | Il cliente è autenticato                                                   |
|     Step#      |                                Description                                 |
|       1        | Selezione del pulsante login                                               |
|       2        | Compilazione del form di accesso                                           |
|       3        | Selezione pulsante Accedi                                                  |

##### Scenario 3.2: 
|  Scenario 3.2  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente non è autenticato                                               |
| Post condition | Il cliente è autenticato                                                   |
|     Step#      |                                Description                                 |
|       1        | Selezione del pulsante login                                               |
|       2        | Compilazione del form di accesso                                           |
|       3        | Selezione pulsante Accedi                                                  |
|       4        | Warning                                                                    |

### Use case 4, UC3: Registrazione
| Actors Involved  |   Cliente                                                            |
| :--------------: | :------------------------------------------------------------------: |
|   Precondition   | Il cliente non è autenticato                                         |
|  Post condition  | Il cliente è autenticato                                             |
| Nominal Scenario | Il cliente accede o crea la sua pagina personale                     |
|     Variants     | Email già registrata                                                 |
|    Exceptions    | Se il cliente non è autenticato viene mostrato un messaggio d'errore |

##### Scenario 4.1: 
|  Scenario 4.1  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente non è registrato                                                |
| Post condition | Il cliente è autenticato                                                   |
|     Step#      |                                Description                                 |
|       1        | Selezione del pulsante login                                               |
|       2        | Compilazione del form di accesso                                           |
|       3        | email già registrata                                                       |
|       4        | Compilazione form registrazione                                            |
|       5        | Selezione pulsante Registra                                                |

##### Scenario 4.2: 
|  Scenario 4.3  |                                                                            |
| :------------: | :------------------------------------------------------------------------: |
|  Precondition  | Il cliente non è registrato                                                |
| Post condition | Il cliente è autenticato                                                   |
|     Step#      |                                Description                                 |
|       1        | Selezione del pulsante login                                               |
|       2        | Compilazione del form di accesso                                           |
|       3        | Compilazione form registrazione                                            |
|       4        | email già registrata                                                       |
|       5        | Warning                                                                    |

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
