# Codifica dell'informazione

Immaginiamo di avere ricevuto la nostra sequenza di bit. Come facciamo a ricavarne informazioni utili?

Prima di tutto dobbiamo sapere che cosa rappresentano questi bit. Possono rappresentare, ad esempio:
- numeri, es. 1498
- parole, es. "ciao"
- immagini
- filmati

Esamineremo ora alcuni tipi di codifica fondamentali.

## Numeri
Interpretare una sequenza di bit in un numero binario è una operazione che richiede una certa attenzione.

Per i numeri positivi, possiamo fare semplicemente una conversione di base da binario a decimale.

Ad esempio:

    11011 binario --> 27 decimale

Per convertire da binario a decimale, vedi il libro:
 - "Interpretiamo il valore binario con le carte", pag. 25

 > Per i numeri negativi, la situazione è più complessa e si possono usare varie convenzioni. Per questa unità ci concentreremo sui numeri positivi.

## Caratteri alfanumerici
Un altro modo per interpretare una sequenza di bit è come un carattere dell'alfabeto. Per fare questa codifica abbiamo necessariamente bisogno di una tabella che ci dica che lettera, o simbolo, assegnare ad una certa sequenza.

Ad esempio nelle nostre lezioni abbiamo usato una codifica proposta da CSUnplugged, che potete scaricare da [qui](./binary-to-alphabet.pdf).

Vedi pagine 34-35 del libro per approfondimenti.

> La codifica più diffusa per i caratteri dell'alfabeto latino e i simboli base è chiamata [ASCII](https://it.wikipedia.org/wiki/ASCII) (American Standard Code for Information Interchange), ed è stata pubblicata per la prima volta nel 1963. Oggi si usa più comunemente lo standard [Unicode](https://it.wikipedia.org/wiki/Unicode), che include anche i caratteri di tutte le lingue del mondo e le emoji 😉

## Immagini
L'interpretazione di una sequenza di bit in una immagine può essere fatta in una multitudine di modi, anche molto diverse fra loro. Qual'è la migliore? Ovviamente, come sapete bene, la risposta è: dipende dal mio contesto d'uso.

In classe abbiamo visto un tipo particolare di codifica, al quale ad ogni bit viene associato un pixel dell'immagine.

Ad esempio:

    10001
    01010
    00100
    01010
    10001

diventa:

<img src='./reti-internet/cross-alpha.png'>

Se vogliamo una maggiore risoluzione o più colori, dobbiamo necessariamente aumentare il numero di bit. Maggiore è il numero di bit, maggiore è lo spazio che occuperà in memoria, detto anche _peso_ dell'immagine. Non c'è una risoluzione migliore in assoluto, ma ci sono alcune accortezze che dobbiamo tenere a mente. In generale, è bene cercare di avere le immagini più leggere possibili senza danneggiare l'esperienza dell'utente: ad esempio
tutto quello che viaggia sul web ha una risoluzione che va bene per la visualizzazione su schermo, ma non per la stampa o ingrandimenti, per ridurre quanto più possibile i tempi di caricamento della pagina ed il traffico dati. I siti di fotografia invece hanno risoluzioni molto più alte.
