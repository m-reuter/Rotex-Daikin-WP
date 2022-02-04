---
title: HPSU Compact Ultra
has_children: False
nav_order: 3
---

## HPSU Compact Ultra / Altherma 3 R ECH2O

Die Rotex HPUS Compact Ultra wird inzwischen von DAIKIN als Altherma 3 R ECH2O vermarktet. 
Das Außengerät stammte schon immer von Daikin, wobei das Innengerät von Rotex
kommt. Daher gibt es auch verschiedene Systeme um Daten der Geräte auszulesen (mehr dazu in Smart-Home).

Die Geräte werden in verschiedenen Klassen (4kW, 6kW, 8kW ..) angeboten. Wichtig ist, 
dass die maximale Leistung dabei an das Haus und an den Warmwassertank angepasst ist. 
Ein 4kW Gerät braucht nämlich viel zu lange um 500l aufzuwärmem (selbst wenn es sich um 
einen Bungalow mit nur einem Raum handelt). 

Genauso sollte der WW-Speicher die richtige Größe haben. Bei 4 Personen (vermutlich auch bei 3) 
ist unbedingt der 500l Speicher zu empfehlen! Sonst wird es schnell mal beim Duschen kalt,
was sogar bei 4 Personen und 500l vorkommen kann. Ausserdem ist für ein Abtauen ohne Heizstab und
für Wärmespeicherung aus Solar oder Photovoltaik ein größerer Speicher sinnvoll. 

