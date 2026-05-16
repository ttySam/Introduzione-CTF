# Capture The Flag (CTF) -  RubaBandiera

## Sommario

- [Introduzione](https://github.com/ttySam/Introduzion-CTF#Introduzione)
- [Siti utili](https://github.com/ttySam/Introduzione-CTF#siti-utili)
- [Categorie CTF](https://github.com/ttySam/Introduzione-CTF#categorie-ctf)
- [Architetture CPU](https://github.com/ttySam/Introduzione-CTF#architetture-cpu)
- [Sistemi Operativi](https://github.com/ttySam/Introduzione-CTF#sistemi-operativi)
- [Sistema Operativo + Architettura](https://github.com/ttySam/Introduzione-CTF#sistema-operativo--architettura)
- [Scelta sistema operativo](https://github.com/ttySam/Introduzione-CTF#scelta-sistema-operativo)
- [Shell linux](https://github.com/ttySam/Introduzione-CTF#shell-linux)
- [Filesystem Hierarchy Standard](https://github.com/ttySam/Introduzione-CTF#filesystem-hierarchy-standard)
- [Directory di Linux](https://github.com/ttySam/Introduzione-CTF#directory-di-linux)
- [Oggetti su Linux](https://github.com/ttySam/Introduzione-CTF#oggetti-su-linux)
- [Comandi base Linux](https://github.com/ttySam/Introduzione-CTF#comandi-base-linux)
- [Installazione programmi aggiuntivi](https://github.com/ttySam/Introduzione-CTF#installazione-programmi-aggiuntivi)
- [Programmi o siti utili per le CTF](https://github.com/ttySam/Introduzione-CTF#programmi-o-siti-utili-per-le-ctf)

## Introduzione

### Che cos'è una CTF?

Una Capture The Flag, abbreviata in CTF, è una competizione di hacking che consiste in vari tipi di prove che però hanno un obiettivo comune: trovare una "flag" per segnare dei punti.
La logica è quella del classico gioco del rubabandiera, entro in territorio nemico e cerco di ritornare alla mia base con la bandiera rubata.

### Chi può giocarci?

Secondo me chiunque può giocarci, ce ne sono di varie difficoltà, e comunque sono utili a sviluppare ragionamento logico e la capacità di risolvere problemi.

### Quindi posso giocarci anche se non so proprio niente?

E' innegabile che avere conoscenze informatiche (di cui parleremo dopo) è molto utile, ma tutto sommato direi di sì!

Alcune prove in realtà non necessitano di grandi conoscenze informatica, e comunque penso sia utile capire di prima mano come funzionano queste competizioni per capire quali competenze acquisire.

### Formato di una flag

Il formato varia molto, chi indice la competizione sceglie il formato, che però segue dei pattern di convenzione.

Solitamente il formato consiste in *sigla organizzatori* + *contenuto della flag racchiuso in parentesi graffe*.

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
E' un archivio di CTF, qui vengono annunciate la maggior parte delle CTF, e ce ne sono praticamente ogni giorno.

Da qui potrete iscrivere la vostra squadra, annunciare la vostra volontà di participare alle CTF, e alla fine di ogni competizione si aggiornerà il contatore dei punti della vostra squadra.

## Categorie CTF

Le CTF hanno al loro interno prove che appartengono a diverse categorie:

- **Misc:** Da Miscellanous, ovvero *misto*, queste sono prove un po' più generiche che variano molto in base all'evento. Sono solitamente quelle più facili e possono far parte di una qualsiasi delle altre sottocategorie.
- **Web Exploitation:** Questo tipo di prova ci mette a disposizione un sito web, un server, o un web app con delle vulnerabilità che dobbiamo sfruttare per ottenere una *flag*
- **Cryptography:** Prove che vogliono testare le vostre conoscenze e competenze del mondo della crittografia.
Quindi serve conoscere concetti come chiavi *simmetriche* e *asimmetriche*, algoritmi di hashing, algoritmi di creazione e scambio di chiavi come *Diffie-Hellman*, e così via.
- **Forensics:** Prove di analisi su file, dischi, oggetti che nascondono al loro interno le nostre tanto ricercate *flag*
- **Reverse Engineering:** Ci viene presentato un programma, come può essere un programma Python di cui quindi possiamo vedere il codice sorgente, oppure un eseguibile, che quindi dovremo decompilare per scoprire qual è il suo funzionamento.
- **PWN/Binary Exploitation:** Questo tipo di prove, che sono tra quelle più difficili, è molto simile al Reverse Engineering, ma con la differenza che qui dobbiamo abusare e sfruttare una falla nel programma. Dovremo quindi sfruttare dei bug per modificare il normale funzionamento del programma.
**ES.** sfruttare buffer overflow, segmentation fault, ecc...
- **OSINT:** *Open Source Intelligente*, il tipo di prove che forse amo di più. Ci viene presentata una foto, un nome, uno username e attraverso vari strumenti di OSINT dovremo cercare di trovare coordinate GPS, città, nomi di aziende che ci serviranno a comporre la nostra *flag*.

## Architetture CPU

### Architetture 64bit

Per ciò che ci interessa, possiamo dividere i processori in due grandi categorie: *x86-64* e *ARM64*

- **x86-64:** Questa è l'architettura più diffusa nei computer Laptop e Desktop, ed è l'architettura per cui sono sviluppati la maggior parte dei programmi e sistemi operativi che usiamo tutti i giorni.

- **ARM:** Questa invece è l'architettura di tutti i nostri smartphone e dei sistemi integrati come router e dispositivi IoT (Internet of Things). Nei laptop, le CPU ARM più diffuse sono quelle della serie M di Apple.

#### Differenze tra CPU x86-64 e ARM64

- **x86-64** fa parte dell'architettura [CISC](https://it.wikipedia.org/wiki/Complex_instruction_set_computer) (Complex Instruction Set Architecture Computer), che utilizza istruzioni più complesse.
- **ARM64** invece fa parte dell'architettura [RISC](https://it.wikipedia.org/wiki/Reduced_instruction_set_computer) (Reduced Instruction Set Architecture Computer), che come suggerisce il nome utilizza istruzioni più semplici.

#### Perchè ci serve saperlo?

Perchè un programma scritto per x86-64 non funziona su ARM64 e viceversa, e nella quasi totalità dei casi i programmi da analizzare nelle CTF sono scritti per architettura CISC.

## Sistemi operativi

### Famiglie

Ci sono varie famiglie di Sistemi Operativi, ma parlerò solamente di questi 3:

- **Windows:** Quasi sempre gira su x86-64.
- **GNU/Linux:** Ci sono distro sia per x86-64 che per ARM
- **MacOS:** I vecchi modelli usano CPU x86-64, mentre i modelli della serie M sono ARM64

### Differenze Sistemi Operativi

- **GNU/Linux** e **MacOS:** sono entrambi sistemi Unix-like e hanno molti comandi identici, il che può essere utile.
- **Windows:** in genere la sintassi dei comandi è completamente diversa.

## Sistema Operativo + Architettura

Abbiamo visto che un programma scritto per un'architettura può girare solo su quella architettura.
Quindi posso usare PC Windows o un vecchio MacBook per analizzare o far girare i programmi x86-64 che mi trovo davanti in una CTF?

No, perché oltre al tipo di architettura, ogni programma è legato ad un Sistema operativo specifico.
E quindi dovremo fornirci di un sistema Linux x86-64, perché solitamente i programmi da analizzare sono programmi scritti per Linux.

## Scelta sistema operativo

Io consiglio una di queste [distro](https://it.wikipedia.org/wiki/Distribuzione_Linux):

- **Kali Linux:** ha già al suo interno programmi utili per le CTF.
- **Parrot OS:** molto simile a Kali.
- **Debian:** al suo interno non ha tool specializzati, ma può essere utile per crearsi da zero il proprio arsenale.
- **Ubuntu Server:** Leggero perché si tratta di una versione a sola riga di comando (CLI), che per la maggior parte delle occasioni è sufficiente.

### Gestore pacchetti

Queste sono tutte distro che usano apt-get/apt come gestore di pacchetti per installare i programmi che ci serviranno.

```bash
    sudo apt-get update
    sudo apt-get install wireshark
```

## Shell linux

### Che cos'è la shell?

La [shell](https://it.wikipedia.org/wiki/Shell_(informatica)) è la nostra interfaccia con il sistema operativo linux, che nel nostro caso intendiamo come shell CLI, ovvero a riga di comando.
Ci accediamo attraverso il terminale, un programma apposito che a volte viene anche chiamato *Console*.

Esistone varie shell, le più comuni sono [sh](https://it.wikipedia.org/wiki/Bourne_shell), [bash](https://it.wikipedia.org/wiki/Bash) e [zsh](https://it.wikipedia.org/wiki/Zsh).

#### Come capire che shell sto usando?

```bash
echo $0
-zsh # risposta da parte della shell
```

#### In che directory si trova la shell?

```bash
which zsh
/bin/zsh # risposta 
```

## Filesystem Hierarchy Standard

### Che cos'è un filesystem?

Da Wikipedia:

>Un [file system](https://it.wikipedia.org/wiki/File_system) (in acronimo FS) è una struttura dati deputata alla gestione e all'archiviazione dei file su un computer.

### Cos'è il Filesystem Hierarchy Standard quindi?

Sempre da Wikipedia:

> In informatica il [Filesystem Hierarchy Standard](https://it.wikipedia.org/wiki/Filesystem_Hierarchy_Standard) (FHS) è uno standard che definisce le directory principali ed il loro contenuto nel file system dei sistemi operativi Unix-like, tra cui i sistemi Linux.

Ci serve imparare a conoscerlo per sapere in quali directory (cartelle) vengono conservati i vari oggetti su Linux.

## Directory di Linux

Ne nominerò soltanto alcune.

- **/**:     chiamata *root*, è la directory iniziale, la madre di tutte le altre.
  - **/bin**: contiene tutti i programmi essenziali.
  - **/opt**: contiene i programmi aggiuntivi.
  - **/home**: contiene le directories principali di ogni utente.
  - **/root**: la home directory dell'utente *root*, ovvero l'utente amministratore.
  - **/var**: file che variano nel tempo, come i log.
  - **/etc**: contiene i file di configurazione.
  - **/tmp**: contiene file temporanei, che vengono cancellati al riavvio della macchina.
  - **/usr**: gerarchia secondaria.
    - **/usr/bin**: contiene la maggior parte dei programmi eseguibili installati dall'utente.
  - **/proc**: contiene informazioni riguardanti i processi.

## Oggetti su Linux

> Everything is a file

Dentro Linux abbiamo 7 tipi di oggetti (ce ne interessano principalmente 5) e grazie al comando *ls -l* possiamo scoprire a quale tipo di oggetto appartengono i file nella directory dentro cui ci troviamo:

Il primo carattere dell'output di ls -l rappresenta il tipo di oggetto

```console
-rw-r--r--@ 1 ttySam  staff  10340 May 16 16:40 README.md
```

| Tipo di oggetto         | Rappresentazione | Descrizione                                                                  |
| :---------------------- | :--------------- | :--------------------------------------------------------------------------- |
| file                    | -                | File generico, potrebbe essere un .txt, .pdf o un'eseguibile                 |
| directory               | d                | Cartella, può contenere altri oggetti al suo interno                         |
| link simbolico          | l                | Oggetto che punta verso un oggetto che si trova in un'altra posizione        |
| dispositivo a blocchi   | b                | Dispositivi come HDD, SSD, USB                                               |
| dispositivo a caratteri | c                | Dispositivi hardware come tastiere o porte seriali                           |

## Comandi base Linux

Per muoverci all'interno del nostro filesystem avremo bisogni di alcuni comandi base:

| Comando                 | Significato acronimo    | Descrizione                                                                  |
| :---------------------- | :---------------------- | :--------------------------------------------------------------------------- |
| sudo                    | super user do           | Ci dà i privilegi da amministratore, necessari per svolgere alcune azioni    |
| pwd                     | print working directory | Ci mostra la directory corrente                                              |
| ls                      | list                    | Ci mostra gli oggetti all'interno di una directory                           |
| cd                      | change directory        | Ci sposta nella directory indicata                                           |
| cp                      | copy                    | Copia un oggetto                                                             |
| mv                      | move                    | Sposta o rinomina un oggetto                                                 |
| rm                      | remove                  | Elimina un oggetto                                                           |
| cat                     | concatenate             | Usato per stampare a video il contenuto di un file                           |
| man                     | manual                  | Apre la pagina di manuale del comando che gli passiamo                       |
| whoami                  |                         | Ci mostra l'utente corrente                                                  |
| less                    |                         | Stampa a video il contenuto di un file e abilita lo scorrimento "a pagine"   |
| find                    |                         | Cerca un oggetto nel Filesystem                                              |
| echo                    |                         | Scrive sullo standard output ciò che gli passiamo                            |

## Installazione programmi aggiuntivi

Per installare programmi ci sono vari modi, e solitamente ci aiuta la documentazione sul sito del programma che vogliamo scaricare.

### Gestore di pacchetti remoti: nel nostro caso apt-get

Installa un programma attraverso Internet.

```console
sudo apt-get install <nome programma>
```

### Gestore di pacchetti locali: nel nostro caso dpkg

Installa un programma a partire da un pacchetto *.deb* che abbiamo scaricato.

```console
sudo dpkg -i pacchetto-bellissimo-02.4.1.deb
```

### Ultima spiaggia - ./configure && make && make install

In caso di programmi scritti in C possiamo usare questi tre comandi per l'installazione.

Rimando a questa pagina di wikipedia.

[https://en.wikipedia.org/wiki/Configure_script](https://en.wikipedia.org/wiki/Configure_script)

## Programmi o siti utili per le CTF

### Generici

- wget
- curl
- nc
- tar
- gzip, gunzip, bzip2, ecc.
- strings
- nmap
- wireshark

### Web Exploitation

- Burp Suite
- gobuster
- ffuf

### Cryptography

- openssl

### Forensics

- exiftool
- steghide

### Reverse Engineering / pwn

- gdb
- objdump
- xxd
- ghidra
- IDA Pro

### OSINT

- Google Search Engine
- Google Lens
- Google Maps/Earth
- sherlock
- nslookup
- whois
