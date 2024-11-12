# Comandi GIT

**clone** : Clona un repository in una nuova directory. quando salvo un lavoro da github di un'altro utnte posso clonare il suo repository sul mio pc, in una cartella di lavoro usando questo comando

\- Esempio: "_**git clone** https://github.com/utente/repository.git_"

**init** : Crea un repository Git vuoto o reinizializza uno esistente in locale e con un nome specifico. In pratica quando creo una cartella di lavoro la devo inizializzare, questo è il primo comando da usare.

\- Esempio: **_git init_**

**status** : Mostra lo stato dell'albero di lavoro, ovvero elenca tutti i file nuovi o modificati. Dopo aver fatto init posso controllare cosa c'è dentro alla mia repository in modo da capire

\- Esempio: **_git status_**

add : Aggiunge i contenuti dei file all'indice. Crea uno snapshot del file in preparazione al versioning. Dopo aver fatto init e status, devo aggiungere i file all'interno della cartella all'indice di lavoro

\- Esempio: "_**git add** nomefile.txt_"

**commit** : Registra le modifiche nel repository. Salva gli snapshot dei file in maniera permanente nello storico. Ogni volta che faccio una modifica al file su cui sto lavorando,(dopo averlo salvato e aggiunto) devo registrare questa modifica usando il comando commit. Con il carattere -m indico una "modifica di gruppo" che aggrega una serie di commit all’interno di un branch, il messaggio va inserito tra virgolette

\- Esempio: _**git commit -m** "Messaggio di commit"_

**git log**: in Git viene utilizzato per visualizzare la cronologia dei commit nel repository. Esso mostra una lista di commit, ordinati in ordine cronologico inverso (dal più recente al più vecchio per impostazione predefinita), con informazioni relative a ciascun commit come autore, data, messaggio di commit e hash del commit.

\-Esempio: **_git log_**

Questo comando visualizzerà la cronologia dei commit nel repository corrente. L'output includerà informazioni su ciascun commit, come l'autore, la data, il messaggio di commit e l'hash del commit. Quando compaiono i due punti nel terminale, per poter uscire dal log, basta scrivere **q**

Puoi personalizzare l'output di git log utilizzando vari opzioni. Alcuni esempi comuni includono:

- _**git log --oneline**_: Visualizza la cronologia dei commit in un formato compatto su una singola linea, mostrando solo l'hash del commit e il messaggio di commit.
- _**git log --graph**_: Visualizza la cronologia dei commit utilizzando un grafo ASCII per mostrare i rami e le fusioni.
- _**git log --author=<autore>**_: Filtra la cronologia dei commit per l'autore specificato.
- _**git log --grep=<pattern>**_: Filtra la cronologia dei commit per i messaggi di commit che corrispondono al pattern specificato.
- _**git log --since=<data>**_: Mostra solo i commit successivi alla data specificata.
- _**git log <file>**_: Mostra solo i commit che hanno coinvolto il file specificato.

\- Esempio: **_git log_**

**branch**: Elenca, crea o elimina branch. In questo caso elenca tutti i branch nel repository corrente

- \- Elenca: _**git branch**_
- \- Crea: _**git branch** \[branch-name\]_
- \- Sposta: _**git switch -c** \[branch-name\]_
- \- Rimuovi: _**git branch -d** \[branch-name\]_
- \- Rinomina (branch locale): _**git branch -m**\[Old-name\]\[New-name\]_

**merge**: Unisce due o più storie di sviluppo.

\- Esempio: _**git merge** \[branch-name\]_

**fetch**: viene utilizzato per scaricare i riferimenti remoti (branch e tag) dal repository remoto nel repository locale. Tuttavia, a differenza di git pull, git fetch non integra automaticamente i cambiamenti scaricati nel branch locale corrente

Esempio: _**git fetch** origin_

**push**: Carica tutti i cambiamenti dal branch locale su GitHub. Dopo aver fatto add e committ, per aggiornare il GitHub, dopo aver creato il collegamento con la repository nel web, uso questo comando per aggiornare la repository online

\- Esempio: **git push origin master**

**pull**: Esegue il fetch e l'integrazione con un altro repository o un branch locale. Combina due azioni in un'unica operazione: _git fetch_ e _git merge_. Ecco cosa fa esattamente git pull:

