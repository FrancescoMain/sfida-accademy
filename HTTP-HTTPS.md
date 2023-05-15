## HTTP

### Introduzione

Il protoccollo http, è il protocollo base del funzionamento del web, esso è un protocollo a livello APPLICATION. 
Il funzionamento si basa su un CLIENT che fa una HTTP REQUEST a un SERVER, 
quest'ultimo manderà una risposta tramite una HTTP RESPONSE al CLIENT.

Esso ha 3 caratteristiche:
 1) STATELESS 
    Ovvero, privo di stato. Quindi le varie richieste fra SERVER e CLIENT sono indipendenti, quindi  in teoria non vengono lasciate tracce delle varie richieste che si susseguono, questo è stato fatto all'epoca per aumentare la velocità.
 2) GENERICO
    Il fatto che sia generico si riferisce alla HTTP RESPONSE, ovvero la risposta può essere di qualsiasi tipo: ovvero un html, un immagine o un'altro tipo di risorsa.
 3) STANDARD
    Ovvero che essendo STANDARDIZZATO non ha bisogno di sapere di che tipo è il server essendo HTTP uno standard indipendente dal server.

#### 0.9

Nel tempo HTTP è stato ampliato, inizialmente supportava solo l'HTML e le chiamate GET e le connessioni non erano persistenti.
Approfondendo il concetto di APPLICATION possiamo dire che il CLIENT per fare una richiesta attraverso il BROWSER va a creare una connessione TSP (ovvero un altro tipo di protocollo), verso il SERVER, in genere sulla porta 80. Una volta che il SERVER accetta questa connessione viene avviata una sessione del protocollo TSP dove all'interno di questa sessione avvengono degli scambi di informazioni col protocollo HTTP. E quindi essendo non persistente veniva aperta e chiusa una sessione per ogni dato/immagine o risorsa che doveva essere caricata.

#### 1.0
In questa versione si aggiunge il concetto di GENERALITA' e quindi non vengono accettate esclusivamente risorse di tipo HTML ma anche di altri generi. E inoltre vengono aggiuntie le richieste POST PUT e HEAD. Quest'ultima richiede solamente il componente HEADER.

#### 1.1
Questa versione implementa i meccanismi di caching che approfondiermo più avanti.
Le connessioni a tempo, o persistenti. Che quindi a differenza di prima invece di aprire e chiudere delle connessioni TSP la sessione rimane aperta per del tempo.
Vengono introdotti i COOKIE e la versione sicura di HTTP, ovvero HTTPS che approfondiremo più tardi.

#### 2.0

Fino alla ultima versione che è retrocompatibile con le precedenti, sfrutta un protocollo binario: ovvero le informazioni vengono trasferite in linguaggio binario e poi trasformate a seconda dell'uso. 
Inoltre è stata aggiunto il MULTIPLEXING, ovvero l'idea di scomporre la pagina in più pacchetti e trasmetterli usando diversi NODI, a seconda della loro disponibilità, per poi lasciare che il CLIENT si occupi di recuperare tutti i pacchetti e riassemblarli nel modo corretto.
Questo rende tutto il processo molto più veloce.
Infine viene aggiunta anche la chiamata PUSH.






### REQUEST &  RESPONDE

#### REQUEST

Un HTTP request formata da 
1) Request line
   Composta da un metoto, un URL e una versione.
2) Header 
   Ovvero l'intestazione del messaggio, composta da il NOME del campo e il valore suddivisi da :
   esempio: nomeCittà:Napoli
3) Body
   Ovvero il corpo del messaggio, sempre che ci sia.

##### Metodi

I metodi sono:
1) Get
   Permette di richiedere una risorsa da parte del CLIENT nei confronti del SERVER
2) Post
   Post invece viene utilizzata per inviare dei dati dal CLIENT al SERVER, a differenza di GET, POST inserisce i dati da mandare al SERVER nel BODY, e non nell'HEAD, rendendo al SERVER più semplice la lettura. Mascherando e rendendo anche più sicura la trasmissione di dati.
4) Head
   una specie di GET che da in risposta solo l'intestazione
5) Delete
   Viene utilizzato per eliminare delle risorse nel SERVER
6) Put
   Viene utilizzato per modificare delle risorse nel SERVER
7) Trace
   Viene utilizzata per tracciare le varie REQUEST
9) Option
   Viene utilizzato per chiedere al SERVERE quali metodi il CLIENT può utilizzare

##### CAMPI

I campi più diffusi che possono esserci in una HTTP Request sono

1) HOST
   Un campo obbligatorio che contiene il nome dell'host a cui sto facendo richiesta, esempio il dominio di un sito.
2) USER-AGENT
   Contiene la versione del browser che il client sta usando.
3) REFERER
   Definisce da dove proviene la richiesta.
4) AUTHORIZATION
   Non più utilizzato ma si usava per fare l'AUTH tramite protocollo.
5) ACCEPT
   Definisce il mediatype che voglio ricevere in risposta
6) ETAG
   Fa comunicare al SERVER la versione della pagine che il BROWSER ha nella cache, in modo che se corrispondono visualizzerà quella aumetando le prestazioni.
7) CONNECTION
   Definisce i parametri della connessione TCP,  per esempio se deve essere persistente o meno
   
   


#### RESPONSE

La risposta in questio caso sarà sempre formata da head e body ma invece della Requesta line ci sara la STATUS LINE, formata da:
1) Versione
   La versione HTTP usata dal server
2) Status
   Ci sarà un numero a cui sarà associato un errore o uno stato
3) Messaggio
   Ci sarà la trscrizione a parole dello stato.

#### STATUS

1) 1xx
   Una risposta provvisoria, significa che la risposta è stata ricevuta e il server la sta ancora processando. Ormai non più diffusa avendo server molto veloci.
2) 2xx
   Una riposta positiva, ovvero che la richiesta è stata ricevuta, compresa ed eseguita. 
3) 3xx
   Indica che il client deve effettuare un'altra azione in modo che la richiesta vada a buon fine.
4) 4xx
   Errore da parte del Client,  un errore di sintassi, di autorizzazione ecc.
5) 5xx
   Errore da parte del Server, ovvero che il server ha ricevuto correttemente la richiesta ma non riesce a processarlo correttamente.

#### Campi

Nell'header di una RESPONSE possono esserci vari campi, i più diffisui sono
1) DATE
   Il tempo in cui è stata inviata la riposta
2) LAST-MODIFIES
   Il time stamp dell'ultima modifica
3) CONTENT-LENGTH
   La lunghezza del corpo inviato come risposta
4) CONTENT-TYPE
   Il tipo della risorsa inviata in RESPONSE
   
#### BODY

A differenza della request il Body è obbligatorio.
   





