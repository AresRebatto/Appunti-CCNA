# TCP/IP Networking Model
Per la comunicazione tra i computer oggi si usa un modello standard chiamato
TCP/IP, ma un tempo ogni compagnia aveva il proprio modello e i dispositivi
appartenenti a quella specificia compagnia potevano comunicare solo con 
dispositivi della uscenti dalla stessa compagnia, poiché le altre facevano
uso di un altro modello proprietario e di protocolli propri per comunicare
tra loro.

All'inizio degli anni '70, **L'International Organizzation for Standarditation(ISO)**
creò uno standard ciamato **Open System InterconnectionI(OSI)**, in modo da 
permettere la comunicazione tra diversi device in tutto il mondo.

Anche il Dipartimento della Difesa Americano(DoD) aveva cercato di creare un
modello che potesse permette la comunicazione di device prodotti da compagnie
differenti, ma il loro lavoro fu meno formale di quello scolto per OSI, dando la
vita al **TCP/IP**, che divenne la scelta piu' gettonata, in quanto la sua uscita
fu anche in anticipo rispetto a quella di OSI: quando si parla di OSI si parla,
per questo motivo, di **standard de jure**, mentre il TCP/IP divenne lo 
**standard de facto**. <br>
I modelli di networking proprietari continuano a esistere ancora oggi, ma la
maggiorparte sono stati sostituiti da TCP/IP.

TCP/IP definisce un grande quantitativo di protocolli e per farlo usa dei 
documenti chiamati **Request For Comments(RFC)**, tranquillamente reperibili
anche online. <br>
Tuttavia si scelse di non ripetere il lavoro che era gia' stato fatto da altri:
hanno deciso quindi di utilizzare degli standard rilasciati da altre compagnie,
come per essempio **l'Ethernet LAN** definito **dall'Istitute of Eletrical and
Electronic Engineers(IEEE)** e quindi non documentato da un RFC.

Il modello **TCP/IP** separa le proprie funzioni in dei blocchi chiamati **layer**(livelli in Italiano), di quale parte viene implementata anche nei sistemi operativi che usiamo tutti i giorni.

```mermaid
block-beta
columns 1
F["Stack TCP/IP CISCO"]
A["Application Layer"] 
B["Transport Layer"] 
C["Network Layer"] 
D["Data Link"] 
E["Physical"]
style F fill:#fff,stroke:#fff
```

Vediamo qui un esempio di **stack TCP/IP**, ovvero tutti i layer del modello. In realtà per lo scopo del corso, lo stack si compone di 5 layer, che non corrisponde propriamente allo stack TCP/IP reale, che unisce il livello fisico e il data link.

Anche **CISCO Packet Tracer**, il software per simulare le reti che sfrutteremo in futuro, fa uso di questo stack TCP/IP esteso.

### Application Layer

E' il layer più in alto dello stack e i suoi protocolli sono moltissimi e, quindi, il suo funzionamento dipende moltissimo da quello che se ne vuole fare.

Esempi di protocolli dell'Application Layer sono **POP3**, **SMTP** e **HTTP**. Quest'ultimo è quello che viene usato, ad esempio, per la visualizzazione delle pagine web e il funzionamento, a grandi linee, è quello che segue:

```mermaid
sequenceDiagram;
Client ->> Server: Header: GET home.html
Server ->> Client: Header: OK, Body: home.html[Piece 1]
Server ->> Client: Body: home.html[Piece 2]
```

Il funzionamento è abbastanza intuitivo: un client, come potrebbe essere il web browser, manda un messaggio(**request**) al server chiedendo di mandargli la pagina home.html. Il server risponde con una **respond** in cui è contenuto nell'header lo **status code**, ovvero un codice che definisce se è andato tutto correttamente.

Lo status code associato all'OK, quindi tutto riuscito bene, è il 200, mentre, ad esempio, c'è anche il **Not Found** con lo status code **404** che indica che una specifica risorsa richiesta, come può essere una pagina web, non è stata trovata.

La pagina viene inoltre divisa in più segmenti e viene inviata in più messaggi, ma dal secondo messaggio in poi, lo status code viene omesso per alleggerire quanto più possibile il pacchetto.

### Transport Layer

Al di sotto dell'application layer troviamo il **transport layer**, che ha un numero molto limitato di protocolli e i più usati sono solamente due: **TCP(Trasmission Control Protocol)** e **UDP(User Datagram Protocol)**.

Ogni protocollo offre un servizio al protocollo soprastante e uno di quelli offerti dal transport layer è quello di **error-recovery**: permette quindi di riconoscere se è avvenuto qualche errore nella comunicazione tra due host mediante il concetto di **acknowledgments**.

```mermaid
sequenceDiagram;
Server ->> Client: [TCP] SEQ= 1 | Header: OK, Body: home.html[Piece 1]
Server -x Client: [TCP] SEQ= 2 | Body: home.html[Piece 2]
Server ->> Client: [TCP] SEQ= 3 | Body: home.html[Piece 3]
Client ->> Server: [TCP] "Reinvia il 2"
```

Per fornire questo servizio, TCP usa un **numero di sequenza(SEQ)** che indica l'ordine con cui devono essere inviati i pacchetti e se ci si accorge che manca un pacchetto, come in questo caso in cui il pacchetto con sequenza pari a 2, viene perso, allora chi riceve i pacchetti può rendersene conto e richiedere nuovamente il pacchetto che è andato perso per qualsiasi ragione.





