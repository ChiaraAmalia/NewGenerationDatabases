# NewGenerationDatabases
L'obiettivo di tale progetto è la progettazione del database ZeusPhone utilizzando un'architettura NoSQL. La progettazione della base di dati ZeusPhone è disponibile al seguente [Link](https://github.com/ChiaraAmalia/Progetto-Database).

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