- _git fetch_: Prima di tutto, git pull esegue un git fetch, che scarica tutti i riferimenti remoti (branch e tag) dal repository remoto nel repository locale. Questo aggiorna il database di oggetti locale con le ultime modifiche dal repository remoto.
- _Aggiornamento dei Riferimenti Remoti_: Durante il fetch, i riferimenti remoti vengono aggiornati nel database di oggetti locale, consentendo a Git di tenere traccia delle modifiche effettuate nel repository remoto.
- _Aggiornamento delle Branch Remote_: Se hai configurato il tracciamento dei branch remoto, git pull aggiorna anche le tue branch remote, aggiornando i puntatori locali delle branch remote con le loro controparti remote.
- _git merge_ (Integrazione Automatica): Dopo il fetch, git pull esegue automaticamente un git merge per integrare i cambiamenti scaricati nel branch locale corrente. Questo può causare una fusione (merge) automatica dei cambiamenti con il branch locale, se non ci sono conflitti.

\- Esempio: _**git pull origin master**_

**checkout** consente di spostarsi tra rami, commit e file nell'albero di lavoro. La sua funzionalità principale è quella di cambiare contesto nel repository Git. Ecco alcuni dei suoi usi principali:

- **Spostarsi tra rami**: Quando si lavora con rami diversi all'interno di un repository Git, git checkout consente di passare da un ramo all'altro. Ad esempio,\*\*

  git checkout nome-ramo

  \*\*ti sposterà sul ramo specificato.

- **Spostarsi tra commit**: Puoi utilizzare git checkout per esplorare lo storico dei commit nel repository. Se conosci l'hash di un commit specifico, puoi scrivere

  **git checkout <hash-commit>**

  per "viaggiare indietro nel tempo" e vedere lo stato del repository a quel determinato commit.

- **Spostarsi tra branch e commit contemporaneamente**: In Git, puoi anche navigare tra rami e commit usando git checkout in combinazione con opzioni specifiche. Ad esempio,

  **git checkout HEAD~2**

  ti sposterà indietro di due commit rispetto al commit corrente, mentre

  **git checkout master~3**

  ti sposterà indietro di tre commit dal ramo master.

- **Ripristinare file modificati**: Se hai apportato delle modifiche a un file e desideri scartarle e tornare allo stato del file nel commit più recente, puoi utilizzare

  **git checkout -- nome-file**

- **Creare nuovi branch**: Puoi anche creare un nuovo ramo e spostarti su di esso contemporaneamente utilizzando

  **git checkout -b nuovo-ramo**

  Questo comando crea un nuovo ramo e commuta su di esso in una sola operazione.

**git remote** in Git è utilizzato per visualizzare, aggiungere e rimuovere repository remoti.

- **git remote**: Questo comando mostra i nomi dei repository remoti attualmente configurati.
- **git remote -v**: Questo comando mostra i nomi dei repository remoti e le rispettive URL. È utile per ottenere una visione dettagliata dei repository remoti configurati.
- **git remote add <nome> <url>**: Questo comando viene utilizzato per aggiungere un nuovo repository remoto. Si specifica un nome per il repository remoto (ad esempio, origin) e l'URL del repository remoto.
- **git remote remove <nome>**;: Questo comando viene utilizzato per rimuovere un repository remoto specificato dal repository locale. Si specifica il nome del repository remoto da rimuovere.
- **git remote rename <nome-vecchio> <nome-nuovo>**: Questo comando viene utilizzato per rinominare un repository remoto esistente. Si specifica il nome del repository remoto esistente che si desidera rinominare e il nuovo nome desiderato.
- **git remote set-url** <nome> <nuova-url>: Questo comando viene utilizzato per modificare l'URL di un repository remoto esistente. Si specifica il nome del repository remoto e la nuova URL.

**git stash** in Git viene utilizzato per temporaneamente salvare le modifiche non commesse nel working directory e nell'area di stage in uno stack di stash. Questo è utile quando si desidera mettere da parte le modifiche attuali per lavorare su un'altra attività, senza la necessità di fare commit delle modifiche parziali. Ecco come funziona git stash:

- _Salvataggio delle modifiche_: Quando esegui git stash, Git salva le modifiche non commesse nel working directory e nell'area di stage in uno stack di stash. Questo include tutte le modifiche non commesse, inclusi i file modificati e i file aggiunti nell'area di stage.
- _Pulizia del working directory_: Dopo aver salvato le modifiche nello stash, Git ripulisce il working directory, lasciandolo pulito come se fosse stato appena clonato o checkout su un altro branch.
- _Utilizzo dello stack di stash_: È possibile salvare più stash nello stack di stash. È anche possibile applicare, elencare, applicare parzialmente, eliminare o popolare gli stash nello stack utilizzando altri comandi git stash come _**git stash apply**_, _**git stash list**_, _**git stash pop**_, _**git stash drop**_, ecc.
- _Ripristino delle modifiche_: In futuro, è possibile ripristinare le modifiche salvate nello stash applicando uno stash utilizzando il comando _**git stash apply**_. Questo riapplicherà le modifiche allo stato del working directory e dell'area di stage.

