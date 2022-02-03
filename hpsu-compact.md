---
title: HPSU Compact Ultra
has_children: False
nav_order: 3
---

## HPSU Compact Ultra / Altherma 3 R ECH2O

Die Rotex HPUS Compact Ultra wird inzwischen von DAIKIN als Altherma 3 R ECH2O vermarktet. 
Das Aussengerät stammte schon immer von Daikin, wobei das Innengerät von Rotex
kommt. Daher gibt es auch verschiedene Systeme um Daten der Geräte auszulesen (mehr dazu in Smart-Home).

Die Geräte werden in verschiedenen Klassen (4kW, 6kW, 8kW ..) angeboten. Wichtig ist, 
dass die maximale Leistung dabei an das Haus und an den Warmwassertank angepasst ist. 
Ein 4kW Gerät braucht nämlich viel zu lange um 500l aufzuwärmem (selbst wenn sich um 
einen Bungalow mit nur einem Raum handelt). 

Auch der Tank sollte die richtige Größe haben. Bei 4 Personen (vermutlich auch bei 3) 
ist unbedingt der 500l Tank zu empfehlen! Sonst wird es schnell mal bei Duschen kalt,
was sogar bei 4 Personen und 500l vorkommen kann. Auch für ein Abtauen ohne Heizstab und
für Wärmespeicherung aus Solar oder Photovoltaik ist ein größerer Tank sinnvoll. 

Auch das "Ultra" Modell mit der neuen Kühlflüssigkeit ist zu empfehlen, da es effizienter 
arbeitet und meist mit niedrigeren Drehzahlen auskommt als das Vorgängermodel. Ausserdem, 
sind wohl einige Probleme am Aussengerät beseitigt worden, die zu ständigen, größtenteils 
unnötigen Abtau-Vorgängen geführt hatten.

Im Folgenden erklären und diskutieren wir die Einstellungen.

## Raumsoll und Heizkurve

Raumsoll und Heizkurve sind bei witterungsgeführter Heizung (empfohlen!) die beiden
wichtigsten Parameter um sowohl die Wärme im Haus als auch den Verbrauch zu regulieren. 
Dabei ist es wichtig, dass zuvor die Fußbodenheizung richtig eingestellt wurde und 
die Einzelraumregler alle (mind. 2/3 der Heizkreise) offen sind
([siehe Heizung]({{ site.baseurl }}{% link heizung.md %}))!

...

## Heizungsunterstützung (HZU)

Die Heizungsunterstützung (HZU) bewirkt, dass die Heizung unter gewissen Bedingungen
Wärme aus dem Warmwassertank entnehmen kann. Diese Einstellung ist ggf. sinnvoll, wenn
der Speicher aus Solarthermie zusätzliche Energie bekommt 
(und selbst da gehen die Meinungen auseinander).
 
**Empfehlung: Daher sollte die HZU ausgeschaltet werden: AUS** 

Ein zusätzliches Problem mit „Heizungsunterstützung EIN“ gibt es in Verbindung mit
Sperrzeiten fürs Warmwasser. Die Steuerung realisiert die Sperrzeit durch Absenkung der
WW-Solltemperatur auf 35°C. Da der Speicher zu Beginn der Sperrzeit deutlich wärmer ist,
wird er danach zugunsten der Heizung auf 35°C runtergekühlt. Nach der Sperrzeit muss das
WW mühsam wieder hochgeheizt werden.

Nach dem Aktivieren oder Deaktivieren der HZU Funktion muss die Heizungssteuerung
unbedingt **neu gestartet** werden! Ab besten einmal kurz mit der Sicherung die Spannung
wegnehmen. Es sind sonst komische Effekte beobachtet worden (z.B. dass das Außengerät 
sonst nicht mehr anspringt). 

## Continuous Heating

Diese Funktion existiert nur bei dem "Ultra" Model. 
Bei eingeschaltetem "Continuous Heating" wird während des Abtauens Wäremenergie für die
Heizung aus dem Speicher entnommen. Die entnommene Wärme muss nachgeheizt werden. Meist
passiert das mit Heizstab, was nicht energieeffizient ist. Bei Fußbodenheizung wird
man die 10-20min Pause beim Abtauen gar nicht merken. Ggf. ist diese Funktion für alte 
Heizkörper und fehlender Dämmung im Haus sinnvoll (z.B. bei Vorlauftemperaturen > 35°C, 
allerdings auch teuer).

**Empfehlung: Bei FBH im Neubau sollte Continuous Heating ausgeschaltet werden: AUS** 


