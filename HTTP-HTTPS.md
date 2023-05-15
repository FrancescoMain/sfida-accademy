## HTTP

### Introduzione

Il protocollo HTTP (Hypertext Transfer Protocol) è il protocollo di base che consente il funzionamento del web. Si tratta di un protocollo a livello applicativo che si basa su un modello client-server. Il client invia una richiesta HTTP al server, il quale risponde con una HTTP response.


Il protocollo HTTP ha tre caratteristiche principali:

 1) Stateless (senza stato): Le richieste e le risposte tra il server e il client sono indipendenti l'una dall'altra, senza alcuna informazione di stato memorizzata. Ciò significa che ogni richiesta viene trattata in modo isolato, senza tenere conto delle richieste precedenti.
 2) Generico: Il protocollo HTTP è in grado di gestire diverse tipologie di risorse, come ad esempio pagine HTML, immagini o qualsiasi altro tipo di risorsa. La risposta del server può essere di qualsiasi tipo, a seconda della richiesta effettuata dal client.
 3) Standard: HTTP è uno standard riconosciuto e indipendente dal tipo di server utilizzato. Non è necessario conoscere i dettagli specifici del server per utilizzare il protocollo HTTP.


#### HTTP 0.9

Nel corso del tempo, il protocollo HTTP è stato ampliato. Nella sua versione 0.9, supportava solo il formato HTML e consentiva solo chiamate GET. Le connessioni non erano persistenti, il che significava che per ogni richiesta di risorsa (dati, immagini, ecc.) veniva aperta e chiusa una connessione separata.

#### HTTP 1.0

Nella versione 1.0, è stato introdotto il concetto di generalità, consentendo l'utilizzo di risorse di diversi tipi, non solo HTML. Sono state aggiunte anche le richieste POST, PUT e HEAD. La richiesta HEAD richiede solo l'header della risorsa, senza il corpo.

#### HTTP 1.1

La versione 1.1 del protocollo HTTP ha introdotto meccanismi di caching per migliorare le prestazioni. Sono state introdotte le connessioni persistenti, che mantengono aperta la connessione per un certo periodo di tempo, invece di aprirne e chiuderne una nuova per ogni richiesta. Sono stati introdotti anche i cookie e l'opzione sicura di HTTP, ovvero HTTPS.

#### HTTP 2.0

La versione 2.0 di HTTP è retrocompatibile con le versioni precedenti, ma utilizza un protocollo binario per il trasferimento delle informazioni. Ciò consente una maggiore efficienza nella trasmissione dei dati. È stato introdotto il concetto di multiplexing, che suddivide una pagina in pacchetti più piccoli e li trasmette utilizzando diversi nodi, a seconda della disponibilità, per poi consentire al client di riassemblare correttamente i pacchetti. Questo rende l'intero processo molto più veloce. Infine, è stata aggiunta la funzionalità di chiamata push.







### REQUEST & RESPONSE

#### REQUEST

Un HTTP request è composto da:

1.  Request line: La linea di richiesta è composta da un metodo, un URL e una versione del protocollo.
    
2.  Header: L'intestazione del messaggio, che contiene campi con il nome del campo e il valore separati da ":". Ad esempio: "NomeCittà: Napoli".
    
3.  Body: Il corpo del messaggio, che può essere presente o assente a seconda della richiesta.
    

##### Metodi

I metodi più comuni sono:

1.  GET: Utilizzato per richiedere una risorsa al server da parte del client.
    
2.  POST: Utilizzato per inviare dati dal client al server. A differenza di GET, POST inserisce i dati nel corpo (body) della richiesta, rendendo più semplice la lettura da parte del server. Questo metodo maschera e rende più sicura la trasmissione dei dati.
    
3.  HEAD: Simile a GET, ma restituisce solo l'intestazione della risposta, senza il corpo.
    
4.  DELETE: Utilizzato per eliminare una risorsa sul server.
    
5.  PUT: Utilizzato per modificare una risorsa sul server.
    
6.  TRACE: Utilizzato per tracciare le varie richieste HTTP lungo il percorso.
    