**git cherry-pick**: in Git viene utilizzato per applicare i cambiamenti specificati di uno o più commit ad un branch diverso da quello in cui sono stati originariamente creati. Questo è utile quando si desidera applicare singoli commit da una branch a un'altra, senza dover unire l'intero branch. Ecco come funziona git cherry-pick:

- _Identificazione del commit_: Prima di eseguire git cherry-pick, è necessario identificare il commit o i commit che si desidera applicare al branch corrente. Puoi utilizzare git log per visualizzare la cronologia dei commit e identificare gli hash dei commit interessati.
- _Esecuzione di git cherry-pick_: Una volta identificati i commit interessati, puoi eseguire git cherry-pick seguito dagli hash dei commit desiderati. Ad esempio:

_**git cherry-pick** <hash-commit>_

- _Applicazione dei cambiamenti_: git cherry-pick applicherà i cambiamenti del commit specificato al branch corrente. Se non ci sono conflitti durante l'applicazione del commit, Git applicherà i cambiamenti e creerà un nuovo commit nel branch corrente con lo stesso contenuto del commit originale.
- _Risoluzione dei conflitti_: Se ci sono conflitti durante l'applicazione del commit, Git metterà in pausa il processo di cherry-pick e richiederà di risolvere manualmente i conflitti. Dovrai risolvere i conflitti, aggiungere i file risolti nell'area di stage e poi completare il cherry-pick utilizzando **git cherry-pick --continue.**
- _Conferma delle modifiche_: Una volta completato con successo il cherry-pick, i cambiamenti del commit saranno applicati al branch corrente e verrà creato un nuovo commit che contiene tali modifiche.

**mv**: Sposta o rinomina un file, una directory o un symlink.

Esempio: _**git mv** vecchio_nome nuovo_nome_

**restore**: Ripristina i file nell'albero di lavoro.

Esempio: _**git restore** nomefile.txt_

**rm**: Rimuove i file dall'albero di lavoro e dall'indice.

Esempio: _**git rm** file_da_rimuovere.txt_

**bisect**: Utilizza la ricerca binaria per trovare il commit che ha introdotto un bug.

Esempio: **git bisect**

**start - diff**: Mostra le modifiche tra i commit, il commit e l'albero di lavoro, ecc.

Esempio: **git diff** HEAD~1

**grep**: Stampa le righe corrispondenti a un pattern.

Esempio: _**git grep** "pattern"_

**show**: Mostra vari tipi di oggetti.

Esempio: _**git show** HEAD_

**rebase**: Riapplica i commit su un'altra punta base.

Esempio: **git rebase master**

**reset**: Resetta HEAD corrente allo stato specificato. Modifica lo stato del repository Git, spostando il branch corrente e/o il puntatore HEAD a un determinato commit

Esempio: _**git reset** --hard HEAD~2_

**tag:** Crea, elenca, elimina o verifica un tag firmato con GPG.

Esempio: _**git tag** -a v1.0 -m "Versione 1.0"_

**git config** in Git viene utilizzato per leggere e modificare le configurazioni di Git a livello globale, a livello di repository e a livello locale (per un singolo progetto). Ecco come viene utilizzato git config:

- _Lettura delle configurazioni:_ Per leggere le configurazioni attualmente impostate, puoi eseguire git config --list. Questo mostrerà tutte le configurazioni Git impostate per il tuo utente, il tuo repository e il progetto locale.
- _Modifica delle configurazioni:_ Per modificare le configurazioni, è possibile utilizzare il comando git config seguito dal nome della configurazione e dal valore desiderato. Ad esempio, per impostare l'indirizzo email associato ai tuoi commit:
  - \_

    git config --global user.email "tuo-indirizzo@email.com"

    \_L'opzione --global indica che la modifica verrà apportata a livello globale per l'utente corrente.
- _Lettura di una configurazione specifica:_ Se desideri leggere il valore di una configurazione specifica, puoi utilizzare il comando git config <nome-configurazione>. Ad esempio, per leggere il tuo indirizzo email configurato:

- _git config user.email_

