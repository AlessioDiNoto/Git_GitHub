# Guida Iniziale a Git e GitHub

## 1. Cos'è Git

Git è un sistema di controllo versione distribuito che consente di tracciare le modifiche apportate ai file e di gestire il codice sorgente in modo efficiente, collaborativo e sicuro. Git è utilizzato principalmente in progetti di sviluppo software per tenere traccia delle versioni di codice, facilitare la collaborazione tra più sviluppatori e gestire le modifiche in modo strutturato.

## 2. Cos'è un Repository Git

Un **repository Git** (o **repo**) è una directory in cui Git memorizza tutte le modifiche, la cronologia e i riferimenti del progetto. Può essere locale (sul tuo computer) o remoto (su piattaforme come GitHub). Un repository Git contiene anche i **branch**, che sono versioni parallele del codice per permettere lo sviluppo di nuove funzionalità senza interferire con il codice principale.

## 3. Come Installare Git

Per iniziare con Git, devi prima installarlo:

- **Windows**: Scarica il programma di installazione da [git-scm.com](https://git-scm.com/) e segui le istruzioni.
- **Mac**: Puoi installare Git tramite [Homebrew](https://brew.sh/) con il comando `brew install git`, oppure tramite Xcode Command Line Tools.
- **Linux**: Usa il gestore di pacchetti della tua distribuzione, ad esempio su Ubuntu, puoi usare il comando:
  ```bash
  sudo apt-get install git
  ```

Una volta installato, puoi verificare l'installazione aprendo il terminale e digitando:

```bash
git --version
```

## 4. Configurare Git e le Informazioni Utente

Prima di utilizzare Git, è necessario configurare il nome e l'email dell'utente, che saranno associati alle modifiche del codice. Esegui i seguenti comandi nel terminale:

```bash
git config --global user.name "Tuo Nome"
git config --global user.email "tuo@email.com"
```

Questi dati saranno utilizzati per identificare gli autori delle modifiche quando collabori su progetti con altre persone.

## 5. Configurare l’Accesso a GitHub

Per interagire con un repository su **GitHub**, dovrai configurare il tuo accesso. GitHub utilizza chiavi SSH o HTTPS per autentificarti.

### 5.1. Chiavi SSH

1. Genera una chiave SSH con il comando:
   ```bash
   ssh-keygen -t rsa -b 4096 -C "tuo@email.com"
   ```
2. Aggiungi la chiave SSH al tuo agente SSH:
   ```bash
   ssh-add ~/.ssh/id_rsa
   ```
3. Aggiungi la chiave pubblica al tuo account GitHub: copia il contenuto del file `~/.ssh/id_rsa.pub` e incollalo nelle **Impostazioni SSH** su GitHub.

### 5.2. HTTPS

Se preferisci usare HTTPS, dovrai fornire il tuo nome utente e la tua password ogni volta che interagisci con un repository remoto. Puoi configurare un token di accesso per evitare di inserire la password ogni volta.

## 6. Comandi Git per Iniziare

Alcuni comandi di base per interagire con un repository Git:

- **Inizializzare un repository Git**:
  Se non hai ancora un repository, inizializzalo con:

  ```bash
  git init
  ```

  Questo creerà una cartella `.git` che traccia tutte le modifiche.

- **Clonare un repository remoto**:
  Se vuoi lavorare su un repository Git esistente (ad esempio su GitHub), puoi clonarlo con:

  ```bash
  git clone https://github.com/username/repo.git
  ```

- **Verifica lo stato dei file**:
  Per vedere quali file sono stati modificati, usa:

  ```bash
  git status
  ```

- **Aggiungere modifiche all'area di staging**:
  Prima di fare un commit, aggiungi i file modificati:

  ```bash
  git add nome_file
  ```

  Per aggiungere tutti i file modificati:

  ```bash
  git add .
  ```

- **Fare un commit**:
  Per registrare le modifiche nel repository:

  ```bash
  git commit -m "Messaggio del commit"
  ```

- **Visualizzare la cronologia dei commit**:
  Usa:
  ```bash
  git log
  ```

## 7. Git Branch

Un **branch** (ramo) in Git è una versione parallela del progetto. Git permette di creare e lavorare su più branch contemporaneamente, senza influenzare la versione principale (tipicamente chiamata `main` o `master`).

- **Creare un nuovo branch**:
  ```bash
  git branch nome-branch
  ```
- **Passare a un branch esistente**:
  ```bash
  git checkout nome-branch
  ```
  Oppure, per creare e passare a un nuovo branch in un solo comando:
  ```bash
  git checkout -b nome-branch
  ```
- **Visualizzare i branch**:
  ```bash
  git branch
  ```

## 8. Git Commit

Il commit è l'operazione che salva le modifiche nel repository. Ogni commit rappresenta una "foto" del progetto in quel momento, con un messaggio che descrive le modifiche apportate.

- **Fare un commit**:
  ```bash
  git commit -m "Descrizione del commit"
  ```

## 9. Git Merge

Il merge è il processo di combinazione dei cambiamenti provenienti da due branch diversi. Quando lavori su un branch e vuoi unire le modifiche nel branch principale (`main` o `master`), usi il merge.

- **Unire un branch nel branch attuale**:
  Passa al branch in cui vuoi unire le modifiche (di solito il `main`), poi esegui:
  ```bash
  git checkout main
  git merge nome-branch
  ```
  Se ci sono conflitti, Git ti avviserà e dovrai risolverli manualmente nei file.

## 10. GitHub: Push e Pull

Una volta che hai fatto dei commit localmente, puoi inviarli al repository remoto su GitHub.

- **Inviare (push) le modifiche al repository remoto**:

  ```bash
  git push origin nome-branch
  ```

- **Scaricare (pull) le modifiche dal repository remoto**:
  Per aggiornare il tuo repository locale con le modifiche presenti su GitHub:
  ```bash
  git pull origin main
  ```

## 11. Link utili

- Per ulteriori dettagli sul flusso di lavoro e la gestione di repository, consulta il file [GITHUB.md](./src/GITHUB.md).
- Per approfondire la convenzione dei commit in Git, consulta il file [CONVENTIONAL_COMMITS.md](./src/CONVENTIONAL_COMMITS.mdCONVENTIONAL_COMMITS.md).
- Per una guida più dettagliata su come configurare e utilizzare i comandi di Git, consulta il file [COMANDI_GIT.md](./src/COMANDI_GIT.md).
- Per una guida dettagliata sull'utilizzo dei comandi Git, consulta il file SETUPECOMANDI_GIT.md.

## Conclusione

Git è uno strumento fondamentale per il versionamento del codice, e GitHub fornisce un potente servizio di hosting per i repository Git. Imparare i concetti di base di Git—come l’inizializzazione di un repository, l’utilizzo dei branch, il commit e il merge—è essenziale per lavorare in modo collaborativo su progetti software. Con un po’ di pratica, sarai in grado di usare Git con facilità per tracciare, condividere e collaborare sul codice.
