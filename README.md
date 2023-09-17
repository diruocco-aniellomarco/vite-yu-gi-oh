**Traccia:**

Continuate a lavorare nella stessa repo di ieri e aggiungete un componente per filtrare le carte di gioco. Procedete in ordine e con calma.
Qui ci sono le slides su emit e computed.

---

**Milestone 1:**
Create un componente BaseSelect per filtrare i risultati in base all’archetipo.
Le option della select devono essere popolate dinamicamente chiamando questo endpoint dell'api:
https://db.ygoprodeck.com/api/v7/archetypes.php

Consigli per la M1:

- Testare la chiamata dell'API con PostMan
- Verificare la struttura dati
- Implementare la chiamata Axios all'API
- Verificare che il componente BaseSelect riceva correttamente l'array di archetipi
- Stampare gli archetipi nelle option della select

---

**Milestone 2:**
Quando l'utente seleziona un valore dalla lista, viene effettuata una chiamata alle API con l'archetipo selezionato

Consigli per la M2:

- Collegare la select ai data
- Verificare che i data siano reattivi al cambio della select
- Emettere un custom event per il genitore di BaseSelect passando come parametro il valore della select
- Sul genitore ascoltare e gestire l'evento customizzato
- Costruire l'url dell'API con il parametro del filtro (verificare che l'url sia corretto)
- Chiamare l'url appena costruito e aggiornare i risultati

---

**Bonus:**

Creare un componente che mostri il numero totale di risultati ottenuti.