- _Rimozione di una configurazione:_ Per rimuovere una configurazione, è possibile utilizzare il comando git config --unset seguito dal nome della configurazione. Ad esempio, per rimuovere l'indirizzo email globale:

_git config --global --unset user.email_

**git blame** in Git viene utilizzato per visualizzare chi ha modificato le righe di un file specifico e in quale commit sono state apportate tali modifiche. Questo è utile per tracciare la storia delle modifiche di un file e per identificare l'origine delle modifiche in un repository Git.

\-Esempio: **_git blame <file>_**

Questo comando visualizzerà il contenuto del file specificato con un elenco di tutte le righe, insieme alle informazioni su chi ha modificato ciascuna riga e in quale commit è stata apportata la modifica. L'output includerà l'hash del commit, il nome dell'autore, la data della modifica e il numero di riga.

Puoi anche utilizzare opzioni aggiuntive con git blame per personalizzare l'output o filtrare le informazioni. Ad esempio:

- **_git blame -L <start>,<end>_**: Visualizza solo le modifiche apportate alle righe tra <start> e <end>.
- **_git blame -L <start>,+<numero>_**: Visualizza solo le modifiche apportate alle righe a partire da <start> per il numero specificato di righe.
- **_git blame -e_**: Visualizza l'indirizzo email degli autori invece dei loro nomi.
- **_git blame -C_**: Abilita la ricerca di similitudini per individuare le righe copiate o spostate all'interno del repository.

## Elenco opzioni vari comandi

### git add

- **\-n**, **\--dry-run**: Visualizza le modifiche che verranno aggiunte senza effettivamente eseguire l'aggiunta.
- **\-p**, **\--patch**: Permette di interagire in modo interattivo per aggiungere parti specifiche dei file alle staging area.
- **\-v**, **\--verbose**: Visualizza dettagli aggiuntivi durante l'aggiunta dei file.

### git branch

- **\-a**, **\--all**: Mostra sia i rami remoti che quelli locali.
- **\-d**, **\--delete**: Elimina il ramo specificato.
- **\-D**: Forza l'eliminazione di un ramo, anche se non è completamente fuso.
- **\-m**, **\--move**: Rinomina il ramo specificato.

### git checkout

- **\-b <branch>**, **\--create**: Crea un nuovo ramo **<branch>** e passa a esso.
- **\-f**, **\--force**: Forza lo spostamento di branch anche se ci sono modifiche non salvate.
- **\-m**, **\--merge**: Esegue un merge durante lo switch di branch.

### git clone

- **\--branch <branch>**, **\--single-branch**: Clona solo un singolo ramo.
- **\-b**, **\--branch <branch>**: Clona solo il ramo specificato.

### git commit

- **\-a**, **\--all**: Aggiunge automaticamente tutti i file modificati all'area di staging prima di eseguire il commit.
- **\-m <message>**, **\--message=<message>**: Utilizza il messaggio **<message>** come testo del commit.
- **\--amend**: Modifica l'ultimo commit senza creare un nuovo commit.

### git fetch

- **\--all**: Recupera tutti i rami da tutti i repository remoti.
- **\-p**, **\--prune**: Rimuove i riferimenti ai rami remoti che non esistono più nel repository remoto.

### git merge

- **\--no-ff**: Esegue sempre un commit di merge anche se non è necessario.
- **\--squash**: Unisce i commit in un singolo commit durante il merge.

### git push

- **\-f**, **\--force**: Forza il push, sovrascrivendo i riferimenti remoti.
- **\--all**: Pusha tutti i rami al repository remoto.
- **\--tags**: Pusha tutti i tag al repository remoto.

### git pull

- **\-r**, **\--rebase**: Esegue un rebase anziché un merge durante il pull.
- **\--tags**: Recupera anche i tag dal repository remoto durante il pull.

### git rebase

- **\-i**, **\--interactive**: Esegue un rebase in modalità interattiva.
- **\--onto**: Specifica il punto di partenza per il rebase.

### git reset

- **\--soft**: Riporta i file all'area di staging senza modificare il working directory.
- **\--hard**: Elimina tutte le modifiche non commesse e riporta i file allo stato dell'ultimo commit.

### git rm

- **\-r**: Rimuove ricorsivamente i file e le directory.

### git tag

- **\-a**, **\--annotate**: Crea un tag annotato.
- **\-d**, **\--delete**: Elimina il tag specificato.

### Altre opzioni globali

- **\-v**, **\--version**: Visualizza la versione di Git installata.
- **\-h**, **\--help**: Mostra l'aiuto per un comando specifico di Git.
