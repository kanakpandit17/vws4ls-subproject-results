# TP2 - Entwicklungsprozesse des Leitungssatzes

**Inhalt**

[AP 2.1 - Konzept kollaboratives Datenmodell](#ap-21---konzept-kollaboratives-datenmodell)

 -- [2.1.1 Kollaboration in der Leitungssatzentwicklung](#211-kollaboration-in-der-leitungssatzentwicklung)

 -- [2.1.2 Datenhaltung in der Leitungssatzentwicklung](#212-datenhaltung-in-der-leitungssatzentwicklung)

 -- [2.1.3 Anwendungspotential der VWS](#213-anwendungspotential-der-vws)

 -- [2.1.4 Fallbeispiel für den Einsatz von VWS bei der Auswahl eines Steckers](#214-fallbeispiel-f%C3%BCr-den-einsatz-von-vws-bei-der-auswahl-eines-steckers)

 -- [2.1.5 Fazit](#215-fazit)

[AP 2.2 - Single-Point-of-Truth-Definition](#ap-22---single-point-of-truth-definition)

 -- [2.2.1 Herausforderung: Produkt mit mehreren Herstellern](#221-herausforderung-produkt-mit-mehreren-herstellern)

[AP 2.3 - Prozessbeschreibung LS-Entwicklung](#ap-23---prozessbeschreibung-ls-entwicklung)

 -- [2.3.1 Analyse des Entwicklungsprozesses](#231-analyse-des-entwicklungsprozesses)

 -- [2.3.2 Entwicklungsprozess mit der Verwaltungsschale](#232-entwicklungsprozess-mit-der-verwaltungsschale)

 -- [2.3.3 Analyse und Integration der Einzelkomponenten](#233-analyse-und-integration-der-einzelkomponenten)

 -- [2.3.4 Strukturierung der Verbundkomponente](#234-strukturierung-der-verbundkomponente)

 -- [2.3.5 Anwendungsfall und Voraussetzungen](#235-anwendungsfall-und-voraussetzungen)

[AP 2.4 - Teilmodelle der Verwaltungsschale](#ap-24---teilmodelle-der-verwaltungsschale)

-- [2.4.1 Teilmodelle für die Entwicklung](#241-der-anwendungsfall)

[AP 2.5 - Umsetzung Digital Twin LS](#ap-25---umsetzung-digital-twin-ls)

-- [2.5.1 Der Anwendungsfall](#251-der-anwendungsfall)

-- [2.5.2 Voraussetzungen für die Umsetzung](#252-voraussetzungen-f%C3%BCr-die-umsetzung)

-- [2.5.3 Verwaltungsschalen der Komponenten](#253-verwaltungsschalen-der-komponenten)

-- [2.5.4 Erstellung Verbundkomponente](#254-erstellung-verbundkomponente)

-- [2.5.5 Fähigkeitsabgleich der Produktionsmaschinen](#255-f%C3%A4higkeitsabgleich-der-produktionsmaschinen)

-- [2.5.6 Abschlussdemonstrator](#256-abschlussdemonstrator)

[2.6 Fazit](#26-fazit)

[Literaturverzeichnis](#literaturverzeichnis)

[Abbildungsverzeichnis](#abbildungsverzeichnis)

# TP2 - Entwicklungsprozesse des Leitungssatzes

Im Teilprojekt 2 "Entwicklungsprozesse des Leitungssatzes“ wurde die Entstehung des Digitalen Zwillings entlang der Anwendungsfälle analysiert, um die Abläufe auf die Verwaltungsschale und die Erzeugung interoperabler Daten und Formate für den gesamten weiteren Lebenszyklus auszurichten. Das Teilprojekt wurde in folgende Arbeitspakete aufgeteilt, deren Resultate hier zusammenfassend erläutert werden:

-   [AP 2.1 - Konzept kollaboratives Datenmodell](#ap-21---konzept-kollaboratives-datenmodell)
-   [AP 2.2 - Single-Point-of-Truth-Definition](#ap-22---single-point-of-truth-definition)
-   [AP 2.3 - Prozessbeschreibung LS-Entwicklung](#ap-23---prozessbeschreibung-ls-entwicklung)
-   [AP 2.4 - Teilmodelle der Verwaltungsschale](#ap-24---teilmodelle-der-verwaltungsschale)
-   [AP 2.5 - Umsetzung Digital Twin LS](#ap-25---umsetzung-digital-twin-ls)

## AP 2.1 - Konzept kollaboratives Datenmodell

Im AP 2.1 "Konzept kollaboratives Datenmodell“ wurde als wesentlicher Inhalt die Datenhaltung im kollaborativen Entwicklungsprozess betrachtet und im Ergebnis ein dezentraler Ansatz als das geeignetere Konzept angesehen.

Denn bei der Entwicklung und Herstellung eines Leitungssatzes sind verschiedene Akteure in einem komplexen Prozess involviert. Der OEM als Fahrzeugentwickler, der Konfektionär als Koordinator der Leitungssatzentwicklung sowie die unterschiedlichen Lieferanten-Abstufungen, die sog. „Tier“. Als Tier-1 werden typischerweise Systemlieferanten wie Hersteller von Steuergeräten oder eben auch Hersteller von Leitungssätzen bezeichnet. Tier-2 bezeichnet Lieferanten von einzelne Komponenten für das Gesamtsystem. Weitere Zulieferer von indirekten Gütern oder Ressourcen werden als Tier-3 bezeichnet. Zudem muss vor einem Einsatz von Komponenten deren Freigabe vom eigentlichen Auftraggeber (hier dem OEM) eingeholt und entsprechend dokumentiert werden. Diese Akteure verteilen sich dabei auf mehrere Unternehmen, die oft auch in verschiedenen Ländern ansässig sind. Darüber hinaus sind die Informationsflüsse zwischen den Akteuren situativ geprägt und lassen sich nicht allgemeingültig definieren, was Richtung und Reihenfolge anbelangt.

Die dahinterliegenden Datensätze müssen für die Aktualisierung und Änderung den beteiligten Akteure sichtbar und zugänglich gemacht werden. Mit Einsatz der VWS könnte diese Datenhaltung entweder in einem zentralen oder dezentralen Ansatz realisiert werden. Gegen den zentralen Ansatz sprachen vor allem Akzeptanzvorbehalte seitens der Akteure bezüglich der Datensicherheit, da sie ihre als sensibel angesehenen Daten in einem zentralen Repository ablegen müssten, dessen Zugänge sich aber nicht unter Ihrer alleinigen Kontrolle befinden. Deshalb werden von diesen Akteuren selbst gehostete Repositories favorisiert, wo sie die Hoheit darüber besitzen, welche Daten nach außen für wen zugänglich gemacht werden.

### 2.1.1 Kollaboration in der Leitungssatzentwicklung

Bei der Entwicklung und Herstellung eines Leitungssatzes sind verschiedene Parteien involviert, die vom OEM über den Tier-1, bis zum Tier-2 reichen. Der der Auftraggeber ist in diesem Szenario der OEM und stellt Produktanforderungen in Form von Funktionsmodulen. Als Tier-1 werden Systemlieferanten wie Hersteller von Steuergeräten und eben auch Hersteller von Leitungssätzen bezeichnet. Der Tier-1 entwickelt den Leitungssatz anhand der vom OEM zur Verfügung gestellten Funktionen. Dabei wird im ersten Schritt eine Umschlüsselung von Funktions- in Produktionsmodule durchgeführt. Der Grund hierfür ist, dass ein Funktionsmodul, lediglich eine Funktion beschreibt aber in den seltensten Fällen auf einer Ressource produziert werden kann. Demgegenüber kann das Produktionsmodul so heruntergebrochen werden, um eine modulare Produktion zu ermöglichen. Lieferanten, die einzelne Komponenten (Stecker, Leitungen oder Terminals) für die Gesamtsystemkomponente herstellen, bezeichnet man als Tier-2. Weitere Zulieferer von indirekten Gütern oder Ressourcen werden als Tier-3 bezeichnet.

In der nachfolgenden Abbildung 2-1 wird eine Vernetzung der Wertkettenteilnehmer während der Leitungssatzentwicklung aus Sicht des Konfektionärs dargestellt. Auf eine vollständige Darstellung aller Informationsflüsse wurde dabei auf Grund der Komplexität und der Übersichtlichkeit verzichtet.

Es soll gezeigt werden, dass es eine Vielzahl an Mitwirkenden und keinen allgemeingültigen Informationsfluss gibt, der sich durch eine vorgegebene Richtung sowie Reihenfolge immer gleich anwenden lässt. Zu sehen ist, dass es zwischen Tier-1 und Tier-2 einen Austausch geben kann und diese Informationen direkt zum OEM geleitet werden aber auch über einen anderen Tier zum OEM kommuniziert werden können. Des Weiteren kann es auch den Fall geben, dass Informationen eines Tier-3 dem OEM größtenteils nicht vorgelegt werden, wenn dies nicht zwingend erforderlich.

![image](https://github.com/user-attachments/assets/ed8856e0-4c92-4d70-9faf-f49433a5e53f)

Abbildung 2-1: Kollaborationsbeziehungen in der Leitungssatz-Entwicklung

Größtenteils findet die Leitungssatzentwicklung durch den Konfektionär in der IT-Systemumgebung des OEMs statt. In der Leitungssatzentwicklung ist der Tier-1 die Schnittstelle zum OEM und zu den verschiedenen Komponentenherstellern (Tier-2). Seitens des OEMs wird der Tier-1 unter anderem mit CAD-Daten von der Karosserie und einer ersten Schaltplan- bzw. Elektrologik versorgt. Diese Datenpakete beinhalten auch Informationen wie bspw. welche Komponenten ggf. bereits festgelegt sind, für welche Funktion oder Spezifikation eine bereits vorhandene Komponente verwendet werden soll oder ob ggf. eine neue Komponente entwickelt werden muss.

### 2.1.2 Datenhaltung in der Leitungssatzentwicklung

Die meisten OEMs pflegen ihre eigenen Stammdaten, wie beispielsweise Teilesachnummern. Zwischen den verschiedenen Tiers und OEMs erfolgt der Austausch der Komponenten über die verschiedensten Schnittstellen und mit unterschiedlichen Datenformaten (siehe Abbildung 2-2). Darüber hinaus gibt es keine „Rückkopplung“ bei Änderungen o.ä., die für eine Synchronisation der Datensätze sorgen kann. Nach der Freigabe durch den OEM eines definierten Entwicklungsstandes wird ein filebasierter Datenstand aus den Systemlandschaften des OEMs exportiert und an den Tier-1 „übergeben“. Beim Tier-1 werden diese Daten verwendet und um Produktionsinformationen angereichert. Diese beiden Datenstände, der vom OEM und der vom Tier-1, existieren parallel und haben keine automatisierte Verlinkung oder Rückkopplung zueinander. Es entstehen somit bereits auf Stammdatenebene Datenbrüche und Inkonsistenzen bei den Datensätzen und die Anwendung der Verwaltungsschale bietet hier viel Verbesserungspotential.

![image](https://github.com/user-attachments/assets/bfb2d671-5a94-428c-9054-9054cbee10a0)

Abbildung 2-2: Eingangs- und Ausgangsdaten im Entwicklungsprozess im Überblick

### 2.1.3 Anwendungspotential der VWS

Der Einsatz der VWS würde vor allem bei der Übertragung von Produktinformationen zwischen den Wertkettenteilnehmern einen großen Mehrwert bieten, da im aktuellen Prozess zwischen den Wertkettenteilnehmern proprietäre Schnittstelle und unterschiedliche Datenformate bedient werden müssen. Die „Neutralität“ der auf XML-basierten VWS könnte zu einer grundsätzlichen Reduktion der proprietären Schnittstellen führen. Dabei würden Stammdatenattribute, CAD-Daten und Schaltpläne, die die elektrologischen Verbindungen und weitere Informationen des Leitungssatzes enthalten, in der VWS hinterlegt. Für die Produktstammdaten kann hierzu auf etablierte Datenstandards wie KBL und VEC zurückgegriffen werden. Bezüglich der Ausgangsdaten aus den verschiedenen Engineering-Tools würde die VWS also eine Art Container darstellen, in der diese Daten aus dem Prozess Leitungssatzentwicklung als Ergebnis „abgelegt“ sind. Es spielt dabei keine Rolle ob Dateien in der VWS abgelegt bzw. verlinkt werden oder ob die Leitungssatzdaten darin „aufgelöst“ abgelegt sind.

Der Einsatz von VWS hätte dabei nur bedingt Auswirkung auf die Engineering-Tools, die bei der Leitungssatzentwicklung verwendet werden. Für die nahtlose Anwendung müssten diese Softwaretools lediglich um eine Schnittstelle zum Import- bzw. Export der VWS erweitert werden. Am wichtigsten für die Umsetzung des interoperablen Digitalen Zwillings ist die Umsetzung der durchgängigen Verlinkung.

### 2.1.4 Fallbeispiel für den Einsatz von VWS bei der Auswahl eines Steckers

In diesem Abschnitt soll ein potenzieller Ablauf einer Kollaboration zwischen dem Konfektionär und mehreren Tier-2 dargestellt werden. Ziel ist es, aufgrund einer Anforderung, die richtige Auswahl eines Steckgehäuses durchzuführen.

Annahme dabei ist, dass es ein im Catena-X Datenökosystem gehostetes zentrales Repository gibt, in dem die Catena-X-Teilnehmer „Angebote“ hinterlegen sowie „Anfragen“ für „Dienstleistungen“ stellen kann (siehe Abbildung 2-3).

Der Konfektionär kann dort eine Anfrage starten, die grundlegende Attribute enthält, die ein bestimmtes Produkt (z.B. Steckgehäuse) haben soll. Das Repository agiert hier also als zentrales Register für „Angebote“ und „Anfragen“.

![image](https://github.com/user-attachments/assets/560277c7-fdcc-4e33-8396-9942fa1495fb)

Abbildung 2-3: Anfrage beim Komponentenhersteller stellen

Im Repository wird dann nachgesehen, ob es passende Kandidaten für diese Anfrage gibt. Als Ergebnis erhält der anfragende Konfektionär eine Liste möglicher Kandidaten, hier Stecker-Hersteller A (oder auch A und B), die eine Lösung für die Anfrage bieten können (Abbildung 2-4).

![image](https://github.com/user-attachments/assets/010668cf-483f-4164-8c54-720c12851625)

Abbildung 2-4: Auskunft auf Anfrage

Im Anschluss, wenn der Konfektionär die Daten der Anbieter für seine Anfrage aus dem Repository zurückerhält, kann er mit den Anbietern in einen detaillierten Austausch gehen. Hierbei können dann noch weitere Bedingungen (z.B. kommerzieller Natur) abgeklärt werden, die weiter ins Detail gehen und evtl. eine Geheimhaltungsvereinbarung voraussetzen (Abbildung 2-5).

![image](https://github.com/user-attachments/assets/97961c11-cd57-405b-b48d-bb8bbe50f5c0)

Abbildung 2-5: 2. Anfrage mit Detail-Anforderungen

Damit wäre ein repräsentatives Anwendungsszenario auf Basis einer dezentralen Datenhaltung mit Verwaltungsschalen konzeptionell grob beschrieben. Neben öffentlich einsehbaren Informationen können in einem weiteren Schritt dann detaillierte und nichtöffentliche Informationen ausgetauscht werden, zudem bleibt die Zuständigkeit für die Aktualität der Daten in der VWS weiterhin beim jeweiligen Hersteller.

### 2.1.5 Fazit

Ein kollaboratives Datenmodell in der Produktentwicklung besteht aus einer zentralen, strukturierten Datenbasis, die von verschiedenen Teams und Abteilungen innerhalb eines Unternehmens gemeinsam genutzt und bearbeitet wird. Es ermöglicht eine Echtzeit-Zusammenarbeit, bei der alle Beteiligten, wie Entwickler, Designer oder Marketingexperten, auf dieselben Informationen zugreifen und diese aktualisieren können. Dieses Modell unterstützt die interdisziplinäre Zusammenarbeit, sorgt für konsistente und aktuelle Daten und erhöht die Effizienz des Entwicklungsprozesses. Durch Rollen- und Rechtemanagement wird sichergestellt, dass die Datenintegrität gewahrt bleibt. Zudem ermöglicht es die Versionierung und Rückverfolgbarkeit von Änderungen, was die Transparenz der Produktentwicklung steigert. Für die Übertragung eines kollaborativen Datenmodell-Ansatzes auf eine Unternehmensübergreifende Ebene, müssen einige Grundbedingungen berücksichtigt werden:

-   Jeder Hersteller erstellt für seine Produkte eigene VWSen, die in einem eigenem Repository gehostet und verwaltet werden.
-   Zugriffsrechte regeln die Sichtbarkeiten der Inhalte bei den Entwicklungspartnern. Diese Zugriffsrechte müssen vom Eigentümer der Datensätze auf VWS-Ebene oder Teilmodell-Ebene erteilt werden, damit die nachfolgende Instanz mit diesen Informationen weiterarbeiten kann.
-   Die beteiligten Stakeholdern im Entwicklungsprozess können die bereits heute etablierten Tools wie [LDorado](https://trias-mikro.de/produktloesungen/bordnetz-design-mit-kbl-standard/)[^1], [Siemens Harness Designer](https://plm.sw.siemens.com/de-DE/capital/products/capital-wiring-harness-designer/)[^2], [Vector PREEvision](https://www.vector.com/de/de/produkte/produkte-a-z/software/preevision/)[^3] etc. weiterverwenden. Voraussetzung wäre, dass die Tools entsprechend ergänzt werden, um die Ergebnisse VWS-konform zu transferieren.
-   Zwischenergebnisse können mit entsprechenden Methodiken zur Versionierung abgegrenzt und an andere Teilnehmer weitergegeben werden.
-   Am Ende kann die finale Produkt-VWS zusammengestellt und freigegeben werden, um mit dem physischen Produkt an den Kunden geliefert zu werden.

[^1]: <https://trias-mikro.de/produktloesungen/bordnetz-design-mit-kbl-standard/>

[^2]: <https://plm.sw.siemens.com/de-DE/capital/products/capital-wiring-harness-designer/>

[^3]: <https://www.vector.com/de/de/produkte/produkte-a-z/software/preevision/>

## AP 2.2 - Single-Point-of-Truth-Definition

Im AP 2.2 „Single-Point-of-Truth-Definition“ wurden Lösungsansätze für das Datenmanagement betrachtet. Wie in AP2.1 beschrieben, ist die Entwicklung eines Leitungssatzes ein stark kollaborativer Prozess mit mehreren Akteuren. Durch die kollaborative Arbeit und die Anforderung einer dezentralen Datenhaltung in verteilten Repositories entsteht die Gefahr von Inkonsistenzen in der Datenhaltung. Damit ist es notwendig, einen Referenzpunkt festzulegen, den sog. „*Single-Point-of-Truth“* oder **SPoT** für alle Daten und Parameterwerte eines Leitungssatzes entlang seiner Wertschöpfung, um eine inkonsistente Datenhaltung in den nebeneinander existierenden Datensilos zu vermeiden.

Der SPoT bezeichnet damit die Datenquelle oder Datenquellen, aus der sämtliche angeschlossenen Systeme für eine bestimmte Prozessphase bedient werden. Im Entwicklungsprozess liegt dieser Referenzpunkt oftmals in der Datenbank des Kunden (OEM). Durch den intensiven Austausch zwischen Konfektionär, OEM und/oder Tier-1/2/3 aber liegen die aktuellen Daten bzw. Parameter nicht mehr unbedingt in der Datenbank des Kunden. Es ist dann Aufgabe des SPoT, diese Datenbeziehungen zu verwalten.

Mit Einsatz der VWS bietet sich die Möglichkeit, der SPoT in einer VWS auf einem VWS-Repository oder -Speicherort zu definieren und damit die Aktualisierung und Änderung sämtlichen Dateien für beteiligten Akteure sichtbar und zugänglich zu machen. Die Implementierung der VWS könnte entweder in einem zentralen oder dezentralen Ansatz realisiert werden. Im zentralen Ansatz (siehe Abbildung 2-6) wird die VWS auf einem zentralen Repository gespeichert. Die jeweilige Akteure haben je nach Rechte-Management Leserecht auf bestimmte Teilmodelle innerhalb der VWS oder können auch Schreibrecht auf relevante Sub-Modelle besitzen, um die Daten oder Parameter zu pflegen. Diese VWS wird anschließend als de-facto SPoT eingesetzt. Die Vorteile von diesem Ansatz sind u.a. zentrale Freigaben sowie aktuelle Dateien und Parameter auf einem zentralen (festen) Speicherort. Dieser Ansatz fordert eine gute Berechtigungssteuerung, einen höheren Aufwand für den Speicherort sowie höhere Anforderungen an die Server-Performance. Diese Anforderung zeigen sich als die Nachteile von einem zentralen Ansatz.

![image](https://github.com/user-attachments/assets/bc5203c5-5c26-422a-8630-d7c36c7c207a)

Abbildung 2-6: Beispiel für zentralen Ansatz

Ein dezentraler Ansatz (siehe Abbildung 2-7) bildet die andere Möglichkeit, um einen SPoT zu definieren. Dabei besitzt jeder Akteur seine eigene VWS der Komponente, die lokal innerhalb der eigenen IT-Systemlandschaft gespeichert wird. Die Anforderung an die IT-Infrastruktur für diese Art von dezentralem Repository ist nicht so hoch wie beim zentralen Ansatz. Jeder Akteur kann die VWS mit relevanten Teilmodellen für den internen, als auch relevanten Teilmodelle von externen Entwicklungspartner aufbauen. Die Teilmodelle anderer Entwicklungspartner werden in der VWS eines Akteures entweder als eine Kopie oder eine Verlinkung implementiert. Die schwierigste Anforderung dieses Ansatzes ist die Synchronisierung der individuellen VWSen oder individuellen Teilmodellen von anderen Entwicklungspartnern. Jeder Data-Owner könnte sein eigenes Teilmodell auf seiner lokalen VWS ändern. Findet eine Änderung statt, dann sollte der Data-Owner diese Änderung (automatisch) mitteilen und eine (automatische) Synchronisierung für andere Entwicklungspartnern ermöglichen. Auf Grund der verteilten VWS ist die Definition des SPoT im Vergleich mit dem zentralen Ansatz nicht trivial.

![image](https://github.com/user-attachments/assets/0d800a71-6a61-4a9a-bb8d-d438e7af2e5c)

Abbildung 2-7: Freigaben und Änderungs-Management beim dezentralen Ansatz

Deshalb wurde im Rahmen dieses APs diskutiert, wie ein SPoT bei einem dezentralen Entwicklungsprozess genau definiert werden kann. Es wurde dabei festgestellt, dass der Ort des SPoT abhängig von der Phase des Lebenszyklus ist. Während der Entwicklungsphase befindet sich der SPoT auf der VWS des Kunden (OEM). In der Produktionsphase wird die VWS auf Instanz-Ebene erweitert. Während des Produktionsprozesses beim Konfektionär werden sämtliche Ist-Werte von Fertigung erfasst und in der VWS integriert. Daher befindet sich der SPoT bei dieser Lebenszyklusphase des Leitungssatzes beim Konfektionär, siehe Abbildung 2-8.

![image](https://github.com/user-attachments/assets/8f6ecf89-3714-41bc-9a9c-83de0d6d28c6)

Abbildung 2-8: SPoT-Bezeichnung beim dezentralen Einsatz

### 2.2.1 Herausforderung: Produkt mit mehreren Herstellern

Eine im Leitungssatz verwendete Komponente wie z.B. ein Stecker muss nicht unbedingt nur in einem Land hergestellt werden, da auch Zulieferer mehrere Werke betreiben. In Abbildung 2-9 sind zwei mögliche Ursprungsländer für einen Stecker aufgelistet.

Bei zwei möglichen Stecker-Herstellern können folgende Szenarien eintreten:

-   Eine OEM-Teile-Nr., zwei verschiedene Hersteller mit je eigener Teile-Nr.
-   Pro Teile-Nr. müssen die jeweiligen Parameter & Spezifikationen verwaltet werden, d.h. die VWS von Stecker ax und Stecker ay.

![image](https://github.com/user-attachments/assets/70c80b76-3c45-4590-86ba-744226096710)

Abbildung 2-9: Beispiel für einen Stecker, der an zwei verschiedenen Standorten verwendet wird

Diese Unterschiede bilden sich in unterschiedlichen Sachnummern für ein funktional identisches Bauteil ab, was in entsprechenden Tabellen niedergelegt wird und bei Änderungen entsprechend gepflegt werden muss. Unabdingbar ist dabei, dass beide Sachnummern mit einer Freigabe belegt sind, siehe Abbildung 2-10. Hier sind die Freigaben seitens des OEM, des Herstellers und des Konfektionärs notwendig, um das entsprechende Bauteil überhaupt verwenden zu können.

![image](https://github.com/user-attachments/assets/5fa0f4b5-fadb-4349-8db3-d1d7cd649025)

Abbildung 2-10: Freigaben und Änderungs-Management

Durch dieses Mapping von Zuordnungen können die verschiedenen Teile-Bezeichnungen und Nummerierungen weitergeführt und je nach Anforderungen angepasst werden. Zudem wird eine Rückverfolgbarkeit gewährleistet und es kann für spätere Betrachtungen, wie z.B. Lieferketten-Analysen oder CO2-Footprint, eine genauere Analyse durchgeführt werden.

## AP 2.3 - Prozessbeschreibung LS-Entwicklung

Im AP 2.3 wurde eine generischer Leitungssatz-Entwicklungsprozess erarbeitet, d.h. eine vereinheitliche Beschreibung aller wesentlichen Prozessschritte und der dazugehörigen Bedarfe (Input, Output). Dazu musste der Ist-Prozess der Leitungssatz-Herstellung analysiert werden, mit den folgenden Zielsetzungen:

a.) Systembedarf abklären,

b.) Gesamtprozess in Teilprozesse/Prozessschritte unterteilen,

c.) Informationsbedarfe der Teilprozesse ableiten,

d.) Kosten-Aspekte berücksichtigen.

Im Anschluss wird die Umsetzung in die Verwaltungsschale beschrieben und erste Tests der Konzepte durchgeführt.

Die resultierenden Analysedaten finden sich mit Input als Anforderung und Output als Zwischenergebnis gesammelt in „[VWS4LS_Submodell_TP2_Entwicklungsprozess_2023_05_22.xlsx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP02/Beispieldaten/VWS4LS_Submodell_TP2_Entwicklungsprozess_2023_05_22.xlsx)“[^4].

[^4]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP02/Beispieldaten/VWS4LS_Submodell_TP2_Entwicklungsprozess_2023_05_22.xlsx>

### 2.3.1 Analyse des Entwicklungsprozesses

Ein Überblick des generischen Entwicklungsprozess ist in Abbildung 2-11 grafisch dargestellt.

![image](https://github.com/user-attachments/assets/7723f709-2bef-4a6c-a7a2-de6317ee9146)

Abbildung 2-11: Überblick Teilprozesse der Leitungssatzentwicklung

Die detaillierte Ansicht der Prozessschritte ist in Abbildung 2-12 dargestellt. Als Ausgangspunkt werden ein 3D-Modell des Bauraums sowie Systemschaltpläne benötigt. Der Bauraum wird meist partitioniert, d.h. abschnittsweise, zur Verfügung gestellt, um die Datenmenge zu begrenzen. Hierfür werden einschlägige CAD-Datenformate verwendet. Die Systemschaltpläne stellen die elektrischen Daten dar, angefangen von der Verbindungsliste bis hin zum Strombedarf der einzelnen Sensoren und Aktoren. Die Entwicklung wird dann parallel auf elektrischer und mechanischer Domäne durchgeführt. In der mechanischen Domäne wird der Leitungssatz grafisch als ein „Rohr“ dargestellt, als Platzhalter für die spätere Verlegung. Der Kunde bzw. OEM und der Komponentenentwickler stellen das 3D-Teilmodell zur Verfügung. Der Leitungssatzentwickler fügt diese 3D-Teilmodelle zusammen und daraus entsteht ein 3D-Modell für den Leitungssatz. Aus der 3D-Teil-Bibliothek kann der LS-Entwickler den passenden Gegenstecker auswählen und am Ende des „Rohres“ platzieren. Neben den mechanischen Eigenschaften bietet dieser Prozessschritt auch die Möglichkeit eine sogenannte „Temperatur-Landkarte“ zu pflegen, da die Umgebungstemperatur eine große Rolle bei Dimensionierung einer Leitung spielt. Daher ist es sehr hilfreich diese Information im 3D-Modell zu integrieren. Als Zwischenergebnis aus diesem Prozess wird das 3D-Modell als *Digital Mock Up (*DMU) erzeugt. In der elektrischen Domäne wird die Information über die Bordnetz-Architektur bzw. der Systemplan vom OEM in eine spezifische Bordnetztopologie umgewandelt und als Zwischenergebnis der Kabel-Schaltplan erzeugt. Dieser Kabel-Schaltplan beinhaltet unter anderem den Typ, Querschnitt, Verortung[^5] des sog. „[Splice](https://ecad-wiki.prostep.org/specifications/vec/guidelines/component-types/splices/)“[^6] einer Leitung sowie die Anforderungen von Kontaktoberflächen.

[^5]: Hier ist nicht die geometrischen Verortung im Fahrzeug gemeint, sondern die Verzweigung eines Kabels nach einer bestimmten Länge auf mehrere Kabelsegmente.

[^6]: <https://ecad-wiki.prostep.org/specifications/vec/guidelines/component-types/splices/>

![image](https://github.com/user-attachments/assets/1cc8edee-9235-4994-8f09-0006d2b85473)

Abbildung 2-12: Referenzprozess der Leitungssatz-Entwicklung

Nach Vorbereitung der 3D-Modelle sowie des elektrischen Schaltplans können mit der Information aus dem Schaltplan die Leitungsgruppe oder -Bündel, sowie deren Dimensionen abgeleitet werden.

Nach Start der Leitungssatz-Entwicklung mit den notwendigen Dokumenten bzw. Dateien spaltet sich der Prozess auf in den Kabelschaltplan und 3D-Teilmodell erstellen. Nach dem Mergen (Zusammenführen) aller 3D-Teilmodelle werden die elektrischen und 3D-Daten zusammengeführt und das Routen der Leitungen beginnt. Im Anschluß werden die Module definiert, die zusammengehörige Leitungen in ein Modul bündelt, die konkreten Kontaktteile für alle Anschlüsse ermittelt und abschließend der Bündel-Durchmesser an allen relevanten Stellen des Kabelsatzes berechnet. Sollten hier Anpassungen z.B. einer Karosserie-Durchführung notwendig werden, wird wieder zurück zur Erstellung der 3D-Teilmodelle gegangen und der Prozess nochmals durchgeführt. Sobald nach dem Bündeldurchmesser berechnen keine Anpassung mehr durchzuführen ist, wird je nach Kundenanforderung das Schwingungsverhalten (meist bei Tür-Übergängen) analysiert und abschließend die Freigabe-Dokumente erstellt. Diese umfassen die entsprechenden Zeichnungen und die dazu gehörigen elektrischen und sonstigen Informationen wie Teilelisten etc.

Bei einer Anfrage auf Änderung wird eine technische Ausarbeitung erstellt, die alle Aspekte und Daten der Änderung umfasst. Das können rein mechanische Änderungen seitens Lage der Anschluß-Buchse bei einem Steuergerät sein oder erhöhter Strombedarf auf einem Anschluss-Pin. Diese Änderung wird von allen betroffenen Zulieferern, dem Konfektionär und dem OEM bewertet und final akzeptiert. Danach muss die Änderung entsprechend in den vorhandenen Leitungssatz eingepflegt und die Umsetzung in die Produktion geplant werden.

Der bisher erzeugte Schaltplan gilt für einen sogenannten „150%-Leitungssatz“, welcher die Informationen von allen möglichen Verbindungen aus verschiedene Ausstattung eines Fahrzeugtyps enthält. Diese Verbindungen werden nie komplett in einem Fahrzeug gebaut, da oftmals eine Ausstattungsoption die andere ausschließt. Deshalb wird nun der Prozessschritt *Modularisierung* durchgeführt und dabei der Leitungssatz in Basis-Leitungssatz und weitere optionale Module unterteilt. Am Ende des Modularisierungsprozesses wird der Durchmesser der Leitungsbündel erneut berechnet. Wenn der neue Durchmesser die entsprechende Anforderung nicht erfüllt, dann wird ein iterativer Prozess ausgelöst und der Entwicklungsprozess wird von der Erstellung des 3D-Teilmodells bis zur Berechnung der Bündeldurchmesser wiederholt. Als Ergebnisse des LS-Entwicklungsprozess werden verschiedene Freigabedokumente erstellt, unter anderem die „150%-Zeichnung“, KBL bzw. VEC und 3D-Muster der LS-Verlegung.

### 2.3.2 Entwicklungsprozess mit der Verwaltungsschale

Wenn der eingangs betrachtete Entwicklungsprozess auf Basis der Verwaltungsschale umgesetzt werden soll, beginnt der Vorgang mit der Bereitstellung einer VWS durch den OEM, welche die zentrale Informationen und Datenstrukturen für die Leitungssatzentwicklung enthält. In dieser VWS sind Freigabelisten für Komponenten, CAD-Zeichnungen sowie relevante Normen und Anforderungen enthalten. Diese umfassende Datensammlung dient als eine zentrale und konsistente Datenquelle, die als Grundlage für alle weiteren Entwicklungsaktivitäten dient.

Im weiteren Verlauf des Entwicklungsprozesses entsteht dann beim Tier-1 eine Struktur zusammenhängender Verwaltungsschalen, die die Anforderungen und Daten der jeweiligen Entwicklungsstufen integriert und konsistent weiterführt. Hierzu wurde untersucht, wie dezentrale Verbundkomponenten im Kontext der Verwaltungsschale umgesetzt werden können, um eine flexible und skalierbare Integration sicherzustellen.

Diese Prozessbeschreibung zeigt, wie die Verwaltungsschale als zentrales Element in der Leitungssatzentwicklung genutzt werden kann, um die Integration von Einzelkomponenten zu erleichtern, die Kommunikation zwischen OEM, Tier-1 und Tier-2 zu optimieren und die Effizienz des gesamten Entwicklungsprozesses zu steigern. Durch die gezielte Bereitstellung spezifischer Produktinformationen wird die Zusammenarbeit entlang der Lieferkette effizient und sicher gestaltet.

In der nachfolgenden Abbildung 2-13 soll der beschriebene Workflow nochmals zusammengefasst auf einer abstrakten Ebene visualisiert werden.

![image](https://github.com/user-attachments/assets/14d87072-e01b-44cc-8878-49810f664c35)

Abbildung 2-13: Workflow Entwicklung Leitungssatz

### 2.3.3 Analyse und Integration der Einzelkomponenten

Der Tier-1 beginnt den Prozess unter anderem, indem er die im Entwicklungsauftrag enthaltenen Einzelkomponenten analysiert und in zwei Kategorien unterteilt:

1.  **Bekannte Einzelkomponenten:** Diese Komponenten sind bereits in der Tier-1-Datenbank vorhanden und können direkt mit der entsprechenden Produktsichtweise weiterverwendet werden. Die Verwaltungsschale des Tier-1 ermöglicht es, diese Komponenten effizient in den Entwicklungsprozess zu integrieren.
2.  **Unbekannte Einzelkomponenten:** Für Komponenten, die nicht in der Tier-1-Datenbank vorhanden sind, gibt es zwei Möglichkeiten:
    -   **Generell bekannte und freigegebene Komponenten:** Die Komponente ist bereits freigegeben beim OEM, aber beim Tier-1 noch nicht in der Datenbank vorhanden. Der Tier 1 kontaktiert den jeweiligen Komponentenhersteller (Tier-2) und fordert den Zugriff auf die Produkt-VWS an, um die fehlenden Informationen zu integrieren.
    -   **Suche nach Komponentenentwicklungspartner:** Falls keine direkte Integration der unbekannten Komponenten möglich ist. kann ein Szenario sein, dass der Tier-1 einen Entwicklungspartner (Tier-2) für die entsprechende Komponente ausfindig machen muss, der die Anforderungen des Entwicklungsauftrags erfüllen kann. Anschließend sind Freigabeprozesse beim OEM zu durchlaufen und die Integration der Daten in die entsprechenden Datenbanken.

Sobald die unbekannten Komponenten erfolgreich angelegt und die VWS-Produktsichtweisen erstellt sind, kann die Aggregation der Verbundkomponente beginnen.

### 2.3.4 Strukturierung der Verbundkomponente

Nachdem der Tier-1-Lieferant den Entwicklungsauftrag in Form einer Verwaltungsschale (VWS) vom OEM erhalten hat, beginnt die eigentliche Leitungssatzentwicklung. Zunächst analysiert der Tier-1 die übergebenen Daten und identifiziert die notwendigen Schritte zur Integration und Erstellung der Verbundkomponente der Verwaltungsschale.

1.  **Identifikation und Erzeugung der notwendigen Teilmodelle**: Basierend auf den vom OEM bereitgestellten VWS-Informationen muss der Tier-1 die spezifischen Teilmodelle für die Leitungssatzentwicklung definieren. Diese Teilmodelle umfassen unter anderem:
    -   **Produktteilmodelle**: Enthalten spezifische Produktinformationen wie technische Spezifikationen, CAD-Daten und freigegebene Komponenten.
    -   **Prozessteilmodelle**: Diese Modelle beinhalten Informationen zu Fertigungsprozessen, Montagereihenfolgen und Prüfanforderungen.
    -   **Ressourcenteilmodelle**: Beinhaltet alle notwendigen Ressourceninformationen, z.B. Werkzeuge, Maschinen und Materialien.
2.  **Verknüpfung der Teilmodelle**: Um eine konsistente und funktionale Verwaltungsschale zu erstellen, müssen die einzelnen Teilmodelle korrekt verknüpft werden. Dies stellt sicher, dass alle relevanten Informationen in einem zentralen Kontext zusammengeführt und genutzt werden können. Die Verknüpfung erfolgt durch die Definition eindeutiger Beziehungen zwischen den Modellen, die den gesamten Lebenszyklus des Leitungssatzes abdecken.
3.  **Integration der Tier-2 VWS**: Für die vollständige Aggregation der Verbundkomponente müssen die VWS der Tier-2-Lieferanten in die 150%-Variante des Leitungssatzes integriert werden. Wichtig ist, dass der Tier-1 nicht die vollständigen VWS der Tier-2-Lieferanten erhält, sondern nur spezifische Sichten, die die relevanten Produktinformationen enthalten. Diese selektiven Sichten müssen vom jeweiligen Tier-2 bereitgestellt und vom Tier-1 in die eigene VWS integriert werden.

Um den Prozess effizienter zu gestalten, kommen Automatisierungstools zum Einsatz, wie bspw. das [VWS4LS-AASPE-Plugin](https://github.com/VWS4LS/vws4ls-aaspe-plugin)[^7]. Solche Tools unterstützen die automatisierte Erstellung und Verknüpfung der Teilmodelle, indem sie Standardprozesse abbilden und somit den manuellen Aufwand reduzieren, da durch den Einsatz solcher Tools viele Schritte automatisiert durchgeführt werden können, was die Konsistenz und Effizienz des gesamten Entwicklungsprozesses erheblich steigert.

[^7]: <https://github.com/VWS4LS/vws4ls-aaspe-plugin>

### 2.3.5 Anwendungsfall und Voraussetzungen

Der OEM erteilt einem Tier-1-Lieferanten einen Entwicklungsauftrag und übergibt dazu eine Verwaltungsschale (VWS). Der Dateninhalt der VWS umfasst alle relevanten Informationen zum Produktmodell wie beispielsweise Komponenten, CAD-Daten, Elektrologik (ELOG) und elektrische Schaltpläne, die auf den Freigabeprozessen aus AP5.2 basieren. Der Tier-1-Lieferant analysiert diesen Entwicklungsauftrag, integriert die bereitgestellten Informationen in seine eigene Datenbank und entwickelt darauf aufbauend den Leitungssatz.

Die Leitungssatzentwicklung ist ein komplexer und iterativer Prozess, der aus mehreren Prozessschritten aufgebaut wird. Diese Prozessschritte erzeugen Zwischenartefakte, die als Input bzw. Anforderung für den nächsten Schritt verwendet werden können oder Auslöser für einen iterativen Prozess sind.

Eine strukturierte Herangehensweise gewährleistet die effiziente Koordination der komplexen Interaktionen zwischen den verschiedenen Projektbeteiligten. Die Verwaltungsschale unterstützt dabei das Änderungsmanagement und fördert die frühzeitige Einbindung von Produktions- und Montagespezifika, wodurch die Gesamteffizienz und Qualität der Leitungssatzentwicklung verbessert werden.

Die beschriebenen Entwicklungsprozesse werden nun durchgeführt, unter Verwendung der bereits verfügbaren Standard-Tools, um z.B. Leitungslängen zu ermitteln. Die dabei anfallenden Ausgangs-Daten werden dann in einem Übergangs-Szenario ermittelt und anschließend in der VWS abgelegt werden. Zu einem späteren Zeitpunkt sollte dies von den genutzten Software-Tools direkt bewerkstelligt werden. Durch den Einsatz von Automatisierungstools für die schnelle und einfache Übernahme der Daten in die VWS kann der Tier-1 erhebliche Zeit- und Kostenvorteile erzielen. Die Tools ermöglichen:

-   Automatisierte Anlage von Teilmodellen: Die Teilmodelle werden auf Basis der vom OEM bereitgestellten VWS automatisch generiert und mit den relevanten Daten befüllt.
-   Effiziente Verknüpfung der Modelle: Die automatisierte Verknüpfung der Teilmodelle minimiert Fehler und stellt sicher, dass die Modelle in einem einheitlichen Kontext stehen.
-   Schnelle Integration von Tier-2 VWS-Sichten: Die spezifischen Sichten der Tier-2 VWS werden effizient in die Verbundkomponente integriert, ohne dass interne Daten der Tier-2-Lieferanten offengelegt werden müssen.

Diese Schritte sind entscheidend, um die Verwaltungsschale als zentrales Element in der Leitungssatzentwicklung erfolgreich zu nutzen. Die integrierten und verknüpften Teilmodelle bilden eine konsistente Datenbasis, die für die gesamte Entwicklung und spätere Produktion genutzt werden kann

## AP 2.4 - Teilmodelle der Verwaltungsschale

Im AP 2.4 „Teilmodelle der Verwaltungsschale“ wurden Anforderungsanalysen für die VWS-Teilmodelle der in AP 2.3 definierten LS-Prozesse durchgeführt, unter Einbeziehung jeder Komponente und jedes Prozessschrittes.

Der Entwicklungsprozess ist die „Wiege“ des Digitalen Zwillings. Entlang der Anwendungsfälle werden die Abläufe auf die Verwaltungsschale und die Erzeugung interoperabler Daten und Formate für den gesamten weiteren Lebenszyklus ausgerichtet. Die VWS soll dabei nicht die etablierten Daten-Formate ersetzen, wie z.B. CAD-Dateiformate, KBL, VEC etc., sondern ergänzen und die Daten vor allem automatisiert und maschinenlesbar bereitstellen. Deshalb ist es neben der Auswahl passender existierender bzw. neu zu erstellender Teilmodelle auch wichtig, anhand von Anwendungsfällen das Zusammenspiel zu betrachten. Hierbei liegt der Fokus zuerst nur auf dem Entwicklungsprozess des Leitungssatzes. Der Übergang zu Produktion und Montage (TP3 und TP4) soll im nachfolgenden AP 2.5 betrachtet werden.

### 2.4.1 Teilmodelle für die Entwicklung

Die zu lösende Fragestellung ist, welche Daten zu welchem Zeitpunkt in der Verwaltungsschale (VWS) zur Verfügung stehen bzw. stehen müssen und in wie diese strukturiert sein müssen.

Hierfür wurden zu Beginn des Arbeitspaketes 2.4 für den Referenzprozess alle existierenden relevanten Daten aus anderen Teilprojekten zusammengetragen. Aus diesen Daten wurde abgeleitet, welche Entwicklungspartner und die ihnen zugeordneten Komponenten mit deren Daten in der Leitungssatzentwicklung eine Rolle spielen. Danach fand eine Betrachtung statt, welcher Entwicklungspartner eine VWS für die Komponenten im Leitungssatz und für den Leitungssatz selbst besitzt. Das Ergebnis ist in Abbildung 2-14 zu sehen. Da im Entwicklungsprozess mit Typen von Leitungssätzen gearbeitet wird, wurde hier derselbige Begriff verwendet. Eine Instanz wird in diesem Fall erst erzeugt, wenn ein Leitungssatz-Typ in die Fertigung gegeben wird und dort physisch produziert wird.

![image](https://github.com/user-attachments/assets/65871584-8b0a-408e-a38f-5c80cdb4eb07)

Abbildung 2-14: Assets und ihre VWS im Entwicklungsprozess des Leitungssatzes

Es wurde ein Grad an Modularität gewählt, sodass durch die Verknüpfung von VWS, wie z. B. der Leitungssatz-Typ-VWS mit den Halbfabrikat- und Komponenten-Typ-VWS, eine Wiederverwendung ermöglicht wird. Beispielsweise kann der Fall eintreten, dass ein bestimmter Halbfabrikat-Typ für mehrere Leitungssatz-Typen Anwendung findet. Neben den Komponenten-Typen für den Leitungssatz-Typ, wurde auch dem Ressourcen-Typ eine VWS seitens des Maschinenherstellers und des Konfektionärs zugewiesen, sodass der Konfektionär noch zusätzliche ressourcenrelevante Daten speichern kann, die später bei der Wahl einer für die Produktion geeigneten Maschinen-Instanz beachtet werden müssen.

Mit der Festlegung der Verwaltungsschalen, die in der Leitungssatzentwicklung benötigt werden, konnte die inhaltliche Zuordnung der Entwicklungsdaten zu den von der „Industrial Digital Twin Association e.V.“ (IDTA) spezifizierten und bereits veröffentlichten Teilmodell-Templates [1] erfolgen. Dabei trat der Fall ein, dass nicht alle zu dem Zeitpunkt veröffentlichten Teilmodelle die Abbildung der vorliegenden Inhalte ermöglichen. Es wurde daher eine Anforderungsanalyse durchgeführt, die

-   alle im Prozess beteiligten Assets mit deren VWS bei den jeweiligen Entwicklungspartnern einbezieht.
-   die Teilmodelle für die jeweiligen VWS mit Details zu Inhalten einzelner Teilmodelle bezogen auf die Lebenszyklusphase des Leitungssatzes (Entwicklung, Produktion und Montage) zeigt.
-   die Notwendigkeit vom Teilen und Synchronisieren von Teilmodellen und VWS mit anderen Entwicklungspartnern festlegt.

Ein kleiner Ausschnitt aus der Analyse für einen Komponenten-Typen (z. B. Gehäuse, Leitung, Terminal) ist in Abbildung 2-15 zu sehen. Aus diesem Beispiel ist ersichtlich, dass sowohl OEM, Konfektionär, Komponentenhersteller und in manchen Fällen auch der Werkzeughersteller eine VWS für den Komponenten-Typen besitzt. Dabei ist in diesem Fall der Komponentenhersteller der SPoT für die Komponentendaten. Alle anderen Entwicklungspartner können ebenfalls eigene VWS zu dem Komponenten-Typ erstellen, verlinken aber immer auf die originale Komponenten-Typ-VWS des Komponentenherstellers, wenn zu dieser eine Verbindung existiert. Dies wurde in der Tabelle mit „[…] VWS der […]“ in der Spalte der Teilmodelle vermerkt. Teilinhalte der originalen VWS werden seitens des Komponentenherstellers den anderen Entwicklungspartnern über Zugangsberechtigungen zugänglich gemacht.

![image](https://github.com/user-attachments/assets/269342bf-5538-4be2-843e-9043d50a8935)

Abbildung 2-15: Ausschnitt aus der Anforderungsanalyse für VWS und deren Teilmodelle 

Im Folgenden wird anhand des Beispiels des Komponenten-Typen näher auf die in der VWS enthaltenen Teilmodelle und ihren Zweck eingegangen. Zu den ersten oft verwendeten Teilmodellen gehören das digitale Typenschild [2], die Kontaktinformationen und die technischen Daten der Komponente. Weiterführend werden in die VWS auch die Dokumente, wie z.B. die Verarbeitungsspezifikationen, die Freigabezeichnung und die 2D-Zeichnung sowie das 3D CAD-Modell abgelegt. Zusätzlich wird das Teilmodell „Capability Description“ [3] integriert, um die von dem Komponenten-Typen geforderten Fähigkeiten aus den Verarbeitungsanforderungen in die VWS aufnehmen zu können. Da das Teilmodell sich zu diesem Zeitpunkt noch in Entwicklung befindet, wurde der aktuell verfügbare Arbeitsstand verwendet.   
Mit den aufgezählten Teilmodellen konnten nicht alle Daten abgebildet werden. Dazu gehören das Produktmodell, welches als KBL [4] oder VEC [5] vorliegt, sowie die Vorlage für die Produktionsdaten, die erst mit der Produktion der Komponente beschrieben werden. Beide sind mit \* umklammert.  
Für das Produktmodell-Teilmodell wird per XPath-Referenzen der VEC bzw. die KBL hinterlegt, um die Daten aus dem Modell in der VWS verfügbar zu machen. Dieses Teilmodell spielt vor allem in den VWS des Leitungssatz-Typs und seiner Modul- und Halbfabrikat-Typen eine Rolle.

Von der Komponenten-Typ-VWS weg hin zu den VWS des Leitungssatz-Typs und der Halbfabrikat-Typen wird das Teilmodell „IDTA 02011: Hierarchical Structures Enabling Bill of Material“ [6] mehrfach verwendet:

-   als **Stückliste** über die im Leitungssatz-Typ oder dem Halbfabrikat-Typ enthaltenen Assets, mit Referenzen zu dem Produktmodell-Teilmodell.
-   als **Konfigurationsliste** der möglichen Varianten, aus den verschiedenen Komponenten- und Halbfabrikat-Typen.
-   als **Produktionsliste** mit den bestellten Varianten, die dann an den Produktionsprozess übergeben werden.

Das Konzept zur Struktur der VWS und der Zugriffsberechtigungen in der Wertschöpfungskette sind dem Kapitel **„Architektur AAS“** zu entnehmen.

Mit den aus der Anforderungsanalyse gewonnen Inhalten konnten die Schnittstellen und auszutauschenden Inhalte sowohl zwischen den einzelnen Entwicklungspartnern als auch zwischen den Lebensphasen des Leitungssatzes herausgearbeitet werden. So ist beispielsweise in Abbildung 2-16 der Austausch der Leitungssatz-Typ-VWS zwischen dem OEM und dem Konfektionär zu sehen. Die orange hinterlegten VWS sind durch ihre Teilmodelle gekennzeichnet, wobei deren Zugriff für externe entweder durch grüne (Zugriff gewehrt) oder rote (Zugriff verboten) Balken gekennzeichnet ist. Bei dem 3D CAD-Modell gibt es z. B. eine Mischung dieser beiden Zugriffsrechte, da die Inhalte des Teilmodells für den Konfektionär manchmal nur direkt bei dem OEM zugriffbereit liegen. Ansonsten kann der Konfektionär sich die VWS mit allen für ihn freigegebenen Teilmodellen vom OEM herunterladen und in seinem System speichern.

Die Leitungssatz-Typ-VWS des OEM bleibt von dem Konfektionär unberührt und wird mit Hilfe der *specificAssetId* der VWS von der Leitungssatz-Typ-VWS des Konfektionärs referenziert. Gründe dafür liegen in der einfacheren Synchronisation von Änderungen seitens des Datenbereitstellers, wie hier dem OEM. Genauere Informationen dazu und zu der Verlinkung sind im Kapitel **„Architektur AAS“** zu finden.

Basierend auf der vom Leitungssatz-Typ-VWS des OEM abgeleiteten VWS zu seinem eigenen Leitungssatz-Typ, kann der Konfektionär mit der Erstellung und Beschreibung der VWS für die Funktionsmodul-, Halbfabrikat- und Komponenten-Typen beginnen. Die weiteren Austauschprozesse mit den dazugehörigen VWS sind bereits in dem Kapitel **Fehler! Verweisquelle konnte nicht gefunden werden.** „Architektur AAS“ detailliert beschrieben.

![image](https://github.com/user-attachments/assets/17a06ac0-b842-471f-871f-e87814190a34)

Abbildung 2-16: VWS-Schnittstellen im Entwicklungsprozess zwischen OEM und Konfektionär

## AP 2.5 - Umsetzung Digital Twin LS

Im Rahmen des Arbeitspakets 2.5 „Umsetzung Digital Twin LS“ wurde das im vorherigen Arbeitspaket 2.4 definierte Vorgehen zur Erstellung der Typ-Verwaltungsschale für den Leitungssatz beim Konfektionär sowie die definierte Aufteilung der Informationen in unterschiedliche Teilmodelle auf ihre Anwendbarkeit in der Leitungssatzentwicklung erarbeitet. Im Vordergrund stand dabei die Rolle der VWS im Gesamtentwicklungsprozess, die Integration der Komponenten-Verwaltungsschalen sowie der Informationsaustausch über Unternehmensgrenzen hinweg, mit dem Ziel, den gesamten Entwicklungsablauf effizienter, transparenter und besser strukturiert zu gestalten.

### 2.5.1 Der Anwendungsfall

Um den Workflow zu verproben, wurde der Beispielleitungssatz aus dem PPR-Workshop verwendet (siehe Abbildung 2-17). Da dieser Beispielleitungssatz bisher nur als schematische Illustration vorhanden war, wurden im Vorfeld für alle notwendigen Komponenten die entsprechenden Teile inklusive der Teilenummern definiert. Um möglichste detaillierte Information zu allen Komponenten zur Verfügung zu haben, wurden vorzugsweise Teile verwendet, die von den VWS4LS-Projektteilnehmern hergestellt werden. Darauf aufbauend wurden alle notwendigen Leitungssatzdaten (Schaltplan, 3D-Modell, VEC usw.) erzeugt.

![image](https://github.com/user-attachments/assets/e68ddcba-a5b3-4e77-8c37-b7904351b24e)

Abbildung 2-17: Beispielleitungssatz aus dem PPR-Workshop

Um die zuvor definierten Teilmodelle für den Entwicklungsprozess mit Leitungssatzdaten zu verproben und mit entsprechenden Daten zu befüllen, musste ein Leitungssatz im VEC-Format erstellt werden (siehe [DRX00012_0002.02_AO_2023_09_08.vec](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP02/Beispieldaten/DRX00012_0002.02_AO_2023_09_08.vec)[^8]).

[^8]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP02/Beispieldaten/DRX00012_0002.02_AO_2023_09_08.vec>

Mit den festgelegten Teilen wurde der Entwicklungsprozess entsprechend durchgeführt.

Die zur Verfügung gestellten abstrahierten 3D-Modelle der Komponenten wurden für die Erstellung des DMU-Modells des Leitungssatzes verwendet. Da hier das Konzept eines 3D-Master Prozesses angewendet wurde, sind alle relevanten Daten des Leitungssatzes, bis auf die elektrologische Verschaltung, im DMU-Modell einzuarbeiten.

Zusätzlich wurden der entsprechende Schaltplan für den Leitungssatz erstellt, um die elektrologische Verbindung zu erhalten, die wie zuvor erwähnt nicht im 3D entsteht.

Im anschließenden Schritt werden die Daten aus DMU und Schaltplan zusammengeführt, um eine vollumfängliche Beschreibung des Leitungssatzes zu erhalten. Im letzten Schritt wird dann noch die sogenannte Modularisierung gemacht. Hierbei wird der 150%-Umfang des Leitungssatzes in sogenannte Funktionsmodule partitioniert.

Als Output des Entwicklungsprozesses wird nach heutigen Stand eine 2D-Zeichung (SVG) und eine KBL-Datei erzeugt (siehe Inhalt von [DRX00012_0002.02_AO_2023_09_08.hcv](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP02/Beispieldaten/DRX00012_0002.02_AO_2023_09_08.hcv)). Abbildung 2-18 zeigt den Leitungssatz dargestellt in der SVG-Zeichnung. In der KBL sind alle Daten zum Leitungssatz in einer standardisierten Form abgelegt und dient als Austauschformat zwischen OEM und Konfektionär.

![image](https://github.com/user-attachments/assets/eae821d8-eec3-4149-b67c-25dcd25b4c29)

Abbildung 2-18: SVG-Darstellung des Leitungssatzes

Die nachfolgende Abbildung 2-19 zeigt die Verbindungsliste (WIRE) und die Materialliste (BOM) für den Leitungssatz, aufgeteilt nach den jeweiligen Varianten/Modulen. Je nach Kundenanforderung müssen die WIRE und die BOM auch auf der SVG-Zeichnung dargestellt werden.

![image](https://github.com/user-attachments/assets/166434c8-a7c3-4136-a05f-668065353a1f)

Abbildung 2-19: WIRE und BOM mit dargestellter Modularisierung (V1, V2 und V3)

Zu einem frühen Zeitpunkt des Projektes wurde sich darauf verständigt, das VEC-Format zur Beschreibung des Leitungssatzes zu verwenden. Hintergrund dieser Entscheidung ist, dass der VEC mehr Informationsfelder zur Beschreibung des Leitungssatzes zur Verfügung stellt.

Allerdings sind viele heutige gebräuchliche Leitungssatzentwicklungstools noch nicht befähigt, eine Produktbeschreibung des Leitungssatzes im VEC-Format auszugeben.

Daher musste die erzeugte KBL-Datei mittels eines Konverters in das VEC-Schema überführt werden, mit dem Nachteil, dass der Inhalt der VEC zur Beschreibung des Produktes dem der KBL entspricht und somit die Vorteile des VEC-Formats brachliegen.

### 2.5.2 Voraussetzungen für die Umsetzung

Um diesen Anwendungsfall erfolgreich umsetzen zu können, sind generell folgende Voraussetzungen notwendig:

-   **Vorhandensein von VWS für alle relevanten Komponenten:** Es wird vorausgesetzt, dass alle notwendigen Komponenten des PPR-Beispiels (Abbildung 2-17) in Form von Verwaltungsschalen bereits vorhanden sind und nicht erst erzeugt werden müssen.
-   **Zugriff auf spezifische VWS-Sichten der Tier-2-Lieferanten:** Der Tier-1 muss in der Lage sein, die spezifischen Produktinformationen der VWSen der Tier-2-Lieferanten zu erhalten, um diese in sein Repository zu integrieren und anschließend in die Entwicklungsdaten einzubinden. Dies erfordert eine koordinierte Bereitstellung der entsprechenden Informationen durch die Tier-2-Lieferanten.
-   **Infrastruktur für dezentrale VWS-Verwaltung:** Eine dezentrale Infrastruktur, die die Integration und Verwaltung der Verwaltungsschalen unterstützt, ist notwendig, um die Flexibilität und Skalierbarkeit der Leitungssatzentwicklung zu gewährleisten.
-   **Etablierung eines kollaborativen Datenmodells:** Ein kollaboratives Datenmodell, das als Single-Point-of-Truth fungiert, muss etabliert sein, um eine nahtlose Integration aller relevanten Datenquellen und Prozesse sicherzustellen.

### 2.5.3 Verwaltungsschalen der Komponenten

Beim Stecksystem wurde der MLK 1,2 ausgewählt (Abbildung 2-20), da dieser nicht im vollen Umfang der Geheimhaltungspflicht von KOSTAL Kontakt Systeme GmbH & Co.KG unterliegt, sondern von weiteren Mitbewerbern aus dem Arbeitskreis genutzt werden kann. Die zugehörige VWS-Datei ist die „[VWS4LS_Terminal_MLK_1-2_0.5-0.75mm_2024_01.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP02/Beispieldaten/VWS4LS_Terminal_MLK_1-2_0.5-0.75mm_2024_01.aasx)“[^9] (Abbildung 2-21).

[^9]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP02/Beispieldaten/VWS4LS_Terminal_MLK_1-2_0.5-0.75mm_2024_01.aasx>

Es wurde ein 4-poliges Gehäuse ausgewählt, das für beide Seiten eingesetzt wird. Allerdings ist die Seite A2 ungedichtet und das Gehäuse der Seite A1 gedichtet. Das heißt die Leitungen auf der Seite A1 werden mit Einzelleitungsdichtungen (ELA) verarbeitet und die nichtbelegten Kammern mit sogenannten Blindstopfen bestückt.

Für dieses Beispiel sind Terminals mit vier verschiedenen Teilenummern notwendig. Dies ergibt sich durch die eingesetzten Querschnitte der Leitungen von 0,35 und 0,5 mm². Dafür sind zwei unterschiedliche Terminals notwendig, da der Crimpbereich einmal für 0,35mm² verwendbar ist und ein weiteres für 0,5 - 0,75mm². Nochmals zwei weitere Varianten kommen hinzu, da der Einsatz der ELA- Terminals einen anderen Isolationscrimpbereich erfordern.

![image](https://github.com/user-attachments/assets/de46d902-6503-4633-a240-902bc63a90d3)

Abbildung 2-20: MLK 1,2 Terminal mit/ohne ELA (KOSTAL Kontakt Systeme GmbH & Co. KG)

Um die einzelnen Typ-Verwaltungsschalten aus Tier-2 Sicht zu erstellen, wurden als Input die Verarbeitungsspezifikationen, das Datenblatt und die dazugehörigen neutralen Kundenzeichnungen verwendet.

![image](https://github.com/user-attachments/assets/17e20481-20d3-4b84-b964-839b7138552f)

Abbildung 2-21: Auszug aus einer Typ-Verwaltungsschale Terminal

Um das PPR-Beispiel zu vervollständigen, wurden auch für das Halteteil und die Bandagierung jeweils eine entsprechende Teilenummer festgelegt.

Typischerweise haben unterschiedliche Partner der Wertschöpfungskette unterschiedliche Sichtweisen auf eine Komponente. Dies fängt bei unterschiedlichen (internen) Teile- bzw. Sachnummern an und geht bis hin zu unterschiedlichen Grenzwerten für den Einsatz einer Komponente. Um dies abzubilden, wurden für jede Komponente nicht nur eine sondern jeweils drei Verwaltungsschalen inkl. zugehöriger Assets erstellt, um die unterschiedlichen Sichtweisen (OEM, Tier1, Tier2) abbilden zu können. Dabei wurde der im Rahmen von TP5.2 entwickelte Mechanismus zur Äquivalenz-Beschreibung zwischen den verschiedenen Assets genutzt. Abbildung 2-22 zeigt dies Anhand der Tier1-Verwaltungsschale für eine Komponente, welche per „*specificAssetID*“ auf die äquivalenten Assets sowohl bei einem OEM als auch bei einem Tier2 verweist. Dies erlaubt das automatische Sachnummern-Mapping, d.h. das automatische Auffinden eines äquivalenten Assets/Verwaltungsschale eines anderen Partners der Wertschöpfungskette.

![image](https://github.com/user-attachments/assets/c94c3eaf-5802-4ab1-b969-0d04bec50bfd)

Abbildung 2-22: Äquivalenzbeziehungen per „spedificAssetId“

### 2.5.4 Erstellung Verbundkomponente

Auf Basis der erstellten Daten für den Gesamtleitungssatz wurde anschließend die zugehörige Typ-Verwaltungsschale aus Sicht des OEM mit entsprechenden Teilmodellen (vgl. Abbildung 2-16) erstellt, die sog. „Verbundkomponente“ (VBK). Abbildung 2-23 zeigt die Verwaltungsschale „[Leitungssatz_und_Komponenten_Typ_OEM.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP02/Beispieldaten/TP2_PPR_Beispieldaten/Leitungssatz_und_Komponenten_Typ_OEM.aasx)“[^10] sowie exemplarisch die dort enthaltene 2D-Zeichnung (vgl. Abbildung 2-18) als Teil des „*HandoverDocumentation*“-Teilmodells.

[^10]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP02/Beispieldaten/Leitungssatz_und_Komponenten_Typ_OEM.aasx>

![image](https://github.com/user-attachments/assets/68911dc0-180d-4663-a17c-863fadde66e6)

Abbildung 2-23: OEM-Verwaltungsschale für den Gesamtleitungssatz

Durch das im Rahmen von TP5.2 sowie des Architekturteams entwickelte [VWS4LS-AASPE-Plugin](https://github.com/VWS4LS/vws4ls-aaspe-plugin)[^11] für den AASX Explorer konnte aus der importierten Produktspezifikation in Form des VEC-Modells automatisch die Product-BOM erstellt und mit den Verwaltungsschalen der Einzelkomponenten verknüpft werden. Abbildung 2-24 zeigt dies anhand der Komponente (bzw. der Komponenten-Verwendung) „A1\*1-B“, welches über die sog. *GlobalAssetId* mit dem entsprechenden Komponenten-Typ verknüpft ist.

[^11]: <https://github.com/VWS4LS/vws4ls-aaspe-plugin>

![image](https://github.com/user-attachments/assets/11bca26e-8825-4c8d-801e-7b66140c9809)

Abbildung 2-24:Verknüpfung Komponenten-Verwendung mit Komponenten-Typ per GlobalAssetId

Ebenfalls unter Zuhilfenahme des [VWS4LS-AASPE-Plugin](https://github.com/VWS4LS/vws4ls-aaspe-plugin) konnte anschließend die Ableitung der Leitungssatz-Verwaltungsschale für den Konfektionär durchgeführt werden (vgl. Abbildung 2-16). Hierbei wurden die im Rahmen des Architekturteams entwickelten Prinzipien zur Verlinkung der unterschiedlichen Sichten angewendet. So verweisen z.B. Elemente in der Produkt-BOM in der Verwaltungsschale des Konfektionärs auf die äquivalenten Elemente in der Produkt-BOM des OEMs. Diese Duplizierung mit Verlinkung ermöglicht einerseits die Nachvollziehbarkeit des Ursprungs von Komponenten, anderseits aber auch die Anpassung der Produkt-BOM durch den Konfektionär z.B. durch Ergänzen von Elementen, die vom OEM nicht betrachtet werden (Klebebänder oder andere für Produktion/Transport notwendige Komponenten).

Auf Basis der OEM-Verwaltungsschale für den Leitungssatz-Typ konnten anschließend Schritt für Schritt benötigte Halbfabrikate abgeleitet werden. Abbildung 2-25 zeigt ein solches Halbfabrikat: eine geschnittene Leitung. Auch hier wurden wieder die im Rahmen des Architekturteams entwickelten Strukturen bzgl. der Verlinkung von Elementen angewendet. Abbildung 2-25 zeigt dies durch die Manufacturing-BOM des Halbfabrikats: Für dessen Herstellung wird lediglich eine einzige Komponente benötigt – die Leitung als Ausgangsmaterial. Diese Leitung ist jedoch über eine entsprechende *SameAs*-Beziehung aus der Manufacturing-BOM des Gesamt-Leitungssatzes referenziert, wodurch eine durchgängige Erkundbarkeit der Produktstruktur vom Gesamtleitungssatz bis hin zu den Halbfabrikaten auf den untersten Ebenen gewährleistet wird.

![image](https://github.com/user-attachments/assets/2d41e8af-e883-484f-adb0-f1af210fc623)

Abbildung 2-25: Verwaltungsschale für ein Halbfabrikat "Geschnittene Leitung"

Die Integration der verschiedenen Teilmodelle von unterschiedlichen Zulieferern in die Verwaltungsschale wurde erfolgreich in Verbindung mit der [BaSyx](https://wiki.basyx.org)[^12] Middleware umgesetzt, die als zentrale Plattform für die Verwaltung und Integration der Verwaltungsschalen diente.

[^12]: <https://wiki.basyx.org>

Die BaSyx Middleware ermöglichte eine flexible und skalierbare Integration der Teilmodelle der verschiedenen Zulieferer. Im Rahmen dessen wurden spezifische Sichten der Verwaltungsschalen von Tier-2 Lieferanten eingebunden, sodass lediglich die relevanten Produktinformationen, jedoch ohne interne Produktionsdaten, in die zentrale Verwaltungsschale des Tier-1 integriert wurden. Dies sicherte den Schutz sensibler Daten und gewährleistete gleichzeitig die Konsistenz und Verfügbarkeit für die Leitungsschatzentwicklung notwendigen Informationen.

### 2.5.5 Fähigkeitsabgleich der Produktionsmaschinen

Ein weiterer Aspekt bei der Integration war die Abstimmung zwischen den produktseitigen Anforderungen und den verfügbaren Fähigkeiten der Produktionsmaschinen. In einem ersten Schritt wurde eine Analyse durchgeführt, um die erforderlichen Fähigkeiten des Produkts für die Produktion zu ermitteln. Darauf aufbauend wurde untersucht, welche Fähigkeiten auf Seiten der Produktionsmaschinen vorhanden sind. In dem Implementierungsschritt bzw. dem Demonstrator wurden zwei verschiedene Produktionsmaschinen über die Verwaltungsschale angebunden und deren Fähigkeiten modelliert.

Durch den Abgleich der Produktanforderungen mit den Maschinenfähigkeiten konnten die Produktionsressourcen optimal genutzt und die Produktionseffizienz gesteigert werden. Die Verwaltungsschalen der Maschinen enthielten detaillierte Informationen zu ihren Fähigkeiten, die über die BaSyx Middleware zentral verwaltet und den spezifischen Anforderungen des Leitungssatzes gegenübergestellt wurden. Dieser Abgleich ermöglichte eine zielgerichtete Planung und Steuerung der Produktionsprozesse.


### 2.5.6 Abschlussdemonstrator

Das im Rahmen von AP 2.5 modellierte System wurde auf den Abschlussdemonstrator übertragen, um dessen Interaktion mit den anderen Teilprojekten zu analysieren. Der Demonstrator diente dabei als Testumgebung, in der die Integration der VWSen sowie die Interaktion der Teilmodelle in einer realistischen Umgebung nach dem folgenden Schema evaluiert wurden:

1.  **Projektion des Modells auf den Demonstrator**: Dies beinhaltete die Implementierung der Verwaltungsschale und der Teilmodelle in der Testumgebung, um die reale Anwendung der entwickelten Struktur zu überprüfen.
2.  **Testen der Integration**: Im Demonstrator wurden alle relevanten Schnittstellen und Interaktionen zwischen den verschiedenen Teilprojekten getestet. Hierbei wurden insbesondere die Verknüpfungen zwischen den Teilmodellen und deren Integration in die BaSyx Middleware überprüft.
3.  **Erfassung der Resultate**: Die durchgeführte Tests ermöglicht wertvolle Einblicke in die Funktionalität der Verwaltungsschale und der Teilmodelle im Zusammenspiel. Die Ergebnisse zeigten, wie gut die Teilmodelle integriert werden konnten, und identifizierten mögliche Schwachstellen oder Optimierungspotenziale.
4.  **Optimierungsmaßnahmen**: Auf Basis der Testergebnisse wurden Anpassungen und Verbesserungen am System vorgenommen. Diese Maßnahmen dienten dazu, die Effizienz der Integration zu erhöhen und sicherzustellen, dass alle Komponenten nahtlos zusammenarbeiten.

## 2.6 Fazit

Das übergeordnete Ziel des gesamten Vorhabens war es, eine dezentrale Datenhaltung zu ermöglichen, während gleichzeitig eine Aggregation der Komponentenverwaltungsschalen erreicht wird. Durch die erfolgreiche Umsetzung konnte dieses Ziel weitgehend realisiert werden. Die wesentlichen Ergebnisse umfassen:

1.  **Integration der Teilmodelle**: Die Verwaltungsschale des Tier-1 konnte erfolgreich mit spezifischen Sichten der Zulieferer-Verwaltungsschalen angereichert werden, ohne sensible interne Informationen offenzulegen. Die dezentrale Datenhaltung wurde beibehalten, während die Aggregation der relevanten Daten durch die zentrale Verwaltungsschale ermöglicht wurde.
2.  **Fähigkeitsabgleich** zur Optimierung der Produktion. Die Verwaltungsschalen der Maschinen ermöglichten eine präzise Zuordnung der Produktionsressourcen.
3.  **Ergebnisse des Abschlussdemonstrators** bestätigten die erfolgreiche Integration und Interaktion der Teilmodelle. Gezielte Optimierungsmaßnahmen bestätigten die Funktionalität der entwickelten Struktur.
4.  **Einsatz der BaSyx Middleware** als zentrale Plattform für die Kommunikation und Datenverarbeitung zwischen den verschiedenen Akteuren.
5.  **Einsatz des AASX-Explorers** und des in VWS4LS entwickelten [VWS4LS-AASPE-Plugin](https://github.com/VWS4LS/vws4ls-aaspe-plugin) unterstützte die schnelle und fehlerfreie Erstellung der VWS, was sehr hilfreich war, um effizient LS-VWSen erzeugen zu können. Allerdings ist der Package Explorer als Prototyping-Tool und nicht für Produktivanwendungen gedacht, daher wäre eine Integration der Funktionalität zur Generierung von LS-VWSen in die Engineering-Applikations-Toolkette wünschenswert. Denkbar wäre bspw. eine BaSyx-Backend-Funktionalität analog zu dem AASPE-Plugin, mit der anhand einer vorliegenden KBL- oder VEC-Datei eine VWS mit den notwendigen Submodellen erzeugt und möglichst weitgehend inhaltlich vorbefüllt werden kann.

    Insgesamt zeigte das TP2, dass die Verwaltungsschale als zentrales Werkzeug zur Steuerung und Optimierung der Leitungssatzentwicklung und der zugehörigen Produktionsprozesse eingesetzt werden kann. Die Kombination aus Verwaltungsschalen, Middleware und Fähigkeitsabgleich kann wesentlich zur Effizienzsteigerung und Flexibilität in der Produktionsplanung beitragen.

    Die erfolgreich durchgeführten Tests im Abschlussdemonstrator bestätigen das Ziel der erfolgreichen Integration einer dezentralen Datenhaltung mit zentraler Aggregation der Verwaltungsschalen. Die in dem Zusammenspiel aller Komponenten gewonnenen Erkenntnisse wurden final dokumentiert, um auch über der Laufzeit dieses Projektes hinaus zur Verfügung zu stehen.

# Literaturverzeichnis

|       | |
|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [1]   | Industrial Digital Twin Association e.V., „Registrierte IDTA Submodelle,“ [Online]. Available: https://industrialdigitaltwin.org/en/content-hub/submodels.                                                                                                                                |
| [2]   | Industrial Digital Twin Association e.V., „IDTA 02006-2-0 Digital Nameplate for Industrial Equipment,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Digital%20nameplate/2/0.                                                             |
| [3]   | Industrial Digital Twin Association e.V., „IDTA 02020-1-0 Capability Description,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/development/Capability/1/0.                                                                                        |
| [4]   | Prostep ivip, „Harness Description List (KBL),“ prostep ivip, 26 Jun 2022. [Online]. Available: https://ecad-wiki.prostep.org/specifications/kbl/.                                                                                                                                        |
| [5]   | Prostep ivip, „Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.                                                                                                                                  |
| [6]   | Industrial Digital Twin Association e.V., „IDTA 02011-1-1 Hierarchical Structures enabling Bills of Material,“ 2024 June. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Hierarchical%20Structures%20enabling%20Bills%20of%20Material/1/1. |
| [7]   | Plattform Industrie 4.0, „Interoperability at Runtime - Exchanging Information via Application Programming Interfaces,“ Plattform Industrie 4.0, Berlin, 2021.                                                                                                                            |
| [8]   | „Verband der Automobilindustrie (VDA),“ [Online]. Available: https://www.vda.de/de.                                                                                                                                                                                                       |
| [9]   | J. Becker, „Whitepaper KBL vs. VEC - Similarities and differences - briefy and concisely summarized,“ 16 December 2022. [Online]. Available: https://ecad-wiki.prostep.org/post/kbl-vs-vec/.                                                                                              |
| [10]  | OPC Foundation, „OPC 40001-3: Machinery Job Mgmt,“ OPC Foundation, [Online]. Available: https://reference.opcfoundation.org/Machinery/Jobs/v100/docs/.                                                                                                                                    |
| [11]  | OPC Foundation, „OPC 30270: Industry 4.0 Asset Administration Shell,“ [Online]. Available: https://reference.opcfoundation.org/I4AAS/v100/docs/.                                                                                                                                          |
| [12]  | OPC Foundation, „OPC 40001-1: Machinery Basic Building Blocks,“ [Online]. Available: https://reference.opcfoundation.org/Machinery/v103/docs/.                                                                                                                                            |
| [13]  | OPC Foundation, „OPC 40001-101: Machinery Result Transfer,“ [Online]. Available: https://reference.opcfoundation.org/Machinery/Result/v100/docs/.                                                                                                                                         |
| [14]  | OPC Foundation, „OPC UA Nodesets,“ [Online]. Available: https://github.com/OPCFoundation/UA-Nodeset.                                                                                                                                                                                      |
| [15]  | Platform Industrie 4.0, „RAMI 4.0: Ein Referenzarchitekturmodell als Kommunikationsgrundlage in der Industrie 4.0,“ 11 04 2022. [Online]. Available: https://www.dke.de/de/arbeitsfelder/industry/rami40.                                                                                 |
| [16]  | OPC Foundation, „OPC 40570: OPC UA for the Wire Harness Manufacturing Industry,“ https://profiles.opcfoundation.org/workinggroup/88, WiP. [Online]. Available: https://profiles.opcfoundation.org/document/214.                                                                           |
| [17]  | „VEC Release Notes - Version 2.1.0,“ prostep ivip, 08 01 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/release-notes/.                                                                                                                                 |
| [18]  | „VWS4LS-Github,“ ARENA2036 e.V., [Online]. Available: https://github.com/VWS4LS.                                                                                                                                                                                                          |
| [19]  | KEBA, „OPC UA – der zentrale Standard für Industrie 4.0 im Überblick,“ [Online]. Available: https://www.keba.com/de/news/industrial-automation/ueberblick-opc-ua-zentraler-standard-industrie-4-0.                                                                                        |
| [20]  | IEC, „IEC 61360-4 - IEC/SC 3D - Common Data Dictionary,“ [Online]. Available: https://cdd.iec.ch/cdd/iec61360/iec61360.nsf/TreeFrameset?OpenFrameSet.                                                                                                                                     |
| [21]  | Industrial Digital Twin Association e.V. (IDTA), „IDTA 02020-1-0 Capability Description,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/development/Capability/1/0.                                                                                 |
| [22]  | „Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.                                                                                                                                                |
| [23]  | „Harness Description List (KBL),“ prostep ivip, 26 Jun 2022. [Online]. Available: https://ecad-wiki.prostep.org/specifications/kbl/.                                                                                                                                                      |
| [24]  | VWS4LS Architektur-Team, „Struktur der VWS (?),“ AREAN2036 e.V., Stuttgart, 2024.                                                                                                                                                                                                         |
| [25]  | Industrial Digital Twin Association e.V., „IDTA 02031-1-0 Bill of Process (WiP),“ [Online]. Available: https://industrialdigitaltwin.org/content-hub/teilmodelle.                                                                                                                         |
| [26]  | Industrial Digital Twin Association e.V., „IDTA 02056-1-0 Data Retention Policies,“ June 2024. [Online]. Available: https://industrialdigitaltwin.org/wp-content/uploads/2024/06/IDTA-02056-1-0_Submodel_Data-Retention-Policies.pdf.                                                     |

# Abbildungsverzeichnis

[Abbildung 2-1: Kollaborationsbeziehungen in der Leitungssatz-Entwicklung](#_Toc178808280)

[Abbildung 2-2: Eingangs- und Ausgangsdaten im Entwicklungsprozess im Überblick](#_Toc178808281)

[Abbildung 2-3: Anfrage beim Komponentenhersteller stellen](#_Toc178808282)

[Abbildung 2-4: Auskunft auf Anfrage](#_Toc178808283)

[Abbildung 2-5: 2. Anfrage mit Detail-Anforderungen](#_Toc178808284)

[Abbildung 2-6: Beispiel für zentralen Ansatz](#_Toc178808285)

[Abbildung 2-7: Freigaben und Änderungs-Management beim dezentralen Ansatz](#_Toc178808286)

[Abbildung 2-8: SPoT-Bezeichnung beim dezentralen Einsatz](#_Toc178808287)

[Abbildung 2-9: Beispiel für einen Stecker, der an zwei verschiedenen Standorten verwendet wird](#_Toc178808288)

[Abbildung 2-10: Freigaben und Änderungs-Management](#_Toc178808289)

[Abbildung 2-11: Überblick Teilprozesse der Leitungssatzentwicklung](#_Toc178808290)

[Abbildung 2-12: Referenzprozess der Leitungssatz-Entwicklung](#_Toc178808291)

[Abbildung 2-13: Workflow Entwicklung Leitungssatz](#_Toc178808292)

[Abbildung 2-14: Assets und ihre VWS im Entwicklungsprozess des Leitungssatzes](#_Toc178808293)

[Abbildung 2-15: Ausschnitt aus der Anforderungsanalyse für VWS und deren Teilmodelle](#_Toc178808294)

[Abbildung 2-16: VWS-Schnittstellen im Entwicklungsprozess zwischen OEM und Konfektionär](#_Toc178808295)

[Abbildung 2-17: Beispielleitungssatz aus dem PPR-Workshop](#_Toc178808296)

[Abbildung 2-18: SVG-Darstellung des Leitungssatzes](#_Toc178808297)

[Abbildung 2-19: WIRE und BOM mit dargestellter Modularisierung (V1, V2 und V3)](#_Toc178808298)

[Abbildung 2-20: MLK 1,2 Terminal mit/ohne ELA (KOSTAL Kontakt Systeme GmbH & Co. KG)](#_Toc178808299)

[Abbildung 2-21: Auszug aus einer Typ-Verwaltungsschale Terminal](#_Toc178808300)

[Abbildung 2-22: Äquivalenzbeziehungen per „spedificAssetId“](#_Toc178808301)

[Abbildung 2-23: OEM-Verwaltungsschale für den Gesamtleitungssatz](#_Toc178808302)

[Abbildung 2-24:Verknüpfung Komponenten-Verwendung mit Komponenten-Typ per GlobalAssetId](#_Toc178808303)

[Abbildung 2-25: Verwaltungsschale für ein Halbfabrikat "Geschnittene Leitung"](#_Toc178808304)
