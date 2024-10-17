# TP 4 - Montageprozesse des Leitungssatzes in der Karosserie

## Inhalt

[4.1 Definition der Randbedingungen](#_4.1)
[4.2 Einbringen der LS-Tasche in die Karosserie](#_4.2)
- [4.2.1 Das Anfahren des Anlieferungspunktes](#_4.2.1)
- [4.2.2 Grobausrichtung der Transporttasche im Innenraum](#_4.2.2)
- [4.2.3 Ablage der Transporttasche innerhalb der Karosserie](#_4.2.3)

[4.3 Grobauslegung des Leitungssatz](#_4.3)
- [4.3.1 Transporttasche Öffnen](#_4.3.1)
- [4.3.2 Leitungssatzstränge im Innenraum auslegen](#_4.3.2)
- [4.3.3 Leitungssatz am Fahrzeugboden montieren](#_4.3.3)

[4.4 Durchführung von Fädelprozessen](#_4.4)
- [4.4.1 Lokalisieren des Einzelstrangs](#_4.4.1)
- [4.4.2 Greifen des Einzelstrangs](#_4.4.2)
- [4.4.3 Leitungsende zum Durchbruch bewegen](#_4.4.3)
- [4.4.4 Leitungsende einfädeln](#_4.4.4)

[4.5 Dichtungselemente befestigen](#_4.5)
- [4.5.1 Lokalisieren des Dichtungselements](#_4.5.1)
- [4.5.2 Grobpositionierung des Dichtungselements](#_4.5.2)
- [4.5.3 Feinpositionierung des Dichtungselements](#_4.5.3)
- [4.5.4 Befestigung des Dichtungselements](#_4.5.4)
- [4.5.5 Senkrechte Einbaurichtung zur Aussparung der Karosserie](#_4.5.5)

[4.6 Strangbefestigung](#_4.6)
- [4.6.1 Clipse und Halterungen befestigen](#_4.6.1)
- [4.6.2 Kabelkanäle und komplexe Halterungen befestigen](#_4.6.2)
- [4.6.3 Einlegen in Kabelkanäle und Schließen des Deckels](#_4.6.3)

[4.7 Steckverbindung herstellen](#_4.7)
- [4.7.1 Konstruktive Gegebenheiten](#_4.7.1)
- [4.7.2 Umsetzung der Steckverbindung im Fahrzeug](#_4.7.2)
- [4.7.3 Verriegelungselemente von Gehäusen (z.B. CPA – Connector Position Assurance)](#_4.7.3)

[4.8 Fazit](#_4.8)


## Zielsetzung
Im TP 4 "**Montageprozesse des Leitungssatzes**" wurden Möglichkeiten untersucht, die Montageprozesse beim OEM über Verwaltungsschalen als standardisierte Digitale Zwillinge abzubilden. Dazu wurden die einzelnen Teilprozesse der Montage eines Leitungssatzes in der Fahrzeugkarosserie analysiert, relevante Informationen abgeleitet und semantisch beschrieben, um diese in einem Teilmodell der Verwaltungsschale zu hinterlegen und für die Prozesse automatisiert abrufbar bereitzustellen.

Der Leitungssatz besitzt die Aufgabe, die Endverbraucher innerhalb eines Fahrzeugs miteinander zu verbinden und somit eine gezielte Ansteuerung einzelner Komponenten zu ermöglichen. Er ist ein Produkt, welches eine hohe Varianz in seinen Einzelteilen besitzt, kundespezifisch (Losgröße 1) produziert wird und schwer handzuhaben ist, da er keine eigene Steifigkeit in sich selbst besitzt.

Das Teilprojekt war in folgende Arbeitspakete aufgeteilt, deren Ergebnisse in diesem Dokument zusammenfassend erläutert werden:

-   AP 4.1 - Verwaltungsschalen der relevanten Montage-Komponenten
-   AP 4.2 - Auswahl der zu automatisierender Prozesse
-   AP 4.3 - Dokumentation der Anforderungen zu diesen Prozessen
-   AP 4.4 - Konzept zur Montage des Leitungssatzes

Das Zielbild insgesamt war, die automatisierte Montage des Leitungssatzes im Fahrzeug möglichst vollständig zu automatisieren. Das bedeutet, dass alle Datenbedarfe, wie bspw. Informationen zur Bahnplanung, Geometrie etc. semantisch beschrieben, digital bereitgestellt, abgerufen und bei Bedarf aktualisiert werden müssen. Als Startpunkt wurde die Anlieferung der Packtasche inklusive des Leitungssatzes an der Montagezelle beim OEM angenommen. Als Grundlage zur Ermittlung der Datenbedarfe für die Prozessschritte wird auf die [VDI2860](https://www.vdi.de/richtlinien/details/vdi-2860-blatt-1-montage-und-handhabungstechnik-handhabungsfunktionen-handhabungseinrichtungen-begriffe-definitionen-symbole) zurückgegriffen werden. Innerhalb der VDI2860 werden grundlegende Handhabungs- und Montagetechniken untergliedert und beschrieben.

Von der Vorgehensweise her wurde der komplexe Montageprozess in automatisierbare Teilprozesse unterteilt, die in den weiteren Kapiteln einzeln betrachtet werden. Dabei soll der Fokus auf notwendige Informationsbedarfe und Fähigkeiten gelegt werden, die für die einzelnen Prozessschritte benötigt und anschließend in einem Submodell der Verwaltungsschale hinterlegt werden sollen.

Für die Vereinfachung des Prozesses werden aufgrund der Komplexität einige Annahmen getroffen, die im folgenden Kapitel erläutert und anschließend in den einzelnen Kapiteln berücksichtigt werden.

## <a name="_4.1"></a>4.1 Definition der Randbedingungen

In diesem Kapitel sollen einige Randbedingungen definiert werden, um einen einheitlichen Handlungsrahmen für die Analyse jedes Teilprozesses zu erzielen.

Da eine robotische Anwendung nicht den vollständigen Montagevorgang binnen eines Prozessschrittes durchführen kann, wird der gesamte Prozess in mehrere Teilprozesse untergliedert. Für die Umsetzung der entsprechenden Prozesse wird ein weiterer Detailierungsgrad in Grob- und Feinauslegung durchgeführt.

-   Grobauslegung: Das Einbringen, öffnen und grobe auslegen des Leitungssatzstränge in der Karosserie. Die richtige Ausrichtung von Clipsen und Steckern, spielen in diesem Prozessschritt noch eine untergeordnete Rolle
-   Feinauslegung: Fokus wie die einzelnen Clipse und Stecker richtig orientiert und formschlüssig in das Gegenstück oder in die Montagevorrichtung gebracht wird.

![image](https://github.com/user-attachments/assets/306c9b5f-6afe-44a0-9201-31ec38bfec86)    
*Abbildung 1-1: Maße der Packtasche eines Leitungssatzes*

In *Abbildung 1-1* ist eine Packtasche zusehen, die verwendet wird, um den Leitungssatz nach der Produktion beim Konfektionär zum OEM an das Montageband zu liefern. Die Packtasche (in der Realität gibt es unterschiedliche) und eine vorgegebene Packanleitung für den Leitungssatz wird in der Branche vorgegeben und unterschiedet sich je nach OEM. Um einige Basisparameter (Abmessungen und Öffnungsmechanismus) zu identifizieren, wird die Packtasche als Referenz herangezogen und analysiert. Diese Angaben sind für die Auslegung des Arbeitsraums und des später zu verwendenden Roboters notwendig. Für das vorliegende Beispiel wird eine Höhe von 50 cm, eine Breite von 110cm und eine Tiefe von 75 cm angenommen. Der Leitungssatz wird mit einem Gewicht von 60 Kg (inkl. Packtasche) angenommen. Der abgebildete Öffnungsmechanismus ist ein Klinkenverschluss und somit herausfordernd für den Roboter diesen zu betätigen. Um eine erste Vereinfachung anzunehmen, wird davon ausgegangen, dass es sich beim Öffnungsmechanismus der Packtasche um einen Klettverschluss handelt, da dies mehrere Angriffspunkte für den Roboter bietet.

Die Reihenfolge, wie die einzelnen Stränge des Leitungssatzes aus der Packtasche entnommen werden müssen, ist durch die Packanleitung vorgegeben. Eine farbliche Markierung am Ende der einzelnen Stränge macht eine Unterscheidung möglich.

In *Abbildung 1-2* sind die Abmessungen der Karosserie dargestellt, die für das Einbringen der Packtasche in das Fahrzeug betrachtet werden.

![image](https://github.com/user-attachments/assets/54a4a52c-85bc-4c1d-9913-08fceb559597)    
*Abbildung 1-2: Maße der Karosserie (S-Klasse)*

Die folgenden Maße für die Karosserie und deren Öffnung wurden gemessen und werden für die weitere Betrachtung verwendet*.*

**Karosserieinnenraum:**

-   *Länge: 252cm*
-   *Breite: 160cm*
-   *Höhe: 122cm*

**Türausschnitt:**

-   *Breite:85cm*
-   *Höhe: 95cm*

**Nullpunkt:**

Um einen grundsätzlichen Nullpunkt festzulegen, wird die geometrische Lage des Schaltknaufs als 0-Punktkoorsinatensystem innerhalb der Karosserie verwendet (gelber Punkt Bild 2).

## <a name="_4.2"></a>4.2 Einbringen der LS-Tasche in die Karosserie

Für eine typische Montagezelle wie in *Abbildung 1-3* schematisch dargestellt, werden die notwendigen Szenarien analysiert. Zum einen müssen die relativen Positionen der einzelnen Prozessteilnehmer (Roboter, Karosserie und Packtasche) bekannt sein. Hierzu müssen die jeweiligen Koordinatensysteme der bestehenden Teilnehmer bekannt sein, damit die relativen Positionen errechnetet werden können. Hierfür wird angenommen, dass wie bereits in Kapitel 2 erwähnte, das Koordinatensystem am Schaltknauf das absolute Koordinatensystem ist. Die weiteren Prozessteilnehmer sind relativ zu diesem Punkt zu sehen und in der Lage die Bahnplanung entsprechend zu berechnen.

![image](https://github.com/user-attachments/assets/2a9e7584-3e3f-4982-8485-c8f194e64869)    
*Abbildung 1-3: Montagezelle für das Einbringen das Leitungssatzes*

Die Teilprozesse, die mit dem Einbringen der Packtasche in die Karosserie einhergehen, sind:

1.  Das Anfahren des Anlieferungspunkt
2.  Die Grobausrichtung der Packtasche im Innenraum
3.  Ablage der Transporttasche innerhalb der Karosserie

### Das Anfahren des Anlieferungspunktes

Der Montageprozess wird durch die Anlieferung der Packtasche ausgelöst, hierbei wird ein Endschalter betätigt, der signalisiert, dass die Packtasche an einem definierten Ort innerhalb der Montagezelle abgelegt wurde. Somit kann der Roboter, der sich auf einer Konstruktion befindet, die es ihm erlaubt, den Weg vom Anlieferungspunkt zur Karosserie zu überbrücken, mit dem Anfahrprozess beginnen. Die Kontrolle, ob es sich hierbei um die „richtige“ Packtasche mit dem richtigen Leitungssatz handelt, wird bereits bei der Anlieferung an das Montagewerk überprüft, und muss somit nicht erneut überprüft werden, d.h. die Anlieferung der Komponente Leitungssatz erfolgt nach der [Just-in-Sequence Methode (JIS)](https://de.wikipedia.org/wiki/Just-in-sequence-Produktion)[^1].

[^1]: <https://de.wikipedia.org/wiki/Just-in-sequence-Produktion>

Nachdem das Startsignal ausgelöst wurde, fährt der Roboter mit entsprechenden Greifern die Henkel der Packtasche an. Für die Bahnplanung zu den Transporthenkeln werden einige Inputparameter benötigt. Grundsätzlich muss überlegt werden, ob für die Bahnplanung statische Parameter hinterlegt, sein müssen, oder diese automatisiert durch ein Kamerasystem erkannt und berechnet werden oder ob eine Kombination von Beidem sinnvoll ist. Beispielsweise können statische Parameter für die Anfahr-, Transport- und Abbremsgeschwindigkeit festgelegt werden und das Erkennen von Position und Orientierung der Transporthenkel (welche formstabil ausgeführt sein müssen), kann durch ein Kamerasystem erkannt werden. Wird davon ausgegangen, dass ein Kamerasystem auf dem Endeffektor montiert ist, welches einen Abgleich von CAD-Daten und der Ist-Situation ermöglicht, können formstabile Transporthenkel erkannt, und ein dynamisches Anfahren umgesetzt werden. Hierfür sind spezielle Greifer zu entwickeln, die in der Lage sind die formstabilen Transporthenkel zu greifen. Eine beispielhafte Darstellung ist in *Abbildung 1-4* dargestellt. Beide Ausprägungen sind starr, durch die Form der unteren Ausprägung, kann das Einfädeln der Transporthenkel jedoch vereinfacht werden.

![image](https://github.com/user-attachments/assets/5b33ab3d-6236-456d-a1d2-7b0411699cf3)     
*Abbildung 1-4: Greifer zum Greifen der Transportlaschen*

**Datenbedarfe***: Für das Greifen der Transporthenkel an der Packtasche müssen die geometrischen Abmessungen (hxbxt) von Packtasche und der explizite Greifpunkt der Transporthenkel durch Koordinaten oder Bildgebung beschrieben bzw. erkennbar sein. Für die Bahnplanung werden Input-Parameter wie Beschleunigung, Fahrgeschwindigkeit, Orientierung und Positionierung des Tool Center Point (TCP) benötigt. Die CAD-Modelle müssen kinematische Daten und Störkonturen bereitstellen.*

**Fähigkeiten***: Positionieren (Beschreibung der kartesischen Koordinaten einer Komponente im Raum), Orientierung (Beschreibung der rotatorischen Achsen im Raum einer Komponente), Greifen (Ein Produkt mit definierten Maßen durch einen Roboter neu zu arretieren oder positionieren zu können, bspw. anheben) und Greifpunktermittlung.*

![image](https://github.com/user-attachments/assets/2641eccd-5e1f-4119-a228-b9e64013cadf)    
*Abbildung 1-5: Hauptkoordinatensystem der Montagezelle*

Nachdem der Greifer die Transporthenkel der Tasche gegriffen hat, kann das Anheben der Packtasche beginnen. Hierfür werden die Parameter für die Bahnplanung erneut benötigt. Um eine Kollision beim Einbringen der Packtasche in die Karosserie zu vermeiden, wird die Packtasche in einer mittig zur Türöffnung ausgerichteten Bahn in die Karosserie transportiert. Hierfür kann bspw. das CAD-Modell der Karosserie und die Geometrien der Türöffnung in Verbindung mit dem 0-Punktkoordinatensystem verwendet werden. Für die Ausführung des Prozesses spielen einige Produktstammdaten (Abmessungen (Packtasche und Karosserie, Gewicht etc.) und Maximalwerte für den Transportparameter (Geschwindigkeiten) eine Rolle.

**Datenbedarfe***: Für die Bahnausführung werden gewisse Input Parameter wie Beschleunigen, Fahrgeschwindigkeit, Orientierung und Positionierung des TCP benötigt. Des Weiteren Kinematische Daten, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem).*

**Fähigkeiten***: Führen (Das Durchführen eines Produktes durch eine Öffnung in der Karosserie von zwei verschiedenen Seiten), Positionieren (Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum), Orientieren (Beschreibung der rotatorischen Achsen im Raum einer Komponente.)*

Nun ist das Anheben und die Positionierung relativ zur Karosserieöffnung durchgeführt, und der Roboter kann die Packtasche in den Karosserieinnenraum fahren.

### Grobausrichtung der Transporttasche im Innenraum

Die Packtasche befindet sich nun im Innenraum des Fahrzeugs und der Roboter soll die Packtasche an einem vorgegebenen Ort innerhalb der Karosserie absetzten. Für die Ausführung dieses Prozesses müssen die Zielkoordinaten des Abstellortes, mögliche Störkonturen, sowie die Input Parameter für die Bahnplanung bekannt sein.

**Datenbedarfe***: Bahnplanung (Zielkoordinaten des Ablageorts, Input Parameter wie Beschleunigen, Fahrgeschwindigkeit, Orientierung und Positionierung des TCP benötigt). Kinematische Daten, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem).*

**Fähigkeit***: Führen (*Das Durchführen eines Produktes durch eine Öffnung in der Karosserie von zwei verschiedenen Seiten) *Positionieren (*Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum*), Orientieren (*Beschreibung der rotatorischen Achsen im Raum einer Komponente.*)*

### Ablage der Transporttasche innerhalb der Karosserie

Die Packtasche wird nun an den Zielkoordinaten abgesetzt und der Roboter fährt ohne eine Kollision kontrolliert aus der Karosserie heraus und begibt sich in die Eingangsposition.

**Datenbedarfe***: Bahnplanung (Zielkoordinaten Eingangsposition, Input Parameter wie Beschleunigen, Fahrgeschwindigkeit, Orientierung und Positionierung des TCP benötigt). Kinematische Daten, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem).*

**Fähigkeiten***: Führen (*Das Durchführen eines Produktes durch eine Öffnung in der Karosserie von zwei verschiedenen Seiten) *Positionieren (*Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum*), Orientieren (*Beschreibung der rotatorischen Achsen im Raum einer Komponente*).*

## <a name="_4.3"></a>4.3Grobauslegung des Leitungssatz

In diesem Kapitel soll sich der Grobauslegung des Leitungssatzes im Fahrzeug gewidmet werden. Der Startzustand sieht wie folgt aus, die LS-Tasche liegt in der Karosserie muss jedoch, bevor die Auslegung durchgeführt werden kann, noch geöffnet werden. Es wird angenommen, dass es sich bei dem Verschluss um einen Klettverschluss handelt, der erkannt und entsprechend geöffnet werden muss. Die einzelnen Stränge sind durch eine Markierung erkennbar, die eine Aussage geben, ob der Strang in Richtung des Motors oder des Kofferraums gelegt werden muss und auf welcher Seite (Fahrer/Beifahrer) der Strang abgelegt werden muss. Es wird angenommen, dass ein zweiter Roboter für die Tätigkeiten innerhalb der Karosserie notwendig ist, da die Anforderungen an Wendbarkeit und Traglast voneinander abweichen.

### Transporttasche Öffnen

Die Tasche liegt durch einen Klettverschluss verschlossen in der Mitte der Karosserie. Um den Verschluss anfahren zu können, müssen die Verschlüsse für den Roboter erkennbar (bspw. durch Apriltag oder Datamatrix als visuelles Referenzsystem) und die notwendigen Informationen zur Öffnung bekannt sein. Dies können Bewegungsparameter und -informationen sein, in welcher Richtung der Greifer zur Öffnung des Verschluss bewegt werden muss, o.ä. Der Prozess kann je nach Anzahl der Verschlüsse mehrmals wiederholt werden, dies soll bei der Grundsätzlichen Beschreibung jedoch keine Rolle spielen. Somit können folgende Informationsbedarfe und Fähigkeiten abgeleitet werden:

**Datenbedarfe***: Zielkoordinaten, Bahnplanung (Input Parameter wie Beschleunigen, Fahrgeschwindigkeit, Orientierung und Positionierung des TCP benötigt). Kinematische Daten, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem), Greifpunktermittlung*

**Fähigkeiten***: Führen (Das Führen des Klettverschlusses zum Öffnen der Tasche), Positionieren (Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum), Orientieren (Beschreibung der rotatorischen Achsen im Raum einer Komponente.)*

### Leitungssatzstränge im Innenraum auslegen

Nach der Öffnung der Transporttasche liegen die einzelnen Stränge entsprechend einer Packanleitung in der geöffneten Packtasche. Das Entfernen der Packtasche kann erstmal vernachlässigt werden, da der Fokus auf dem Auslegen der einzelnen Stränge liegt. Nun muss ein Abgleich mit den möglichen Erkennungsmerkmalen der einzelnen Stränge und dem jeweiligen Zielort umgesetzt werden. Es wird davon ausgegangen, dass die Stränge in wiederum einzelnen Schläuchen verpackt sind, die ein verknoten der einzelnen Abgänge verhindern und somit das Auslegen vereinfachen soll. Die Informationen, an welchen Zielort die einzelnen Stränge gezogen werden müssen, müssen durch ein übergeordnetes System zur Verfügung gestellt werden. Diese sind kein Bestandteil der Produktverwaltungsschale. Der Greifer fährt nun die einzelnen Stränge an, muss die einzelnen Greifpunkte der jeweiligen Stränge identifizieren und diese in die Zielposition und -orientierung bringen. Grundsätzlich soll das Vorgehen auch für weitere Auslegeprozesse angewendet werden können, bspw. das Verschieben von Kanälen im Cockpitinnenraum. Bei der Auslegung in Richtung des Kofferraums, müssen aufgrund der fehlenden Metallwand im Bereich der Rücksitze die Überzieher der ausgelegten Stränge nach der Grobauslegung bereits entfernt werden.

**Datenbedarfe***: Zielkoordinaten, Bahnplanung (Input Parameter wie Beschleunigen, Fahrgeschwindigkeit, Orientierung und Positionierung des TCP benötigt). Kinematische Daten, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem), Greifpunktermittlung, Produktspezifikationen*

**Fähigkeiten***: Führen (Das Durchführen eines Produktes durch eine Öffnung in der Karosserie von zwei verschiedenen Seiten), Positionieren (Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum), Orientieren (Beschreibung der rotatorischen Achsen im Raum einer Komponente.)*

### Leitungssatz am Fahrzeugboden montieren

Nach Fertigstellung der Grobauslegung, wird mit der Befestigung der Hauptverlegewege des Leitungssatzes im Fahrzeuginnenraum begonnen.

**Datenbedarfe***: Zielkoordinaten (zum Stecken der Befestigungselemente), Bahnplanung (Input Parameter wie Beschleunigen, Fahrgeschwindigkeit, Orientierung und Positionierung des TCP benötigt). Kinematische Daten, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem), Greifpunktermittlung, Produktspezifikationen (bspw. Abmessung der jeweiligen Produkte)*

**Fähigkeiten***: Führen (Stecken der einzelnen Befestigungselemente in die in der Karosserie vorgesehenen Befestigungselemente), Positionieren (Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum), Orientieren (Beschreibung der rotatorischen Achsen im Raum einer Komponente.).*

## <a name="_4.4"></a>4.4 Durchführung von Fädelprozessen

Unter Fädeln wird üblicherweise das Durchführen von Leitungssatzsträngen durch Karosseriedurchbrüche verstanden.

Grundsätzlich kann beim Fädeln zwischen Ziehen und Schieben unterscheiden werden. Für einen „einarmigen“ Roboter sind beide Techniken problematisch. Das Ende des Leitungsstranges mit dem jeweiligen Steckergehäuse bis zu dem Durchbruch bspw. in Richtung des Motorraums zu manövrieren, ist grundsätzlich kein Problem. Herausfordernd werden die zur Seite abzweigenden Leitungsstränge während des fädeln durch die Öffnung in Richtung des Motorraums. Die Stecker können am Durchbruch verkanten und zu einer Beschädigung des Leitungssatzes und Funktionsverlust führen.

Möglicher Lösungsansatz:

-   Die Leitungsstränge, welche durch Karosseriedurchbrüche geführt werden, sind bereits in verschiedenfarbige Packsäcke verpackt

In diesem Dokument soll vermehrt auf die technische Umsetzbarkeit und die dafür notwendigen Informationen bzw. Parameter eingegangen werden. Wird davon ausgegangen, dass der Leitungssatz im Cockpitraum vollständig durch den vorherigen Prozessschritt „Grobauslegung“ ausgebreitet wurde, muss sich nun der Umsetzung des Fädelprozesses gewidmet werden. Das bedeutet, dass sich im nächsten Schritt der Erschließung der jeweiligen Leitungsstrangenden und der jeweiligen Angriffspunkte gewidmet werden muss.

### Lokalisieren des Einzelstrangs

Für die Lokalisierung des zu greifenden Leitungsendes muss das Kamerasystem auf dem Greifarm den richtigen Leitungsstrang erkennen. Das wäre durch eine Erkennung des jeweiligen Produktes oder ein Vision System umsetzbar. Hierbei wird ein Abgleich mit der durch das Kamerasystem erzeugten Punktewolke und dem originalen CAD-Modell in der richtigen Position und Orientierung durchgeführt. Die grobe Positionierung des jeweiligen Leitungsendes ist bereits durch die Grobauslegen bekannt.

**Datenbedarf***: Bündelquerschnitt bzw. Bündeldurchmesser, Masse des Teilleitungsstrangs, Angriffspunkte der jeweiligen Leitungen, Zielkoordinaten des Durchbruchs, Durchmesser der Karosserieöffnung, Bahnplanung*

**Fähigkeiten***: Führen (Das Durchführen eines Produktes durch eine Öffnung in der Karosserie von zwei verschiedenen Seiten), Positionieren (Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum), Orientieren (Beschreibung der rotatorischen Achsen im Raum einer Komponente.), Greifpunktermittlung, Greifen*

### Greifen des Einzelstrangs

Das Greifen und schlussendlich anheben, kann nicht an jeder Stelle entlang des Stranges durchgeführt werden. Die Angriffspunkte müssen optisch oder durch definierte Koordinaten kenntlich gemacht werden, damit der Roboter nicht an Gehäusen oder anderen unvorteilhaften Positionen angreift, diese anhebt und schlussendlich durch die Aufgebrachte Zugkraft gesteckte Pins löst oder Gehäuse zerstört. Die Ermittlung des Greifpunktes muss durch den Abgleich zwischen Punktewolke und CAD-Model geschehen.

1.  Der Greifer fährt zum definierten Aufenthaltsort und erkennt dort optisch den gesuchten Leitungsstrang. Dies kann durch unterschiedliche farbige Netzschläuche unterstützt werden.
2.  Greifen des Stranges in einem Sicherheitsabstand hinter dem Gehäuse

    **Datenbedarf***: Produktstammdaten (Durchmesser, Gewicht), Greifkoordinaten*

    **Fähigkeiten***:* **Greifpunktermittlung***,* **Greifen** *(Ein Produkt mit definierten Maßen durch einen Roboter neu zu arretieren oder positionieren zu können (bspw. anheben)*

### Leitungsende zum Durchbruch bewegen

Die grobe Position eines Durchbruchs ist durch die 3D-Daten der Karosserie bekannt. Der Roboter bewegt sich mit dem gegriffenen Leitungssende und einem Sicherheitsabstand zur Karosserie in Richtung des Durchbruchs. Die genaue Position der Durchbruchsmitte wird durch den Abgleich der CAD-Datei und des Kamerasystems am Endeffektor korrigiert. Der herbeizuführende Zielzustand muss eine möglichst mittige und rechtwinklige Ausrichtung des Leitungsstranges vor dem Durchbruch herbeiführen. Dazu ggf. Position und Winkel des Greifarmes korrigieren, um das Gehäuse mittig vor dem Durchbruch zu positionieren und das Ende des Leitungsstranges annähernd senkrecht zur Oberfläche der Trennwand auszurichten.

**Datenbedarf***: Mittelpunkt des Bündels, Mittelpunkt des Durchbruchs, Kinematische Informationen, Bahnplanung, Zielkoordinaten, Produktstammdaten (Geometrische Informationen des Strangs), Bahnplanung*

**Fähigkeiten***: Greifen, Greifpunktermittlung, Bahnplanung*

### Leitungsende einfädeln

Der Fädelprozess kann in der Regel nicht von einem einzelnen Greifarm bewältigt werden, da die beiden beteiligten Bauräume (Cockpit und bspw. Heck- oder Motorraum) durch eine Trennwand voneinander separiert sind. Es muss somit ein zweiter Roboter das Ende des Leitungsstranges auf der anderen Seite des Durchbruchs annehmen und durch eine aufgebrachte Zugkraft in eine vorgegebene Position bringen und anschließend ablegen. Wichtig hierbei ist, dass die Zugkraft nicht größer als die Schubkraft sein darf, sonst würde der Greifer inkl. Strang innerhalb der Karosserie in Richtung der Karosseriewand „gezogen“ werden.

Während des Greifens, ist es wichtig, dass der Leitungsstrang nicht an einem Steckergehäuse gegriffen und anschließend daran gezogen wird. Dies könnte dazu führen, dass mechanische Verbindung von Pins und Stecker oder anderen Verbindungen gelöst, eine Beschädigung und somit ein Fehlerfall produziert wird. Der Leitungsstrang inklusive des Überzugs muss durch das Kamerasystem auf dem Greifarm lokalisiert werden. Der Strang muss in ausreichendem Abstand hinter dem Strangende gegriffen werden. Das Ziehen muss langsam erfolgen, dabei muss permanent die Schub- und Zugkraft bzw. der Widerstand überwacht werden. Das Ende des Prozesses, muss durch eine Überwachung des zurückgelegten Weges erfolgen. Das Ende des Stranges (außerhalb des Cockpits) wird an einer definierten Position abgelegt.

**Datenbedarf***: Zielposition des Greifers: Die grobe Position des Durchbruchs ist durch die 3D Daten der Karosserie bekannt. Der Greifarm bewegt sich in einem Sicherheitsabstand vor die erwartete Position des Durchbruchs. Die genaue Position wird durch optische Erkennung des Durchbruchs durch die Kamera am Greifer korrigiert.*

**Fähigkeiten***: Bahnplanung, Greifpunktermittlung, Greifen*

Ein innovativerer Ansatz, könnte die Entwicklung eines Fördergreifers sein (siehe *Abbildung 1-6*). Hierbei würde die Leitung (in der *Abbildung* Kupferfarben dargestellt) von einem Greifer (in der *Abbildung* Blau dargestellt) umschlossen werden. Auf der Innenseite des Greifergehäuses hat der Greifer zwei oder mehr Förderrollen, die durch eine Drehbewegung den Strang in eine definierte Richtung befördern können. Somit könnte eine Schubbewegung auf den Strang ausgeübt und dieser durch den Durchbruch geschoben werden. Die Konstruktion würde den zweiten Roboter jedoch nicht ersetzten, lediglich das Fädeln vereinfachen. Denn der zweite Greifer müsste das Ende des Leitungsstrangs immer noch außerhalb des Cockpits annehmen und an die Zielposition führen.

![image](https://github.com/user-attachments/assets/7d26c3ae-2b03-4884-ba47-6c9a042c0ac1)    
*Abbildung 1-6: Idee: Fördergreifer als mögliche Lösung*

## <a name="_4.5"></a>4.5 Dichtungselemente befestigen

An den Durchbrüchen dient das Dichtungselement oder die Kabeltülle als Schutz gegen mechanischen Verschleiß zwischen Kabelbündel und Karosserieteil sowie Schutz gegen Eindringen von Wasser zwischen zwei Karosseriebereiche. Während des Herstellungsprozess des Leitungssatzes, werden die notwendigen Leitungen durch die Kabeltülle eingebracht und befestigt. Je nach seiner Einbaurichtung kann die Befestigung eines Dichtungselements an den Durchbrüchen auf zwei Arbeitsprozessen unterschieden werden.

![image](https://github.com/user-attachments/assets/0f32a8d9-6c65-4740-ba46-e65fbb0d2a83)    
*Abbildung 1-7: Kabeldichtungen (Quelle: https://www.woco-kkw.com)*

Axiale Einbaurichtung zum Durchbruch an der Karosserie:

Diese Art von Einbaurichtung ist ein Folgeschritt nach dem Fädelprozess (siehe Kapitel *Abbildung 1-7*). Daher ist die grobe Positionierung der Dichtung durch den Abschluss des Fädelprozesses bereits erfolgt.

### Lokalisieren des Dichtungselements

Die Dichtung liegt somit vor dem Durchbruch der Karosserie, in einer undefinierten Position und Orientierung. Als Grundlage müssen die Ist-Position und Orientierung des Elements erkannt werden.

**Datenbedarf***: Koordinaten der Ist-Position des Karosseriedurchbruches, Bahnplanung, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem),*

**Fähigkeiten***: Positionieren (*Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum*), Orientieren, Führen.*

### Grobpositionierung des Dichtungselements

Der Roboterarm greift das Dichtungselement an den vordefinierten Angriffspunkten und bringt es in die definierte Orientierung und Position vor dem Durchbruch.

**Datenbedarf***: Koordinaten des Greift-Punkt, max. zul. Greifkraft, Bahnplanung, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem), Zielkoordinaten Karosseriedurchbruch*

**Fähigkeiten***: Positionieren (*Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum*), Orientieren.*

### Feinpositionierung des Dichtungselements

Ist die Grobpositionierung des Dichtungselements relativ zum Karosseriedurchbruch erfolgreich umgesetzt worden, muss die Dichtung in den dafür vorgesehenen Durchbruch eingesetzt werden. Hierfür greift der 2. Roboterarm die bereits durch den Durchbruch gefädelte Leitung und zieht die Dichtung, bis Kontakt zwischen der nach außen gerichteten Dichtungslippe und der Karosserie besteht. Die Parallele und zentrische Ausrichtung von Dichtung und Durchbruch muss hierbei während der ausgeführten Bewegung durch das Kamerasystem überprüft und wenn notwendig justiert werden.

**Datenbedarf***: Zielposition Dichtungselement, Produktabmessung der Dichtung, Bahnplanung*

**Fähigkeiten***: Führen, Positionieren (*Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum*), Orientieren.*

### Befestigung des Dichtungselements

Der tatsächliche Befestigungsprozess erfolgt von der „End“-Seite der Karosserie. Der Roboterarm greift die vordere Seite des Dichtungselements und zieht dieses, bis die Dichtung in der dafür vorgesehenen Aussparung sitzt. Das Dichtungselement hat mehrere „Dichtungslippen“, die i.d.R. einen größeren Durchmesser als die Karosserieöffnung besitzen. Diese Dichtungslippen müssen durch die Öffnung gezogen werden, um das Abschotten von Innenraum (Trockenraum) zu bspw. Motor (Nassraum) gewährleisten zu können.

**Datenbedarf***: Zielposition Dichtungselement, Koordinaten vom Greift-Punkt, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem), Soll-Drück- bzw. Zugkraft.*

**Fähigkeiten***: Führen, Positionieren (*Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum*), Orientieren, Kraft-Überwachung*

![image](https://github.com/user-attachments/assets/dde5c8d6-c6b6-43eb-92e4-db08117a286f)    
*Abbildung 1-8: Dichtungselement mit axialer Einbaurichtung.*

### Senkrechte Einbaurichtung zur Aussparung der Karosserie

Diese Art von Einbaurichtung ist ein Folgeschritt nach dem Fädelprozess (siehe Kapitel 1.4). Daher ist die grobe Positionierung der Dichtung durch den Abschluss des Fädelprozesses bereits erfolgt. Für den Senkrechten Einbau der Dichtung, wird die Ist-Position und Orientierung der Dichtung festgestellt. Anschließend wird der Strang gegriffen und in die notwendige Zielposition oberhalb des Durchbruchs, siehe gebracht. Somit wird auch bei der senkrechten Einbauweise zu Beginn die Ist-Position und Orientierung berechnet.

**Datenbedarf***: Koordinaten der Soll-Position des Dichtungselements, Bahnplanung, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem), Zielkoordinaten des Karosseriedurchbruchs*

**Fähigkeiten***: Positionieren (*Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum*), Orientierung.*

Ist das Dichtungselement in der richtigen Position und Orientierung, wird es über die Aussparung positionierte. Die Position und Orientierung des Dichtungselements relative zur Aussparung wird optisch noch einmal überprüft. Falls keine Abweichungen erkannt werden, wird das Dichtungselement in die Aussparung gesenkt.

**Datenbedarf***: Koordinaten der Soll-Position des Dichtungselements, Bahnplanung, Störkonturen (CAD-Modelle oder Erkennung durch das Kamerasystem), Zielkoordinaten der Aussparung*

**Fähigkeiten***: Führen, Positionieren (*Beschreibung der Position (X-, Y-, oder Z-Achse) einer Komponente im Raum*), Orientieren, Kraft-Überwachung.*

![image](https://github.com/user-attachments/assets/fffb8b36-4c4e-4981-b9a4-8c86a3483025)    
*Abbildung 1-9: Radiale Einbaurichtung*

## <a name="_4.6"></a>4.6 Strangbefestigung

Die Absprungbasis, für die in dem nachfolgenden Absatz beschriebenen Tätigkeiten ist, dass die unter Kapitel 1.1 beschriebene Grobauslegung und Befestigung des Leitungsstrangs bereits erfolgt ist. Das heißt, alle Hauptabgriffe sind bereits in einer der Endlage angenäherten Position verlegt.

Die folgenden Schritte zur Befestigung des Leitungsstranges werden in drei Kategorien unterteilt, um die spezifischen Anforderungen, die diese Vorgänge aufweisen, in den entsprechenden folgenden Unterkapiteln detaillierter darzustellen.

Die Reihenfolge wie der Leitungssatz in der Karosserie befestigt wird lässt sich laut Aussage der Teilnehmer in diesem TP nicht weiter ausarbeiten. Dazu würden mehr Daten benötigt, wann und in welchen Montageabschnitten welche Verlegearbeiten am Leitungssatz gemacht werden. Wenn diese Daten vorhanden wären -am besten über mehrere Baureihen hinweg- könnte evtl. dazu eine Aussage gemacht bzw. Richtlinie erarbeitet werden.

Gewisse Verlegearbeiten werden immer individuell je Fahrzeugderivat sein und müssen ohnehin immer für das entsprechende Derivat eigens geplant werden. Es ist auch wahrscheinlich, dass erst Steckverbindungen hergestellt werden müssen, bevor die letzten Clipse des Abgriffes befestigt werden dürfen.

### Clipse und Halterungen befestigen

Clipse gibt es in unterschiedlichen Ausführungen. Zum einen unterscheiden sie sich in der Art wie diese am Leitungssatz befestigt werden (welche hier aber nicht genauer betrachtet wird), und zum anderen, wie die Art der Befestigung an der Karosserie realisiert wird. Anschließend werden die gängigsten Ausprägungen zur Befestigung an der Karosserie gezeigt.

-   Kante
-   Bolzen
-   Langloch
-   Rundloch
-   Schraubbefestigung
-   Rohr- und Schlauchhalterung

Tabelle 4-1: Bilder aus dem Onlinekatalog von [Hellermann Tyton](https://www.hellermanntyton.de/produkte/befestigungselemente)

![image](https://github.com/user-attachments/assets/3915121e-ee36-492c-a46e-9ee0cb0def49)    

Im CES-Arbeitskreis wurde ein Leitfaden zur Erstellung von Elektrik-Bauteilen mit CATIA V5 (Version 2.6 Stand: 18.05.2010) erstellt. Die darin aufgeführten Konstruktionsrichtlinien, speziell für die Clips, sollen als Grundlage herangezogen werden für die standardisierte Kategorisierung dieser Bauteile. Folgendes ist im Leitfaden dazu beschrieben:

Die Positionierung der Bauteilgeometrie im CATPart (natives Dateiformat von Catia V5) ist wie folgt vorzunehmen:

-   Der Ursprung des Bauteils liegt im Schnittpunkt der Auflagefläche des Clips (im montierten Zustand) mit der Mittelachse des Rastzapfens, der Bolzenaufnahme oder des Lochs bzw. Langlochs (je nach Befestigungsart).
-   Die Y-Achse liegt in der Ebene der Auflagefläche, und ist parallel zu der Richtung orientiert, in der der Kabelbaum durch den Clip geführt wird.
-   Die Z-Achse steht normal zur Ebene der Auflagefläche und zeigt entgegen der Montagerich-tung des Clips.
-   Bei Befestigungselementen, die auf eine Kante aufgesteckt werden (siehe *Abbildung* 5.41), liegt der Ursprung des Bauteils im Schnittpunkt der Auflagefläche des Bauteils (im montierten Zustand) mit der Mitte der seitlichen Anlagefläche des Bauteils am Blech

![image](https://github.com/user-attachments/assets/0ece2460-f515-4441-a7c5-0faea5934c42)    
*Abbildung 1-10: Clip mit Bolzenaufnahme*

![image](https://github.com/user-attachments/assets/eb044e42-3d60-4f39-8e8e-6d25e21467d9)    
*Abbildung 1-11: Kantenbefestiger*

Mit Hilfe dieser einheitlichen konstruktiven Vorgaben lässt sich eine einfachere Montage der Befestigungselemente realisieren, durch die Standardisierung des Ursprungspunktes/Nullbezugspunkt und des festgelegten Achsensystems.

Aus den CAD-Modellen sind die Positionen der Clipse sowie deren Orientierung im Bezug zur Karosserie und dessen Achsen-/Koordinatensystem bekannt. Diese Informationen müssen über die Verwaltungsschale transportiert werden.

Bei der Leitungssatzkonstruktion bekommen die Clipse eine eindeutige ID zugewiesen. Diese ID ist wiederum mit einem Stammdatum verknüpft, welche das exakte Bauteil (Instanz) identifiziert. Diese Bauteilstammdaten sollten zur einfacheren Handhabung mit einem Merkmal versehen werden, um welche Karosseriebefestigungsart es sich handelt, damit der Roboter das Handling auf den spezifischen Clip einstellen kann. Ein Offset eines Steckers, kann durch ein Vision System erkannt und angefahren werden. Hierbei zählt lediglich die Richtung des Kraftvektors.

Annahme:

Analog zum Leitungssatz haben auch Bolzen, Löcher usw. eine eineindeutige ID, diese müsste vorhanden sein, um eine automatisierte prozessuale Fertigung bei der Karosseriefertigung realisieren zu können. Die IDs der Karosseriebefestigungen und der Clipse müssen eine Referenz zueinander aufweisen, diese dann für die Zuordnung beim Montageprozess verwendet werden kann.

Zwei wesentliche Herausforderungen bei der Befestigung des Leitungsstranges müssen noch geklärt werden:

-   Identifizierung der am Leitungssatz verbauten Clipse und die entsprechende Zuordnung zu den in der CAD-Konstruktion vergebenen IDs.
-   Ermittlung der Greifpunkte, die sich durch sich ändernde Geometrien des kundenspezifischen Leitungsstranges ergeben und je nach Varianten des Clips unterschiedlich sein können. Zusätzlich müssen Angriffspunkte definiert werden, damit die Montagekräfte ohne Schädigung des Bauteils ausgeübt werden können. Die notwendigen Informationen sind in der 100%-Variante hinterlegt.

    **Datenbedarf***: Koordinaten inkl. IDs der Befestigungen der Karosserie; Art des Clips zu jeder ID; Verarbeitungsrichtung (Verarbeitungskoordinaten) des Clips und der Karosseriebefestigung; Montagekräfte*

    **Fähigkeiten***: Identifizieren des Clips, Erkennen der aktuellen Ausrichtung; Greifen von sich ändernden Gegebenheiten, Fügen des Bauteils in Endlage; Kräftemessung*

### Kabelkanäle und komplexe Halterungen befestigen

Die Befestigungsarten von Kabelkanälen, die bei Anlieferung des Leitungssatzes am Leitungssatz befestigt sind, lassen sich im Grunde, bezüglich der Befestigungsvarianten an der Karosserie, analog zu den Clipsen ableiten. Der Unterschied besteht darin, dass es mehrere Befestigungspunkte an einem Bauteil geben kann. Und dass unterschiedliche Ausprägungen von Befestigungen an einen Bauteil vorliegen können, z.B. ein Teil der Befestigungen ist für Rundlöcher und anderer Teil für Bolzen.

In der Leitungssatzkonstruktion hat der Kabelkanal als Ganzes eine eindeutige ID aber nicht jeder Befestigungspunkt.

**Datenbedarf***: Druckpunkte für die Befestigung; Montagekräfte; evtl. eine Reihenfolge zur Montage; Koordinaten inkl. IDs der Befestigungen der Karosserie;* *Art des Befestigungspunktes an den Kabelkanälen zu jedem Befestigungspunkt; Verarbeitungsrichtung (Verarbeitungskoordinaten) des Kabelkanals als Ganzes oder für jeden Befestigungspunkt einzeln und der Karosseriebefestigung, Output Informationen (Kräftemessung)*

**Fähigkeiten***:* *Identifizieren des Kabelkanals, Erkennen der aktuellen Ausrichtung; Greifen; Fügen des Bauteils in Endlage;*

### Einlegen in Kabelkanäle und Schließen des Deckels

In diesem Punkt soll die Verlegung in Kabelkanälen betrachtet werden, die nicht wie im Kapitel 1.6.2 am Leitungssatz befestigt sind, sondern in der Karosserie montiert sind bevor der Leitungssatz darin verlegt wird.

Nicht näher betrachtet wird, wie die Kabelkanäle in die Karosserie befestigt werden. Es ist aber davon auszugehen, dass dies ähnlich wie in Punkt 7.1.2 auch im Vorfeld dann von einem Roboter übernommen werden könnte.

Für das Einlegen in den Kabelkanal müssen entweder das vollständige Routing oder Routingpunkte festgelegt werden. Hierfür müssen zusätzlich die EIntriis bzw. Austrittspunkte der Stränge definiert werden.

Nach dem Einlegen kann es eine Herausforderung sein, dass der Leitungssatz nicht in der gewünschten „Verlegebahn“ bleibt. Denn es kann je nach der Dicke des Bündels wegen der erhöhten Steifigkeit oder fehlendem Eigengewicht etc. vorkommen, dass das Leitungsbündel die angedachte Verlegeposition wieder verlässt.

![image](https://github.com/user-attachments/assets/3a1eedf9-cb34-4485-a2be-e053eab8d5f1)    
*Abbildung 1-12: Abbildung eines Kabelkanals mit Hilfselementen (Quelle: Dräxlmaier)*

Der Leitfaden zur Erstellung von Elektrik-Bauteilen mit CATIA V5 (Version 2.6 Stand : 18.05.2010) zeigt, wie in der *Abbildung* oben zu sehen ist, dass Kabelkanäle bereits mit Hilfs- und Referenzpunkten sowie Referenzplane konstruiert werden.

**Datenbedarf***: Routingweg/Routingpunkte; Befestigungsmechanismus des Leitungsstrangs im Kabelkanal falls vorhanden z.B. Kabelbinder; Befestigungsmechanismus Kabelkanaldeckel; Kräfte für Schließung des Deckels;*

**Fähigkeiten***: Greifen; Fügen des Bauteils in Endlage; Kräftemessung; Erkennung von Abgriffen für mehrere Ausbindemöglichkeiten*

## <a name="_4.7"></a>4.7 Steckverbindung herstellen

Nachfolgend wird über den Aufbau und die Lage von Steckverbindungen eingegangen und wie diese Definition bei der automatisierten Montage des Leitungssatzes verwendet werden kann. Dies stellt nur eine Möglichkeit dar dies zu realisieren. Weitere Möglichkeiten sind denkbar werden aber hier nicht betrachtet.

Um Steckerverbindungen zwischen verschiedenen Leitungssätzen (Trennstellen) oder Aggregaten, wie beispielsweise Steuergeräte, Sensoren, Aktoren usw., und dem Leitungssatz herzustellen, sind verschiedene Daten notwendig. Hierzu müssen einheitliche konstruktive Richtlinien gegeben sein, um nicht für jede mögliche Verbindung individuelle Daten zu erzeugen. Des Weiteren müssen produktbezogene Daten vorhanden sein, um eine prozesssichere Herstellung der Steckverbindung zu gewährleisten. Im TP3 wurde hierfür bereits die Grundlagen (CAD2BOP) erarbeitet.

### Konstruktive Gegebenheiten

Zur Konstruktion von Steckerverbindungen wird auf den Leitfaden des CES-Arbeitskreises zur Erstellung von Elektrik-Bauteilen mit CATIA V5 (Version 2.6 Stand: 18.05.2010) Bezug genommen, der folgende Richtlinien enthält:

*Die Positionierung der Bauteilgeometrie im CATPart ist wie folgt vorzunehmen:*

-   *Der Ursprung des Bauteils liegt in der Ebene der elektrischen Anlagefläche in der Lochmitte der Kammer/Pin mit dem kleinsten alphanumerischen Zeichen, z.B. Kammer/Pin 1 oder A1.*
-   *Die Y-Achse liegt in der Ebene der elektrischen Anlagefläche und zeigt in Richtung der Kammer/Pin mit dem nächsthöheren alphanumerischen Zeichen, z.B. Kammer/Pin 2 oder A2, bei einpoligen Steckern in Richtung der Kodiernase, falls vorhanden.*
-   *Die Z-Achse steht normal zur Ebene der elektrischen Anlagefläche und zeigt in Richtung des Buchsengehäuses nach innen und vom Stiftgehäuse nach außen.*

![image](https://github.com/user-attachments/assets/0f94a512-ead8-420b-90f3-c9c50d446899)    
*Abbildung 1-13: Konstruktionsmerkmale von Steckverbindungen*

Diese konstruktiven Richtlinien müssen auch auf die Gehäuseaufnahmen von Aggregaten übertragen werden.

Die zuvor beschriebenen Informationen, bezüglich des Nullpunkts, Achssysteme, usw., sind für alle Steckverbindungen ausreichenden, wenn sich diese durch Fügung in Y-Richtung herstellen lassen und keine weiteren Elemente des Gehäuses betätigt werden müssen, um das Gehäuse in Endposition zu bringen (dazu nähere Informationen in Punkt 8.2).

Ausnahmen gelten für Steckverbindungen wie beispielsweise in der nachfolgenden *Abbildung* dargestellt. Hierbei ist das Fügen in Y-Richtung nicht möglich, sondern Bedarf einer speziellen Montagevor-gabe, bei der erst die „Rastnase“ eingehakt werden muss. Bei diesen Ausnahmen muss dann für die jeweilige Steckverbindung separat eine Beschreibung erstellt werden.

![image](https://github.com/user-attachments/assets/3830eda2-f201-41de-a7b6-cfc182144e93)    
*Abbildung 1-14: Steckverbindung mit Rastnase*

### Umsetzung der Steckverbindung im Fahrzeug

Wenn die Nullpunkte der Gehäuse und die Achssysteme entsprechend den Vorgaben wie unter Punkt 8.1.1 beschrieben konstruiert sind, ist die Endlage der Steckverbindung bereits definiert. Die Nullpunkte müssen übereinander liegen ebenso die Achssysteme der beiden Komponenten.

Der Nullpunkt und das Achssystem der zu kontaktierenden Komponente muss in Relation zum Achssystem und Nullpunkt der Karosserie sein, damit ein Roboter weiß, wo sich die Komponenten befinden. Die Komponenten habe eine eindeutige ID, so dass zu jeder ID ein eindeutiger Nullpunkt und Achssystem zugewiesen ist. Eine Ausnahme bilden Komponenten, die mehrere Gehäusepositionen haben, bei denen gibt es dann entsprechend der Anzahl der Positionen diese Zuordnungen. Diese Informationen müssen aus der VWS oder der CAD-Datei abgeleitet werden.

Die Gehäuse am Leitungssatz haben ebenfalls eine eindeutige ID, die den der Komponenten zugeordnet sind. In der Instanz-VWS dürfen dann auch nur die Gehäuse-IDs wieder zu finden sein, die der Konfiguration des Fahrzeuges entsprechen.

Es werden noch weitere Daten auf Stammdatenebene benötigt. damit eine automatische Fügung der Steckverbindungen hergestellt werden kann. Dazu zählen beispielsweise

-   Kragenhöhen, die den Mindestabstand der beiden Komponenten bestimmen, um die Fügung durchzuführen
-   Greifpunkte an denen ein Roboter das Gehäuse greifen darf mit Angaben zur maximalen Greifkraft
-   Bestückungshub/-weg (ggf. nicht notwendig, da die Steckverbindung hergestellt ist wenn die Nullpunkte übereinander/aneinander liegen)
-   Bestückungskraft, wird wahrscheinlich ein schwieriges Thema da je nach Anzahl an Terminals, die im Gehäuse verbaut sind, voraussichtlich auch wo die Terminals verbaut sind (einseitig oder gleichmäßig verteilt), andere Kräfte aufzubringen sind
-   Rückzugskraft, zur Prüfung ob die Steckverbindung richtig hergestellt wurde
-   Für nicht linear in Y-Richtung verfügbare Steckverbindungen muss eine Montagevorgabe gemacht werden die maschinenlesbar ist

**Datenbedarf***:* **siehe zuvor genannte Punkte***; Gehäuse-IDs; Nullpunkt und Achsensystem zu jeder Komponente; Komponenten-IDs inkl. Nullpunkt und Achssystem in Relation zum Fahrzeug;*

**Fähigkeiten***: Greifen; Fügen des Bauteils in Endlage; Kräftemessung; Erkennung von Abgriffen und. der Gehäuse*

### Verriegelungselemente von Gehäusen (z.B. CPA – Connector Position Assurance)

Es gibt verschiedene Verrieglungsarten bei Gehäusen, die meisten besitzen ausschließlich nur eine sogenannte Primärverrastung die sich bei einem korrekten herstellen der mechanischen Steckverbindung automatisch schließt. Beim Schließen bzw. Einrasten der Primärverriegelung gibt es eine akustische und haptische Rückmeldung, kann aber auch optische kontrolliert werden. Diese Primärverriegelungen lassen sich meist durch einfache Betätigungen einer Lasche o.ä. lösen, so dass sich die Steckverbindung wieder lösen lässt.

Für besonders sicherheitskritische Steckerverbindungen gibt es eine Sicherung, dass diese Primärverrastung nicht durch ein einfaches Betätigen von z.B. einer Lasche gelöst werden kann. Die Primärverriegelung wird durch ein zusätzliches Element gesichert und kann erst betätigt werden, wenn die Connector-Position-Assurance (CPA) wieder gelöst wird. Es gibt verschiedene Varianten von CPAs,

-   solche die sich jederzeit in Endposition schieben lassen, unabhängig ob eine Steckverbindung hergestellt ist oder nicht,
-   und die andere Variante, die sich erst betätigen lässt, wenn eine korrekte Steckverbindung hergestellt wurde (dient somit noch zusätzlich der Kontrolle), dass richtig gesteckt wurde.

#### Was ist eine CPA

Die CPA ist ein Mechanismus, der sicherstellen soll, dass ein Paar zusammengesteckter Steckverbinder zusammenbleibt, sobald sie zusammengesteckt sind. Das in *Abbildung 1-15* dargestellte Steckverbindersystems verfügt über eine kabelmontierte Buchse und über eine primäre Verriegelung. Die Verriegelung gleitet unter eine Halteklammer am Gegenstecker und fixiert die Steckverbinder in der gesteckten Position. Die Steckverbinder können nur getrennt werden, indem die primäre Verriegelung gedrückt wird, um sie vom Halteclip des Gegensteckers zu lösen.

![image](https://github.com/user-attachments/assets/6179f5cf-aa4a-456c-8f5e-c62f8ea53354)    
*Abbildung 1-15: Mini-Fakra Steckverbindersystem*

Um zu verhindern, dass sich die Steckverbinder lösen, gibt es eine einfache Lösung (siehe *Abbildung 1-15*). Indem die Bewegung der Verriegelung mit einer CPA-Vorrichtung eingeschränkt wird, kann die Verriegelung nicht betätigt werden und der Steckverbinder verbleibt in der gesteckten Position.

![image](https://github.com/user-attachments/assets/c312503e-fba6-4341-a394-0d02414a75a6)    
*Abbildung 1-16: Funktionsweise CPA-Vorrichtung*

Die Positionssicherung ist für die Installation von Steckverbindungen in der Automobilindustrie von entscheidender Bedeutung. Sie stellt sicher, dass die gesteckten Steckverbinder verbunden bleiben (CPA) und die Kontaktkörper vollständig in der richtigen Position sitzen (TPA). (Quelle: [What is Position Assurance?](https://www.amphenolrf.com/news/what-is-position-assurance))[^2]

[^2]: <https://www.amphenolrf.com/news/what-is-position-assurance>

#### Herstellen der Steckverbindung mit CPA

In der Regel werden bei einem Leitungssatz die Gehäuse, die eine CPA besitzen, mit geöffneten CPA angeliefert. Das heißt, die Steckverbindungen können hergestellt werden und anschließend bzw. während der Herstellung der Steckverbindung geschlossen werden.

In Ausnahmefällen wird die CPA im geschlossenen Zustand angeliefert, dies wird aber explizit vom OEM gefordert. Dadurch ist im Anlieferungszustand des Leitungssatzes die Position einer CPA, falls diese vorhanden ist, immer definiert und kann an einen Roboter übertragen werden.

**Datenbedarf***: Gehäuse ID mit der Information hat das Gehäuse eine CPA; Position der jeweiligen CPA im Anlieferungszustand des Leitungssatzes (geschlossen oder offen); wo befindet sich die CPA am Gehäuse; wie lässt sich die CPA betätigen; wann muss eine CPA betätigt werden (während der Herstellung der Steckverbindung oder erst danach);*

**Fähigkeiten***: Greifen; Kräftemessung; Fügen (CPA in Endposition bringen und erst lösen falls der Anlieferungszustand der CPA geschlossen ist)*

## <a name="_4.8"></a>4.8 Fazit

Im TP 4 "Montageprozesse des Leitungssatzes" wurden Möglichkeiten untersucht, die Montageprozesse beim OEM über Verwaltungsschalen als standardisierte Digitale Zwillinge abzubilden. Es wurde ein Überblick über die Montage des Leitungssatzes beim OEM erstellt, mit einem besonderen Fokus auf die prozessualen Herausforderungen und Notwendigkeiten aus der Sicht der Bereitstellung, der Nutzung und des automatisierten Abrufens von Daten zur automatisierten Montage. Es wurde untersucht, welche Fähigkeiten der Ressourcen erforderlich sind, um diese Prozesse erfolgreich auszuführen. Diese Betrachtung betont die Notwendigkeit, die spezifischen Datenbedarfe und notwendigen Fähigkeiten der Roboter für die einzelnen Prozesse und Teilprozesse in der Montage des Leitungssatzes durch Roboter abzudecken.

Ein zentrales Ergebnis der Untersuchungen in TP 4 war die Feststellung, dass es derzeit oft an digital bereitgestellten Informationen aus den Bereichen Produkt, Prozess und Ressourcen mangelt. Diese Lücken erschweren die Effizienz und Genauigkeit der automatisierten Prozesse erheblich. Der Leitungssatz selbst stellt eine besondere Herausforderung dar, da er in Losgröße 1 produziert wird, was eine hohe Varianz und Anpassungsfähigkeit der Produktion erfordert.

Die hohe Produktvielfalt und das komplexe Design der Leitungssätze stellen weitere Hürden für eine vollständig automatisierte Montage dar. Jeder Leitungssatz kann individuell in Länge, Anschlussarten und Anordnung der Komponenten variieren, was eine flexible und adaptive Montageanlage erfordert. Diese Variabilität erhöht die technischen Anforderungen an die Automatisierungslösungen und macht den Einsatz hochspezialisierter Roboter und intelligenter Steuerungssysteme notwendig.

Zudem werden die Leitungssätze in der Regel in sog. „Best-Cost-Countries“ gefertigt und müssen anschließend über Logistiknetzwerke zum Montageort transportiert werden, was zusätzliche Komplexität in die Planung und Ausführung der Montageprozesse einbringt.

Zusammenfassend wurde als Ergebnis festgestellt, dass für eine vollständige automatisierte Montage des Leitungssatzes aus heutiger Sicht noch technische Hürden zu lösen sind. Die Losgröße 1 bei hoher Produktvielfalt und das komplexe Design der Karosserie erschweren eine automatisierte Montage erheblich. Eine Verbesserung könnte jedoch durch eine grundlegende Neugestaltung der Architektur des Leitungssatzes erfolgen, um eine einfachere und kosteneffizientere Automatisierung zu ermöglichen.

