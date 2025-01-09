# Sistema di Gestione Azienda di Pulizia (in elaborazione)

Un'applicazione per la gestione di un'azienda di pulizie, che include il controllo di dipendenti, clienti, lavori e risorse necessarie. Il progetto è sviluppato in **Java**, utilizza **Spring Boot** per il backend e si interfaccia con un database relazionale.

## Funzionalità Principali

- Gestione dei **dipendenti** e dei loro contratti.
- Gestione dei **clienti** e dei loro dettagli.
- Organizzazione e monitoraggio dei **lavori** (assegnazione, stato, risorse utilizzate).
- Gestione degli **indirizzi** per clienti e lavori.
- Integrazione con un database per il salvataggio dei dati persistenti.

## Entità Principali

### Dipendente
Rappresenta un dipendente dell'azienda con i seguenti attributi principali:
- `nome`, `cognome`, `codiceFiscale`, `email`, `telefono`
- `dataAssunzione`, `dataFineContratto`
- `posizione` (es. Addetto Pulizie, Manager)
- `attivo` (indica se il dipendente è attualmente in servizio)

### Cliente
Estende `Dipendente` e rappresenta un cliente, con informazioni condivise come `nome`, `cognome`, e `email`.

### Lavoro
Rappresenta un'attività di pulizia o manutenzione, con i seguenti attributi:
- `nome`, `description`
- `numeroPersonne` richieste per il lavoro
- Stato (`IN_PREPARAZIONE`, `IN_CORSO`, `COMPLETATO`)
- Relazioni con:
  - Cliente
  - Indirizzo
  - Dipendenti
  - Risorse

### Indirizzo
Rappresenta l'indirizzo associato a un cliente o un lavoro, con i seguenti attributi:
- `città`, `via`, `cap`

### Risorsa
Rappresenta materiali o strumenti necessari per i lavori, con:
- `id`, `nome`

## Endpoint API Principali

### Dipendenti
- **GET /api/dipendenti**: Elenco di tutti i dipendenti.
- **POST /api/dipendenti**: Creazione di un nuovo dipendente.
- **GET /api/dipendenti/{id}**: Dettagli di un dipendente specifico.
- **PUT /api/dipendenti/{id}**: Aggiornamento delle informazioni di un dipendente.
- **DELETE /api/dipendenti/{id}**: Eliminazione di un dipendente.

### Clienti
- **GET /api/clienti**: Elenco di tutti i clienti.
- **POST /api/clienti**: Creazione di un nuovo cliente.
- **GET /api/clienti/{id}**: Dettagli di un cliente specifico.

### Lavori
- **GET /api/lavori**: Elenco di tutti i lavori.
- **POST /api/lavori**: Creazione di un nuovo lavoro.
- **PUT /api/lavori/{id}**: Aggiornamento delle informazioni di un lavoro.
- **DELETE /api/lavori/{id}**: Eliminazione di un lavoro.

## Tecnologie Utilizzate

- **Java 17**
- **Spring Boot 3.x**
- **Hibernate/JPA** per l'interazione con il database.
- **PostgreSQL** come database relazionale.
- **H2 Database** per test e sviluppo locale.

