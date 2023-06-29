# NewGenerationDatabases
L'obiettivo di tale progetto è la progettazione del database ZeusPhone utilizzando un'architettura NoSQL. La progettazione della base di dati ZeusPhone è disponibile al seguente [link](https://github.com/ChiaraAmalia/Progetto-Database).

## Da cosa siamo partiti
Siamo partiti da una **Base di dati relazionale** finalizzata alla gestione di un operatore nel settore telecomunicazioni.
Gli obiettivi perseguiti sono:
+ Supporto clienti e gestione dei relativi dati
+ Gestione interna dei dipendenti
+ Memorizzazione dati relativi ad impianti e guasti segnalati

## Requisiti fondamentali
I requisiti che la nostra base di dati deve soddisfare sono:
+ Memorizzazione dati del cliente e relativi contratti, offerte, modem e bollette
+ Memorizzazione dati del dipendente
+ Gestione del meccanismo di segnalazione guasti da parte degli utenti
+ Memorizzazione dati relativi agli impianti e relativi guasti.

## Schema E-R di partenza

<p align="center">
<img src="https://github.com/ChiaraAmalia/NewGenerationDatabases/blob/main/schema_ER.png" height=375></p> 
<p align="center">Schema E-R</p>

## Schema semplificato
Per una migliore progettazione, dallo schema E-R di partenza sono state applicate delle modifiche:
+ L'entita **Modem** è stata rimossa in quanto secondaria ai fini del progetto
+ L'entità **Email** è stata accorpata nell'entità cliente
+ L'entità **Attrezzatura** è stata rimossa in quanto secondaria ai fini del progetto
+ L'entità **Offerta** è stata annidata in **Contratto Cliente**; tale scelta è legata alle operazioni di modifica.

Nella figura sottostante è riportato lo schema E-R semplificato.
<p align="center">
<img src="https://github.com/ChiaraAmalia/NewGenerationDatabases/blob/main/schema_semplificato.png" height=375></p> 
<p align="center">Schema E-R semplificato</p>

## Progettazione degli aggregati
Il processo di valutazione degli aggregati tramite il calcolo delle ridondanze (basato sulle query più frequenti e sui volumi delle varie entità e relazioni) ha portato i seguenti risultati:
+ Informazioni relative al **Cliente** e alla **Bolletta** sono state accorpate nell'entità radice **Contratto Cliente**
+ **Contratto Cliente** e **Guasto** sono rimaste separate
+ **Tecnico** e **Guasto** sono rimaste separate
+ Informazioni relative al **Guasto** sono state annidate nell'entità radice **Impianto**

Di seguito sono riportati gli aggregati di livello 1:

<p align="center">
<img src="https://github.com/ChiaraAmalia/NewGenerationDatabases/blob/main/aggregati_liv1.png" height=375></p> 
<p align="center">Aggregati di livello 1</p>

Di seguito sono riportati gli aggregati finali:

<p align="center">
<img src="https://github.com/ChiaraAmalia/NewGenerationDatabases/blob/main/aggregati_finali.png" height=375></p> 
<p align="center">Aggregati finali</p>

## Rappresentazione degli aggregati
Al fine dei risultati ottenuti, la soluzione ottimale si ottiene considerando:
+ 1° aggregato: costituito da **CONTRATTO CLIENTE**, che al suo interno contiene **CLIENTE**, **BOLLETTA**, **OFFERTA**;
+ 2° aggregato: costituito da **TECNICO**, che al suo interno contiene **CONTRATTO DIPENDENTE**;
+ 3° aggregato: costituito da **IMPIANTO**, che al suo interno contiene **GUASTO**.

È stato adottato **NoAM** come modello di rappresentazione per gli aggregati ed utilizzata la strategia di rappresentazione **ETF**. Il modello **NoAM** è stato poi tradotto in modello **NoSQL**.

## Implementazione
A seguito della fase di progettazione, si è proceduto nell'implementazione del database **NoSQL**:
+ Traduzione del database e dei dati in formato **SQL** in database **NoSQL** mediante **Studio3T**
+ Esecuzione delle query.

Maggiore documentazione e lo sviluppo delle query sono reperibili nella seguente [relazione](https://github.com/ChiaraAmalia/NewGenerationDatabases/blob/main/Progetto_NGDB_2023.pdf).

# Autori

:woman_technologist: [Chiara Amalia Caporusso](https://github.com/ChiaraAmalia) 

:woman_technologist: [Margherita Galeazzi](https://github.com/MargheritaGaleazzi)

:man_technologist: [Alessandro Bedetta](https://github.com/Alessandrob99)

