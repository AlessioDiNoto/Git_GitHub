# Messaggi di Commit Convenzionali

## Formati dei Messaggi di Commit

### Tipi

I messaggi di commit devono seguire uno dei seguenti tipi:

- **Modifiche rilevanti per l'API**
  - `feat`: Commit che aggiungono o rimuovono una nuova funzionalità.
  - `fix`: Commit che risolvono un bug.
- **Refactoring del codice**
  - `refactor`: Commit che riscrivono o ristrutturano il codice, ma non cambiano il comportamento dell'API.
  - `perf`: Commit di tipo `refactor` che migliorano le prestazioni.
- **Modifiche di stile**
  - `style`: Commit che non influiscono sul significato del codice (spazi bianchi, formattazione, punto e virgola mancante, ecc.).
- **Test**
  - `test`: Commit che aggiungono test mancanti o correggono test esistenti.
- **Documentazione**
  - `docs`: Commit che riguardano solo la documentazione.
- **Costruzione del progetto**
  - `build`: Commit che riguardano componenti di build come strumenti di build, pipeline CI, dipendenze, versione del progetto, ecc.
- **Operazioni e infrastruttura**
  - `ops`: Commit che riguardano componenti operativi come infrastruttura, distribuzione, backup, recupero, ecc.
- **Miscellanea**
  - `chore`: Commit miscellanei, ad esempio modifiche al file `.gitignore`.

### Scope

Lo **scope** fornisce informazioni contestuali aggiuntive riguardanti il cambiamento.

- È una parte **opzionale** del formato.
- Gli `scope` consentiti dipendono dal progetto specifico.
- Non usare identificatori di issue come scope (ad esempio, `JIRA-1337`).

### Indicatore di Cambiamenti Incompatibili

I cambiamenti incompatibili devono essere indicati con un `!` prima del `:` nella riga dell'oggetto. Ad esempio:

- `feat(api)!: rimuovi l'endpoint di status`
- È una parte **opzionale** del formato.

### Descrizione

La **descrizione** contiene una breve spiegazione del cambiamento.

- È una parte **obbligatoria** del formato.
- Usa l'imperativo al tempo presente: "cambia", non "cambiato" o "cambia".
  - Pensa a `Questo commit farà...` o `Questo commit dovrebbe...`.
- Non maiuscolare la prima lettera.
- Non mettere un punto (`.`) alla fine della descrizione.

### Corpo

Il **corpo** del commit dovrebbe includere la motivazione del cambiamento e mettere in contrasto il comportamento precedente con quello nuovo.

- È una parte **opzionale** del formato.
- Usa l'imperativo al tempo presente: "cambia", non "cambiato" o "cambia".
- Questo è il posto giusto per menzionare identificatori di issue e le loro relazioni.

### Footer

Il **footer** dovrebbe contenere qualsiasi informazione relativa ai **Cambiamenti Incompatibili** ed è anche il posto per **riferire alle Issue** a cui il commit fa riferimento.

- È una parte **opzionale** del formato.
- **Facoltativamente** riferisci un issue tramite il suo ID.
- I **Cambiamenti Incompatibili** dovrebbero iniziare con la parola `BREAKING CHANGES:` seguita da uno spazio o due nuove righe. Il resto del commit sarà usato per questo.

### Esempi

- ```bash
  feat: aggiungi notifiche via email per i nuovi messaggi diretti
  ```
- ```
  feat(carrello): aggiungi il pulsante straordinario
  ```
- ```
  feat!: rimuovi l'endpoint della lista dei ticket

  si riferisce a JIRA-1337

  BREAKING CHANGES: l'endpoint ticket non supporta più la lista di tutte le entità.
  ```

- ```
  fix(carrello): previeni l'ordine di un carrello vuoto
  ```

- ```
  fix(api): correggi il calcolo errato del checksum del corpo della richiesta
  ```

- ```
  fix: aggiungi parametro mancante alla chiamata del servizio
  ```

- ```
  perf: riduci l'uso di memoria per determinare i visitatori unici usando HyperLogLog
  ```
- ```
  build: update dependencies
  ```
- ```
  build(release): bump version to 1.0.0
  ```
- ```
  refactor: implementa il calcolo dei numeri di Fibonacci come ricorsione
  ```

- ```
  style: rimuovi la riga vuota
  ```
