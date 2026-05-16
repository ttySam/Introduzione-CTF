# Capture The Flag (CTF) -  RubaBandiera

## Introduzione

### Che cos'è una CTF?

Una Capture The Flag, abbreviata in CTF, è una competizione di hacking che consiste in vari tipi di prove che però hanno un obiettivo comune: trovare una "flag" per segnare dei punti.
La logica è quella del classico gioco del rubabandiera, entro in territorio nemico e cerco di ritornare alla mia base con la bandiera rubata.

### Chi può giocarci?

Secondo me chiunque può giocarci, ce ne sono di varie difficoltà, e comunque sono utili a sviluppare ragionamento logico e la capacità di risolvere problemi.

### Quindi posso giocarci anche se non so proprio niente?

E' innegabile che avere conoscenze informatiche (di cui parleremo dopo) è molto utile, ma tutto sommato direi di sì!<br>
Alcune prove in realtà non necessitano di grandi conoscenze informatica, e comunque penso sia utile capire di prima mano come funzionano queste competizioni per capire quali competenze acquisire.

### Formato di una flag

Il formato varia molto, chi indice la competizione sceglie il formato, che però segue dei pattern di convenzione.<br>
Solitamente il formato consiste in *sigla organizzatori* + *contenuto della flag racchiuso in parentesi graffe*.<br>
Quindi se io dovessi creare una CTF, il formato protebbe essere questo:

```CTF
ttySam{sono_una_flag}
```

## Siti utili

### Allenamento CTF

Ci sono vari siti per potersi allenare sulle CTF, qui ve ne suggerisco un paio:

- **[CyLab Academy](https://cylabacademy.org):** Precedentemente noto come picoCTF, è un siito creato apposta per allenarsi per partecipare alle CTF, completamente gratuito.
- **[TryHackMe](https://tryhackme.com):** Sito che tratta un po' tutte e tematiche della sicurezza informatica, in parte gratuito ma molte stanze sono disponibili su abbonamento
- **[HackTheBox](https://academy.hackthebox.com):** Molto simile a TryHackMe ma con un'impostazione un po' diversa, anche lui in parte gratuito con possibilità di sottoscrivere un abbonamento

### Partecipazione a CTF

- **[CTFtime](https://ctftime.org):** Questo è *il* sito su cui bisogna iscriversi.
E' un archivio di CTF, qui vengono annunciate la maggior parte delle CTF, e ce ne sono praticamente ogni giorno. <br>
Da qui potrete iscrivere la vostra squadra, annunciare la vostra volontà di participare alle CTF, e alla fine di ogni competizione si aggiornerà il contatore dei punti della vostra squadra.

## Categorie CTF

Le CTF hanno al loro interno prove che appartengono a diverse categorie:

- **MISC:** Da Miscellanous, ovvero *misto*, queste sono prove un po' più generiche che variano molto in base all'evento. Sono solitamente quelle più facili e possono far parte di una qualsiasi delle altre sottocategorie.
- **Web Exploitation:** Questo tipo di prova ci mette a disposizione un sito web, un server, o un web app con delle vulnerabilità che dobbiamo sfruttare per ottenere una *flag*
- **Cryptography:** Prove che vogliono testare le vostre conoscenze e competenze del mondo della crittografia.
Quindi serve conoscere concetti come chiavi *simmetriche* e *asimmetriche*, algoritmi di hashing, algoritmi di creazione e scambio di chiavi come *Diffie-Hellman*, e così via.
- **Forensics:** Prove di analisi su file, dischi, oggetti che nascondono al loro interno le nostre tanto ricercate *flag*
- **Reverse Engineering:** Ci viene presentato un programma, come può essere un programma Python di cui quindi possiamo vedere il codice sorgente, oppure un eseguibile, che quindi dovremo decompilare per scoprire qual è il suo funzionamento.
- **PWN/Binary Exploitation:** Questo tipo di prove, che sono tra quelle più difficili, è molto simile al Reverse Engineering, ma con la differenza che qui dobbiamo abusare e sfruttare una falla nel programma. Dovremo quindi sfruttare dei bug per modificare il normale funzionamento del programma.<br>**ES.** sfruttare buffer overflow, segmentation fault, ecc...
- **OSINT:** *Open Source Intelligente*, il tipo di prove che forse amo di più. Ci viene presentata una foto, un nome, uno username e attraverso vari strumenti di OSINT dovremo cercare di trovare coordinate GPS, città, nomi di aziende che ci serviranno a comporre la nostra *flag*.