7.  OPTIONS: Utilizzato per chiedere al server quali metodi il client può utilizzare.
    

##### Campi

I campi più comuni presenti in una HTTP Request sono:

1.  HOST: Campo obbligatorio che contiene il nome dell'host a cui viene fatta la richiesta, ad esempio il dominio di un sito web.
    
2.  USER-AGENT: Contiene la versione del browser o dell'applicazione che il client sta utilizzando.
    
3.  REFERER: Specifica da dove proviene la richiesta, solitamente l'URL della pagina precedente.
    
4.  AUTHORIZATION: Utilizzato per l'autenticazione tramite protocolli specifici (meno comune ora).
    
5.  ACCEPT: Definisce i tipi di media (media types) che il client accetta come risposta.
    
6.  ETAG: Comunica al server la versione della pagina che il browser ha nella cache, consentendo al server di restituire la versione corrispondente per migliorare le prestazioni.
    
7.  CONNECTION: Definisce i parametri della connessione TCP, come la persistenza della connessione.
    

#### RESPONSE

La risposta HTTP è composta da un'intestazione (header) e un corpo (body). Al posto della linea di richiesta (request line), viene utilizzata la linea di stato (status line) che comprende:

1.  Versione: La versione del protocollo HTTP utilizzata dal server.
    
2.  Status: Un codice numerico associato a uno stato o a un errore.
    
3.  Messaggio: Una descrizione verbale dello stato o dell'errore.

##### STATUS

I codici di stato HTTP sono suddivisi in diverse categorie:

1.  1xx (Informazionali): Indica una risposta provvisoria. Questo tipo di risposta significa che il server ha ricevuto la richiesta e sta ancora elaborando. Tuttavia, questi codici non sono più molto comuni a causa dell'efficienza dei server moderni.
    
2.  2xx (Risposte di successo): Indica che la richiesta è stata ricevuta, compresa ed eseguita correttamente dal server.
    
3.  3xx (Risposte di reindirizzamento): Indica che il client deve effettuare un'altra azione per completare la richiesta. Ad esempio, può essere necessario seguire un nuovo URL o effettuare una nuova richiesta con un metodo diverso.
    
4.  4xx (Errori del client): Indica un errore causato dal client. Questi errori possono essere dovuti a una sintassi errata nella richiesta, problemi di autorizzazione o risorse non trovate.
    
5.  5xx (Errori del server): Indica un errore causato dal server. Questo tipo di errore si verifica quando il server riceve correttamente la richiesta, ma non è in grado di elaborarla correttamente o di soddisfare la richiesta.
    

##### Campi

Nell'intestazione (header) di una HTTP response possono essere presenti vari campi. Alcuni dei più comuni sono:

1.  DATE: Indica il momento in cui la risposta è stata inviata dal server.
    
2.  LAST-MODIFIED: Rappresenta il timestamp dell'ultima modifica apportata alla risorsa richiesta.
    
3.  CONTENT-LENGTH: Specifica la lunghezza del corpo (body) della risposta in byte.
    
4.  CONTENT-TYPE: Definisce il tipo di contenuto della risorsa inviata come risposta, ad esempio "text/html" per una pagina HTML o "application/json" per un documento JSON.
    

##### BODY

A differenza della richiesta (request), il corpo (body) è obbligatorio in una risposta HTTP. Il corpo contiene i dati effettivi inviati dal server come risposta alla richiesta del client. Il contenuto del corpo può variare a seconda della natura della risposta e del tipo di risorsa richiesta. Ad esempio, potrebbe essere un documento HTML, un'immagine, un file JSON, ecc.
   







### COOKIE

Il protocollo HTTP è stateless, il che significa che ogni richiesta inviata da un client a un server è indipendente dalle richieste precedenti e successive. Tuttavia, molte applicazioni web richiedono interazioni tra le richieste, come la selezione della lingua o un carrello della spesa che deve rimanere aggiornato anche dopo la chiusura e la riapertura della pagina. Per gestire queste interazioni, viene introdotto il concetto di sessione, che offre una sorta di memoria per evitare la necessità di autenticarsi ad ogni richiesta.

