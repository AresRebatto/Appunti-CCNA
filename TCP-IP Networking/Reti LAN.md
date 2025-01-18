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