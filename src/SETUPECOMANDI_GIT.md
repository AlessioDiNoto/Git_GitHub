# Guida a Git: Installazione, Setup e Comandi di Base

Git è un sistema di controllo di versione distribuito utilizzato per tenere traccia delle modifiche nel codice sorgente durante lo sviluppo software. Ecco una guida che ti aiuterà a installarlo, configurarlo e iniziare a usarlo.

## 1. Come Scaricare Git

### Su Windows:
1. Vai al sito ufficiale di Git: [https://git-scm.com/](https://git-scm.com/).
2. Scarica l'installer per Windows.
3. Esegui l'installer e segui le istruzioni. Durante l'installazione, scegli le opzioni predefinite, che di solito sono quelle raccomandate per la maggior parte degli utenti.

### Su macOS:
1. Puoi usare il package manager Homebrew (se non lo hai, installalo da [https://brew.sh/](https://brew.sh/)):
   ```bash
   brew install git

### Su Linux:
Su distribuzioni basate su Debian (come Ubuntu), puoi usare apt:

sudo apt update
sudo apt install git

Su distribuzioni basate su Red Hat (come Fedora), usa dnf:

sudo dnf install git

# Guida ai Comandi Git

## 1. Configurazione di Git

### Imposta il nome utente
```
git config --global user.name "Il Tuo Nome"
```
- Imposta il nome utente per tutti i repository locali.

### Imposta l'email dell'utente
```
git config --global user.email "tua.email@example.com"
```
- Imposta l'email dell'utente per tutti i repository locali.

### Visualizza la configurazione attuale
```
git config --list
```
- Mostra tutte le configurazioni attuali.

## 2. Creazione e Gestione di un Repository

### Inizializza un repository Git
```
git init
```
- Crea un nuovo repository Git in una directory esistente.

### Clona un repository esistente
```
git clone <url-repository>
```
- Clona un repository remoto nella tua macchina locale.

## 3. Modifiche e Snapshot

### Controlla lo stato del repository
```
git status
```
- Mostra lo stato delle modifiche, inclusi i file tracciati e non tracciati.

### Aggiungi file all'area di staging
```
git add <nome-file>
```
- Aggiunge file specifici all'area di staging.

```
git add .
```
- Aggiunge tutti i file modificati all'area di staging.

### Conferma le modifiche
```
git commit -m "Messaggio di commit"
```
- Registra le modifiche con un messaggio descrittivo.

## 4. Visualizzazione della Cronologia

### Mostra la cronologia dei commit
```
git log
```
- Mostra la cronologia dei commit con dettagli.

```
git log --oneline
```
- Mostra la cronologia dei commit in formato compatto.

## 5. Lavorare con i Branch

### Crea un nuovo branch
```
git branch <nome-branch>
```
- Crea un nuovo branch.

### Cambia branch
```
git checkout <nome-branch>
```
- Passa a un branch specifico.

### Crea e passa a un nuovo branch
```
git checkout -b <nome-branch>
```
- Crea un nuovo branch e passa ad esso.

### Unisci un branch nel branch corrente
```
git merge <nome-branch>
```
- Unisce il branch specificato nel branch corrente.

### Elimina un branch
```
git branch -d <nome-branch>
```
- Elimina un branch locale.

## 6. Aggiornare e Condividere il Lavoro

### Aggiungi un remote
```
git remote add origin <url-repository>
```
- Aggiunge un repository remoto.

### Visualizza i remote configurati
```
git remote -v
```
- Mostra i remote configurati.

### Recupera modifiche da un repository remoto
```
git fetch
```
- Recupera aggiornamenti dal repository remoto.

### Recupera e unisce le modifiche
```
git pull
```
- Recupera e unisce le modifiche dal repository remoto nel branch corrente.

### Invia le modifiche al repository remoto
```
git push origin <nome-branch>
```
- Invia le modifiche al branch remoto specificato.

## 7. Gestione dei Conflitti

### Visualizza i conflitti
- I conflitti devono essere risolti manualmente nei file in conflitto.

### Segna i conflitti come risolti
```
git add <nome-file>
```
- Dopo aver risolto un conflitto, aggiungi il file all'area di staging.

## 8. Altri Comandi Utili

### Ignora file con .gitignore
- Crea un file `.gitignore` per specificare i file e le cartelle da ignorare.

### Annulla modifiche
```
git checkout -- <nome-file>
```
- Ripristina le modifiche non tracciate a un file.

### Annulla l'ultimo commit
```
git reset --soft HEAD~1
```
- Annulla l'ultimo commit mantenendo i cambiamenti nell'area di staging.

## 9. Comandi Avanzati

### Stash: salva modifiche temporaneamente
```
git stash
```
- Salva le modifiche temporaneamente e ripristina un'area di lavoro pulita.

```
git stash apply
```
- Applica le modifiche salvate in precedenza.

## Conclusione

Questa guida copre i comandi di base di Git per gestire versioni e collaborazioni efficienti nei progetti software. Per ulteriori informazioni, puoi consultare la [documentazione ufficiale di Git](https://git-scm.com/docs).