---
title: Smart-Home
has_children: false
nav_order: 4
---

## Smart-Home

Leider gibt es keine gute und günstige Lösung die Rotex WP in ein Smart-Home System 
einzubinden. Daikin verkauft für viel Geld den in die Jahre gekommenen RoCon G1 Gateway,
der sowohl Daten ausliest, als auch Befehle an die WP senden kann. Allerdings über eine
externe Cloudanbdindung (Internet nötig). 

Es gibt hingegen einige sehr gute Bastellösungen die für wenig Geld mehr können. Dazu 
sollte man allerdings ein wenig IT Know-How mitbringen. Macht auch mehr Spaß. Eine 
Diskussion läßt sich auch im [HaustechnikDialog](https://www.haustechnikdialog.de/Forum/t/237662/Wissensaustausch-Smart-Home-Anbindung-u-Kommunikationsschnittstellen-Rotex-HPSU-Daikin-Altherma-3-ECH2O)
finden.

## Smart-Home Server

Um Daten zu loggen und Geräte zu steuern ist eine kleiner Rechner notwendig, der 
permanent angeschaltet ist. Dazu eignet sich z.B. ein Raspberry Pi 4, wegen seinem 
niedrigen Stromverbrauch und ausreichender Rechenleistung und RAM. 

Es gibt etiliche open source Software-Systeme für die Smart-Home Steuerung, z.B. 
[OpenHAB](https://www.openhab.org/), [FHEM](https://fhem.de/) etc. Hier empfehlen wir:

[HomeAssistant](https://www.home-assistant.io/)
 
wegen seiner aktiven Community, Bedienerfreundlichkeit, regelmäßigen Updates und flexiblen
Erweiterbarkeit. Es existieren auch bereits Erweiterungen die eine Anbindung der HPSU WP
über die folgenden zwei Projekte ermöglicht.

## ESPAltherma

[ESPAltherma](https://github.com/raomin/ESPAltherma) ist eine Software, die auf einen
ESP (mini-computer), in diesem Fall z.B. ein M5StickC oder M5StickCplus geladen wird. 
Der Stick wird an die Rotex WP angeschlossen, und kann dort Daten auslesen (und zwar
sowohl vom Rotex-Teil Innengerät, sowie DAIKIN Aussengerät). Die Daten werden per 
MQTT versand und können von einem Smart-Home (z.B. HomeAssistant) mitgeschrieben werden. 
Befehle können nicht geschickt werden, allerdings kann ein zusätzliches Relais an J16
angeschlossen werden um ein externes Raumthermostat zu simulieren und die Heizung
an- und abzuschalten (siehe [externes Raumthermostat]({{ site.baseurl }}{% link hpsu-compact.md %}#externes-raum-thermostat)).


## pyHPSU
