---
title: Smart-Home
has_children: false
nav_order: 4
---

## Smart-Home

Leider gibt es keine gute und günstige kommerzielle Lösung die Rotex WP in ein Smart-Home System 
einzubinden. Daikin verkauft für viel Geld den in die Jahre gekommenen RoCon G1 Gateway,
der sowohl Daten ausliest, als auch Befehle an die WP senden kann. Allerdings über eine
externe Cloudanbindung (Internet nötig). 

Es gibt hingegen einige sehr gute Bastellösungen die für wenig Geld mehr können. Dazu 
sollte man allerdings ein wenig IT Know-How mitbringen. Macht aber auch mehr Spaß. Eine 
Diskussion läßt sich im [HaustechnikDialog](https://www.haustechnikdialog.de/Forum/t/237662/Wissensaustausch-Smart-Home-Anbindung-u-Kommunikationsschnittstellen-Rotex-HPSU-Daikin-Altherma-3-ECH2O)
finden.

## Smart-Home Server

Um Daten zu loggen und Geräte zu steuern ist ein kleiner Rechner notwendig, der 
permanent angeschaltet ist. Dazu eignet sich z.B. ein Raspberry Pi 4, wegen seines 
niedrigen Stromverbrauchs, ausreichender Rechenleistung und RAM. 

Es gibt etliche Open Source Software Projekte für die Smart-Home Steuerung, z.B. 
[OpenHAB](https://www.openhab.org/), [FHEM](https://fhem.de/) etc. Hier empfehlen wir:

[HomeAssistant](https://www.home-assistant.io/){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
oder [ioBroker](https://www.iobroker.net/){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }
 
wegen ihrer aktiven Community, Bedienerfreundlichkeit, regelmäßigen Updates und flexiblen
Erweiterbarkeit. Für HomeAssistant existieren auch bereits Erweiterungen die eine einfache 
Anbindung der HPSU WP
über die ESPAltherma und pyHPSU Projekte ermöglicht. Ein großer Vorteil ist, dass sämtliche
Kommunikation direkt funktioniert und keine Cloudanbindung nötig ist! Die Daten bleiben
im Haus!

## ESPAltherma

[ESPAltherma](https://github.com/raomin/ESPAltherma) ist eine Software, die auf einen
ESP (mini-computer), in diesem Fall z.B. ein M5StickC oder [M5StickC Plus](https://shop.m5stack.com/products/m5stickc-plus-esp32-pico-mini-iot-development-kit?variant=35275856609444) geladen wird. 
Der Stick wird an die Rotex WP angeschlossen, und kann dort Daten auslesen (und zwar
sowohl vom Rotex-Innengerät, sowie vom DAIKIN-Aussengerät). Die Daten werden per 
MQTT versandt und können von einem Smart-Home (z.B. HomeAssistant) mitgeschrieben werden. 
Befehle können nicht geschickt werden, allerdings kann ein zusätzliches Relais an J16
angeschlossen werden um ein externes Raumthermostat zu simulieren und die Heizung
an- und abzuschalten (siehe [externes Raumthermostat]({{ site.baseurl }}{% link hpsu-compact.md %}#externes-raum-thermostat)).

Bei HomeAssistant kann leicht ein MQTT Broker (z.B. Mosquitto) als Add-On installiert werden, 
der die Daten der ESP empfängt. Für das Setup in HomeAssistant siehe die Dokumentation 
des ESPAltherma Projekts. 

## pyHPSU

[pyHPSU](https://github.com/Spanni26/pyHPSU) ist eine Python basierte Software, die 
mittels des CAN Bus mit der Rotex WP kommuniziert (allerdings nur Daten des Innengeräts
sehen kann). Mit dieser Software können auch Befehle gesendet werden, z.B. um  
die WW-Soll oder Raum-Soll Temperatur zu setzen. Benötigt wird ein CAN-Hat für den Raspberry Pi ([PiCan 2 Hat](https://raspberry-valley.azurewebsites.net/Raspberry-Pi-PICAN2-Hat/)).
Auch gibt es bereits ein Add-On für 
HomeAssistant [pyhpsu2mqtt](https://github.com/m-reuter/ha-addons). Dieses Add-On läßt eine
Version von pyHPSU laufen, die auch über MQTT kommuniziert und daher leicht in 
HomeAssistant eingebunden werden kann. 

## vzlogger

[vzlogger](https://wiki.volkszaehler.org/software/controller/vzlogger) ist Teil der 
Volkszähler Software und erlaubt es über einen Infrarot Adapter moderne Stromzähler
auszulesen. Dadurch kann der Verbrauch des Hauses oder der Wärmepumpe mitgeschrieben 
werden. Auch hierzu gibt es ein HomeAssistant Add-On [vzlogger2mqtt](https://github.com/m-reuter/ha-addons),
das die Installation und MQTT Kommunikation übernimmt. 

## Shelly 3EM

Eine andere Möglichkeit den Strom der WP ohne Smart-Meter zu messen ist der [Shelly 3EM](https://shelly.cloud/products/shelly-3em-smart-home-automation-energy-meter/). 
Shellies sind kleine Relais mit W-LAN die z.B. in die Unterputzdose eingesetzt werden können
um Rolladen, Lichtschalter, Dimmer, oder Gartenbewässerung zu steuern. Es gibt auch
Shelly Plugs, die als
Zwischenstecker für Stehlampen, Waschmaschine etc. sowohl für die Steuerung als auch 
Strommessung genutzt werden können. Der (nicht ganz günstige) 3EM hingegen ist ein 
3-Phasen Strommesser, z.B. für den Elektroherd oder die Wärmepumpe. Shellies können 
sehr leicht in HomeAssistant eingebunden werden. 
