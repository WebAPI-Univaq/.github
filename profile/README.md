# [**Web API**](https://people.disim.univaq.it/~dellapenna/content.php?page=students) course
> Master in Mobile and Web Technology, University of L'Aquila, Italy

![University of L'Aquila](https://www.disim.univaq.it/skins/aqua/img/logo2021-2.png)

---

This repository contains sample code and other didactic material used in the course lectures.
Examples are updated and fixed at least once for every academic year.
The code is organized to best match the lecture topics and examples. It is not intended for production use and is not optimized in any way. 

---

## Suggerimenti per la creazione di uno *spazio di lavoro* per il corso

Nel nostro corso utilizzeremo tre software principali:

- Netbeans (<https://netbeans.apache.org/>), l'IDE per lo sviluppo,
- Tomcat (<https://tomcat.apache.org/>), il web server Java,
- la JDK (<https://openjdk.java.net/>), su cui gireranno entrambi i
 programmi di cui sopra.
 
Inoltre, utilizzeremo
-	Postman (<https://www.postman.com/>) per testare i servizi RESTful
-	Swagger Editor (<https://editor.swagger.io/>) per scrivere in maniera assistita le specifiche OpenAPI
-	SOAPUI (https://www.soapui.org/) per testare i servizi SOAP (ma anche quelli RESTful)
-	Il WSDL Editor (distribuito a lezione) per scrivere in maniera assistita le specifiche WSDL

Purtroppo questi software, soprattutto la JDK, sono soggetti a
continui aggiornamenti, che oltre a correggere problemi e aggiungere
funzionalità possono, talvolta, introdurre bug e incompatibilità
rispetto agli esempi presentati durante il corso, che si basano su una
precisa combinazione di versioni testata e "certificata" *prima*
dell'avvio del corso stesso.

Per ridurre al minimo i problemi, quindi, vi consiglio di **installare
le stesse versioni che vi sono state segnalate all'inizio del corso**
(anche se non sono le ultimissime disponibili). Ancor meglio, vi
consiglio di **creare uno spazio di lavoro "privato" dedicato ai tool
del nostro corso** che sia influenzato il meno possibile dall'assetto
software della macchina su cui lavorerete. Questo è molto utile
soprattutto se sulla vostra macchina avete già installate altre versioni
dei software di cui sopra. La procedura è la seguente.

Le versioni del software utilizzate **per l'anno accademico 2021/22**
sono le seguenti:

- Netbeans 12.6
- Tomcat 10
- JDK 16

**Attenzione**: **Tomcat 9 e Tomcat 10 non possono eseguire le stesse
applicazioni web**: mentre Tomcat 9 utilizza la JEE 8 Web, Tomcat 10 usa
la Jakarta EE 9 Web, il che rende necessario intervenire manualmente
modificando i package di molte classi utilizzate dalle web applications.
Nel corso useremo Tomcat 10.

**Attenzione: La JDK 16 introduce delle novità che rendono incompatibili
alcuni plugin Maven** utilizzati normalmente da Netbeans. Durante il
corso mostreremo come modificare i progetti standard generati dall'IDE
per renderli di nuovo funzionanti. In ogni caso, tutti i progetti messi
online saranno sempre corretti e, essendo basati su Maven, potranno
essere usati come ponto di partenza per le vostre applicazioni, anche su
altri IDE.

*Nota: se siete sufficientemente esperti nell'uso di un altro IDE,
potete utilizzare quello che avete già a disposizione al posto di
Netbeans, ma ovviamente in tal caso dovrete gestire da soli i vari
aspetti di connessione al web server e la corretta configurazione
dell'ambiente.*

### Scaricamento e Installazione del Software

1. **Create una nuova cartella** nella vostra *home utente* (documenti
 per chi usa Windows). Di seguito indicheremo tale cartella con
 "\<D\>" (dove \<D\> è un percorso assoluto, ad esempio
 C:\\Users\\pippo\\Documents\\workspace o /home/pippo/workspace).

2. Nella cartella \<D\> **create tre sotto-cartelle** denominate
 \<D\>/nb_userdir, \<D\>/nb_cachedir e \<D\>/tomcat_base

3. **Scaricate gli archivi zip** (*niente installer!*) della JDK, di
 Netbeans e di Tomcat con le versioni consigliate nel corso. Se non
 si tratta delle ultimissime versioni, potreste doverle prelevare da
 pagine "archivio" come <https://jdk.java.net/archive/>,
 <https://netbeans.apache.org/download/archive/> (o
 <https://netbeans.apache.org/download>) e
 <https://tomcat.apache.org/whichversion.html>.

4. **Espandete gli archivi** nella cartella \<D\>. Otterrete quindi tre
 cartelle, ad esempio (*il nome reale dipenderà dalle versioni*)
 \<D\>/jdk-16-0-1, \<D\>/netbeans-126-bin e
 \<D\>/apache-tomcat-10.0.17.

5. Nella cartella in cui è stato espanso Netbeans, nel nostro esempio
 \<D\>/netbeans-126-bin, troverete il file **etc/netbeans.conf**.
 All'interno di questo file, modificate le chiavi seguenti come
 indicato.\
 Notate che *il path della JDK va definito sulla base della cartella
 in cui è stata effettivamente espansa al punto 4*. Se necessario,
 eliminate il commento (#) prima delle righe contenenti queste chiavi
 per abilitarle. Ricordate di salvare il file netbeans.conf al
 termine delle modifiche.

    a. netbeans_default_userdir=\"\<D\>/nb_userdir\"
    
    b. netbeans_default_cachedir=\"\<D\>/nb_cachedir\"
    
    c. netbeans_jdkhome=\"\<D\>/jdk-16-0-1\"

6.	Potete installare **Postman** globalmente (<https://www.postman.com/downloads/>) oppure, 
se preferite anche in questo caso tenerlo isolato nel vostro spazio di lavoro per il corso, 
scaricate la versione standalone realizzata dal progetto *PortApps* 
(<https://portapps.io/app/postman-portable/#download>)  per il vostro sistema operativo. 
Scegliete la **versione senza installer (archivio 7z)** ed espandetela in all’interno di \<D\>/postman.

7.	Per quel che riguarda lo **Swagger** editor, si tratta di un’applicazione web che 
  potete usare online oppure, se volete, potete clonarla dal repository GitHub per 
  usarla offline. Basterà clonare il repository <https://github.com/swagger-api/swagger-editor> in
  \<D\>/swagger e poi aprire index.html per avviare la vostra copia locale.
  
8.	Potete installare **SOAPUI** (<https://www.soapui.org/downloads/latest-release>) globalmente oppure, 
se preferite, anche in questo caso tenerlo isolato nel vostro spazio di lavoro per il corso,
scaricando la versione standalone **senza installer  (archivio zip)** ed espandetela in all’interno di \<D\>/soapui. 
In quest’ultimo caso, dovrete editare lo script di lancio nella directory bin (**soapui.bat** nella versione Windows) 
impostando la JAVA_HOME su "\<D\>/jdk-16-0-1" (*il path della cartella in cui la JDK è stata effettivamente espansa al punto 4*)

9.	Il **WSDL Editor** vi verrà fornito a lezione. Si tratta di una vecchia applicazione non più distribuita sulla rete, 
ma ancora valida. Data l’età del software, questo non funzionerà con versioni di Java superiori alla 1.8. 
Per questo motivo, nel pacchetto che vi verrà fornito sono presenti una copia della JRE versione 1.8.0_201 e degli 
script (riconoscibili dal suffisso *_embeddedjre*) che lanciano l’editor utilizzando questa JRE integrata.

### Primo Avvio dell'IDE

8. A questo punto, potete **lanciare Netbeans** usando i launcher
 presenti nella cartella *bin*. Se lavorate su Windows, usate
 l'eseguibile "netbeans64.exe" se avete scaricato una JDK a 64bit,
 altrimenti usate l'eseguibile "netbeans.exe". Su sistemi Unix e Mac,
 usate lo script shell "netbeans".\
 Se all'avvio l'IDE vi chiede di importare la configurazione già
 presente sulla vostra macchina (magari di una versione precedente)
 rispondete no.

9. Selezionate la voce di menu **Tools \> Java Platforms** e verificate
 che la JDK che avete installato sia presente nella lista e marcata
 come "Default" (il relativo "Platform folder" dovrà essere quello
 specificato nella chiave *netbeans_jdkhome*, e quindi situato
 all'interno di \<D\>).

### Configurazione di Tomcat

10. A questo punto potete procedere a **connettere Netbeans a Tomcat**.

   a. Selezionate la voce di menu **Tool \> Servers** e di seguito il bottone "*Add Server...*".
   
   b. Nel successivo wizard selezionate "*Apache Tomcat or TomEE*" e come "*Server location*" specificate la cartella \<D\>/apache-tomcat-10.0.17 (*anche qui il nome effettivo cambierà al variare della versione, ovviamente*).
   
   c. Opzionalmente, spuntate la casella "*use private configuration folder*" e immettete come "*Catalina base*" la cartella \<D\>/tomcat_base. Questa operazione non è necessaria se avete decompresso Tomcat nella vostra home utente, mentre lo è nel caso in cui lo abbiate installato in altre posizioni sulla vostra macchina (ad esempio nella cartella Programmi di Windows).
   
   d. Inserite delle credenziali semplici nelle caselle "*Username*" e "*Password*" (l'IDE potrebbe richiedervele più volte in futuro) e assicuratevi che la casella "*Create user if if does not exist*" sia spuntata.
   
   e. Terminate il processo. A questo punto dovreste vedere il server appena istallato nella lista "Servers" del box di dialogo. Controllate che nella linguetta "*Platform*" relativa al nuovo server la "*Java Platform*" sia la stessa JDK di default usata dall'IDE.

### Test della Configurazione

11. Per **testare la nuova configurazione**,

   a. Provate prima di tutto ad **avviare Tomcat** cliccando 
	col tasto destro sulla relativa sotto-voce del nodo "*Servers*" presente nella linguetta/box "*Services*" dell'IDE e selezionando "*Start*". Se vi vengono chieste le credenziali per la "*Tomcat Manager Application*", inserite quelle definite al punto 8.d. Se tutto va bene, vedrete i log del server mostrati dall'IDE elencare una serie di informazioni che termineranno con una riga del tipo "*Server startup in \[...\] milliseconds*". Questo vuol dire che il server si è avviato con successo.
	
   b. **Create una semplice web application**, aggiungetevi una servlet e provate ad eseguire il tutto. 
Se il browser web si apre mostrando la pagina di benvenuto di default dell'applicazione (index), provate ad accedere alla URL della servlet che avete creato. Se anche la servlet vi risponde col suo messaggio di default, l'ambiente è configurato correttamente. Nota: potreste dover configurare quale browser aprire automaticamente selezionandolo dalla voce di menu **Tools \> Options.**
