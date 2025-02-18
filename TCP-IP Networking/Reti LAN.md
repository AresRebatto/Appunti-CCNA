# Reti LAN

Di seguito parleremo di LAN e della loro realizzazione fisica con i rispettivi standard.

LAN sta per **Local Area Network** e si riferisce a reti di piccole dimensioni. Al suo interno distinguiamo altre due categorie legate alla dimensione della rete:

- **Small Office/Home Office(SOHO) LAN**: di compone di una decina di device collegati o a uno switch o direttamente a router, che consente di collegare la nostra SOHO LAN alla **Wide Area Network(WAN)**, ovvero, sostanzialmente, a internet. Molto spesso possiamo trovare anche un router che però ha 4 o 8 porte per permettergli di fare da switch in un'**Ethernet LAN**(con questo termine si fa riferimento a una rete che mischia dispositivi degli utenti, switch e differenti tipi di cavi per collegare tra loro gli host).
  Oggi le SOHO LAN supportano anche le connessioni con delle **wireless LAN**, descritte, come detto in passato, **dall'IEEE 802.11**, che fanno uso degli **Access Point** per far connettere i dispositivi come se fosse uno switch, ma comunicando con onde radio.
- **Enterprise LAN**: le esigenze di questo tipo di LAN sono molto simili alle SOHO LAN, ma su scala molto maggiore: basti pensare che in delle **Enterprise Ethernet LAN** ci sono  una serie di switch dentro a degli armadietti che sono presenti in ogni piano.

I cavi usati per le Ethernet LAN vengono definiti nell'IEEE 802.3 in base alla loro velocità e alla lunghezza massima per cui si possono tirare.

| Velocità | Nome comune         | Nome dello Standard  IEEE(Informale) | Nome dello Standard  IEEE(Formale) | Tipo di cavo, lunghezza massima |
| -------- | ------------------- | ------------------------------------ | ---------------------------------- | ------------------------------- |
| 10Mbps   | Ethernet            | 10BASE-T                             | 802.3                              | Rame, 100 m                     |
| 100Mbps  | Fast Ethernet       | 100BASE-T                            | 802.3u                             | Rame, 100 m                     |
| 1000Mbps | Gigabit Ethernet    | 1000BASE-LX                          | 802.3z                             | Fibra, 5000 m                   |
| 1000Mbps | GigabitEthernet     | 1000BASE-T                           | 802.3ab                            | Rame, 100 m                     |
| 10Gbps   | 10 Gigabit Ethernet | 10GBASE-T                            | 802.3an                            | Rame, 100 m                     |

### Le LAN fisiche con UTP

Di seguito andremo vedere come sono collegati tra loro due host fisicamente mediante i cavi definiti come **Unshielded Twited Pair(UTP)**, di cui standard più comunemente usati sono 10BASE-T(**Ethernet**), 100BASE-T(Fast Ethernet, **FE**) e 1000BASE-T(Gigabit Ethernet, **GE**).

Due dispositivi che comunicano tra di loro seguono alcune regole chiamate **encoding scheme**: il dispositivo che trasmette, modifica il segnale elettrico nel tempo e il ricevente usa le stesse regole per interpretare il messaggio in 0 e 1(Da un segnale **analogico** a un segnale **digitale**). Per esempio il 10BASE-T codifica lo 0 come la transizione fra un voltaggio più alto a uno più basso in 1/10.000.000 di secondi.

E' importante evidenziare come il fatto che i cavi sono attorcigliati tra loro è necessario alla risoluzione di un problema relativo alla trasmissione fisica: le **interferenze elettromagnetiche(EMI)**, che dipendono dal campo elettromagnetico generato dallo scorrimento della corrente all'interno del cavo.

I cavi UTP per il 10BASE-T e il 100BASE-T è composto da **due coppie** di cavi attorcigliati, mentre il 1000BASE-T è composto da **quattro coppie** e entrambi, di solito, hanno ai loro capi dei connettori **RJ-45**, che è un connettore con dentro 8 inserti in cui i cavi possono essere inseriti, chiamati **pin**, che sarà a contatto con la parte in rame del cavo.

Gli switch CISCO supporta tuttavia anche altri tipi di connettori, oltre che includere alcune porte che possono essere modificate in seguito all'acquisto.

Vediamo il confronto tra alcuni connettori nella seguente tabella:

| Caratteristiche         | RJ-45           | GBIC                             | SFP                              | SFP+                             |
| ----------------------- | --------------- | -------------------------------- | -------------------------------- | -------------------------------- |
| **Media fisico**        | Rame(UTP)       | Fibra ottica o rame              | Fibra ottica o rame              | Fibra ottica o rame              |
| **Dimensioni**          | Piccole         | Più grandi                       | Compatto                         | Compatto                         |
| **Velocità supportate** | Fino a 10Gbps   | Fino a un 1Gbps                  | Fino a 4Gbps                     | Funo a 10Gbps                    |
| **Standard supportati** | 10BASE-T        | 1000BASE-T,fibra (1000BASE-LX)   | 1000BASE-T,fibra (1000BASE-LX)   | 1000BASE-T,fibra (1000BASE-LX)   |
| **Distanza massima**    | 100 metri       | Fino a diversi chilometri(fibra) | Fino a diversi chilometri(fibra) | Fino a diversi chilometri(fibra) |
| **Costo**               | Basso           | Medio-alto                       | Medio                            | Medio-alto                       |
| **Usi principali**      | Reti LAN        | Backbone aziendali               | Backbone aziendali               | Backbone aziendali               |
| **Evoluzione**          | Ancora presente | Obsoleto                         | Evoluzione di GBIC               | Evoluzione di SFP                |