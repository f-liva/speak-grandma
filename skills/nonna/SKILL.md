---
name: nonna
description: "Speak Grandma: spiega un sistema, una feature, un'architettura o una decisione tecnica come lo racconteresti a tua nonna — una metafora quotidiana coerente, comportamenti al posto dell'implementazione, schema ASCII nella stessa metafora, morale in una riga. Usala quando l'utente chiede «spiegamelo semplice», «come alla nonna», «senza tecnicismi», «cosa fa in pratica», vuole capire i COMPORTAMENTI di un sistema senza i dettagli di codice, o deve far capire qualcosa di tecnico a una persona non tecnica (cliente, collega, familiare). Trigger: /nonna."
---

# Nonna (Speak Grandma)

Trasforma un sistema tecnico in un racconto che chiunque capisce al primo
ascolto. Il lettore non deve sapere COME è fatto: deve capire COSA fa, QUANDO
si muove da solo e QUANDO viene a cercarlo. I dettagli implementativi (nomi di
funzioni, file, commit, sigle) sono rumore: il valore sta nei comportamenti.

## Perché funziona

Una spiegazione tecnica costringe il lettore a costruirsi il modello mentale da
solo. Una metafora buona GLIELO CONSEGNA già montato: se il daemon è «la
segretaria» e il classificatore è «il capoufficio», ogni regola nuova si
aggancia a un mondo che il lettore conosce da sempre. La comprensione arriva
prima della fine della frase.

## Processo

1. **Capisci davvero, prima di semplificare.** La semplificazione è
   compressione con perdita: puoi permettertela solo se sai esattamente cosa
   stai buttando. Se il sistema non lo conosci a fondo, studialo prima
   (codice, spec, log) — una metafora sbagliata è peggio del tecnichese,
   perché consegna un modello mentale falso.

2. **Scegli UNA metafora portante, dal quotidiano.** Un ufficio, una cucina,
   una bottega, un condominio. Una sola: le metafore mischiate (mezzo ufficio,
   mezzo cantiere) rompono il mondo e il lettore si perde. Prova la metafora
   contro i 3-4 comportamenti più strani del sistema: se uno non ci entra
   naturalmente, cambia metafora, non forzarla.

3. **Mappa gli attori su ruoli umani.** Ogni processo/componente diventa una
   persona o un oggetto del mondo scelto: la segretaria (il daemon), l'aiutante
   (il worker), il capoufficio (il classificatore), il taccuino (il file di
   config), il guardiano (il watchdog), il campanello (la notifica). Usa
   **grassetto** alla prima apparizione di ogni attore. Da lì in poi chiamalo
   SEMPRE con quel nome: la coerenza dei nomi È la mappa.

4. **Racconta comportamenti, mai implementazione.**
   - Sì: «se torna con lo stesso problema, suona il campanello a te».
   - No: «se l'impronta coincide, la guard ritorna C».
   I NUMERI che governano il comportamento restano, concreti: «6 gettoni»,
   «scade dopo 30 giorni», «entro 30 secondi» — i numeri non sono tecnicismi,
   sono le regole della casa.

5. **Le regole come conseguenze, non come feature.** Non «c'è il dedup dei
   gemelli»: ma «se due pratiche dello stesso cliente chiedono lo stesso
   gesto, si ferma e te lo dice — è già successo, con due ticket gemelli».
   Quando puoi, aggancia un aneddoto vero: la prova vissuta vale dieci
   asserzioni.

6. **Schema ASCII nella STESSA metafora.** Box e frecce con i nomi degli
   attori del racconto (CASSANDRA, AIUTANTE, CAPOUFFICIO), non i nomi dei
   moduli. Lo schema è il riassunto visivo del racconto, non un diagramma
   d'architettura travestito. Tienilo sotto ~30 righe e ~70 colonne (deve
   reggere su un telefono). Le annotazioni a margine dello schema sono il
   posto giusto per le regole brevi («budget 6 gettoni · guardiano 30s»).

7. **Chiudi con la morale in una riga.** Un corsivo che condensa tutto:
   *«il campanello suona solo quando c'è da decidere qualcosa che è davvero
   tuo»*. Se non riesci a scriverla, la spiegazione non è ancora matura.

## Cosa resta tecnico (poco, e con criterio)

- I nomi-targhetta che il lettore dovrà USARE: il tasto da premere («R»,
  «F»), il comando da scrivere («/fiducia»), il file da aprire se gli serve.
  Mettili tra parentesi dopo il nome del mondo: «il taccuino della fiducia
  (`/fiducia` su Telegram)».
- Tutto il resto — moduli, funzioni, hash di commit, acronimi — fuori. Se
  un'informazione serve solo a chi metterà le mani nel codice, non è per
  questa spiegazione.

## Tono

Frasi corte. Seconda persona («tu approvi», «ti arriva»). Niente sigle non
sciolte, niente anglismi evitabili (ma i nomi propri dei prodotti restano).
Un filo di calore: la nonna non è stupida, è solo di un altro mestiere — il
tono è quello di chi racconta volentieri, mai di chi banalizza.

## Struttura del risultato

1. Apertura nel mondo della metafora (2-3 frasi che piazzano la scena).
2. Gli attori, in ordine di apparizione nel flusso.
3. I comportamenti nuovi/centrali, ognuno col suo perché.
4. Le protezioni/regole («le catene di sicurezza»), come elenco breve.
5. Lo stato attuale, se rilevante («siamo in scuola guida»).
6. Schema ASCII.
7. Morale in una riga, in corsivo.

Lunghezza: 400-700 parole più lo schema. Oltre, stai spiegando troppo: taglia
i comportamenti secondari, non comprimere lo stile.

## Esempio (estratto reale, sistema di dispatch ticket)

> **Cassandra è la segretaria.** Ogni 3 minuti guarda la posta. Per ogni
> lettera nuova apre una **pratica** e la dà a un **aiutante**, che lavora in
> una **stanzetta separata** così non pasticcia sulla scrivania degli altri.
> [...] Prima di disturbare te, la relazione passa dal **capoufficio**, che
> sceglie fra tre cassetti: **A — «arrangiati»** [...], **D — «si fa e
> basta»** [...], **C — «chiama Federico»**. Nel dubbio, sempre C: il
> capoufficio sbaglia semmai chiedendo troppo, mai facendo troppo.
>
> *Le lettere arrivano da sole, le pratiche si lavorano da sole — e il
> campanello suona solo quando c'è da decidere qualcosa che è davvero tuo.*

Nota come: una sola metafora (ufficio), numeri concreti, il fail-safe spiegato
come carattere del personaggio («sbaglia semmai chiedendo troppo»), zero nomi
di moduli.
