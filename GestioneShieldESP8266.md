# Gesione ESP8266

## Cos'è l'ESP8266?
L'ESP8266 è una scheda che incorpora l'uso del Wi-Fi.
Si hanno tanti tipi di ESP8266, cambiano forme e costi, ma essenzialmente svolgono lo stesso principio.
Per questo progetto si è utilizzato un ESP8266 ESP-12E con scheda di programmazione già integrata, per facilitarne l'utilizzo.
<img src="https://i.imgbox.com/NBxGte5C.jpg"/>
La scheda presenta 30 pin e un'alimentazione attraverso micro USB.
Questo tipo di scheda può sostituire o essere un degno alleato di arduino, perchè dispone di pin che possono essere utilizzati per la gestione di dati di INPUT e/o OUTPUT.
La scheda, come si può vedere, è compatta, leggera, di buona fattura e può essere utilizzata per vasti utilizzi (domotica, robotica, automazione in generale).


## Come installare la scheda su Arduino
* Lancia l'IDE di Arduino dal tuo PC
* Vai su *File* > *Impostazioni*
* Inserisci questo link `http://arduino.esp8266.com/stable/package_esp8266com_index.json` nelle URL aggiuntive per la gestione delle schede e clicca su OK
* Vai su *Strumenti* > *Gestione Schede* e installa la piattaforma "ESP8266"
* Installare la [libreria ESP8266](https://github.com/googlesamples/firebase-arduino/archive/master.zip) aggiuntiva della scheda

*N.B: Installazione di questo pacchetto aggiuntivo per l'IDE di Arduino, comprende tante schede WI-FI in commercio*

## Come utilizzare la scheda ESP8266
* Lancia Arduino
* Selezione *Strumenti* > *Schede* e seleziona la shcheda che vuoi utilizzare nella sezione "ESP8266 Modules"

Noi utilizziamo, per questo progetto, una ESP8266 ESP-12E, quindi selezioneremo la scheda ESP-12E MODE MCU 1.0.


## <a name="ancora-collegamento-wifi"></a>Come collegare la scheda ESP8266 alla rete WI-FI
Per collegare la shield Wi-Fi, ad un router, dobbiamo seguire questi passi:
* Collegare la shield, tramite cavo mini USB, al PC
* Aprire l'IDE di Arduino 1.8.0 o superiori
* Andare su *Strumenti* e selezionale la scheda ESP8266 corrispondente a quella inserita(nel nostro caso MODE MCU 1.0)
* Impostare la porta di collegamento seriale (Esempio COM4)
* Impostare il bound rate a 115200
* Lanciare il [programma](https://github.com/domoticawifi/Network-nodes/blob/master/sketch_Connessione_Rete_WiFi.ino) per la connessione

## Programma di lancio per il collegamento
Analizziamo, riga per riga, il programma di lancio per il collegamento della scheda al router.

*N.B: abbiamo utilizzato, per le varie prove, un hotspot Wi-Fi con un HUAWEI P8. Il telefono, in questo caso, funge da router...*

Codice:
* Includiamo la libreria che abbiamo scaricato in precedenza, per utilizzare, più facilmente, le funzionalità della shield Wi-Fi (#include ESP8266.h)
* Creiamo due variabili di tipo string ed andiamo ad inserire le credenziali per l'accesso al router SSID e Password
* SSID è il nome della rete, nel nostro caso HUAWEI P8
* La Password è quella con cui accedete al router, per connettervi a internet
* Impostiamo la porta 80 per la comunicazione
* Nel ciclo di loop è presente la parte di programma che andrà a connettere la shield al router
* Una volta avvenuta la connessione verrà visualizzato, sulla porta seriale di arduino, l'indirizzo IP della scheda
* La scheda risulterà collegata alla rete LAN

*N.B: Potete verificare l'indirizzo IP, di ogni dispositivo connesso, andando sull'indirizzo IP del router, accedendo tramite browser. Di solito i router hanno come indirizzo 192.168.0.1. Potete verificare il vostro indirizzo di router sul manuale di quest'ultimo*
