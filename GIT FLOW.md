
## INSTALLAZIONE

Git flow è un idea astradda di un flusso di lavoro di GIT.
Per installarlo su una nuova macchina osx bisogna lanaciare da terminale i seguenti comandi

```shell
brew install git-flow
```

invece su microsot bisogna  [scaricare e installare git-flow](https://git-scm.com/download/win).

## QUICK START

Dopodichè bisogna usarlo nel progetto eseegendo

```shell
git flow init
```


![[Schermata 2023-05-16 alle 09.54.18 AM.png]]

Come in foto invece di un singolo main ne avremo due, uno dedicato alle relase ufficiali e invece l'altro dedicato alle implementazioni di funzionalità lato sviluppo.
Il primo passo infatti consisste nel integrare il branch main con un branch develop, possiamo semplificare il tutto con i comandi dell'estensione git flow

```shell
git flow init
```

## NEW FUTURE

![[Schermata 2023-05-16 alle 09.59.25 AM.png]]

Come si nota dallo schema le nuove feature avranno per ognuno un branch a sè che una volta terminato non verrà mergato nel main ma nel branch di develop

se usiamo l'estensione di git-flow il processo di creazionie di una nuova future può essere semplificato col comando

```shell 
git flow feature start nomefeature
```

e alla fine del lavoro sulla future sempre utilizzando l'estensione il comando di riferimento è 

```shell
git flow feature finish feature_branch
```

## RELEASE


![[Schermata 2023-05-16 alle 10.07.56 AM.png]]

Una volta raggiunta una vesione di develop pronta per la relase bisogna creare un fork di un branch relase da develop.
La creazione di questo branch avvia il ciclo di rlascio successivo, pertanto non è possibile aggiungere nuove dunzioni e devono essrere inserite solo correzioni di bug, la creazione di documentazioni e task relative al rilascio
Quando è tutto pronto si fa un merge del branch relase in main e il branch viene contrassegnato con un numero di versione.
Inoltre dovrebbe essere eseguito nuoveamente il merge in develop che nel rgattempo potrebbe essere avanazato dall'inizio del rilascio.
git flow ci viene in aiuto coi comandi
```shell
git flow release start 0.1.0
Switched to a new branch 'release/0.1.0'
```

Una volta che il rilascio è pronto ne verrà eseguito il merge in main e in develop e relase verrà eliminato. 
Per terminare la relase usiamo 

```shell
git flow release finish '0.1.0'
```

## HOTFIX
![[Schermata 2023-05-16 alle 10.17.03 AM.png]]
i branch di manutenzione vengono utilizzati per rilasciare rapidamente patch di correzione. 

```shell
git flow hotfix start hotfix_branch

```

```shell
git flow hotfix finish hotfix_branch
```
