# Gestionale cantieri per imprese edili

Il codice di questo progetto è privato perché è un prodotto che vendo. Qui racconto cosa fa, come è costruito e come
l'ho verificato.

## Cosa fa

È un'applicazione web pensata per le piccole imprese edili. Tiene insieme i cantieri, i preventivi con gli incassi, i
rapportini giornalieri con ore e firma, le spese di ogni cantiere e un portale dove il cliente dell'impresa vede lo
stato dei lavori. Ogni persona entra con il suo ruolo (titolare, ufficio, capocantiere) e vede solo quello che le
compete.

## Come è costruito

React e TypeScript per l'interfaccia, Supabase con PostgreSQL per i dati, Cloudflare per la pubblicazione. Ogni
impresa ha la sua installazione separata: i dati di un'impresa non stanno mai nello stesso database di un'altra.

## Come l'ho verificato

- 279 test automatici.
- Prima di ogni commit girano il controllo dei segreti, il lint, il controllo dei tipi, i test dell'app e quelli del
  database.
- Uno script ricostruisce il database da zero e prova, con ogni ruolo, a leggere e modificare dati che non gli
  spettano. Il risultato deve essere zero falle, altrimenti il lavoro non va avanti.
- Un audit di sicurezza finale su permessi e dati.

## Come ci ho lavorato

Specifiche scritte prima del codice, con i casi limite. Il codice lo genera Claude Code, un compito alla volta; io lo
dirigo, lo controllo con i test e lo faccio rivedere da un secondo agente prima del collaudo.

## Stato

Completo, non ancora in uso presso un cliente.