Auch das "Ultra" Modell mit der neuen Kühlflüssigkeit ist zu empfehlen, da es effizienter 
arbeitet und meist mit niedrigeren Drehzahlen auskommt als das Vorgängermodel. Ausserdem, 
sind wohl einige Probleme am Außengerät beseitigt worden, die zu ständigen, größtenteils 
unnötigen [Abtau-Vorgängen](https://www.haustechnikdialog.de/Forum/t/215735/Rotex-HPSU-Daikin-Abtaugeschaedigte) geführt hatten.

Im Folgenden erklären und diskutieren wir die Einstellungen. Viele der informationen 
stammen aus dem [HPSU compact ultra Forum](https://www.haustechnikdialog.de/Forum/t/226662/ROTEX-HPSU-compact-Ultra-ab-2018-Erfahrungen-Optimierung)
des Haustechnikdialogs. Ein Dank geht an die vielen Helfer dort!


## Service-Menu

Damit nicht aus Versehen wichtige Einstellungen verändert werden, lassen sich einige
Einstellungen nur nach Eingabe des Service-Codes erreichen. Der vier-stellige Code
wurde in den Haustechnik Foren schon mindestens *tausend-und-ein* mal erwähnt! Wer 
Einstellungen an seiner WP verändert, ist dafür und für alle Konsequenzen
natürlich selbst verantwortlich. 


## Raumsoll und Heizkurve

Die Heizung sollte im Witterungsgeführten Betrieb laufen, damit sich die Heizleistung 
der Außentemperatur anpassen kann!

Raumsoll und Heizkurve sind bei witterungsgeführter Heizung die beiden
wichtigsten Parameter um sowohl die Wärme im Haus als auch den Verbrauch zu regulieren. 
Dabei ist es wichtig, dass zuvor die Fußbodenheizung richtig eingestellt wurde und 
die Einzelraumregler alle (mind. 2/3 der Heizkreise) offen sind
([siehe Heizung]({{ site.baseurl }}{% link heizung.md %}))!

Der Raumsoll ist nicht genau der Wert, der im Haus sein soll, sondern nur ein Parameter, 
der die Heizkurve komplett nach oben oder unten verschiebt. Ist es also sowohl in der
Übergangszeit als auch im Winter zu warm oder zu kalt, muss dieser Parameter entsprechend
angepasst werden. Meist liegt der Wert so bei 20 - 22.

Die Heizkurve wird über den "Heizkurve" Parameter gewählt. Diese Einstellung liegt meist
bei 0,5 oder 0,4 (empfohlen für KfW55). Wenn es z.B. nur im Winter zu kalt ist, sollte 
eher dieser Paramater erhöht werden, statt mit Raumsoll die ganze Kurve zu verschieben. 

Ein weiterer Wert, die "Vorlauftemperatur Heizbetrieb" ist bei einer witterungsgeführten
Heizung irrelevant, da dieser Wert ja durch die Heizkurve (in Abhängigkeit von Raumsoll, 
Heizkurve-Parameter, und Außentemperatur) berechnet wird und nicht konstant festgelegt wird. 

**Empfehlungen:**
- Einzelraumregler auf
- Witterungsgeführt
- Raumsoll 21 (und später verschieben, wenn nötig)
- Heizkurve 0,4 (auch bei Bedarf anpassen)
- Vorlauftemperatur Heizbetrieb: egal, wird ignoriert


## Vorlauftemperatur Min und Max

Die Vorlauftemperatur Min und Max stellt die minimalen und maximalen Vorlauf ein, den die
Heizung im witterungsgeführten Betrieb annehmen darf. Besonders wichtig bei der Rotex 
ist hier die Vorlauftemperatur Min! Diese sollte bei genau 25°C liegen. Dadrüber wird
das Haus im Frühling oder Herbst zu warm, und bei einer Einstellung dadrunter
funktioniert die WP nicht mehr richtig.
Nach einem Stopp (z.B. nach WW Aufbereitung) springt die WP nämlich erst dann wieder an,
wenn die Heizwassertemperatur 3K unter VL-Soll liegt (Reglereigenschaft, nicht veränderbar).
Wenn in der Übergangszeit die witterungsgeführte Heizkurve z.B. nur 24°C als Sollwert
berechnet, startet die WP nach einem Stopp erst wieder bei 24°-3°=21°C. Das dauert „ewig“.
Bis das Heizwasser so weit abgekühlt ist, ist die Raumtemperatur schon ungemütlich kühl. 
Der Min. Vorlauf von 25°C verhindert das. 

Der Max Vorlauf sollte auf etwas oberhalb des Wertes einstellen, der maximal laut
Heizkurve erwartet wird, oder z.B. einfach auf 55°C. 

**Empfehlung: Min Vorlauf = 25, Max Vorlauf 55**


## Warmwasser-Soll und Hysterese

Das WW-Soll gibt an auf welche Temperatur das WW aufgeheizt werden soll. Hier ist z.B. 
48°C eine gute Einstellung. Höhere Einstellungen kosten deutlich mehr Strom und sind evtl. sinnvoll 
wenn Strom über eigenen Photovoltaik kostenlos ist. 

Die Hysterese ist die Temperatur um die das WW abfallen kann, bevor wieder aufgeheizt wird. 
Hier hat sich z.B. 5 (meist 4-7) bewährt. Beide Einstellungen hängen aber von vielen
Faktoren ab (z.B Duschverhalten, Anzahl der Personen).

Hinweis: Der WW-Speicher ist gut isoliert und verliert kaum Wärme. Wärme wird natürlich
entnommen wenn Warmwasser genutzt wird (Händewaschen, Duschen, ...), aber auch bei
laufender Frischwasser-Zirkulationspumpe (ca 1/2 Grad pro h), oder bei Abtauzyklen.
Achtung: falsche Einstellungen an der Heizung (HZU, Continuous Heating) können viel Energie 
entziehen, die meist über den Heizstab nachgeheizt wird. 

**Empfehlung: WW-Soll 48, Hysterese: 5**

## Heizungsunterstützung (HZU)

Die Heizungsunterstützung (HZU) bewirkt, dass die Heizung unter gewissen Bedingungen
Wärme aus dem Warmwassertank entnehmen kann. Diese Einstellung ist ggf. sinnvoll, wenn
der Speicher aus Solarthermie zusätzliche Energie bekommt 
(und selbst da gehen die Meinungen auseinander).
 
**Empfehlung: HZU: AUS** 

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

**Empfehlung: Continuous Heating: AUS** 

## Bivalenztemperatur

Die Bivalenztemperatur ist der Wert der Außentemperatur, bei dessen Unterschreitung
der Heizstab beim Heizbetrieb mithelfen darf. Eine falsche Einstellung kann da sehr
teuer werden. Bei einem gut gedämmten Haus (z.B. KfW55) wird eigentlich bei ausreichender
Auslegung der WP gar kein Heizstab benötigt, daher kann die Bivalenztemperatur auf -10°C
oder sogar dadrunter festgelegt werden. Wer natürlich mit einem 4kW Gerät 200qm beheizen
möchte benötigt da eine andere Einstellung, daher kann hier keine generelle Empfehlung 
gegeben werden. Ggf. einfach ausprobieren und bei Minusgraden wenns im Haus kalt wird,
hochsetzen. 

**Empfehlung: -10 bei gut gedämmten Haus und 6 oder 8 kW WP**

## Frostschutz

Frostschutz ist dazu gedacht das Einfrieren der Heizung und Wasserleitungen im Haus zu
verhindern. Bei Frostschutz=0 läuft dann die Heizung weiter (z.B. bei Bereitschaft läuft
die Heizung auf min. Vorlauf also 25°C), wenn die Außentemperatur nachts
knapp unter 0°C abfällt. Das macht vielleicht in einer wasserbeheizten Baracke ohne
Wärmedämmung Sinn. In gut gedämmten Häusern, kann man z.B. auf -10 stellen. 

**Empfehlung: -10 bei gut gedämmten Haus**

Diese Einstellung ist natürlich sicherheitsrelevant. Z.B. schaltet man die WP auf
Bereitschaft und fährt für 10 Tage in den Urlaub und es bleibt in dieser Zeit konstant
-9°C, dann kann evtl. schon was einfrieren. Meist sollte man aber sowieso die Heizung 
weiterlaufen lassen, evtl. bei abgesenktem Raum-Soll. 

## Gebäudedämmung

Bei Fußbodenheizung einfach auf **AUS** oder **Gering** stellen, damit die Heizung 
auf veränderte Außentemperaturen besser reagieren kann. 

## Flüstermodus

Flüstermodus im Nachtbetrieb ist durchaus sinnvoll. Bei der "Ultra" gibt es drei Stufen:

1. Stufe: Keine Veränderungen erkennbar 
2. Stufe: Reduktion der maximalen, elektrischen Verdichterleistung um ca. 13%
3. Stufe: Zusätzlich Reduktion der Lüfterdrehzahl von max. 780U/min auf 680U/min

In Stufe drei dürfte die 8kW-Version damit ungefähr der 6kW-Version entsprechen.
Die 13% niedrigere Verdichterleistung (elektrisch) kann durchaus 30% weniger thermische
Leistung, also 6kW bedeuten. Das schont die WP und hat keinen erwähnenswerten Einfluss
auf die Arbeitszahl (AZ).

Achtung: Es wurde vereinzelt berichtet dass ein Dauerbetrieb in Stufe 3 nicht sinnvoll ist, 
da

- i) die Heizung an kalten Tagen für das Haus zu schwach ist, und
- ii) diese Einstellung zu häufigen, unnötigen Abtauzyklen führen kann.

