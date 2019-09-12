# Protocolli di rete

Finora noi abbiamo trasmesso l'informazione come una sequenza di bit da una macchina all'altra. Questo potrebbe andare abbastanza bene se ci fossero solo due computer, senza nessuna interferenza tra loro. Ma nella realtà ci sono tantissimi computer che comunicano sulla stessa rete, e tantissime interferenze per la strada.

Abbiamo fatto una simulazione della confusione della rete in classe, quando provavate a mandarvi dei messaggi da un banco all'altro, con il professore che faceva da messaggero, ed ogni tanto si perdeva o mischiava i biglietti.
In effetti su Internet è come se due computer parlassero da un lato all'altro della vostra classe.

Per poter comunicare in maniera affidabile è necessario che siano implementati dei meccanismi per assicurarsi che i dati viaggino e arrivino in maniera corretta. Questi meccanismi vengono detti _protocolli di rete_.

[Vint Cerf](https://it.wikipedia.org/wiki/Vint_Cerf) negli anni settanta, insieme Bob Kahn, ha ideato un tipo di protocollo particolarmente efficace, che ha avuto una larghissima diffusione. Questo protocollo si chiama TCP/IP ed è alla base di Internet.

# Divisione dei dati in pacchetti
Per aumentare la probabilità che i dati arrivino a destinazione, si usa prima di tutto una tecnica chiamata "segmentazione dei pacchetti" (packet segmentation, in inglese). In pratica, se i dati da inviare superano una certa dimensione, il nostro computer li spezzetta.

Ipotizziamo di voler inviare questo messaggio:

    CIAOCOMESTAIVINT

Se ogni pacchetto contiene al massimo 6 caratteri, lo dovremo dividere in 3 pacchetti:

     CIAOCO
     MESTAI
     VINT

I pacchetti vengono quindi inviati separatamente e gestiti in maniera indipendente dalla rete. Possono succedere principalmente due cose spiacevoli:
- i pacchetti si mischiano tra di loro
- qualche pacchetto si perde del tutto

> Come fa a perdersi un pacchetto? Ci possono essere varie cause: il traffico nella rete è troppo alto ed alcuni pacchetti vengono buttati, qualche cavo o computer sparso per il mondo si rompe, interferenze elettromagnetiche...

> Tipicamente si dividono i pacchetti hanno una dimensione massima di circa 1500 bytes.

## Numerazione dei pacchetti
Per evitare che i pacchetti arrivino nell'ordine sbagliato, possiamo numerarli. Utilizziamo quindi parte del nostro spazio per scriverci il numero del pacchetto. Quando dall'altra parte il computer riceve un pacchetto, lo mette nell'ordine corretto.

## Richiesta di ritrasmissione
E se qualche pacchetto non arrivasse del tutto? Dobbiamo prevedere un meccanismo per richiedere al mittente un pacchetto perso. Per fare questo dobbiamo sacrificare un'altra parte del nostro spazio, ma ne vale la pena!
