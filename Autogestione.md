# Autogestione
A cura di:  
Emanuele Canazza 

**Attività:** A meno di variazioni per impossibilità a preparare o utilizzare gli strumenti e i laboratori, l'ordine di esposizione sarà:

0. Presentazioni, setup, saluti fnali (10 minuti)
1. [Phishing (10 minuti)](#phishing)
2. [Passwords e Craks (10 minuti)](#passwords-e-craks)
3. [Cattura di pacchetti con connessioni pubbliche (10 minuti)](#cattura-di-pacchetti-con-connessioni-pubbliche)
4. [Buone pratiche (5 - 10 min)](#buone-pratiche)
5. [PC pubblici e Keyloggers (10 minuti)](#pc-pubblici-e-keyloggers)
6. [Rubber ducky (5 minuti)](#rubber-ducky)
7. [Trojan e Ransomware (5 minuti)](#trojan-e-ransomware)
8. [Conclusioni](#conclusioni)


## Phishing

**Strumenti:** [Zphisher](https://github.com/htr-tech/zphisher), eventuale supporto di [Ngrok](https://ngrok.com/)

**Scopo:** Dimostrare attacchi di phishing ingegneria sociale

**Ampliamenti:**
- Worm ILOVEYOU (2000) - uno dei virus più devastanti della storia
- Altri casi famosi di attacchi di ingegneria sociale
- Caratteri simili (es. cirillico o paypal→paypaI/paypa1) con esempi visivi
- Statistiche: oltre il 90% degli attacchi informatici inizia con il phishing
- Spear phishing: attacchi mirati verso specifiche persone/organizzazioni

**Tecniche di contrasto:**
- **Controllare sempre l'URL**: verificare il dominio effettivo, non solo il nome visualizzato
- Email che parlano di accessi sospetti o modifiche non richieste dall'utente
- **HTTPS non è garanzia**: anche i siti di phishing possono avere certificati SSL
- **Regola d'oro**: vai sempre direttamente sul sito digitando l'indirizzo, non cliccare link ricevuti via email/SMS
- Hover sul link (senza cliccare) per vedere la destinazione reale (visto che trova ip questo evita possibile dos/ddos anche se raro per target comuni)
- Verificare mittente email (attenzione ai domini simili: amazon.com vs amazom.com)
- Diffidare di urgenze artificiali ("il tuo account sarà chiuso tra 24 ore!")


## Passwords e Craks

**Strumenti:** [JtR](https://github.com/openwall/john) (John the Ripper), [rockyou.txt](https://weakpass.com/wordlists/rockyou.txt)

**Scopo:** Dimostrare quanto possa essere facile o difficile craccare passwords con brute force o con tool e wordslist.

**Ampliamenti:**
- Il leak del 2009 di RockYou (32 milioni di password in chiaro)
- [Have I Been Pwned](https://haveibeenpwned.com/) - verifica se le tue credenziali sono state compromesse
- Tempo di cracking: password di 8 caratteri solo minuscole = secondi, con maiuscole/numeri/simboli = anni
- Rainbow tables e hash collision
- Attacchi dictionary vs brute force

**Tecniche di contrasto:**
- Password complesse: minimo 12 caratteri con maiuscole, minuscole, numeri e simboli
- **Non riutilizzare mai** la stessa password su più siti
- Usare un **password manager** (Bitwarden, 1Password, KeePass)
- Attivare l'**autenticazione a due fattori (2FA)** ovunque possibile
- Cambiare periodicamente password critiche (email principale, banking)
- Evitare informazioni personali prevedibili (date di nascita, nomi di animali)


## Cattura di pacchetti con connessioni pubbliche

**Strumenti:** [Wireshark](https://www.wireshark.org/), form e backend su localhost o vulnerable docker

**Scopo:** Dimostrare come le reti pubbliche rendano vulnerabili ed esposti i nostri dati

**Ampliamenti:**
- **Man-in-the-Middle (MitM) attacks**: intercettazione e modifica del traffico in tempo reale
- Differenza HTTP vs HTTPS (crittografia end-to-end)
- Sniffing di password in chiaro su reti WiFi pubbliche
- ARP spoofing e DNS poisoning
- Assicurarsi di usare siti che si preoccupino della nostra sicurezza (es. uso di POST invece di GET, HTTPS)

**Tecniche di contrasto:**
- **Non connettersi a reti WiFi sconosciute**, nemmeno se hanno nomi che sembrano affidabili
- Esempio: router con SSID "Paleocapa WiFi" posizionato fuori scuola per intercettare dati di studenti
- Usare una **VPN** quando ci si connette a reti pubbliche
- Verificare sempre che il sito usi HTTPS (lucchetto nella barra indirizzi)
- Disabilitare la connessione automatica a reti WiFi
- Preferire hotspot personale (smartphone) quando possibile


## PC pubblici e Keyloggers

**Strumenti:** Keylogger, VM

**Scopo:** Dimostrare come i PC pubblici o non controllati possano essere usati da malintenzionati per rubare informazioni e credenziali a utenti ignari

**Ampliamenti:**
- Tipologie di keylogger: software vs hardware
- Keylogger hardware: dispositivi USB inseriti tra tastiera e PC
- Spesso vengono installati tramite altri malware (trojan, virus)
- Registrazione di tutto ciò che viene digitato: password, numeri carte di credito, messaggi privati
- Alcuni keylogger avanzati possono fare screenshot periodici

**Tecniche di contrasto:**
- **Evitare PC pubblici** per attività sensibili (banking, email, social). Anche i pc scolastici sono soggetti a questo tipo di attacco
- Se necessario usare PC pubblici: **mai inserire password o dati sensibili**
- Ispezionare fisicamente le porte USB prima di usare il PC
- Usare autenticazione biometrica quando possibile (fingerprint, face ID)
- Tastiere virtuali per inserimento password critiche
- Controllare sempre il task manager per processi sospetti (se hai privilegi)


## Buone pratiche

**Regole generali di sicurezza:**
- **Bloccare sempre il PC** quando ci si allontana (Win+L su Windows, Ctrl+Alt+L su Linux)
- **Logout sempre** dagli account, soprattutto su PC condivisi
- Se ci si dimentica: disconnessione remota disponibile su Google, Facebook, etc.
- **Aggiornamenti regolari**: sistema operativo e software (molte vulnerabilità vengono patchate)
- **Antivirus/antimalware** aggiornato e attivo
- **Backup regolari** dei dati importanti (regola 3-2-1: 3 copie, 2 supporti diversi, 1 offsite)
- **Minimizzare i privilegi**: non usare account amministratore per attività quotidiane
- **Controllo permessi app**: verificare cosa chiedono le applicazioni installate
- **Email aziendale/scolastica**: usarla solo per scopi legittimi, evitare iscrizioni a servizi esterni
- **Social engineering awareness**: diffidare di chiamate/email che richiedono azioni urgenti


## Rubber ducky
**Strumenti:** Immagini e screenshots, eventuale demo device

**Scopo:** Dimostrare come oggetti apparentemente innocui possano essere strumenti per attività malevole

**Ampliamenti:**
- USB Rubber Ducky: si presenta come tastiera USB, esegue script in millisecondi
- **Stuxnet e l'Iran**: il worm che ha sabotato centrifughe nucleari iraniane (2010), diffuso via USB
- Altri attacchi: BadUSB, O.MG Cable (cavo USB malevolo indistinguibile dall'originale)
- Possibili payload: installazione backdoor, furto dati, ransomware deployment
- Social engineering: USB "persi" in parcheggi aziendali con etichette tipo "Stipendi 2024"

**Tecniche di contrasto:**
- **Mai collegare hardware sconosciuto** ai propri dispositivi
- Meglio lasciare per terra una chiavetta da 10 euro che subire le conseguenze di un attacco
- Disabilitare AutoRun/AutoPlay nel sistema operativo
- Usare "USB data blocker" per caricare dispositivi in luoghi pubblici
- Educare dipendenti/studenti sui rischi (spesso l'anello debole è l'utente)
- Policy aziendali: vietare uso di USB personali su PC aziendali


## Trojan e Ransomware

**Strumenti:** Immagini, screenshots, VM e esecuzione

**Scopo:** Dimostrare come programmi scaricati da fonti non ufficial spesso nascondano insidie

**Ampliamenti:**
- **WannaCry (2017)**: ransomware che ha infettato oltre 200.000 computer in 150 paesi
- **Trojan**: si maschera da software legittimo, apre backdoor per altri malware
- **Ransomware**: cripta i file e chiede riscatto in Bitcoin
- Siti di crack/giochi piratati: principale vettore di infezione
- **Cryptolocker, Locky, Petya**: altri ransomware famosi
- Costi: WannaCry ha causato danni stimati in 4 miliardi di dollari

**Tecniche di contrasto:**
- **Scaricare software solo da fonti ufficiali** (store ufficiali, siti verificati)
- Evitare crack, keygen, software piratato (rischio altissimo)
- **Backup offline**: ransomware non può criptare ciò che non è connesso
- Antivirus con protezione real-time
- Non eseguire file .exe ricevuti via email
- Verificare hash/firma digitale per software critico
- Principle of least privilege: limitare permessi amministratore
- **Network segmentation**: separare sistemi critici dalla rete principale


## Conclusioni

**Messaggio finale:**

La sicurezza informatica è un compromesso continuo tra comodità e protezione. Io per primo non rispetto tutte queste regole, ma essendo consapevole di quello che sto facendo cerco di abbassare il più possibile i rischi senza limitarmi eccessivamente.

**Punti chiave:**
- **Non esiste sicurezza al 100%**, ma si possono ridurre drasticamente i rischi
- La maggior parte degli attacchi sfrutta l'**errore umano**, non vulnerabilità tecniche
- **Awareness** è il primo strumento di difesa
- Pensare sempre: "Cosa succederebbe se questo dispositivo/account venisse compromesso?"
- La cybersecurity riguarda **tutti**, non solo esperti IT

**Fonti ufficali dei tool:**
**SI ALLEGANO SOLO A SCOPO DI PRESERVARE I DIRITTI D'AUTORE, NON DEVONO ESSERE IN ALCUN CASO IN AMBIENTI NON CONTROLLATI E SENZA L'AUTORIZZAZIONE DEI PROPRIETARI DEL DISPOSITIVO ATTACCATO**
- [Wireshark](https://www.wireshark.org/)
- [Zphisher](https://github.com/htr-tech/zphisher)
- [Ngrok](https://ngrok.com/)
- [John the Ripper](https://github.com/openwall/john)
- [Rockyou.txt](https://weakpass.com/wordlists/rockyou.txt)