Daher sollte der Flüstermodus nur 
nachts eingesetzt werden. Oder besser, man schaltet nachts ganz ab ([Nachtabschaltung](#nachtabschaltung)).

**Empfehlung: Nachts auf Stufe 3** 

## 1xWW

Die Menüfunktion 1xWW sollte nicht genutzt werden um schnell das WW aufzuheizen. Diese
Funktion bedient sich leider ausschließlich des Heizstabs. Ist also teuer und bei
deaktiviertem Heizstab ohne Funktion. 

**Empfehlung: Nicht nutzen**

Besser: Die WW-Bereitung kann angestoßen werden, indem man die WW-Solltemperatur im
Reglermenü kurz hochstellt (1 grad über Hysterese Differenz). Sobald die Anlage den
WW-Modus gestartet hat (<1 Minute) kann man wieder auf den ursprünglichen Sollwert
runtergehen, ohne dass die WW-Bereitung dadurch gestört wird. 


## Heizstab (BUH)

Der Heizstab (auch Backup-Heater BUH genannt) ist in den meisten Fällen der größte, und
häufig komplett unnötige, Stromverbraucher. Der Heizstab wird normalerwise eingesetzt:
- Beim Abtauen
- Nach einer Wartezeit bei WW Aufbereitung
- Auch im Sommer wenn das Außengerät über 35°C misst (daher Gerät verschatten)

Es können mehrere Anpassung vorgenommen werden um den Verbrauch des BUH zu reduzieren:
1. Die drei Verbrauchstufen können angepasst werden
2. Die Wartezeit bei WW kann verlängert werden
3. Der Heizstab kann komplett auskonfiguriert werden

### Externe Leistung
Es gibt für den Heizstab 3 Einstellungen für WW, Stufe 1 und Stufe 2,
z.B. 3kW, 6kW, 9kW, die angeben wie viel Strom jeweils bei WW und beim Abtauen (Stufe 1,2)
gezogen wird.  Unter 25°C Rücklauftemperatur wird der Heizstab z.B. beim Abtauen in
Stufe 1 zugeschaltet, ab 20°C Stufe 2. Man kann daher die Stufen heruntersetzen um etwas
Strom zu sparen, z.B. auf 3,3,3.

### Wartezeit ext. Wärmeerzeuger
Für WW Aufbereitung ist es vermutlich besser den Heizstab über die Wartezeit ganz
abzustellen. Die „Wartezeit ext. Wärmeerzeuger“ kann daher auf 90 Minuten erhöht werden.
Liegt die "Max. Warmwasser Ladezeit" dadrunter (z.B. 60 min), springt der Heizstab nie
an (ausser ggf. im Sommer bei über 35°C außen).

### Heizstab AUS
Der Heizstab ist ein optionaler Zusatz und kann technisch komplett auskonfiguriert
werden über:

„Einstellungen“ => „Ext. Quelle“ => „Konfig. externe Wärmequelle“

Nur so kann die Nutzung des Heizstabes beim Abtauen (und im Sommer) vermieden werden.
Jeder Abtauvorgang zieht den Speicher dann um ca 1-2 Grad runter.
Das Wiederaufwärmen mit Hilfe der WP (Arbeitszahl > 2) ist günstiger als mit Heizstab 
AZ=1). Die Anlage macht evtl. eine Sicherheitsabschaltung, wenn beim Abtauen die
Speichertemperatur unter 30°C fällt. Dies könnte passieren, wenn morgens der Speicher
nach nächtlicher Abschaltung kühl ist, und jemand duscht und einen Abtauvorgang auslöst. 
Man kann ggf. durch eine kleinere WW-Hysterese (z.B. 3 Grad) entgegenwirken.
Schaltet die Anlage doch mal ab, lässt sich der Heizstab ja schnell wieder aktivieren.
Man muss nur drauf achten. Es zur Zeit keine Fälle bekannt wo so ein 
Notstopp passiert ist, da mit WW-Soll 48 und 3-5K Hysterese immer genug Wärme da sein 
sollte. Im Sommer kann es passieren, dass mittags bei sehr hohen Temperaturen kein WW gemacht
wird, aber wer will da schon heiß duschen. 

**Empfehlung: Ext. Leistung runtersetzen (3,3,3) und Max WW Ladezeit auf 90 Min**
oder den Heizstab ganz abschalten. Sollte die WP (zu kleines Gerät?) das WW nicht in 1h
warm bekommen, oder Haus wird kalt, kann man einfach den Heizstab wieder zulassen.


## Zirkulationspumpe

Die Zirkulationspumpe (falls überhaupt installiert) verteilt permanent Warmwasser im 
ganzen Haus, damit man nicht lange darauf warten muss. Das funktioniert meist nicht 
besonders gut: das Wasser ist trotzdem zunächst nur lauwarm. Ausserdem entzieht die 
Zirkulation dem WW-Speicher permanent Wärme, ca. 1/2 Grad pro Stunde, die zum großen
Teil das Haus wärmt, aber leider das ganze Jahr. Es lohnt sich daher evtl. nur ein oder
drei mal (morgens, mittags, abends), die Pumpe anzuschmeißen. 

Die Zirkulationspumpe wird entweder mit einem eigenen Zeitprogramm gesteuert, oder sie
hängt am Zeitprogramm der Warmwasserbereitung. Beide Optionen sind einstellbar.
Es läuft das eigene Zeitprogramm, wenn die Einstellung "Zirkulationspumpe Ansteuerung"
auf AUS ist! Genau umgekehrt als in der Betriebsanleitung. Wer das nicht weiß
(also Ansteuerung auf EIN hat) und keine WW Sperrzeiten eingestellt hat, lässt unwissend
die Zirkulation auch in der Nacht durchlaufen, egal welches Zeitprogramm bei der 
Zirkulation eingestellt ist. 

**Empfehlung: Zirkulationspumpe Ansteuerung: AUS und dann im Zirkulationsprogramm 1-3
kurze Zeiträume wählen**


## Nachtabschaltung

WW-Aufbereitung, Zirkulationspumpe und sogar die Heizung können in der Nacht über
Zeitprogramme abgeschaltet werden. Da nachts die Außentemperaturen meist niedriger sind,
und um viele Abtauzyklen zu vermeiden, macht eine Abschaltung viel Sinn. Bei guter
Isolation des Hauses, kühlt es um ca 1/2 Grad ab. Falls eine Lüftungsanlage ohne
Wärmerückgewinnung installiert ist (nicht gut!), sollte diese evtl. auch abgeschaltet 
oder runter gedreht werden damit das Haus nicht stärker auskühlt. 

Leider lässt sich die Heizung nachts über das Zeitprogramm nicht komplett ausschalten:

- falls die Frostschutzemperatur erreicht wird (selten)
- oder falls die Rücklauftemperatur unter 22 Grad sinkt (durchaus möglich)

schaltet die Heizung automatisch wieder ein! Dies lässt sich nur mit einem externen
Wohnraumthermostat vermeiden. 

**Empfehlung: alles nachts aus**

## Externes Raum-Thermostat

Ein Externes Raum-Thermostat kann basierend auf der tatsächlichen Raumtemperatur in einem 
Leitraum die WP-Heizung abschalten. Dies ist hilfreich um in der Übergangszeit bei 
Sonneneinstrahlung ein Überheizen zu vermeiden. Ein Empfänger wird dabei über zwei Kabel
an der WP angeschlossen (J16 Pin 1,2) und der Sender im Leitraum installiert.
Darüber lässt sich auch ein Zeitprogramm einstellen dass die WP z.B. in der Nacht 
wirklich abschaltet (bei Frostschutz geht sie natürlich weiterhin an).
In Frage kommt z.B. ein Computherm Q3 RF oder Q7 RF.  Ähnliches lässt sich auch mit
einer [Smart-Home]({{ site.baseurl }}{% link smart-home.md %}) Anbindung realisieren.

**Empfehlung: ein ext. Raum-Thermostat macht Sinn**


---

[Weiter: Smart-Home]({{ site.baseurl }}{% link smart-home.md %}){: .btn .btn-primary .fs-5 .mb-4 .mb-md-0 .mr-2 }

