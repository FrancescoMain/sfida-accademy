Rest è un acronimo di REPRESENTATIONAL STATE TRANSFER.

Rest è un approccio architetturale alla creazione di WEB API basate sul protocollo HTTP, che tenga conto delle seguenti caratteristiche:

1) Risorse accessibli tramie Endpoint URL
2) Utilizzo del formato JSON o XML
3) Senza stato (stateless, come HTTP)
4) Impiego dei principali meotdi HTTP

Aggiungendosi alle altre caratteristiche fondamentali del protocollo HTTP e non ovvero:
1) Un sistema Client- Server fatto di richieste e risposte.
2) Riposte che siano Cacheable in modo da migliorare le prestazioni.
3) Layared system, faendo in modo che più server possano gestire varie aree di un solo sito, creando il sistema in microservizi.
   
DA CHAT GPT

Una REST API (Application Programming Interface) è un insieme di regole e convenzioni che consentono a due sistemi software di comunicare tra loro attraverso il protocollo HTTP (Hypertext Transfer Protocol). La REST (Representational State Transfer) è un'architettura software che definisce un insieme di principi per la progettazione di servizi web scalabili, leggeri e orientati alle risorse.

Le REST API sono basate sul concetto di risorse, che possono essere oggetti, dati o funzionalità offerti da un sistema. Ogni risorsa è univocamente identificata da un URL (Uniform Resource Locator) e può essere manipolata utilizzando i metodi standard del protocollo HTTP, come GET, POST, PUT, DELETE, tra gli altri.

I principi fondamentali delle REST API includono:

1.  Architettura client-server: I sistemi sono organizzati in una struttura client-server, in cui il client è responsabile dell'interazione con l'utente e la richiesta di servizi, mentre il server gestisce le richieste e fornisce le risorse.
    
2.  Stateless (senza stato): Ogni richiesta del client al server deve contenere tutte le informazioni necessarie per comprenderla. Il server non deve mantenere lo stato della sessione tra le richieste del client. Ogni richiesta viene elaborata in modo indipendente dalle precedenti.
    
3.  Utilizzo dei metodi HTTP: I metodi HTTP, come GET, POST, PUT e DELETE, vengono utilizzati per specificare l'azione che il client desidera eseguire sulla risorsa. Ad esempio, GET viene utilizzato per recuperare una risorsa, POST per creare una nuova risorsa, PUT per aggiornarne una esistente e DELETE per eliminarla.
    
4.  Rappresentazione delle risorse: Le risorse sono rappresentate in un formato specifico, spesso JSON (JavaScript Object Notation) o XML (eXtensible Markup Language), che viene utilizzato per trasmettere i dati tra client e server. Il client può richiedere una rappresentazione specifica di una risorsa utilizzando header o parametri nella richiesta.
    
5.  Hypermedia come motore dello stato dell'applicazione (HATEOAS): Le risorse possono contenere collegamenti ipertestuali (hyperlinks) che consentono ai client di scoprire e navigare verso altre risorse correlate. Questo rende le REST API altamente discoverable e flessibili.
    

Le REST API sono ampiamente utilizzate per creare servizi web che possono essere consumati da diverse piattaforme e dispositivi. Grazie alla loro natura basata su standard aperti come HTTP e JSON, le REST API offrono una soluzione flessibile per l'integrazione tra sistemi eterogenei e la creazione di applicazioni distribuite e scalabili.