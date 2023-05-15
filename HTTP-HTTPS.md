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