Una delle soluzioni per gestire le sessioni sarebbe stata quella di creare un nuovo protocollo, ma è stato scelto di integrare i cookie come tecnologia. Quando un client invia una nuova richiesta HTTP, il server può includere un cookie nella risposta (HTTP response) utilizzando l'intestazione Set-Cookie. Il browser salva l'ID del cookie nella cache e successivamente può includere l'ID del cookie nelle richieste successive tramite l'intestazione Cookie.

Il campo Set-Cookie nella risposta del server contiene un numero identificativo chiamato session ID. Questo ID viene memorizzato nel browser e viene utilizzato per associare le informazioni specifiche della sessione lato server a quell'ID. Quindi, il server può accedere a queste informazioni quando riceve richieste successive contenenti l'ID del cookie.

I componenti principali per il trattamento dei cookie sono:

1.  Set-Cookie: È creato nella prima risposta del server e inviato al client per impostare il cookie.
    
2.  Cookie: È l'intestazione contenente il cookie che verrà incluso in tutte le richieste successive dopo aver ricevuto il Set-Cookie.
    
3.  File del cookie: È il file memorizzato nel browser che gestisce i cookie lato client.
    
4.  Database: È una raccolta di informazioni gestita dal server e associata all'ID della sessione.
    

Nella prima risposta del server, ci possono essere anche altri campi opzionali:

1.  Domain: Specifica il dominio a cui il cookie è associato.
    
2.  Path: Indica il percorso all'interno del dominio a cui il cookie è collegato.
    
3.  Expires: Indica quando il cookie scadrà.
    
4.  Secure: È un campo booleano che indica se il cookie deve essere inviato solo tramite una connessione HTTPS sicura.
    
5.  HttpOnly: È un altro campo booleano che impedisce l'accesso al cookie tramite JavaScript.


TIPI DI COOKIE

ANONOMIO / SPECIFICO
Anonimo significa che il cookie viene generato dal server e viene restituito alla response senza nessun tipo di autenticazione da parte dell'utente.
Specifico invece al contrario viene collegato il cookie ad un account preciso.

SESSIONE / PERSISTENTE
Sessione sono  i cookie che vengono cancellati alla chiusura del browser.
Persistenti invece che persistono alla chiusura del bworser.

FIRST-PARTY / THIRD-PARTY
Quelli prime parti sono i cookie appartenenti al sito che sto visitando.
Quelli terze parti sono cookie che entrano in gioco all'interno di un dominio che non è quello che ha generato i cookie, ad esempio sono presenti nei banner publicitari, infatti questi cookie sono quelli che recano più problemi a livello di sicurezza.


## HTTPS

HTTPS (HyperText Transfer Protocol Secure) è un protocollo utilizzato per la comunicazione sicura attraverso Internet. È una versione sicura del protocollo HTTP (Hypertext Transfer Protocol).

La principale differenza tra HTTP e HTTPS è che HTTPS utilizza una connessione crittografata tramite crittografia asimmetrica, fornita da protocolli come Transport Layer Security (TLS) o Secure Sockets Layer (SSL). Ciò garantisce una serie di vantaggi, tra cui:

1.  Autenticazione del sito web visitato: HTTPS conferma l'identità del sito web a cui ci si connette, consentendo agli utenti di verificare che stiano comunicando con il sito desiderato e non con un sito falso o compromesso.
    
2.  Protezione della privacy: HTTPS crittografa i dati scambiati tra il browser dell'utente e il sito web, proteggendo così la riservatezza delle informazioni personali, come le credenziali di accesso, i dati di pagamento e altre informazioni sensibili.
    
3.  Integrità dei dati: HTTPS assicura l'integrità dei dati durante la trasmissione, impedendo la manipolazione o l'alterazione dei dati da parte di terzi non autorizzati.
    

Questo protocollo si adatta benissimo al HTTP perch'è fa in modo che basta che solo una delle due parti sia autorizzata, come succede il più delle volte essendo solo il server protetto da HTTPS.





