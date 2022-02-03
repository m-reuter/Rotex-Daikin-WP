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

## Warmwasser-Soll und Hysterese

Das WW-Soll gibt an auf welche Temperatur das WW aufgeheizt werden soll. Hier ist z.B. 
48°C eine gute Einstellung. Höhere Einstellungen kosten deutlich mehr Strom und sind evtl. sinnvoll 
wenn Strom über eigenen Photovoltaik kostenlos ist. 

Die Hysterese ist die Temperatur um die das WW abfallen kann, bevor wieder aufgeheizt wird. 
Hier hat sich z.B. 5 (meist 4-7) bewährt. Beide Einstellungen hängen aber von vielen
Faktoren ab (z.B Duschverhalten, Anzahl der Personen).

Hinweis: Der WW-Speicher ist gut isoliert und verliert kaum Wärme. Wärme wird natürlich
entnommen wenn Warmwasser genutzt wird (Händewaschen, Duschen, ...), aber auch bei
laufender Frischwasser-Zirkulationspumpe (ca 1/2 Grad pro h), oder bei Abtauzyklen. Auch 
falsche Einstellungen an der Heizung (HZU, Continuous Heating) können viel Energie 
entziehen, die meist über den Heizstab nachgeheizt wird. 


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
allerdings dann auch teuer).

**Empfehlung: Bei FBH im Neubau sollte Continuous Heating ausgeschaltet werden: AUS** 

## Gebäudedämmung

Bei Fußbodenheizung einfach auf AUS stellen, da irrelevant (FBH reagiert zu langsam).

## Flüstermodus

Flüstermodus im Nachtbetrieb ist durchaus sinnvoll. Bei der "Ultra" gibt es drei Stufen:

Stufe 1: Keine Veränderungen erkennbar 
Stufe 2: Reduktion der maximalen, elektrischen Verdichterleistung um ca. 13%
Stufe 3: Zusätzlich Reduktion der Lüfterdrehzahl von max. 780U/min auf 680U/min

In Stufe drei dürfte die 8kW-Version damit ungefähr der 6kW-Version entsprechen.
Die 13% niedrigere Verdichterleistung (elektrisch) kann durchaus 30% weniger thermische
Leistung, also 6kW bedeuten. Das schont die WP und hat keinen erwähnenswerten Einfluss
auf die Arbeitszahl (AZ).

Achtung: Es wurde vereinzelt berichtet dass ein Dauerbetrieb in Stufe 3 nicht sinnvoll ist, 
da i) die Heizung an kalten Tagen für das Haus zu schwach ist, und ii) diese Einstellung
zu häufigen, unnötigen Abtauzyklen führen kann. Daher sollte der Flüstermodus nur 
nachts eingesetzt werden. Oder besser, man schaltet nachts ganz ab (mehr unten).

**Empfehlung: Nachts auf Stufe 3** 

## 1xWW

Die Menüfunktion 1xWW sollte nicht genutzt werden um schnell das WW aufzuheizen. Diese
Funktion bedient sich leider ausschließlich des Heizstabs. Ist also teuer und bei
deaktiviertem Heizstab ohne Funktion. 

Besser: Die WW-Bereitung kann angestoßen werden, indem man die WW-Solltemperatur im
Reglermenü kurz hochstellt (1 grad über Hysterese Differenz). Sobald die Anlage den
WW-Modus gestartet hat (<1 Minute) kann man wieder auf den ursprünglichen Sollwert
runtergehen, ohne dass die WW-Bereitung dadurch gestört wird. 


