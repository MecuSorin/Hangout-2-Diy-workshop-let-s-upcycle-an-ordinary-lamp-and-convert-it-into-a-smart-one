# Hangout-2-Diy-workshop-let-s-upcycle-an-ordinary-lamp-and-convert-it-into-a-smart-one

#Event description (RO)

Salutare,

La cea de-a doua intalnire Bucharest IoT Hangouts, pe langa #IoT, vom avea parte si de putin #upcycling.

Vom invata impreuna cum sa convertim o simpla lampa de birou intr-o lampa inteligenta, pe care sa o poti instala oriunde ai o conexiune Wi-Fi si pe care sa o poti controla de la distanta, prin Internet.

In acest workshop includem tot:

- Descrierea si intelegerea pieselor si a interactiunii dintre ele
- Modificarea fizica a lampii astfel incat sa poata fi controlata de pe Internet
- Implementarea de UI/UX pentru o usoara conectare a lampii, oriunde exista Wi-Fi
- Implementarea unui API folosit pentru viitoare integrari. (Ex. #Alexa, turn on my magic lamp)
- Si pana faci tu aceste viitoare integrari, vom adauga un mic buton web care prin #AJAX va controla starea lampii.

Pregateste-te sa te murdaresti pe maini, vom face si vom desface.
O sa taiem, o sa lipim, totul pana la acel moment #Evrika, cand tu vei pleca acasa cu propria ta lampa smart.

De asemenea, daca ai participat si la prima editie de IoT Hangouts, vei putea folosi experienta si cunostintele dobandite acum pentru a-ti conecta roverul la Wi-Fi sa-l poti controla wireless sau programa de la distanta.

Tu ai nevoie doar de laptop, disponibilitate si de imaginatie.
#ESP8266 #diy #magicLamp #IoT #upcyling

Ce este inclus? Tot!

Taxa pe care o plătiți pentru acest eveniment reprezintă costul pentru kitul pe care îl veți primi.

Kitul conține:
- ESP8266 modulul Wi-Fi ESP-01
- Releul ESP8266 pentru ESP8266 ESP-01S
- Adaptor de alimentare (220 V până la 5 V, 0,7 A)
- Lampa AC
- Interfață serială USB pentru modul ESP-266 ESP-01
- accesorii, cabluri, consumabile

Cost kit: 120 lei
Cost kit fara modul Wi-Fi: 100 lei (pentru participantii care au deja modulul de la prima editie de IoT Hangouts)

Veți găsi în locație toate uneltele și echipamentele necesare pentru acest workshop, cum ar fi șurubelnițe, pistoale de lipit sau de topit plastic.

În a doua jumătate a serii vom povesti, vom face networking si vom avea pizza, sucuri si bere, oferite de gazdele evenimentului, Crowd Favorite.

#About ESP8266
https://www.espressif.com/en/products/hardware/esp8266ex/overview

#Steps

##Connect the ESP8266 following the image:

![ESP8266 Bootloading mode](http://remotexy.com/img/help/help-esp8266-firmware-update-usbuart.png)

##Install Arduino and ESP8266 libraries following the tutorial on https://randomnerdtutorials.com/how-to-install-esp8266-board-arduino-ide/

##Download and install project dependencies

Libraries:
```
<PubSubClient.h>              https://github.com/knolleary/pubsubclient
<WiFiManager.h>               https://github.com/tzapu/WiFiManager
#include <ESP8266WiFi.h>      https://github.com/esp8266/Arduino
#include <DNSServer.h>        https://github.com/esp8266/Arduino
#include <ESP8266WebServer.h> https://github.com/esp8266/Arduino
```

##Upload the code on ESP8266

#Controlling the LAMP via MQTT

`Turning On: mosquitto_pub -t "6bcdb172-b427-11e8-96f8-529269fb1459/control" -h "broker.hivemq.com" -m ON`
`Turning Off: mosquitto_pub -t "6bcdb172-b427-11e8-96f8-529269fb1459/control" -h "broker.hivemq.com" -m OFF`
`Factory Reset: mosquitto_pub -t "6bcdb172-b427-11e8-96f8-529269fb1459/control" -h "broker.hivemq.com" -m reset_settings`
