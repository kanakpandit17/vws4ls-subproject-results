# TP 3 - Produktionsprozesse des Leitungssatzes

## Inhalt

[Zielsetzung](#zielsetzung)

[AP 3.1 - Untersuchung von Anforderungen](#_3.1)
- [3.1.1 Vorgehen](#_3.1.1)
- [3.1.2 Ergebnisse](#_3.1.2)

[AP 3.2 - Erforschung eines Referenzmodells](#_3.2)
- [3.2.1 Datenfluss-Architektur](#_3.2.1)
- [3.2.2 Use Cases](#_3.2.2)
- [3.2.3 CAD2BOP](#_3.2.3)

[AP 3.3 - Erforschung von Teilmodellen für Rückmeldedaten](#_3.3)

- [3.3.1 Leitungssatzproduktion](#_3.3.1)
- [3.3.2 Produktionsprozesse](#_3.3.2)
- [3.3.3 Prozess VWS](#_3.3.3)
- [3.3.4 Capabilities aus Prozesssicht](#_3.3.4)
- [3.3.5 Prozesssteuerung](#_3.3.5)
  
[AP 3.4 - Proof of Concept](#_3.4)
- [3.4.1 Datenvalidierung](#_3.4.1)
- [3.4.2 Datenmapping](#_3.4.2)

[AP 3.5 - Validierung der Prinzipien](#_3.5)
- [3.5.1 Prozessablaufsteuerung für Produktionsprozesse](#_3.5.1)
- [3.5.2 Datenmapping mit Validierung](#_3.5.2)
- [3.5.3 Micro-Service „Datenvalidierung“](#_3.5.3)
- [3.5.4 Traceability](#_3.5.4)
- [3.5.5 Transfer in andere Produktserien](#_3.5.5)

[3.6 Fazit](#_3.6)

[3.7 Anhang: UML-Diagramm](#_3.7)

[Literaturverzeichnis](#literaturverzeichnis)

## <a name="zielsetzung"></a>Zielsetzung
Im Teilprojekt 3 "**Produktionsprozesse des Leitungssatzes**" wurden Konzepte und Verfahren entwickelt, welche die Informationen der Verwaltungsschalen der Produkte, Ressourcen und Prozessbeschreibungen sowie den aktuellen Anlagenzuständen kombinieren, aufbereiten und verarbeiten, um automatisiert die Produktionsmaschinen bzw. deren Montage-Skills zu konfigurieren und zu parametrieren.

Kernthema war daher die Erforschung eines Konzeptes bzw. Modelles, wie unter diesen Bedingungen der Digitale Zwilling des gesamten Leitungssatzes angewendet werden kann.

Das Teilprojekt wurde in folgende Arbeitspakete aufgeteilt, deren Resultate in diesem Dokument zusammenfassend erläutert werden:

-   AP 3.1 - Untersuchung von Anforderungen
-   AP 3.2 - Erforschung eines Referenzmodells
-   AP 3.3 - Erforschung von Teilmodellen für Rückmeldedaten
-   AP 3.4 - Proof of Concept
-   AP 3.5 - Validierung der Prinzipien

## <a name="_3.1"></a>AP 3.1 - Untersuchung von Anforderungen

Im Arbeitspaket 3.1 „Untersuchung von Anforderungen“ lag der primäre Fokus auf der Erfassung und Analyse aller Anforderungen für die Anwendung des digitalen Zwillings eines Leitungssatzes unter Nutzung der Verwaltungsschale. Dies erfolgte durch explizite Partnerzusammenarbeit innerhalb des Projektes, um eine Anforderungsbasis zu erstellen. Auf diese Basis wurde im weiteren Projektverlauf zurückgegriffen, um die Berücksichtigung bzw. Implementierung der einzelnen Anforderungen zu prüfen.

### <a name="_3.1.1"></a>3.1.1 Vorgehen

Für die Anforderungsspezifikation wurde ein fünfstufiges Phasenmodell verfolgt. *Abbildung* 11 zeigt die einzelnen Phase und welche Teilprojekte bzw. Partner für die jeweilige Phase verantwortlich waren. In den folgenden Unterkapiteln wird jede einzelne Phase genauer beschrieben.

![image](https://github.com/user-attachments/assets/1818ee29-3e0f-4282-afe5-549332b85055)    
*Abbildung 3-1: Phasenmodell für die Anforderungsspezifikation*

#### Phase 1 - Anforderungstemplate erstellen

Die Anforderungserhebung wurde für mehrere Teilprojekte geplant, um möglichst zum Projektstart eine solide Anforderungsbasis zu schaffen. In TP3 wurde hierfür ein einheitliches Anforderungstemplate erarbeitet und allen TPs zur Verfügung gestellt. Das Anforderungstemplate wurde auch als Grundlage für die Anforderungsdokumentation entwickelt, damit für die später folgende Anforderungskonsolidierung die Zusammenführung aller Anforderungen in einem Dokument effizient erfolgen konnte.

Das Template wurde in einer Excel-Datei aufgebaut und beinhaltet folgende Informationen für jede Anforderung:

-   **ID**  
    Ein eindeutiger Identifier, bestehend aus den beiden ersten Buchstaben des Vor- und Nachnamens und einer laufenden Nummer. Beispiel: Max Mustermann erstellt seine erste Anforderung mit ID „MaMu-01“, die Zweite mit „MaMu-02“, und so weiter.
-   **Titel**  
    Die Kurzbezeichnung der Anforderung.
-   **Beschreibung**  
    Eine ausführliche Beschreibung der Anforderung mit Bezug zu den jeweiligen Anwendungsfällen und wichtigen Kriterien.
-   **PPR-Kategorie**  
    Eine Zuordnung der Anforderung in die drei Kategorien Produkt, Prozess und Ressource, wobei Prozess in die Unterkategorien Entwicklungsprozess, Produktionsprozess und Montageprozess unterteilt wurde.
-   **Wertschöpfungsstufe**  
    **Eine Zuordnung der Anforderung zu einer oder mehrerer Wertschöpfungsstufen, als Unterkategorisierung der PPR-Kategorien (Entwicklung, Produktion, Montage, etc.).
-   **Datenbedarf**  
    **Daten, die für die Umsetzung der Anforderung zwingend notwendig sind.
-   **Priorisierung**  
    **Einordnung der Anforderung in die Kategorien: Muss (Gesetzlich), Soll oder Wunsch.
-   **Link zu User Story**  
    **Wenn zu einer Anforderung noch eine User Story beschrieben wurde, konnte diese hier verlinkt werden.
-   **Unternehmen, Autor, E-Mail**  
    **Informationen zum Anforderungsersteller.**

Zusätzlich wurden Felder für die Teilprojekte 1-8 und den Use Cases 1-5 hinzugefügt, um die Anforderung relevanten Teilprojekten bzw. Use Cases zuordnen zu können.

#### Phase 2 - Anforderungssammlung

In Phase 2 wurde das Anforderungstemplate allen Konsortialpartnern für die Anforderungssammlung zur Verfügung gestellt. Der Zeitraum für die Anforderungssammlung betrug 4 Wochen. In diesem Zeitraum wurden unternehmensinterne Anforderungen aus den verschiedenen Fachbereichen vom jeweiligen Konsortialpartner gesammelt und in das Anforderungstemplate eingetragen. Zum Ende dieser Phase wurden alle Anforderungsdokumente zentral abgelegt.

#### Phase 3 - Anforderungskonsolidierung

Im Rahmen der Anforderungskonsolidierung wurden die einzelnen Anforderungsdokumente der Konsortialpartner strukturell bereinigt und zu einem partnerübergreifenden Dokument zusammengefasst. Das vorgegebene Template ermöglichte hierbei ein unkompliziertes Zusammenführen aller Einzeldokumente in einem Gesamtdokument. Nach Beendigung der Anforderungskonsolidierung konnten insgesamt 166 Anforderungen in einer zusammengefassten Anforderungsliste integriert werden.

#### Phase 4 - Anforderungsanalyse

Für die Anforderungsanalyse wurde auf Grundlage der einheitlichen Anforderungsliste eine Arbeitsgruppe eingesetzt. Diese hatte die Aufgabe alle Anforderungen auf Vollständigkeit und Verständlichkeit zu prüfen. Unklare oder unvollständige Anforderungen wurden identifiziert und an den Anforderungsersteller zur Nachbesserung weitergeleitet und ergänzt.

#### Phase 5 - Anforderungsspezifikation

In einer weiteren Arbeitsgruppe wurden schließlich alle Anforderungen auf Redundanz geprüft. Dies beinhaltete die Zusammenfassung inhaltstechnisch gleicher und überlappender Anforderungen, damit ein einheitliches Verständnis zu jeder Anforderung erzielt werden konnte. In diesem Zuge wurden zusätzliche globale Identifier integriert, auch um den Bezug zu den ursprünglichen Anforderungen zu erhalten. In dieser Phase konnten insgesamt 89 Anforderungen spezifiziert werden für die weitere Nutzung und Bearbeitung im Projekt.

### <a name="_3.1.2"></a>3.1.2 Ergebnisse

Im Rahmen des AP 3.1 wurde eine Vorlage für die Anforderungserhebung entwickelt, TP übergreifend von allen Konsortialpartnern angewendet, partnerübergreifend konsolidiert und bereinigt. Hieraus ist eine Liste mit konkreten Anforderungen an den digitalen Zwilling eines Leitungssatzes und dessen Umsetzung durch Nutzung von Verwaltungsschalen entstanden.

Die Anforderungsliste wurde durch TP1 ergänzt, um die Anforderungen gegen projektrelevante Themen wie OPC UA, KBL, VEC und MIKO abzugleichen. Das „[Manufacturing Interface Komax“ (MIKO)](https://www.komaxgroup.com/de-de/products/software-and-networking/miko)[^1] ist eine Schnittstelle für den Datenaustausch an kabelverarbeitende Automaten der Fa. Komax, basierend auf den Protokollen [HTTP](https://de.wikipedia.org/wiki/HTTP) und [MQTT](https://de.wikipedia.org/wiki/MQTT).

[^1]: <https://www.komaxgroup.com/de-de/products/software-and-networking/miko>

Die gesammelten Ergebnisse finden sich in der Anforderungstabelle „[VWS4LS_AP3.1_Requirementsammlung_2022_05_06.xlsx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/VWS4LS_AP3.1_Requirementsammlung_2022_05_06.xlsx)“[^2].

[^2]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/VWS4LS_AP3.1_Requirementsammlung_2022_05_06.xlsx>

| **Global-ID** | **Personen-ID** | **Titel**   | **Title**    | **Beschreibung**               | **Description**             |
|---------------|-----------------|-------------|--------------|--------------------------------|-----------------------------|
| GL_1          | ALKI-05 PANE-02 | Grenz- und Sollwerte       | Limits and nominal values     | Für die Auslegung des Prüfequipments und Bewertung von Messwerten müssen die Grenz- bzw. Sollwerte bekannt sein.  Diese Anforderung richtet sich speziell an Werte die in der Produktion überprüft und bewertet werden müssen und somit Ausschlaggebend für die Bewertung eines OK-Teils sind.  Die Grenzwerte entsprechen hierbei den Bewertungskriterien für einen Messwert. Sie sind zudem ausschlaggebend für die Wahl eines geeigneten Messsystems.  Es ist nicht notwendig für jeden Messwert eine absolute Ober- und Untergrenze oder eine unabhängige Toleranz zu definieren, solange sich die Grenzwerte aus den vorhandenen Angaben ableiten lassen.  Beispiele:  • Widerstand 1-0,05 Ohm • Drehmoment 15 Nm ±10% • Länge 100 mm (Allgemeintoleranz ISO 2768-mK) • Isolationswiderstand \>4.5 MOhm  Dabei ist zu beachten, dass die Prüftoleranz von den Zeichnungsangaben abweichen können. Beispielsweise kann eine Verschraubung mit 15 Nm ±10% in der Zeichnung definiert sein und tatsächlich mit 15 Nm ±5% bewertet werden.  | The limits and nominal values must be defined, so that the test equipment can be designed and measured value can be evaluated.     |
| GL_2          | EmDa_21        |          | Data access for machine manufacturers - Monitoring (rw)     | Als Maschinenhersteller will ich in Abhängigkeit der aktivierten Überwachungssysteme (bei der akuellen Produktspezifikation) die zugehörigen Überwachungstools ermitteln können, um damit die Messungen durchführen zu können.    | As a machine manufacturer I want to read the state of all enabled monitoring processes so that I can choose the appropriate measurement equipment/resource to perform the task depending on the product specification     |
| GL_3          | ROMI-01 HORÖ-03  | Istanzdatenversion   | Crimp/Seal data version       | Als Manager möchte ich in der Lage sein, eine Version der Instanzdaten zu erstellen, damit ich ihre Parameter ändern kann. Historische Instanzdaten müssenzugänglich sein, um z.B. Fehlerursachen ermitteln zu können.  | As a manager, I want to be able to create a version of the instance data so I can change its parameters.  |
| GL_4          | ROMI-02     | Versionierung von Instanzdaten        | Versioning of Crimp/Seal data versions      | Als Manager möchte ich die verschiedenen Versionen von Instanzdaten visualisieren, damit ich nachvollziehen kann, wer Änderungen vorgenommen hat und warum   | As a manager, I want to visualize the different versions of instance data so I can understand who made changes and why        |
| GL_5          | ROMI-03        | Zulassung Prozessdaten (Crimpdaten)     | Approval crimp data   | Als Manager möchte ich „freigegebene“ neue Sätze von Prozessdaten (bspw. Crimp- und Werkzeugdaten) aus meiner Datenbank abrufen, damit sie in den Produktionsmaschinen verwendet werden können.   | As a Manager I want to fetch "Released" new sets of crimp and tool data from my database so that it can be used in production machines.    |
| GL_6          | TOKR05 ROMI-07   | Möglichkeiten der Parameter-Anpassung der Komponenten  Bestehende Produktionsparameter ändern    | Possibilities of parameter adjustment of the components  Modify existing production parameters | Möglichkeiten der Parameter-Anpassung in der laufenden Maschine. D.h. bei Produktionsänderungen soll es möglich sein, prozessrelevante Parameter einer Komponente anzupassen.  Als Kunde möchte ich die neuesten Versionen von Prozessdaten (Crimp- und Werkzeugdaten) aus einer Datenbank abrufen, damit ich neue Werkzeuge verwenden oder die Parameter der bereits Verwendeten ändern kann.    | Possibilities of parameter adjustment in the running machine. This means that it should be possible to adjust process-relevant parameters of a component in case of production changes.  As a Customer I want to fetch the latest versions of crimp and tool data from a database so that I can use new tools or modify the parameters of the ones I am already using. |
| GL_7          | HORÖ-02  | Ausstattung und Konfiguration der Maschine     | Equipment and configuration of the machine    | Um die Fehlerursache zu ermitteln, müssen die Ausstattungs- und Konfigurationdaten der Maschine zum Zeitpunkt der Prüfung bekannt sein.     | In order to determine the cause of a defect, the equipment and configuration data of the machine at the time of the test must be known.                                                                                                                                                                                                                                |
| GL_8          | FRST-01 ALKI-01 RoMi_04 RoMi_05 JOZI-07 JOZI-01 MIBR-08 RoMi_07 BeJo_03    | Eindeutige Beschreibung und Identifikation des Leitungssatzes und aller Einzelkomponenten im Leitungssatz     | Für alle im Leitungssatz vorhandenen Teile (auch Zusammenbauteile, Kaufteile o.ä.) gibt es eine Beschreibung/Auflösung aller Einzelkomponenten (in der KBL/VEC/…). Diese können durch eine Art "hierarchische Klammerung" als Zusammenbauteil gekennzeichnet sein  Für die eindeutige Zuweisung von Steckern und Leitungssatzkomponenten muss jede Komponente eindeutig identifiziert sein (Steckerbezeichnung, Steckernummer, XCode, etc.).  Für die automatische Zuordnung von Prüfaufnahmen und Leitungssatzkomponenten muss die eindeutige (global) Typidentifikation aller Komponenten bekannt sein.  Für die Auslegung des Prüfequipments müssen die Merkmale für alle Komponenten des Leitungssatzes bekannt sein (Steckerbezeichnung, Ausstattung, Kontaktbezeichnungen, etc.).  Als API-Benutzer möchte ich auf die Daten jedes Kabels zugreifen, damit ich dessen Länge, Crimp, Dichtung, Aufdruck und andere Informationen lesen kann  Jedes Produkt (ein Kabel oder ein Bündel)erhält eine eigene ID zur Identifikation. Weiter müssen alle Teilprodukte (entnehme zwei Leitungen aus dem Bündel und werden verdrillt) müssen ebenfalls eine eigene ID erhalten. |    |
| GL_9          | JuNe-02 FRST-07       | OEM-Input - Last- und Temperaturprofile von Verbrauchern und Bauraum zur Leitungsauslegung   |    | Zur Ermittlung des zu verwendenden Leitungsquerschnitt und Isolationsmaterial sind Umfeldparameter wie die Bauraumtemperatur und die Lastprofile (Dauerstrom, dynamische Last usw,) der zu versorgenden Verbraucher notwendig. Wenn diese Parameter bekannt sind, lässt sich eine weitestgehend automatisch Leitungsdimensionierung und Sicherungsauslegung erreichen. Sowie eine robust Auslegung hinsichtlich Spannungsfälle ohne der Gefahr einer Über- oder Unterdimensionierung.  |     |
| GL_10         | DIN-N-05 PEBR-04    | Geometrische Informationen von Tüllen und Schächten, sowie des Verlegeweges innerhalb     | Geometrical representation of grommets and cable ducts and routing inside them   | Um eine eindeutige digitale Beschreibung des Leitungssatzes zu bekommen ist die geometrische Ausgestaltung innerhalb von Tüllen und Schächten erforderlich, sowie die geometrische Ausgestaltung der Tüllen und Kabelschächte selbst. Die geomtrische Ausgestaltung wird verwendet für die Konstruktion von Werkzeugen, Kabelformbrettern und Kabelformbrettaufnahmen.    |     |
| GL_11         | DIZA-01      | Maschinenidentifikation       | Machine identification        | Um die Fehlerursache an der richtigen Maschine zu ermitteln, muss die Maschinenidentifikation bekannt sein.   | In order to determine the cause of a fault on the correct machine, the machine identification must be known.       |
| GL_12         | BAMA-04 BeJo-01 EmDa_11 GENE-02 GENE-04 CaWe_009 HORÖ-01 ArBe-02 GENE-09 MaFe-08 CaWe_012 CaWe_013 EmDa_20 BeJo_06    | Horizontale Rückverfolgbarkeit    | Horizontal Traceability         | Für die Herstellung einer horizontalen Rückverfolgbarkeit müssen Rückmeldedaten aus dem Prozess/ von der Maschine abgefragt und in der Verwaltungsschale des hergestellten Produktes gespeichert werden. Dies gilt insbesondere für Rückmeldungen zu in dem Prozess integrierten Qualitätsüberwachungen. Bietet die Maschine eine aktive Verwaltungsschale ist es sinnvoll, wenn die Rückmelddaten darüber interaktiv abgefragt werden können, um diese Daten z.B. zur Entscheidungsfindung in Verhandlunsgprozessen zwischen Verwaltungsschalen zu nutzen. Auch das für eine Prozess verwendet Rezept soll nachvollziehbar sein.     |      |
| GL_13         | FRST-05 DIN-N-09 DIN-N-04 JOZI-06 PEBR-01 JOZI-02 JOZI-03    | Detailierte geometrische Informationen zu Kontaktträgern und weiteren Anbauteilen (Tüllen, Clipse, Kabelführungen, Kabelbinder uws.)                           |                                                                                                | Geometrische Informationen zu Außenkonturen (Länge, Höhe, Breite) und Innenkonturen von Anbeiteilen und Kontaktträger, sowie zusätzliche konstruktive Informationen beispielsweise bei Kontakträgern Kammernkoordinaten, Stecktiefen usw.   Diese Informationen sind u.a. auch notwendig für die Konstruktion von Prüfaufnahmen  Für eine (teil-)automatisierte Ableitung des Tischlayouts muss die genaue Lage aller Stecker inklusive Einlagerichtung bekannt sein.  Für die Bereitstellung von Hilfswerkzeugen und Produktionshilfsmitteln müssen die Anbauteile (z.B. Kabelbinder) bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_14         | SEAI-01 SEAI-02 DIN-N-01 DIN-N-02 DIN-N-07 FRST-04                                                                                                              | Verarbeitungs- und Verfahrensinformation für diverse Produkttypen (Splice, UTP-verdrillte Leitung, Wicklung usw.)                                              |                                                                                                | Alle notwendigen Verarbeitungspezifikationen und dazugehörige Parameter müssen den entsprechenden Produkttypen datentechnisch zugewiesen und/oder eindeutig identifizierbar sein. Beispiele: *UTP*: Schlaglänge, Entdrilllänge, mit Wicklung gesicherte Enden usw. *Splice*: Verbinderart (End- oder Durchgangsverbinder), Verbidnugnstechnik (U-Schall, Crimp, ...), Gedichtet/Ungedichtet usw. *Wicklung*:Überlappungsgrad und -winkel von Wickelstrecken muss im Datenmodell hinterlegt werden. Zur (automatisierten) Verarbeitung wird sowohl der Überlappungsgrad als auch der Überlappungswinkel benötigt.  |    |
| GL_15         | SEAI-03 FRST-03 FRST-06 WOAI-03   | Vererbung von Klassifikation, Sicherheitsrelevanz, Verbauinformation, Anforderungen usw. von Brodnetzkomponenten auf den Leitungstrang bzw. dessen Komponenten |                                                                                                | Sicherheitsanforderungen die beispielsweise aus FuSi (ISO 26262), ASPICE, Bauraum o.ä. kommen muss diese Information an die angeschlossenen Komponenten übergeben/vererbt werden, um die Komponenten richtig auszuwählen (Festlegung und Verwendung von Standard-Attributen für functional safety (FuSI) und ISO26262 relevante Umfänge). Diese Information muss auch systemübergreifend transferriert werden können. Ebenso brauchen Komponenten entsprechende Properties ob diese Anforderungen erfüllt werden. Beispiel: Steuergeräte mit entsprechenden Anforderungen müssen diese an den Leitungsstrag und dessen Komponenten vererben. FuSi-relevante Verbindungen, die über Trennstellen geführt werden, müssen diese Information an die Trennstelle übergeben. Für die Herstellung der Prüftechnik ist es wichtig die kritischen Abgriffe (z.B. Airbag) für den Test und das Layout zu haben                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_16         | FRST-05 WOAI-04                                                                                                                                                 | Detaillierte Informationen zum Kontaktträger bezüglich der Kompabilität zu Terminals, EADs                                                                     |                                                                                                | Kompatibiltäten von Kontaktträgern zu Terminalsystemen inklusive der verwendbaren Einzeladerdichtungen, maximalen Leitungsdurchmesser usw. u.a. auch für die Prüftechnik relevant zur Konstruktion von Prüfadaptern                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_17         | FRST-05                                                                                                                                                         | Detaillierte Informationen zum Kontaktträger bezüglich der Verarbeitungsspezifikation                                                                          |                                                                                                | Für die automatisierte Fertigung werden die Ausrichung des Terminals zur Kammer des Kontaktträgers benötigt sowie Parameter für Stecktiefe, Steckkräfte usw.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_18         | MIBR-01                                                                                                                                                         | Position der Kontakte im Steckergehäuse                                                                                                                        |                                                                                                | Die Position der Kontakte im Steckergehäuse muss bekannt sein, damit im Fehlerfall die genaue Fehlerposition visualisiert werden kann.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_19         | FRST-02 DIN-N-08                                                                                                                                                | Einheitliche Deklarierung / Klassifizierung von Komponenten (Stammdaten)                                                                                       |                                                                                                | Damit die Kundendaten ohne weitere "Manipulation/Anpassung" bearbeitet und aufbereitet werden können, müssen die Komponenten/Stammdaten einer einheitlichen Klassifikation und Mindestanforderung an Attributierung unterliegen. Auf Seitens OEM sowie auch der Lieferanten z.B: Tüllen / Schrumpfschlauch / Glattschläuche / Wellschläuche / Geflechtsschläuche / Rollschläuche Kabelkanäle / nichtelektrische Leitungen / usw.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_20         | DIN-N-03                                                                                                                                                        | Verzinnen von Litzen nach verbinden Terminal mit Leitung                                                                                                       |                                                                                                | Die Kenntlichmachung, dass Litzen nachträglich verzinnt werden müssen, ist notwendig; heute wird dies teilweise über Text based instructions gemacht, dies ist jedoch nicht einheitlich umgesetzt. Zum einen kann dies eine Anforderung vom OEM sein, so dass dies über KBL/VEC kenntlich gemacht sein muss. Andererseits kann dies auch eine Verarbeitungsrichtliche für das Terminal sein, was dann über ein Attribut des Terminals kenntlich gemacht werden muss.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_21         | DIN-N-10                                                                                                                                                        | Detaillierte Informationen zu Kontaktteilen / Kabelschuhen bezüglich Verbindungsverfahren und Geometriedaten                                                   |                                                                                                | Für Kontaktteile muss eine vollständige geometrische Beschreibung vorliegen im unverabeiteten und verarbeiteten Zustand (Daten wie z.B. Kontaktteilüberstand usw).  Ebenso soll das Verbindungsverfahren des Kontaktierungsbereichs als Merkmal mit übermittelt werden.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_22         | DIN-N-13                                                                                                                                                        | Befestigungstechnik für Clipse und Kabelführungen                                                                                                              |                                                                                                | Mit welcher Prozesstechnik Clipse und Kabelführungen am Leitungsstrang befestigt werden (z.B. Wickelband, Kabelbinder usw.) soll mit übertragen werden. Die Typanweisung zur Befestigung des Clips / Kabelfürhung muss definiert sein und die Information des einzelnen Clips / Kabelführung (je Position) muss ebenso definiert und übermittelt werden.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_23         | BAMA-02 BAMA-03 EmDa_13                                                                                                                                         | Überwachung des Materialverbrauchs                                                                                                                             |                                                                                                | Um rechtzeitig Material nachbestellen zu können, und inkorrekt eingestellte Prozessparameter zu erkennen, muss der Materialverbrauch und Ausschuss aller Teile (Kabel, Kontakte, etc.) überwacht werden können.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_24         | EmDa_16 EmDa_17 EmDa_18 EmDa_19                                                                                                                                 | Produktbeschreibung inklusive Verarbeitungsspezifikationen der Komponenten für die Durchführung der Produktionsprozesse                                        |                                                                                                | Als Produktionsressource möchte ich alle Spezifikationsdaten (Kabel, Terminals, Seal, Sleeve, ...) auslesen, damit ich Einrichts- und Prozesschritte planen und durchführen kann.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_25         | WOAI-01 MAZI-02 MIBR-05                                                                                                                                         | Eigenschaften von Konnektoren / Kontaktträgern                                                                                                                 |                                                                                                | Für die Herstellung und richtige Auswahl der Prüftechnik ist es wichtig die Eigenschaften von Konnektoren und die Anforderungen des Leitungssatzes zu haben, um Prüfadapter zu konstruieren/auszuwählen (!!!evtl. ist hier GL_8 mit zu berücksichtigen!!!)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_26         | MAZI-01 PEBR-02                                                                                                                                                 | Leitungssatzinformationen für die Angebotserstellung                                                                                                           |                                                                                                | Für die Angebotserstellung müssen die Leitungssatzinformationen (Zeichnungen, Verbindungspläne, Dimensionen, etc.) bekannt sein.  Mit den Informationen aus der Verwaltungsschale Leitungssatz soll eine Auswahl des geeigneten Produktionsequipments durch Abgleich mit den in den Verwaltunschalen der Ressourcen beschreibenen Fähigkeiten möglich sein. Die Informationen zu den Ressourcen soll eine Mengen/Kapazitätsplanung unterstützen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_27         | PEBR-03 PEBR-05 JOSC-04                                                                                                                                         | Steuerung des Materialflusses durch die Fabrik                                                                                                                 |                                                                                                | Mit den Informationen aus der Verwaltungsschale der Leitungssatz-Instanz soll der Weg des Produktes durch die Fertigung geplant und gesteuert werden. Die einzelnen Anlagen sollen mit Produktdaten und Prozess Vorgabeparametern versorgt werden.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_28         | Anforderung wurde gelöscht und muss nicht weiter berücksichtigt werden. Um den Mehraufwand der Zeilenanpssung nicht vornehmen zu müssen bleibt die Zeile leer.  |                                                                                                                                                                |                                                                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_29         | TOKR03 GENE-10                                                                                                                                                  | Detektierbare Komponente/Ressource im Maschinennetzwerk                                                                                                        |                                                                                                | Auffinden der Komponente in der Maschine zum Zwecke der autom. Verhandlungen (Discovery). Dabei wird die VWS der Komponente im Maschinennetzwerk instanziiert. Analoges gilt für das Auffinden von Produktionsressourcen: Als Produktionsressource möchte ich über einen einen automatsierten Verhandlungsprozess durch Abgleich meiner Capabilities mit Anforderungen entscheiden, welchem Dienst/Steuerungssytem (MES) ich mich anschliessen kann, um so ein Plug&Produce Szenario zu realisieren.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_30         | GENE-11                                                                                                                                                         | Hearbeat & Wiederverbinden                                                                                                                                     |                                                                                                | Als Produktionsressource möchte ich den Status der Verbindung zum Steuerungssystem abfragen, so dass ich das Wiederverbinden oder den Wechsel auf einen Fallback-/Offlinemodus einleiten kann.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_31         | CaWe_010 GENE-07 MiRo-03 CaWe_001                                                                                                                               | Übertragen von Rezepten                                                                                                                                        |                                                                                                | Als Steuerungssystem möchte ich ein Rezept an meine Produktionsressource senden, so dass ich die Durchführung meines Produktionsplanes vorbereiten kann oder Rezepte oder Einstellungen von einer Maschine auf eine andere übertragen kann.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_32         | CaWe_014 GENE-13 GENE-14 CaWe_013                                                                                                                               | Abfragen von Werkzeug-Setup                                                                                                                                    | Read die-set and tool ID                                                                       | Als Steuerungssystem (MES) oder Produktionsressource möchte ich die eingerichteten Werkzeuge (Artikelnummer, Seriennumer, Position) abfragen, so dass ich über die Produktionsfreigabe entscheiden kann und Daten für die Rückverfolgbarkeit sammeln kann.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_33         | BAMA-01 MiRo-01 MiRo-03                                                                                                                                         | Überwachung des Produktionsfortschitts und Status der Produktionsressourcen                                                                                    |                                                                                                | Für eine optimale Planung der Maschinennutzung muss der aktuelle Produktionsfortschritt überwacht werden können. Der Status, Werte der Prozessüberwachung und ggf. Fehlerzustände sollen von den Produktionsressourcen abgefragt werden können.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_34         | MaBa-01 TOKR04 MaFe-10                                                                                                                                          | Bereitstellung von Fähigkeiten der Machinen und Maschinenkomponenten                                                                                           |                                                                                                | Zur Prozessbeschreibung werden Fähigkeiten der Komponenten (Maschine/Anlage) / Ressourcen benötigt. Mit diesen Fähigkeiten können (z.B. KI gestützte) Automatismen und automatisierte Verhandlunsgprozesse durchgeführt werden.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_35         | MiRo-04                                                                                                                                                         | Ausführen von Aktionen auf Produktionsressource                                                                                                                |                                                                                                | Als Kontrollsystem will ich Aktionen/Befehler auf der Produktionsressource ausführen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_36         | MIBR-07                                                                                                                                                         | Leitungs-Routen                                                                                                                                                | Wire routing information                                                                       | Für die Bewertung von kritischen Signalpfaden, müssen die Leitungs-Routen bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | For the evaluation of critical signal paths, the wire routes must be known.                                                                                                                                                                                                                                                                                            |
| GL_37         | JuNe-01 TOKR01                                                                                                                                                  | Digitaler Materialkatalog                                                                                                                                      |                                                                                                | Auf Basis von Designparametern können Materialvorschläge (z.B. passende Stecker) aus den verfügbaren Verwaltungsschalen der Komponenten ausgegeben werden, durch Abgleich der Anforderungen mit den in der VWS hinterlegten Merkmalen der Komponenten. Die Daten je Kategorie der Leitungssatzkomponente sind noch zu beschreiben. Die Attribute werden neben dem Entwicklungsprozess auch zur Steuerung bzw. Validierung der Produktionsprozesse benötigt. In der VWS soll sowohl die Herstellteilenummer als auch die OEM-Teilenummer zu finden sein. Nicht Funktionale Anforderung an OPCUA Companion spec                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_38         | WOAI-02 MaFe-03                                                                                                                                                 | 3D-Daten (CAD-Daten) vom Leitungssatz                                                                                                                          |                                                                                                | Es werden die CAD-Daten des Leitungssatzes benötigt um darauf aufbauend weiterführende Themen zu prüfen, designen, simulieren usw.  Beispiele: Prüftisch Gestaltung Leitungsstrang autom. in Karosserie zu verlegen usw.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_39         | MaFe-03                                                                                                                                                         | 3D-Daten (CAD-Daten) von Ressourcen                                                                                                                            |                                                                                                | Es werden die CAD-Daten der Ressourcen z.B. Greifer, Schrauber, Roboter etc. Als Datenformat wird ein Open Standard Format empfohlen, z.B. glTF, Collada etc, jedoch nicht proprietäre Formate wie JT oder 3DXML.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_40         | ArBe-01                                                                                                                                                         | Standardisierte Kennzeichnung der physikalischen Assets um den Bezug zur Verwaltungsschale herstellen zu können.                                               |                                                                                                | Einheitliche Beschreibung und Spezifikation von Anforderungen für die Codierung(=Kennzeichung) von Komponenten und Systemen zur Traceability zwischen den Unternehmen und auch innerhalb des Unternehmens. Aufgrund der sehr unterschiedlichen Funktionen und Geometrien der Leitungssatzkomponenten wird es notwendig sein, verschiedene Arten der physischen Kennzeichnung am Artikel zu nutzen. Die daraus resultierenden Anforderungen an die Hardware (z.B. Barcodescanner) sind zu berücksichtigen, damit erforderliche Hardware nicht dem durchgängigen Einsatz der VWS im Wege steht.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_41         | ArBe-04                                                                                                                                                         | Validierungsdaten für Kontaktteile für Kontakteilauswahl und Validierung der Leitunsgsatzentwicklung.                                                          |                                                                                                | Um zu überprüfen, ob die Verwendung eines Steckersystems mit dem ausgewählten Leitungsmaterial möglich ist, soll die VWS des Kontaktteils vereinheitlichte Informationen zu den freigegeben/Validierten Kombinationen enthalten (z.B. Leitermaterial, Leiteraufbau, Leitungshersteller, Querschnittsbereich).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                | Freigabeinformationen des Kontakteilhersteller Freigabeinformationen des OEM Erlaubter Querschnittsbereich Erlaubte Leitungsart (Leitermaterial+Litzenaufbau) Erlaubte Leitungshersteller                                                                                                                                                                              |
| GL_42         | SeOl-01                                                                                                                                                         | Variantenabbildung                                                                                                                                           |                                                                                                | Das Datenmodell muss in der Lage sein, die Variantenvielfalt eines Leitungssatzes abzubilden. D.h. eine KBL / VEC muss maximal ausgeprägt sein, jedoch ein Kennzeichen für Varianten für Komponenten mitgeben können.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_43         | HeWi-01                                                                                                                                                         | Projekt IILS: TP5 - Rationalisierung EoL-Prüfung                                                                                                               |                                                                                                | Erweiterte und eindeutige Produktionsdaten müssen einem Leitungssatz zugeordnet werden können, um mithilfe dieser Daten eine EoL-Prüfung zu rationalisieren                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_44         | FRST-08                                                                                                                                                         | Konfigurationsinformationen an Komponenten und Leitungen                                                                                                       |                                                                                                | Wenn alle Komponenten und Leitungen eine ensprechend auswertbare Ausstattungs-/Konfigurationslogik erhalten, können Bestellungen auf Konsistenz geprüft werden und Prüfprogramme gezielter auf den spezifischen KSK erstellt werden.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_45         | DIN-N-06                                                                                                                                                        | Detaillierte Beschreibung der Außenkonturen vor allem bei Kreuzungen und Ausbindungen                                                                          |                                                                                                | Bei den Ausbindungen und Kreuzungen sollen die Bündeldurchmesser berücksichtigt werden und datentechnisch auswertbar sein                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_46         | DIN-N-11                                                                                                                                                        | Verarbeitungs- und Typinformation für Tüllen                                                                                                                   |                                                                                                | Informationen zum Tüllentyp sollen als Merkmal mit übergeben werden, handelt es sich um eine einteilige Tülle mit Fädelprozess oder um eine mehrteilige Tülle die nachträglich angebracht werden kann. Ebenso soll es eine Definition dafür geben, ob es sich um eine Schaumtülle handelt.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_47         | DIN-N-12                                                                                                                                                        | Information zur Ausführungsart von Schläuchen                                                                                                                  |                                                                                                | Mit den Schläuchen soll ein Merkmal übermittelt werden, ob diese in geschlitzter oder geschlossener Ausführung verwendet werden sollen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_48         | TOKR02                                                                                                                                                          | Teilmodell Simulation                                                                                                                                          | Simulation submodel                                                                            | Für die Simulation der Prozesse werden Simulationsmodelle der beteiligten Komponenten benötigt.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | For the simulation of the processes, simulation models of the involved components are required.                                                                                                                                                                                                                                                                        |
| GL_49         | MIBR-02                                                                                                                                                         | Verbindungsinformationen                                                                                                                                       | Connection information                                                                         | Für die automatische Erstellung von elektrischen Prüfprogrammen müssen die Verbindungsinformationen vorhanden sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | For the automatic creation of electrical test programs, connection information must be available.                                                                                                                                                                                                                                                                      |
| GL_50         | MIBR-03                                                                                                                                                         | Bilder von der Kontaktseite der Stecker                                                                                                                        | Picture of the contact side of the connectors                                                  | Für die Fehlervisualisierung muss ein Bild von der Kontaktseite des Steckers vorhanden sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | A picture of the contact side of a connector must exist, so that it can be displayed in case of a failure.                                                                                                                                                                                                                                                             |
| GL_51         | PANE-01                                                                                                                                                         | Seriennummer des Leitungssatzes                                                                                                                                | Serial number of the harness                                                                   | Für die lückenlose Rückverfolgbarkeit aller Prüfergebnisse, muss die Serialnummer des Leitungssatzes bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | For the complete traceability of all test results, the serial number of the harness is required.                                                                                                                                                                                                                                                                       |
| GL_52         | MIBR-04                                                                                                                                                         | Artikelnummer                                                                                                                                                  | Part Number                                                                                    | Für die automatische Konfiguration des Prüfprogramms muss die Artikelnummer des Leitungssatzes bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | For the automatic configuration of the test program, the article number of the harness must be known.                                                                                                                                                                                                                                                                  |
| GL_53         | MIBR-06                                                                                                                                                         | Eigenstabile Gehäuse                                                                                                                                           | Intrinsically stable housings                                                                  | Für die prozesssichere Aufnahme von großen Gehäusen (z.B. Sicherungsboxen) muss sichergestellt werden, dass die Gehäuse eigenstabil sind.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | For the reliable intake of large housings (e.B. fuse boxes), it must be ensured that the housings are intrinsically stable.                                                                                                                                                                                                                                            |
| GL_54         | MIBR-09                                                                                                                                                         | Prüfaufgaben                                                                                                                                                   | Inspection tasks                                                                               | Für die automatische Programmgenerierung müssen die Prüfaufgaben bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | For automatic program generation, the inspection tasks must be known.                                                                                                                                                                                                                                                                                                  |
| GL_55         | JOSC-01                                                                                                                                                         | Prüfanforderungen und Vorschriften                                                                                                                             | Test requirements and regulations                                                              | Für die Auslegung des Prüfequipments müssen die Prüfanforderungen und Vorschriften (standortbezogen) bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | For the design of the test equipment, the test requirements and regulations (plant based) must be known.                                                                                                                                                                                                                                                               |
| GL_56         | JOSC-02                                                                                                                                                         | Hallenlayout                                                                                                                                                   | Production layout                                                                              | Für die Auslegung der Prüfmaschine muss das Hallenlayout inklusive Anschlussmöglichkeiten und Arbeitsrichtung bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | For the design of the testing machine, the production layout including supply sockets and working direction must be known.                                                                                                                                                                                                                                             |
| GL_57         | JOZI-03                                                                                                                                                         | Bereitstellungsart                                                                                                                                             | Supply mode                                                                                    | Für die Bereitstellung geeigneter Schnittstellen und Peripheriegeräten muss die Bereitstellungsart (z.B. Trolley) bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | For the provision of suitable interfaces and peripheral devices, the mode of supply (i.e. trolley) must be known.                                                                                                                                                                                                                                                      |
| GL_58         | JOZI-04                                                                                                                                                         | Produktions-Stückzahlen                                                                                                                                        | Production quantities                                                                          | Für die Wahl eines geeigneten Werkstoffs für die Steckeraufnahmen müssen die Produktionsstückzahlen bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | In order to choose a suitable material for the connector intakes, the production quantities must be known.                                                                                                                                                                                                                                                             |
| GL_59         | JOZI-05                                                                                                                                                         | Kennzeichnungsart                                                                                                                                              | Labeling type                                                                                  | Für die Kennzeichnung von Leitungssätzen nach bestandener Prüfung muss die erforderliche Kennzeichnungsart (Körnerpunkt, Label, etc.) bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | For the marking of harnesses after the test has passed, the desired type of marking (dot marking, label, etc.) must be known.                                                                                                                                                                                                                                          |
| GL_60         | JOSC-05                                                                                                                                                         | Bewertungskritieren für Prüfergebnisse                                                                                                                         | Evaluation criteria for test results                                                           | Für die endgültige Bewertung eines Prüfergebnisses (reparabel, Ausschuss, etc.) müssen die Bewertungskriterien bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | For the final evaluation of a test result (repairable, scrap, etc.), the evaluation criteria must be known.                                                                                                                                                                                                                                                            |
| GL_61         | ROMI-04                                                                                                                                                         | Prozessdaten (Crimpdaten) zur Validierung einreichen                                                                                                           | Submit crimpt data to validation                                                               | Als Manager möchte ich überprüfte Änderungen an Prozessdaten (Crimp- und Werkzeugdaten) aus meiner Validierungsressource an meine Datenbank „übermitteln“, damit sie in der gesamten Organisation verwendet werden können                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | As a Manager I want to "Submit" reviewed changes of crimp and tool data from my validation resource to my database so that it can be used across the whole organization                                                                                                                                                                                                |
| GL_62         | ROMI-09                                                                                                                                                         | Synchronisierung Prozessparameter über Organisationen hinweg                                                                                                   | Synchronization process parameters across organizations                                        | Als Kunde möchte ich Prozessparameter über mehrere Datenbanken hinweg synchronisieren, damit ich die neuesten genehmigten Parameter verwenden kann                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | As a Customer I want to synchronize process parameters across multiple databases so that I can use the latest parameters approved                                                                                                                                                                                                                                      |
| GL_63         | HORÖ-06                                                                                                                                                         | Wartungs- und Kalibrierdaten                                                                                                                                   | Maintenance and calibration data                                                               | Um eine regelmäßige Wartung und Kalibrierung der Maschine durchzuführen, müssen die Wartungs- und Kalibrierdaten bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | In order to carry out regular maintenance and calibration of the machine, the maintenance and calibration data must be known.                                                                                                                                                                                                                                          |
| GL_64         | HORÖ-07                                                                                                                                                         | Wartungsprotokolle                                                                                                                                             | Maintenance logs                                                                               | Um die Fehlerursache zu ermitteln, müssen die Wartungsprotokolle (Reinigung, Wartung, etc.) bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | In order to determine the cause of the error, the maintenance protocols (cleaning, maintenance, etc.) must be known.                                                                                                                                                                                                                                                   |
| GL_65         | ALKI-03                                                                                                                                                         | Maximalausstattung                                                                                                                                             | Maximal configuration                                                                          | Um die Prüfmaschine für die Prüfung aller möglichen Leitungssatzvarianten auszustatten, muss die Maximalausstattung des Leitungssatzes bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | In order to equip the testing machine for testing all possible harness variants, the maximum configuration of the harness must be known.                                                                                                                                                                                                                               |
| GL_66         | ALKI-04                                                                                                                                                         | Bestückungsvarianten                                                                                                                                           | Assembly variants                                                                              | Für die Auslegung des Prüfequipments müssen alle Bestückungsvarianten bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | For the design of the test equipment, all assembly variants must be known.                                                                                                                                                                                                                                                                                             |
| GL_67         | ALKI-06                                                                                                                                                         | Projektbezeichnung bzw. Fahrzeugidentifikation                                                                                                                 | Project name or vehicle identification                                                         | Für eine eindeutige Zuordung des Projektes muss die Projektbezeichnung bzw. Fahzeugidentifkation bekannt sein.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | For a clear assignment of the project, the project name or vehicle identification must be known.                                                                                                                                                                                                                                                                       |
| GL_68         | ArBe-03                                                                                                                                                         | Tracebility For- and Backwards                                                                                                                                 |                                                                                                | Stand aktuell - Rheels (Spulen) der Kontakte sind mit Tracebilitydaten codiert - wie kann diese Information nach der Vereinzelung abgesichert werden                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_69         | ArBe-05                                                                                                                                                         | Spezifikationsanforderungen Produkt                                                                                                                            |                                                                                                | Anforderungen und Spezifikationen des 1st Tier und OEM durchgängig auf Produktebene in digitaler Form                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_70         | GENE-01                                                                                                                                                         | Auftragsfreigabe                                                                                                                                               |                                                                                                | Als Produktionsressource möchte ich eine Freigabe für den (Wieder-)Start der Produktion eines Auftrags vom Steuerungssystem erhalten.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_71         | GENE-03                                                                                                                                                         | Qualitätsprüfungen anstoßen                                                                                                                                    |                                                                                                | Als Steuerungssystem (MES) möchte ich Qualitätsprüfungen anstoßen, die implementiert durch meine Ressource sind, so dass ich den Produktionsstart freigeben oder verweigern kann und Rückmeldedaten sammeln kann.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_72         | GENE-05                                                                                                                                                         | Schicken des Auftrages an die Maschine                                                                                                                         |                                                                                                | Als Steuerungssystem möchte ich einen Auftrag an meine Produktionsressource mit Produktspezifikation und Menge senden, so dass ich meinen Produktionsplan durchführen kann.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |                                                                                                                                                                                                                                                                                                                                                                        |
| GL_73         | GENE-06  | Schicken von Konfigurationsänderungen an die Maschine  | | Als Steuerungssystem möchte ich meine Produktionsressource konfigurieren (Grundeinstellungen, nicht Rezept, z.B. automatischer Werkzeugwechsel), so dass ich die Durchführung meines Produktionsplanes vorbereiten kann.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |                                                                                                                                                                                                                                                                                                                           |
| GL_74         | GENE-08   | Abrufen von Rückmeldedaten für die Rückverfolgbarkeit  |               | Als Steuerungssystem möchte ich die gemessenen Prozessparameter (Rückmeldedaten) anfragen, so dass ich Daten für die Rückverfolgbarkeit sammeln kann.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |                                                                                                                                                                                                                                                                                                                                    |
| GL_75         | GENE-12     | Abfragen von Material-Setup      |    | Als Steuerungssystem (MES) möchte ich die eingerichteten Materialien (Artikelnummer, Chargennummer) abfragen, so dass ich über die Produktionsfreigabe entscheiden und Daten für die Rückverfogbarkeit sammeln kann. |        |
| GL_76         | GENE-15     | Abfragen von Material-Setup    |       | Als Produktionsressource möchte ich Informationen über das eingerichtete Material (Artikelnummer, Seriennummer, Verarbeitungsspezifikation) sammeln, so dass ich Daten für die Rückverfolgbarkeit sammeln kann und diese an andere VWS weiterleiten kann. |        |
| GL_77         | MaFe-04     | Zugriff auf Verwaltungsschalen     |   | Für die Produktion bzw. Montage des Kabelbaums wird ein standardisierter Zugriff auf die Verwaltungsschale benötigt, um Daten zu lesen und zu schreiben. Hierfür muss eine Kommunikationstechnolgie (z.B. REST über HTTP) zur Verfügung gestellt werden   |      |
| GL_78         | MaFe-05    | Die in der Anlage zur Verfügung gestellten verwaltungsschalen müssen über eine Repository standardisiert zur Verfügung gestellt werden   |     |
| GL_79         | MaFe-06    | Physikalische Daten von Produkten und Ressourcen    |    | Es werden physikalische Daten von Produkten benötigt, insb. Masse und Trägheit    |      |
| GL_80         | MaFe-07    | Kinematikbeschreibung von Produkteu und Ressourcen  |    | Es werden die Kinematik der Ressourcen benötgit, insb. des Greifers   |    |
| GL_81         | CaWe_006   |        | Hardwired safe modes    |  | As a crimp machine manufacturer, I want to have the operation modes “safe shutdown” and “local operation” to be implemented by an electrical signal connection (e.g.: “Emergency shutdown loop”) so that I can implement the safety functions by hardware elements.                                                                                                    |
| GL_82         | CaWe_007                                                                                                                                                        |                                                                                                                                                                | Locking and unlocking machine for manual operation                                             |   | As an OEM, I want to have means to lock and unlock operation of a crimp machine, which is part of a partially automated system, so that I can make sure that it will only be operated in relation to a specific manufacturing job.                                                                                                                                     |
| GL_83         | CaWe_015                                                                                                                                                        |                                                                                                                                                                | Verify die-set and tool                                                                        |   | As a crimp machine manufacturer, I want to have the machine verifying that the currently loaded program can be safely executed with the installed die-set and tool so that I can prevent damage of the machine.                                                                                                                                                        |
| GL_84         | EmDa_11   |     | Data access for OEMs - gather quality information      |   | As an OEM I want to be able to identify each part of a produced harness instance (according to BOM) so that I can visualize the product  |
| GL_85         | RoMi_01   | Hierarchical product data model  |  | As an API user I want to query my product data model so that I can group the details in a hierarchical structure  |
| GL_86         | RoMi_02   | | Harness as root element  |     | As an API user I want to access the Product data model over a Harness root element so that I have always the same entry point     |
| GL_87         | RoMi_03   |       | Harness metadata   |    | As an API user I want to access metadata for a Harness so that I can read the model identifier, Unique harness ID, and other data    |
| GL_88         | MiRo-02   |       | Receive events from resource  | | As a Control System I want to receive events of my production resources so that I can react to changes in my production line     |
| GL_89         | MaFr-01   |       | Lock a resource  |    | As a Control System I want to be able to reserve a resource for production exclusively     |

## <a name="_3.2"></a>AP 3.2 - Erforschung eines Referenzmodells

Im Arbeitspaket 3.2 wurde auf Grundlage der Ergebnisse des AP3.1 ein Referenzmodell erforscht, mit dem es in Zukunft möglich ist, einen automatisierten Austausch eines Digitalen Zwillings eines Leitungssatzes mittels der Verwaltungsschale durchzuführen.

Wertschöpfungskettenübergreifend gilt es die verschiedenen Systemlandschaften der einzelnen vor- und nachgelagerten Wertschöpfungsstufen (Bsp. OEM, Tier-n) miteinander zu verbinden, um eine Datendurchgängigkeit über die VWS zu erreichen. Dies betrifft Systeme wie bspw. PLM, MES sowie Leitungssatzspezifische Entwicklungs- und Produktionssysteme. Dies wird anhand der nachfolgend beschriebenen Use Cases veranschaulicht.

Die wesentlichen Elemente dieses Modells beziehen sich auf die VWS für Produktionsmittel, Produktionsprozesse und der Integration der Daten-/Informationsmodelle aus TP1. Für letzteres wurde in AP3.2 noch ein Konzept namens CAD2BOP definiert, welches CAD-Daten und Parameter erfasst, die einen starken Einfluss auf eine spätere Automatisierung der Produktions- und Montageprozesse in der Wertschöpfungskette für Leitungssätze haben.

### <a name="_3.2.1"></a>Datenfluss-Architektur

Für einen unternehmensübergreifenden Datenaustausch über einen IDS wie bspw. [Catena-X](https://catena-x.net/de/) sind Konzepte für den unternehmensinternen Datenzugriff, -aggregation und -konvertierung notwendig, um alle relevanten Daten bereitstellen zu können. Hierzu wurde eine initiale High-Level Architektur entworfen, um alle Elemente für die Datengenerierung und -haltung in einem Modell zusammenzufassen (siehe dazu die grün hinterlegten Bestandteile in *Abbildung 3-2*).

![image](https://github.com/user-attachments/assets/424d0812-7fe7-4ff4-9d5e-1a4665e6301f)    
*Abbildung 3-2: High-Level Architektur*

Die unterste Ebene beschreibt den Shopfloor mit allen dazugehörigen Produktions- und Testanlagen. Diese Ebene kommuniziert mit Unternehmensanwendungen in einer darüber liegenden Schicht wie bspw. einem Manufacturing Execution System (MES) zur Produktionssteuerung oder einem Enterprise Resource Planning (ERP) System, um Produktionsressourcen sowie Materialverbräuche zu managen. Für eine Kommunikation mit einer Verwaltungsschale ist meist eine ETL-Schicht (ETL: Extract, Transform, Load) [1] notwendig, da die Daten in den Unternehmensanwendungen in den seltensten Fällen bereits passend für eine Integration in die Verwaltungsschale vorliegen. Diese Transformation erfolgt im sog. „AAS Data Hub“. In der vorgeschlagenen Architektur besteht die Annahme, dass die Verwaltungsschalen in einem sog. „Cloud Data Space“ gehalten werden, in dem für jedes Mitglied in der Wertschöpfungskette sowohl die Typ- als auch Instanz-VWS gespeichert sind und über APIs angesprochen werden können. Für den unternehmensübergreifenden Datenaustausch wird angenommen, dass dieser über den in Catena-X entwickelten [Eclipse Dataspace Connector](https://github.com/eclipse-edc/)[^3] (EDC) erfolgen wird.

[^3]: <https://github.com/eclipse-edc/>

### <a name="_3.2.2"></a>Use Cases

Aufbauend auf der High-Level Architektur wurden drei verschiedene Use Cases definiert, um die Datenflüsse im Kontext einer konkreten Anwendung darzustellen. Diese Use Cases werden in den folgenden Unterkapiteln vorgestellt.

#### UC1: Predictive Maintenance

In diesem Use Case werden Sensordaten von der Maschine dem Maschinenhersteller zur Verfügung gestellt für Predictive Maintenance. Die Sensordaten werden durch Produktinformationen angereichert.

Die Architektur für diesen Use Case ist in *Abbildung 3-3* dargestellt, wobei eine Produktionsanlage (hier der Maschinentyp „Crimpwerkzeug“) eine AAS kompatible Interfacetechnologie besitzt und direkt mit einer Verwaltungsschale kommunizieren kann. Der andere Maschinentyp (Prüfgerät) besitzt keine AAS kompatible Interfacetechnologie und kann somit nicht direkt mit einer Verwaltungsschale kommunizieren. Die für den Predictive Maintenance Service notwendigen Daten sind in der Verwaltungsschale „[EHC10-PLK14_5_50mm2_instance1.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/EHC10-PLK14_5_50mm2_instance1.aasx)“ hinterlegt. Die einzelnen Datenpunkte sind auf der rechten Seite in der *Abbildung* gelistet.

![image](https://github.com/user-attachments/assets/fc87a1de-c442-44e4-8e5d-56d427325d1a)    
*Abbildung 3-3: Use Case Predictive Maintenance*

Für den zweiten Fall verläuft der Datenfluss über den zuvor erwähnten AAS Data Hub. Dieser beinhaltet in diesem Szenario ein EAI-System (Enterprise Application Integration) für eine prozessorientierte Integration von Anwendungssystemen in heterogenen IT-Anwendungsarchitekturen. Hierüber ist die Kommunikation zu einem ERP oder MES möglich. Daneben wurde die [Eclipse BaSyx DataBridge](https://github.com/eclipse-basyx/basyx-databridge)[^4] (nachfolgend DataBridge), integriert für eine unkomplizierte Datenintegration. Sie unterstützt verschiedenste Protokolle und erlaubt eine einfache Transformation von Daten. D.h. das Prüfgerät in diesem Szenario kommuniziert über die DataBridge mit der Verwaltungsschale und integriert dort alle Produktionsdaten, die in einem weiteren Schritt als Rückmeldedaten über das EAI ans MES übergeben werden.

[^4]: <https://github.com/eclipse-basyx/basyx-databridge>

#### UC2: Pay-per-Use für Anlagenbetreiber

Eine Ressource soll mittels Pay-Per-Use Modell betrieben werden. Dabei ist es nötig, bestimmte Daten direkt in der Maschine zu halten, damit sie vor Manipulation geschützt sind. Dazu wird die Ressourcen- Verwaltungsschale direkt in die Maschine integriert, damit der Anlagenhersteller sichergehen kann, dass die Nutzdaten der Maschine unverfälscht sind.

In *Abbildung* 3-4 werden wie im Use Case zuvor 2 Szenarien beschrieben:

In Szenario 1 kommunizieren die Anlagen, beispielhaft als ‚Cable cutting‘ und ‚Testing‘ dargestellt, über Unternehmensanwendungen und dem AAS Data Hub mit den einzelnen Verwaltungsschalen. Szenario 2 wird anhand eines Industrieroboters dargestellt. Hier besteht eine direkte Kommunikation zwischen der Produktionsressource und ihrer zugehörigen Verwaltungsschale.

![image](https://github.com/user-attachments/assets/091e0055-eb9f-402d-9b57-d432450c0034)    
*Abbildung 3-4: Pay-per-Use: Maschinenhersteller greift auf Ressource AAS bei Kunde zu*

Die Produktion von Leitungssätzen heutzutage folgt Szenario 1, in dem die Produktionsressourcen über ein MES und dort verwalteten Produktionsaufträgen gesteuert werden. Die Kommunikation erfolgt über standardisierte Protokolle wie bspw. OPC UA oder Message Queuing Telemetry Transport (MQTT) oder proprietäre Protokolle wie bspw. [MIKO](https://www.komaxgroup.com/de-de/products/software-and-networking/miko). Die Rückmeldedaten dieser Produktionsressourcen werden im MES hinterlegt und sind über den AAS Data Hub für die Verwaltungsschalen im Cloud Data Space Tier 1 zugänglich.

Für den Anwendungsfall „Pay-Per-Use“ erscheint eine solche Anbindung jedoch nicht praktikabel, ist es doch erforderlich, dass hierbei zwischen der Ressource und ihrem Hersteller (im Bild ‚Ressource Manufacturer‘) manipulationssicher kommuniziert werden kann. Entsprechende Möglichkeiten zur Durchleitung signierter Daten durch die Unternehmensanwendungen müssten erst noch geschaffen werden.

Für die Pay-Per-Use Ressource wird daher Szenario 2 angewendet (siehe*Abbildung 3-4*): Sie kommuniziert mittels ihrer eingebauten AAS direkt mit dem unternehmensinternen Cloud Data Space. Dort liegt aus Datenhaltungs- und Performancegründen gegebenenfalls noch eine Kopie der Ressourcen- Verwaltungsschale „Ressource AAS (Kopie)“. Sowohl die ressourceninterne Verwaltungsschale „AAS Maschine (intern)“ als auch ihre Kopie umfassen sowohl Daten, die der Hersteller für das Abrechnungsmodell Pay-per-Use benötigt, als auch weitere Daten, die nicht mit dem Hersteller geteilt werden sollen, zum Beispiel Rezepturen und Traceability-Daten.

Die Kommunikation mit dem Hersteller erfolgt von EDC (Tier 1) zu EDC (Resource Manufacturer), worüber die relevanten Daten für das Pay-per-Use vom Tier 1 an diesen weitergegeben werden. Die interne Kommunikation mit den Unternehmensanwendungen erfolgt über den AAS Data Hub direkt mit „Ressource AAS (Kopie)“.

#### UC3: OEE-Berechnung

Die OEE-Berechnung ist von zentralem Interesse, wenn ein Betreiber von Anlagen und Maschinen eine Erhöhung der Effizienz anstrebt. Auch für Anlagen- und Maschinenhersteller sind diese Daten von hohem Wert. Dieser KPI findet oft Verwendung bei FAT’s (Factory Acceptance Test) und kann auch im späteren Verlauf dem Hersteller wertvolle Informationen zur Weiterentwicklung seiner Maschinen liefern.

![image](https://github.com/user-attachments/assets/ac7a9296-473d-4e60-8a9d-d5cf72cab67f)   
*Abbildung 3-5: OEE-Berechnung: MES greift auf Ressource AAS zu*

In diesem Use Case kommt folgende Annahme zum Einsatz. Die “Eclipse BaSyx Data Bridge” ist im Einsatz und ermöglicht somit die Anbindung von Maschinen mit “nur” proprietären Schnittstellen. Des Weiteren wird unterstellt, dass die AAS der Maschine mit der AAS-Kopie der Ressource des Tier 1 synchronisiert ist, bzw. wird (s. 5). Ein MES muss daher nicht mehr zwingend mit der Ressource direkt kommunizieren, sondern kann über verfügbare EAI (Enterprise Application Integration) Zugang zu den benötigten Daten erhalten. Bei der Anreicherung der AAS der Ressource mit OEE-Daten ist darauf zu achten, dass auch die Ermittlung der einzelnen OEE-Bestandteile (Availability, Perfomance, Quality) transparent dargestellt wird. Sowohl in Bezug auf die Datenbasis als auch die Berechnungen.

### <a name="_3.2.3"></a>CAD2BOP

Hinter „Computer-Aided-Design to Bill-of-Process“ (CAD2BOP) steht die Erstellung eines Konzepts zur Definition von CAD-Daten und weiteren Parametern, die einen starken Einfluss auf eine spätere Automatisierung der Produktions- und Montageprozesse in der Wertschöpfungskette für Leitungssätze haben. Im Speziellen werden hier Gehäuse und Kontakte betrachtet, um den Prozess der Steckerbestückung (das sog. „Blockload“) mit Automatisierungsparametern zu unterstützen.

#### Ist-Zustandsbeschreibung

Für die Bestückung von Gehäusen werden teilautomatisierte Maschinen verwendet (z.B. [Komax Omega Serie](https://www.komaxgroup.com/de/products/harness-manufacturing)), die dazu in der Lage sind, nach der Fertigung der Kabel und der Kontaktierung diese entsprechend in ein Gehäuse zu platzieren.

Hierzu werden unbestückte Gehäuse auf einer Palette mit speziell angefertigten Halteteilen platziert (siehe *Abbildung* 16). Für jede Kammer muss der Bediener anschließend die Position, Stecktiefe, Ausrichtung der Verriegelung sowie die Steck- und Rückzugskraft anlernen. Das ist notwendig, um einen sicheren Sitz der Kontaktteile nach der Herstellung zu gewährleisten. Um einen wiederholbaren Prozess zu gewährleisten, muss der Bediener zudem jede weitere Palette nach demselben Muster bestücken.

Ebenso ist das Prüfen solcher Gehäuse mit einem hohen Maß an Handarbeit verbunden. Hier werden oft die Gegenstellen durch manuelle Vermessung der Originale hergestellt, statt sie aus bestehenden Konstruktionen abzuleiten.

![image](https://github.com/user-attachments/assets/cbffa956-a149-46d8-bab5-276798c5ef26)    
*Abbildung 3-6: Palette mit zu bestückenden Gehäusen*

#### Anforderungen

##### Allgemein

-   Die nachfolgenden geometrischen Beschreiben, vor allem für die elektrischen Steckverbindungen (Gehäuse), bezüglich des Nullpunktes und der Achssysteme haben den „Leitfaden zur Erstellung von Elektrik-Bauteilen mit CATIA V5“ des CES-Arbeitskreises (CES = Car Electrical System) als Grundlage.
-   Das Informationsmodell des VEC [2] bildet die Datenbasis.
-   Daten, die nicht aus dem VEC extrahiert werden können, müssen über die VWS bereitgestellt werden.
-   CAD-Daten (z.B. im STEP-format) liefern auch bei vereinfachten Modellen aussagekräftige Informationen (z.B. über Außenmaße).
-   Eine einheitliche Ausrichtung der Konstruktionen und Referenzpunkte muss definiert sein.

##### Gehäuse (siehe *Abbildung 3-7*)

-   Der Mittelpunkt der Kammer 1 in der Ebene der elektrischen Kontaktfläche des Gehäuses ist der Nullpunkt Gehäuses und der Ursprung des Koordinatensystems.
-   Die Z-Achse entspricht bei Stiftgehäusen der Steckrichtung, somit zeigt diese nach außen. Bei Buchsengehäusen zeigt die Z-Achse in das Gehäuse hinein und verläuft gegen die Steckrichtung des Gehäuses. Siehe dazu auch Abschnitt 1.2.3.3.1.
-   Die X-Achse zeigt auf weitere Reihen (sofern vorhanden). Diese wird auch als Spurmaß bezeichnet.
-   Die Y-Achse zeigt auf die nächste Kammer derselben Reihe (sofern vorhanden). Diese wird auch als Rastermaß bezeichnet.
-   Orientierung/Drehwinkel der Primärverriegelung im Winkelmaß gegenüber der Y-Achse im Uhrzeigersinn um die Z-Achse (siehe Beschreibung von VEC-Gehäusen).
-   Alle weiteren Koordinatensysteme referenzieren auf das Ursprungskoordinatensystem.

![image](https://github.com/user-attachments/assets/a3dd2139-c99a-49d8-bfd0-814b74d1c24e)    
*Abbildung 3-7: Gehäuse*

##### Kontakt (siehe *Abbildung 3-8, 4 und 5*)

-   Der Nullpunkt des Terminals liegt im Kreuzungspunkt der Mittelachse (Z-Achse) und der Endlage des Terminals in der Kammer (Endlage des Terminals in der Kammer, siehe *Abbildung 3-8*).
-   Die Z-Achse des Terminals orientiert sich an der Richtung der Z-Achse des Gehäuses. Beim Buchsenterminal zeigt die Z-Achse in Richtung des Crimps und beim Stiftterminal entgegen der Richtung des Crimps.
-   Die Y-Achse zeigt in Richtung der Primärverriegelung (0°).
-   Die X-Achse ergibt sich aus der Rechte-Hand-Regel
-   Um eine Orientierung im Raum zu gewährleisten, ist ein weiterer Parameter notwendig (Parameter Name: CrimpOrientation). Dazu wird der Drehwinkel der Crimpöffnung (bei F-Crimp) im Verhältnis zur Y-Achse angegeben. Ausschließlich positive Werte und analog zur Bestimmung des Drehwinkels wie beim Gehäuse (im Uhrzeigersinn). Beispiele dazu zeigen die *Abbildung 3-8*.

![image](https://github.com/user-attachments/assets/b6749920-3c60-4297-a08c-7829e199d534)   
*Abbildung 3-8: Kontaktbeispiel 1 (Y-Achse zeigt in Richtung Primärverriegelung)*

Beim Ein- /Zusammenführen des Terminals in die Gehäusekammer ist zu beachten, dass die Nullpunkte bzw. die Achsen der Nullpunkte von Gehäuse und Terminal in der Endposition nicht übereinander liegen. Die Beschreibung der Nullpunkte für Terminal und Gehäuse wurde bereits zuvor gemacht und in der *Abbildung 3-9* nochmal visuell verdeutlicht. Die Distanz zwischen den beiden Nullpunkten kann mit einem Offsetwert angegeben werden und daraus die Endposition des Terminals in der Kammer bestimmt werden.

![image](https://github.com/user-attachments/assets/757be961-ae49-483d-9e65-521dac60d9bb)    
*Abbildung 3-9: Definition des Nullpunkts für das Terminal und gegenüber dem Gehäuse*

Zu beachten ist beim Stiftkontakt, dass sich der Nullpunkt nicht an der Spitze des Terminals befindet, sondern analog zum Buchsengehäuse/-terminal, wie in *Abbildung 3-10* gezeigt, dort wo sich das Kammernende befindet.

Zudem ist beim Stiftkontakt eine zusätzliche Längenangabe des Stiftes (vom Nullpunkt bis zur Kontaktspitze) notwendig. Dies ist erforderlich um eine „Hindernisumfahrung“ zu ermöglichen, damit das Terminal nicht kollidiert wenn es zu der erforderlichen Kammer geführt und anschließend gesteckt wird.

![image](https://github.com/user-attachments/assets/ad52562d-b29c-4da1-9962-9f6b37d036f0)   
*Abbildung 3-10: Stiftkontakt*

**Besonderheit bei Terminals mit mehreren Primärverrastungen**

Bei Terminals mit mehreren Primärverrastungen (Beispiel siehe *Abbildung 3-11*) obliegt es dem Konstrukteur/Hersteller des Terminals zu welcher Primärverrastung die Y-Achse ausgerichtet ist, dies gilt nur wenn die Terminals in mehreren Positionen steckkompatibel in der Kammer sind.

Sollte bei mehreren Primärverrastungen keine Steckkompatibilität in mehreren Positionen vorhanden sein, ist die Ausrichtung der Achsensysteme, von Terminal und Gehäuse, analog wie bei Terminals mit nur einer Primärverrastung auszuführen.

![image](https://github.com/user-attachments/assets/f546a877-9cbb-4f7f-a4a1-40f3e45a88b4)   
*Abbildung 3-11: Kontaktbeispiele mit zwei Verriegelungen*v

#### VEC als führender Standard

![image](https://github.com/user-attachments/assets/12b5de2e-b384-413a-95f9-852b86079651)    
*Abbildung 3-12: : VEC-Definition für Steckrichtung und Achsensystem (Source Prostep)*

Dieses Konzept basiert auf diesem Auszug aus den Spezifikationen des VEC (Vehicle Electrical Container, *Abbildung 3-12*: 

Der folgende Abschnitt enthält alle relevanten Definitionen, die für die entsprechenden Modellelemente im VEC erforderlich sind.

Die geometrischen Eigenschaften von Steckergehäusen stehen in engem Zusammenhang mit der LocalGeometrySpecification, die im Abschnitt "Koordinatensysteme der Komponenten" beschrieben wird. Alle Koordinaten und Werte sind im gleichen Koordinatensystem definiert. Alle geometrischen Eigenschaften, die nicht ausschließlich für Verbindergehäuse gelten, werden dort definiert (z.B. BoundingBox, PlacementPoints / SegmentConnectionPoints).

Das 3D-Modell und das Koordinatensystem eines Steckergehäuses sind wie folgt definiert:

-   Der Ursprung des Steckers liegt in der Ebene der elektrischen Kontaktfläche in der Mitte der Öffnung der/des Kammer/Stifts mit der kleinsten alphanumerischen Kennung (z. B. Hohlraum/Stift 1 oder A1).
-   Die Y-Achse liegt in der Ebene der elektrischen Kontaktfläche und zeigt in Richtung der Mitte der/des Kammer/Stifts mit der nächsthöheren alphanumerischen Kennung (z. B. Kammer/Stift 2 oder A2). Bei einpoligen Steckergehäusen in Richtung der Kodierung, sofern vorhanden.
-   Die Z-Achse steht senkrecht zur Ebene der elektrischen Kontaktfläche und zeigt bei Buchsengehäusen in das Gehäuse und bei Stiftgehäusen nach außen (der Stecker in der *Abbildung* oben ist eine Buchse). Bei weiblichen Gehäusen zeigt die Z-Achse also in die entgegengesetzte Richtung der Steckrichtung. Bei männlichen Gehäusen zeigt sie in die gleiche Richtung wie die Steckrichtung.
-   Die X-Achse ist das Vektorprodukt von Y und Z.

    Für Kammern gibt es zwei relevante Positionen im Stecker:

-   Die Position in der elektrischen Kontaktfläche (blau hervorgehoben), und
-   Die Position in der Eintrittsfläche während des Einführens (gelb hervorgehoben).

Die Lage der Kammer innerhalb des Verbinders wird als der Winkel zwischen der Y-Achse und der primären Verriegelung in der Kammer definiert.

<https://ecad-wiki.prostep.org/specifications/vec/v202/component-characteristics/geometric-properties-of-connector-housings-definitions/>

In den folgenden Unterkapiteln werden die erforderlichen Attribute für die Automatisierung genannt und beschrieben. Es wird dabei zwischen Attributen des Gehäuses und des Kontakts unterschieden.

##### Attribute des Gehäuses

In diesem Abschnitt wird nur das Bezugssystem des Steckverbinders beschrieben. Für die Automatisierung an einer Maschine muss das Bezugssystem entsprechend den entstehenden Anforderungen erweitert werden. Diese Möglichkeit bietet z.B. die OPC UA Companion Specification "Relative Spatial Location".

###### HousingCoordinates

-   Der Ursprungsnullpunkt muss auf der Mitte der Kammeröffnung mit der kleinsten alphanumerischen Zahl (z. B. 1, A1 usw.) innerhalb der elektrischen Kontaktfläche liegen. Er liegt immer in der Ebene der X- und Y-Achsen
-   Die Ausrichtung der Achsen entspricht der VEC-Spezifikation

![Ein Bild, das Design, Text, Diagramm, Reihe enthält. Automatisch generierte Beschreibung](media/be2d0e5602191f7033417b2e858088c7.png)
![Ein Bild, das Diagramm, Reihe, Design enthält. Automatisch generierte Beschreibung](media/0f4a1128b59ff2a6c6969e317d305378.png)

###### CavityNumber

-   Jede Kammer eines Gehäuses hat seine eigene eindeutige Nummer (z. B. "A5") zur Identifizierung

###### CavityId

-   Definiert den Typ der Kammer (z. B. NanoMQS)

###### CavityRotation

-   Winkel zwischen Y-Achse und Primärverriegelung (um die Z-Achse im Uhrzeigersinn)
-   Der Winkel ist immer positiv und beginnt bei 0° auf der Y-Achse und dreht sich im Uhrzeigersinn.

###### CavityCoordinate

-   Die Koordinaten des Mittelpunkts der Kammeröffnung innerhalb der elektrischen Kontaktfläche in Bezug auf den Ursprungsnullpunkt (CoordinatesHousing). Sie liegt immer in der Ebene der X- und Y-Achsen

###### OffsetInsertDirectionXCavityCenter

-   Verschiebung des Einführpunktes auf der X-Achse (notwendig, wenn Nullpunkt der Kammer und des Konntakts nicht übereinstimmen)

###### OffsetInsertDirectionYCavityCenter

-   Verschiebung des Einführpunktes auf der Y-Achse (notwendig, wenn Nullpunkt der Kammer und des Konntakts nicht übereinstimmen)

###### InsertionDistance

-   Einstecktiefe, die der Kontakt erreichen muss (gemessen von der Kammeröffnung innerhalb der Eintrittsfläche). Die Bewegung erfolgt ausschließlich entlang der Z-Achse (Richtung variiert je nach männlich oder weiblich)

###### InsertionTrajectory

-   Einfügepfad (Richtung, Drehung, Geschwindigkeit) ist ein optionales Attribut

##### Attribute des Kontakts

Die Konstruktion des Kontakts ist das Gegenstück zur VEC-Spezifikation des Gehäuses. Das bedeutet, dass die Steckrichtung des Kontakts ebenfalls über die Z-Achse dargestellt werden muss. Der Ursprungsnullpunkt des Koordinatensystems des Kontakts muss in der Mittellinie des Kontakts an der Endposition der Kammer liegen.

**TerminalOrientation**: Der Winkel der Primärverriegelung um die Z-Achse. Immer positiv, beginnend mit 0° auf der Y-Achse und im Uhrzeigersinn

**TerminalCoordinates**: Der Ursprungsnullpunkt des Kontaktes muss auf der Endlage in der Kammer an der Mittelline liegen. Die Richtung der Z-Achse zeigt in Richtung Crimp der Z-Achse des Gehäuses und ist die Bewegungsachse der Steckrichtung

**MaximumInsertionForce**: Die maximale Kraft, die beim Einführen bis zur primären Verriegelung des Kontakts aufgebracht werden darf.

**MaximumTerminalPullOutForce**: Die maximale Auszugskraft, die aufgebracht werden darf, bis die Primärverriegelung zerstört ist.

**CrimpOrientation**: Bezugspunkt der Öffnung des Crimp in Relation zur Primärverrastung (Y-Achse) des Terminals, wird in Grad (ausschließlich positive Werte) angegeben, Drehrichtung im Uhrzeigersinn.

**MaximumTerminalPullOutLength**: Maximale Auszugslänge.

**Overlength**: Überlänge (Kabelspitze bis Terminal Ende).

#### Umsetzungskonzept

Viele benötigte Parameter liegen bereits im VEC vor [3] und müssen Anwendung in der Konstruktion der entsprechenden Bauteile finden. Vereinfachte CAD-Modelle (z.B. im STEP-format) müssen eine klare Auskunft über die Außengeometrie von Gehäusen sowie notwendigen Informationen über die einzelnen Kammern liefern. Diese Daten sind essenziell für eine automatisierte Bestückung, da sie ein in sich geschlossenes Bezugssystem haben.

Dieses Bezugssystem muss nun in einer Maschine in Relation gesetzt werden. Hierfür ist folgendes Szenario entstanden:

Die Gehäuse werden mittels Universalhalterungen frei auf einer Palette (früher Lochplatte) fixiert. Ein Vermessungssystem ermittelt die relative Positionierung zum Nullpunkt der Palette. Die Palette selbst hat zum Zeitpunkt der Bestückung eine definierte Position relativ zum Nullpunkt der Maschine (z.B. durch Nullstellung des Greifarms). Aus der relativen Positionierung der unterschiedlichen Komponenten und der Beschreibung des Gehäuses lässt sich somit vollautomatisch die Kammerposition ermitteln und der Steckvorgang durchführen. Für die Ausführung der relativen Positionsermittlungen kommt das bereits bestehende OPC UA-Informationsmodell OPC 10000-210 (Industrial Automation - Relative Spatial Location) [4] zum Einsatz. Fehlende Informationen, wie Einstecktiefe und Rückzugskraft, müssen anderweitig erfasst werden (z.B. durch den Maschinenbediener oder die Arbeitsvorbereitung).

#### Fazit

Unter Verwendung des VEC-Datenmodells und OPC UA-Informationsmodells OPC 10000-210 [4] kann ein hoher Grad der Automatisierung im Bereich der Gehäusebestückung erreicht werden. Voraussetzung hierfür ist, dass die CAD-Modelle sich an den Vorgaben des VEC orientieren und über alle Hersteller einheitlich darstellen, oder die Verwaltungsschale eine Möglichkeit zur Querreferenzierung der übermittelten Daten bietet (z.B. Steckrichtung Kontakt = -X).

## <a name="_3.3"></a>AP 3.3 - Erforschung von Teilmodellen für Rückmeldedaten

Das Arbeitspaket 3.3 „Erforschung von Teilmodellen für Rückmeldedaten“ beschäftigt sich mit den Teilmodellen für Rückmeldedaten zum Abgleich der im Fertigungsprozess gemessenen Ist-Werte.

### <a name="_3.3.1"></a>Leitungssatzproduktion

Bei der Herstellung eines Leitungssatzes werden eine Reihe von zugelieferten Rohmaterialien, Bauteilen und Halbfertigprodukten verarbeitet, die in komplexen Produktionsprozessen zum Endprodukt eines Leitungssatz in der gewünschten Variante verarbeitet werden.

![image](https://github.com/user-attachments/assets/28f73c6f-c122-48d3-adcf-aaca14af9d42)    
*Abbildung 3-15: Produktionsprozesse beim Konfektionär*

Bevor die eigentliche Kabelbaumproduktion beginnt, treffen alle notwendigen (Roh-)Materialien in der Eingangslogistik oder im Lagerbereich ein, wo diese gescannt werden. Auch findet eine Qualitätsprüfung der angelieferten Materialien statt.

Die Leitungssatzproduktion beginnt mit dem **Schneidprozess und der Leitungsverarbeitung (P1).** Diese Prozesse werden im sog. Schneidraum durchgeführt und weisen einen sehr hohen Automatisierungsgrad auf. Der Schneidprozess wird derzeit von Leitungsverarbeitungsmaschinen durchgeführt, die von einem MES-System gesteuert werden. In der Regel übernehmen die Maschinen in diesem Schritt die Prozesse des Ablängens, des Abisolierens, des Aufbringens von Dichtungen und Kontaktteilen und ggf. der Beschriftung durch Etikettierung, Farbcodierung oder maschinenlesbare Markierungen.

Der **Vormontageprozess (P2)** ist teilautomatisiert. In diesem Schritt finden verschiedene Prozesse statt, wie z. B. manuelles Konsolidieren, Ultraschallschweißen (USW), Abdichtung und viele andere, siehe *Abbildung 3-15*.

Der **Endmontageprozess (P3)** wird überwiegend in Handarbeit durchgeführt, wobei die Teile und Module aus P2 als Input für die Leitungssatzmontage dienen, in der diese Inputs montiert, gewickelt, abgedeckt und das Layout fertiggestellt werden.

In der Stufe **"Spezielle Verfahren und Prüfungen" (P4)** ist es möglich, dass spezielle Verfahren wie z.B. das Schäumen durchgeführt werden. Am Ende dieser Phase wird der Testprozess durchgeführt, um die Qualität des Leitungssatzes zu überprüfen, wobei die Qualität des gesamten Leitungssatzes und all seiner Komponenten überprüft wird, einschließlich des Vorhandenseins von Komponenten, elektrischen Anschlüssen, Widerständen, Kondensatoren, Dioden, Drahtfarben, Pinpositionen, Glasfaserdrähten, Airbags, Thermistoren und mehr.

Schließlich wird der Produktionsprozess abgeschlossen, so dass die Kommissionierung und die Verpackung erfolgen können, bevor der Leitungssatz das Werk verlässt.

Jeder dieser Bereiche und die Produktionsschritte benötigen und generieren Informationen über das Produkt (Bauteile, Baugruppen, Kabelbäume usw.), die Produktionsprozesse (Schneiden, Crimpen, Blockladen, Prüfen usw.) und die Produktionsressourcen (Maschinen, Werkzeuge, Bediener usw.). Für eine generalisierte Prozessbeschreibung müssen die Informationselemente in einer standardisierten Beschreibung zugänglich gemacht werden. Die in *Abbildung 3-16* dargestellte Vorgehensweise soll die Aggregation der einzelnen Attribute für die Ausführung des Prozesses aus verschiedenen Quellen verdeutlichen. Der Fokus liegt auf der Abhängigkeit der verschiedenen Bereiche.

![image](https://github.com/user-attachments/assets/54e1b5fa-bf90-4f0e-86fb-7126e69f0913)   
*Abbildung 3-16: PPR-Modell*

### <a name="_3.3.2"></a>Produktionsprozesse

Entsprechend der Vorhabensbeschreibung zum AP 3.3 wurden die Produktionsprozesse der Leitungssatzfertigung identifiziert und dokumentiert. Nachfolgend soll die Entwicklung dieser Ausarbeitung und der dazugehörigen Ergebnisse dargestellt werden, bis hin zur finalen Version dieser Dokumentation. Im letzten Abschnitt dieses Kapitels wird noch darauf eingegangen, wie die Ausarbeitungen dazu als Basis weiterer Standardisierungsvorhaben genutzt werden konnten.

#### Definitionsphase der Einzelprozesse in der Produktion eines Leitungssatzes

Initial wurde eine erste Auswahl an Produktionsprozessen erarbeitet, inklusive der dazugehörigen Input- und Output-Parameter. Ziel war es die relevanten Informationen zur Leitungssatzfertigung zusammen zu fassen. Ursprünglich umfasste der fertige Erstentwurf der Liste 25 Prozesse, 76 Input-Parameter und 73 Output-Parameter (*Abbildung* 3-17). Diese Daten sollen hier nur, als Randnotiz erwähnt werden, um später im Dokument die Entwicklung dieser Liste nachvollziehen zu können. Die abgebildete Excelliste ist in der Datei „[Initial_Process_List.xlsx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/Initial_Process_List.xlsx)“[^5] zu finden

[^5]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/Initial_Process_List.xlsx>

![image](https://github.com/user-attachments/assets/2c7ae1c9-4bba-4b3e-a823-78d67133311e)    
*Abbildung 3-17: Initiale Prozessliste*

Diese Liste bildete die Grundlage für alle nachfolgenden Aktivitäten.

##### Darstellung als UML-Diagramm

Aufbauend auf der initialen Prozessliste wurde wegen der beschränkten Übersichtlichkeit des Formates diese Liste in ein UML-Klassendiagramm übertragen (*Abbildung* 118). In mehreren Arbeitsterminen konnten weitere Prozesse mit den notwendigen Parametern angereichert werden, d.h. sowohl Soll- als auch Ist-Werte und dabei auch schon, wo es möglich war, ersten Datentypen zu den Parametern definieren.

![image](https://github.com/user-attachments/assets/fde81450-2167-4c4e-b25d-ea32609125e1)   
*Abbildung 3-18: UML-Klassendiagramm für Produktionsprozesse*

Bei der Erstellung und weiteren Ausarbeitung des UML-Diagramms wurden initial zwei generische Klassen definiert (*Abbildung* 3-19) und in den sogenannten allgemeingültigen Bereich „Common“ überführt. Der Hintergrund dieser Vorgehensweise war, dass diese Datenmodelle für jeden Prozess relevant sind und möglichst Redundanzen bezüglich der Parameter in den Prozessdefinitionen vermieden werden sollte. Durch dieses Vorgehen konnten die jeweiligen Prozessdefinitionen auf die wesentlichen spezifischen Parameter beschränkt gehalten werden.

Die Hauptklasse wurde „Manufacturing Process“ genannt und soll alle übergreifenden Parameter enthalten, die zur Durchführung und Dokumentation des Prozesses erforderlich sind. Dazu gehören beispielsweise Start- und Endzeit der Prozessausführung, das Ergebnis des Prozesses usw. Des Weiteren wird zwischen dem geplanten Materialeinsatz (*Consumption*) und ungeplantem Mehrverbrauch (*AdditionalConsumption*) unterschieden.

Die zweite Klasse „Material Consumption“ enthält die notwendigen Informationen hinsichtlich des Materialeinsatzes, die für die Ausführung des zugehörigen Prozesses zur Erzeugung des Produktes notwendig sind, beispielsweise die Parameter Material_Id, Amount, Unit usw.

![image](https://github.com/user-attachments/assets/ad62d3a6-2f08-4eb5-a92d-8ab6dc474c0b)   
*Abbildung 3-19: Allgemeingültige Klassen*

Im weiteren Verlauf wurden das Thema „Testing“, das bis dato eher rudimentär mitgeführt wurde, im UML-Diagramm spezifischer ausgearbeitet und eingetragen. Dabei wurden verschiedene Testprozesse, die beispielsweise bei der End-of-Line-Prüfung eines Leitungssatzes anfallen können, mit den entsprechenden Parametern erarbeitet.

Das Layout und die Benamungen der Prozesse inklusive der dazugehörigen Parameter mit Datentypen wurden im Laufe der Arbeitstermine immer weiter verfeinert, bis das UML-Diagramm in seiner finalen Version abgeschlossen wurde. Die finale Version des UML-Diagramms ist im Anhang hinterlegt.

Im nachfolgenden Unterkapitel werden noch die Gründe der Verwendung des ECLASS-Standards für das weitere Vorgehen bei der Erstellung der Prozessübersicht erläutert.

##### Semantische Interoperabilität

Um eine interoperabel agierende Wertkette zu ermöglichen, müssen die einzelnen Informationselemente mittels eindeutiger semantischer Beschreibungen für den Mensch als auch für die Maschine eindeutig interpretierbar gemacht werden.

Zu diesem Zweck existiert der [ECLASS-Standard](https://eclass.eu/) [5] zur Klassifizierung und Beschreibung von Produkten und Dienstleistungen (Datenwörterbücher basieren auf der ISO 13584-42 und IEC 61360-2). Die dort eingepflegten Informationen erhalten eine global eindeutige ID (eine sog. IRDI) und sind somit eindeutig für alle Teilnehmer, die ebenfalls den ECLASS-Standard nutzen, interpretierbar. Das Datenmodell in *Abbildung* 120 gibt einen Überblick, welche Informationen für die Beschreibung der einzelnen Informationselemente notwendig sind. Für eine detaillierte Erläuterung des Datenmodells wird auf die [technische Spezifikation von ECLASS](https://eclass.eu/fileadmin/Redaktion/pdf-Dateien/Wiki/ECLASS_Technical-Specification_11_Conceptual-Data-Model_v_1.0.pdf) [6] verwiesen. In unserem Anwendungsfall wurde vorwiegend auf die Struktur-Elemente **Property**, **Value** und **Unit** zurückgegriffen.

**Property***: Ein Property (Eigenschaft) beschreibt eine bestimmte Eigenschaft und weist dieser Eigenschaft durch eine Beziehung einen definierten Value zu (Bspw. Eigenschaft: Leitungsfarbe, Value: Rot).*

**Value***: Der Value ist eine Aufzählung innerhalb einer PROPERTY, die die Menge der möglichen Werte für die Eigenschaft einschränken.*

**Unit***: Die Unit setzt eine Maßeinheit in Beziehung zur Basisdimension des zugrunde liegenden Einheitensystems.*

![image](https://github.com/user-attachments/assets/fd207c97-f129-4b5d-bb23-602a6bcc357d)   
*Abbildung 3-20: ECLASS Datenmodell und Detaillierung des Properties (Quelle:* [*ECLASS*](https://eclass.eu/fileadmin/Redaktion/pdf-Dateien/Wiki/ECLASS_Technical-Specification_11_Conceptual-Data-Model_v_1.0.pdf) [6]*)*

Die hierarchische Struktur, die in ECLASS verwendet wird, kann ohne großen Aufwand auf das UML-Diagramm gemappt werden. Der Fokus zu diesem Zeitpunkt lag auf den Prozessen *Common, Cut* und *Crimp*. Für diese Prozesse wurden ECLASS Klassen angelegt. Während der Übertragung mussten den einzelnen Informationselementen noch weitere Details hinzugefügt werden, um eine semantische Beschreibung zu ermöglichen:

-   Definition
-   Data-Type
-   Preferred-Name
-   Property-Data Type

Nach der Anreicherung wurde für jedes Informationselement eine International Registration Data Identifier (IRDI) erzeugt, die global von dem System lediglich einmal vergeben wird. Der Aufbau eines solchen Identifiers kann in den Spezifikationen von ISO/IEC 11179-6, ISO 29002 and ISO 6532 näher betrachtet werden.

#### Struktur der finalen Prozessliste

Die [Prozessliste](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/Prozessliste.xlsx)[^6] bildet für das weitere die Grundlage. Wie im letzten Unterkapitel beschrieben, musste eine Anreicherung an Informationen gemacht werden, um die Daten für eine Interoperabilität zu präparieren. Aufgrund der begrenzten Möglichkeiten dies auf eine übersichtliche Weise im UML-Diagramm darzustellen, wurde wieder auf eine Listenform übergegangen. Diese wurde in ihrer Form zur ursprünglichen Liste optimiert und erweitert, um die zusätzlichen Angaben darin in strukturierter Weise abbilden zu können.

[^6]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/Prozessliste.xlsx>

##### Ableitung der Prozessliste aus UML-Diagramm

Die im ULM-Diagramm begonnene Kategorisierung von ähnlichen Prozessen mit dem Herauslösen von identischen Parametern in die übergeordnete Kategorie wurde in der neuen Vorlage der Prozessliste konsequent weitergeführt und noch verfeinert. Ebenso wurde die Parameter in einzelne Zeilen geschrieben, damit die Informationsanreicherung in den dahinterliegenden Spalten vorgenommen werden konnte.

Die Entwicklung der Darstellung und Aufbereitung der Daten zu den Prozessen, soll in der nachfolgenden *Abbildung 3-21* am Beispiel des Prozesses „Cut“ gezeigt werden.

![image](https://github.com/user-attachments/assets/f982b575-d257-484e-b818-f87a6b9a395e)    
*Abbildung 3-21: Entwicklung der Darstellung zu den Prozessen*

Auf diese Weise wurden alle im UML-Diagramm enthaltenen Prozesse inklusive der Parameter in einem ersten Schritt in die neue Form der Prozessliste übertragen. Mit der Übernahme aus dem UML-Diagramm wurden auch die einzelnen Parameter und deren Zuordnung nochmals diskutiert und ggf. korrigiert. Zudem wurden in diesem Zuge auch fehlende Datentypen und Properties noch ergänzt.

##### Ergänzung der Prozessliste

Nach der Übertragung der Prozesse und der dazugehörigen Daten wurden für die einzelnen Prozesse entsprechende Prozessexperten eingeladen. Mit denen wurden die bisher erarbeiteten Ergebnisse diskutiert und bei Bedarf wurden Änderungen und Ergänzungen vorgenommen.

Um den Reifegrad der Prozessliste weiter zu erhöhen, wurden mit den Experten auch weitere Properties zu den Parametern befüllt. Speziell ging es um die Zuordnung, ob es sich um Input- oder Output-Daten handelt. Eine weitere wichtige Eigenschaft war die Bestimmung, ob es sich bei dem entsprechenden Parameter um einen optionalen oder mandatorischen handelt, sowohl auf der Input-Seite für die Prozessausführung als auch beim Output für die Rückmeldewerte. Abschließend wurden auch nochmal der Datentyp und die entsprechende Einheit abgestimmt (*Abbildung* 122).

![image](https://github.com/user-attachments/assets/caaa4be9-b4b0-4e60-998d-e5a3e112595e)   
*Abbildung 3-22: Erweiterte Properties zu den Prozessparametern*

Nach der Definition aller Prozesse und der zugehörigen Parameter wurde bei der Benamung auf eine einheitliche Nomenklatur bei ähnlich zusammenhängenden Bedeutungen geachtet. Um auch die semantische Standardisierung voranzutreiben, wurden die Einheiten der Parameter mit ECLASS abgeglichen und mit verfügbaren IRDIs entsprechend verknüpft (*Abbildung 3-23*).

![image](https://github.com/user-attachments/assets/ebfdd98a-795e-4870-91b8-50edc33de670)   
*Abbildung 3-23: Einheiten mit den dazugehörigen ECLASS IRDIs*

Nachdem die Definitionen rundum die Prozesse und Parameter abgeschlossen waren, wurde der Common-Bereich nochmals überarbeitet und die in der *Abbildung 3-24* dargestellten Kategorien inklusive der dazugehörigen Parameter definiert.

![image](https://github.com/user-attachments/assets/dfb7c653-b8f6-4673-92d5-3e129ab5a89b)   
*Abbildung 3-24: Common-Bereich der finalen Prozessliste*

Der Common- Bereich unterteilt sich in die Kategorien, denen das Präfix „Process“ vorangestellt ist, d.h. Informationen zu einem Prozess. Demgegenüber beziehen sich die Kategorien „**ProductionOrder**“, „**Batch**“ und „**Lot**“ auf ein Produkt, was ein End- oder Halbfabrikat sein kann. Diese Kategorien können einen aber auch mehrere Prozesse beinhalten.

Die Begriffe werden oft unterschiedlich verwendet[^7], in unserem Kontext jedoch wird unter einem **Lot** (dt. Los) eine kleinere, oft gleichartige Produktionsmenge verstanden, die unter gleichen Bedingungen gefertigt wurde. Ein **Batch** hingegen beschreibt eine größere, organisatorisch definierte Menge, die oft mehrere Lots umfassen kann. Das Lot ist immer identifizierbar, hingegen das Batch eine logische Einheit.

[^7]: 

    https://de.wikipedia.org/wiki/Losfertigung

Um den Arbeitsaufwand rundum die Prozessliste zu verdeutlichen, ist in der nachfolgenden Tabelle die Entwicklung der Umfänge von der initialen zur finalen Liste dargestellt. Bei der finalen Prozessliste sind die Testing- und Common-Prozesse mitberücksichtigt.

Tabelle 11Vergleich zwischen initialer und finaler Prozessliste

|                  | **Initiale Prozessliste** | **Finale Prozessliste** |
|------------------|---------------------------|-------------------------|
| **Input-Daten**  | 76                        | 405                     |
| **Output-Daten** | 73                        | 138                     |
| **Insgesamt**    | 149                       | 552                     |

#### Basis für OPC UA Companion Specification

Dieser Abschnitt beschreibt die Überführung von Teilbereichen der Prozessliste in die OPC UA Companion Specification “Wire Harness Manufacturing” [7].

In TP 1 wurde im Laufe der Zeit erkannt, dass eine Verallgemeinerung und Standardisierung der Maschinenschnittstellen von entscheidender Bedeutung sind. Daher wurde mit Unterstützung des VDMA (Verband Deutscher Maschinen- und Anlagenbauer) die OPC UA Arbeitsgruppe ‘Wire Harness Manufacturing’ ins Leben gerufen. Durch diese Initiative können Maschinen und Anlagen standardisiert ihren “Datenbeitrag” zur VWS4LS leisten.

Im ersten Schritt wurden die relevanten Prozesse für die Version 1.0 diskutiert und festgelegt. Dies war notwendig, da der bestehende Detailgrad der Prozessliste zu umfangreich für eine erste Version war. In der Version 1.0 der Companion Specification werden daher folgende Prozesse zu finden sein:

-   Cut
-   Strip
-   Slit
-   Crimp
-   Seal
-   Sleeve

Nach der Festlegung der Prozesse war außerdem eine erneute “Synchronisation” zwischen der OPC UA-Arbeitsgruppe und TP3 erforderlich, da aus Sicht der Maschinen der ein oder andere Prozess mit zusätzlichen Daten angereichert werden musste. Ebenso erfolgte eine Aufgliederung der Prozesse auf Maschinenseite in die Bereiche “Spezifikation”, “Validierung” und “Überwachung”.

Wie auch in der Prozessliste dargestellt, sind für den Input und Output auf der OPC UA-Seite unterschiedlichste Datentypen erforderlich. Diese werden als Strukturen repräsentiert, die sowohl in Methodenaufrufen (wie „*Store*“, „*Start*“ usw.) als auch für “*ResultTransfer*” verwendet werden können. Der Aufbau dieser Datenstrukturen orientiert sich selbstverständlich an der Prozessliste und spiegelt diese wider um eine effektive Integration zwischen OPC UA “Wire Harness Manufacturing” [7] und VWS4LS zu gewährleisten.

### <a name="_3.3.3"></a>Prozess VWS

In diesem Kapitel wird die Umsetzung der Prozess VWS (siehe Datei „[AAS_Prozesse_2024_01_26_V3 - Demonstrator.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/AAS_Prozesse_2024_01_26_V3%20-%20Demonstrator.aasx)“[^8]) im Kontext des PPR-Modells beschrieben. Die im vorherigen Kapitel vorgestellte Prozessliste bildete dabei die zentrale Grundlage zur Strukturierung der Prozess VWS mit ihren einzelnen Bestandteilen.

[^8]: [https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/AAS_Prozesse_2024_01_26_V3 - Demonstrator.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/AAS_Prozesse_2024_01_26_V3%20-%20Demonstrator.aasx)[https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/AAS_Prozesse_2024_01_26_V3 - Demonstrator.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/AAS_Prozesse_2024_01_26_V3%20-%20Demonstrator.aasx)

Im VWS-Kontext wird zwischen Typ und Instanz unterschieden. Für den Leitungssatz lässt sich diese Unterscheidung auf die Phasen bzw. Prozesse (Entwicklung, Produktion) abbilden. Auf Typenebene wird im Engineering zunächst ein sog. „150%-Leitungssatz“ definiert, der alle Funktionsmodule des Leitungssatzes beschreibt, die in einem Fahrzeugprojekt aus rein funktionaler Sicht existieren können. Das heisst, der 150%-Leitungssatz beinhaltet alle möglichen Varianten, inkl. sich gegenseitig ausschließende Funktionsmodule und Konstellationen, die somit nie produziert werden. Aus diesem Grund wird für einen konkret zu produzierenden Leitungssatz von einem sog. „100%-Leitungssatz“ gesprochen. Dieser wird aus dem 150%-Leitungssatz abgeleitet und beinhaltet die notwendigen Funktionsmodule für ein konkretes Fahrzeug.

Grundsätzlich wurde bei der Strukturierung der VWS für die Produktion eines Leitungssatzes in Typ und Instanz unterschieden. Die VWS „*ProductType*“ beschreibt dabei das zu fertigende Produkt bzw. Halbfabrikat auf Typebene. Die Instanzenebene beginnt, sobald ein Produktionsauftrag (VWS *ProductionOrder*) für das Produkt bzw. Halbfabrikat existiert. Dieses Produkt bzw. Halbfabrikat kann in der Produktion in mehreren Batches (VWS *Batch01*) und mehreren Lots (VWS *Lot01*) gefertigt werden. Nachfolgend werden die Struktur und Inhalte der einzelnen VWS genauer beschrieben.

#### ProductType

Die VWS *ProductType* ist eine VWS auf Typebene und beinhaltet alle Informationen, um das Produkt bzw. Halbfabrikat zu fertigen (*Abbildung 3-25*).

![image](https://github.com/user-attachments/assets/f991a512-aeea-4eb7-babb-869dfbcf5517)   
*Abbildung 3-25: VWS ProductType*

Die VWS *ProductType* beinhaltet die Submodelle „*ManufacturingBOM*“, „*BillOfProcess*“ und „*Required* *Capabilities*“. In der *ManufacturingBOM* werden alle notwendigen Materialien als Entities gelistet. Analog werden im Submodel *BillOfProcess* alle notwendigen Prozesse in einer SMC *ProcessSequence* aufgeführt.

Die einzelnen Prozesse sind wiederum in eigenen SMCs strukturiert und besitzen eine Namenskonvention, bei der vor jedem Prozess das Präfix „Nominal“ vorangestellt wird (z.B. *NominalCutProcess01*).

![image](https://github.com/user-attachments/assets/bfa46aa1-3c47-4526-a4d4-c4a45d3379f9)   
*Abbildung 3-26: SMC Product Sequence*

Die Nominalprozesse bzw. Sollprozesse beinhalten eine einheitliche Struktur mit den folgende Properties (*Abbildung* 127):

-   *ProcessId*: Jeder Prozess soll eine eindeutige ID besitzen
-   *ProcessName*: Der Name des Prozesses
-   *OperatorRole*: Die Rolle des Maschinenbedieners (bspw. Werker, Wartungsmitarbeiter)
-   *ProcessDescription*: Prozessbeschreibung
-   *PlannedProcessTime*: Die Planzeit des Prozesses

![image](https://github.com/user-attachments/assets/54179d4d-3fa4-4da2-bb57-98bd7a1ab40b)   
*Abbildung 3-27: Nominalprozess Cut*

Des Weiteren sind folgende SMC enthalten (*Abbildung* 3-28):

-   *ProductParameters*: Listet alle Einzelmaterialien mit ihren Produkteigenschaften auf
-   *ProcessParameters*: Beinhaltet die Prozessparameter (z.B. Schneiden auf Solllänge (*NominalLength*)
-   *ResourceParameters*: Beinhaltet die Referenzen auf die eingesetzte Maschine und gerüstete Werkzeuge
-   *ProcessBom*: Beinhaltet Referenzen auf alle zu verarbeitenden Materialien für den Prozess auf Planungsebene für den Materialverbrauch

![image](https://github.com/user-attachments/assets/7139147d-65b4-4813-8875-b43d294934b4)   
*Abbildung 3-28: SMC PPR, ProcessBom*

Anschließend wurde innerhalb der VWS *ProductType* das Submodell „*RequiredCapabilities*“ definiert. Die Struktur folgt der offiziellen Spezifikation und unterteilt die *RequiredCapabilities* in eine SMC *CapabilitySet* und dieses wird wiederum in einem oder mehreren *CapabilityContainern* untergliedert (*Abbildung* 3-29). Jeder einzelne *CapabilityContainer* beinhaltet eine Capability „Cap“ mit der entsprechenden Bezeichnung und einer SMC *PropertySet*.

![image](https://github.com/user-attachments/assets/3e47a4c2-2137-434f-849e-72fa3bef609b)   
*Abbildung 3-29: Required Capabilities*

#### ProductionOrder

Die Instanzenebene beginnt mit der Erstellung eines konkreten Produktionsauftrages. Hierzu wurde die VWS *ProductionOrder* („[AP3.5_AAS_Prozesse_2024_04_12_V3.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/AP3.5_AAS_Prozesse_2024_04_12_V3.aasx)“[^9]) definiert (siehe *Abbildung* 130).

[^9]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/AP3.5_AAS_Prozesse_2024_04_12_V3.aasx>

![image](https://github.com/user-attachments/assets/f3c4ebd5-99cf-45b2-8acb-62d15e9d6d80)   
*Abbildung 3-30: VWS ProductionOrder*

Die VWS *ProductionOrder* enthält ein Submodell „*ProductionOrder*“ mit den folgenden Inhalten:

-   *ProductionOrderSize*: Die zu produzierende Stückzahl für den Produktionsauftrag
-   *ProductionOrderStatus*: Der Status des Produktionsauftrags, bspw. „erstellt“, „freigegeben“, „gestartet“, „abgeschlossen“ oder „Fehlermeldung“
-   *ProductionOrderResult*: Das Ergebnis des Produktionsauftrages, bspw. „OK“ oder „NOK“ (Not OK)
-   SMC *BatchReferences*: Verlinkt die einzelnen Batches des Produktionsauftrages mit der VWS *Batch* (im Beispiel „Batch01“ und „Batch02“)
-   *ProductTypeReference*: Referenz auf den zu fertigenden Produkttyp

#### IDTA Standardisierung BoP Submodel

Die in diesem Dokument entworfenen Prozess-VWS diente als Grundlage für die Standardisierung des Submodells „IDTA 02031: *Bill of Process*“ [8].

![image](https://github.com/user-attachments/assets/eca391ef-7c56-49e0-bff6-d40b0c1ac478)    
Abbildung 3-31: IDTA 2031 Bill of Process

### <a name="_3.3.4"></a>Capabilities aus Prozesssicht

Als typisches Muster in der konventionellen Informationsmodellierung sind nach dem PPR-Paradigma die Prozess- und Ressourcendimensionen eng miteinander verbunden. Für jeden Vorgang in einem Produktionsprozess weist die klassische Fertigungsplanung die für die Durchführung des Vorgangs am besten geeignete Maschine als Ressource zu. Daher sind Produktdesign, Fertigungsplanung und -ausführung in der konventionellen Planung oft eng miteinander gekoppelt. Um ein Szenario der flexiblen Fertigung nach den Ideen von Industrie 4.0 zu realisieren, muss diese enge Kopplung in der Planungsphase aufgelöst werden, damit die Zuordnung von Prozessen zu Ressourcen flexibel entschieden und automatisiert werden kann.

Um die bislang statische Verknüpfung zwischen dem Prozess und den zugehörigen Ressourcen aufzubrechen, benötigt man daher ein zusätzliches Element, das zwischen den beiden vermittelt. Ein solches zusätzliches Element auf Basis des PPR-Modells wird als Fähigkeit (Capability) oder Fertigkeit (Skill) bezeichnet. Das daraus resultierende konzeptionelle Modell ist eine Erweiterung des etablierten PPR-Darstellungsparadigmas um die Konzepte "Capability", "Skill" und "Service", welche die zugrunde liegende produktionsrelevante Funktion aus einer anderen Perspektive erfassen. Daher wird das resultierende Modell das als Capability-Skill-Service-Modell oder kurz CSS-Modell bezeichnet, welches die grundlegenden formalen Elemente für die Realisierung von flexiblen Produktionsszenarien liefert [9].

Das CSS-Modell umfasst vier Bereiche, die in *Abbildung 3-32* farblich hervorgehoben wurden. Gelb kennzeichnet die einzelnen Elemente des PPR-Modells. Orange bezeichnet Funktionen, die sich in Produktionsprozessschritten widerspiegeln, die einerseits für die Herstellung von Produkten erforderlich sind und andererseits an Produktionsressourcen ausgeführt werden. Erforderliche und bereitgestellte Fähigkeiten (Required und Offered Capabilities) müssen abgeglichen werden, um eine geeignete Abfolge von Produktionsschritten für gegebene Anforderungen zu finden. Dies kann zunächst auf einer deskriptiven Ebene geschehen - z.B. durch den Vergleich von Fähigkeitstypen und deren Eigenschaften - unabhängig davon, welche tatsächlichen Ressourcen diese Prozessschritte später ausführen.

Um die durch eine Fähigkeit beschriebene Funktion in einem bestimmten Produktionsprozessschritt anzuwenden, wird ein so genannter "Skill" (Fähigkeit) aufgerufen, d.h. eine Implementierung dieser Funktion, die von einer bestimmten Ressource bereitgestellt wird (blau in *Abbildung* 132). Ein Skill wird über eine Schnittstelle aktiviert und gesteuert, die von der Skill-Implementierung bereitgestellt wird, um externen Einheiten den Zugriff auf einen Skill zu ermöglichen, ohne interne Implementierungsdetails preiszugeben. Skills werden Ressourceninstanzen zugewiesen.

Zusätzlich zu den funktionalen Aspekten, die durch die Fähigkeiten beschrieben werden, müssen auch weitere organisatorische und kommerzielle Aspekte, wie z.B. Zeitplanung, Qualität oder Kosten, berücksichtigt werden. Zu diesem Zweck werden im Modell erforderliche und angebotene Services (grün in *Abbildung* 132) definiert [10]. Services (Dienstleistungen) beschreiben das Angebot von Fähigkeiten in einem breiteren Rahmen größerer Lieferkettennetzwerke, die über die lokale Produktionseinrichtung hinausgehen. Daher sind Services in der Regel nicht Teil einer Ressource, sondern von übergeordneten Softwarekomponenten wie Enterprise Resource Planning (ERP)-Systemen.

![image](https://github.com/user-attachments/assets/b3c47a89-0e82-40e2-8cbd-9be9120c496a)    
*Abbildung 3-32: CSS-Modell* [10]

#### Definition der Capabilities

Im Teilprojekt 3 liegt der Fokus auf den Produktionsprozessen eines Leitungssatzes, weshalb der Bereich „Process“ und die dazugehörigen „Required Capabilities“ anhand des CSS-Modells näher analysiert wurden. Hierzu wurden an einem typischen Beispielprodukt (*Abbildung 3-33*) die „Required Capabilities“ abgeleitet, um das Matching mit den „Offered Capabilities“ durchführen zu können.

![image](https://github.com/user-attachments/assets/adc2d45c-1e76-456f-9d24-7148de94d374)    
*Abbildung 3-33: Beispielprodukt zur Ableitung der Required Capabilities*

Das Beispielprodukt besteht aus einem verdrillten Leitungspaar mit jeweils einem Entdrillschutz auf jeder Seite. An beiden Enden werden Terminals gecrimpt und eine Einzelleiterdichtung angebracht. Für das Beispielprodukt wurden folgende Prozesse identifiziert, um eine Herstellung durchführen zu können:

-   Cut
-   Strip
-   Crimp
-   Twist
-   Montage Einzelleitungsabdichtung (ELA)
-   Marking

In den nachfolgenden Unterkapiteln werden zu den einzelnen Prozessen die benötigten Parameter aus Fähigkeitenperspektive (Required Capabilities) vorgestellt.

##### Cut

Für den Prozess „Cut“ werden folgende Parameter benötigt:

-   Leitungslänge
-   Leitungsquerschnitt
-   Isolationsdurchmesser
-   Leitermaterial (Keine Mischung der Materialien (z.B. Alu, Kupfer) bei Kabelschneid-Maschinen)

##### Strip

Für den Prozess „Strip“ werden folgende Parameter benötigt:

-   Isolationswandstärke
-   Abisolierungslänge
-   Startposition für Abisolierung
-   Leitungsaußendurchmesser
-   Leitungsquerschnitt
-   Überwachung für Berührung des Messers beim Abisolieren (Verfügbarkeit der Überwachungseinrichtung

##### Crimp

Für den Prozess „Crimp“ werden folgende Parameter benötigt:

-   Crimpkraftüberwachung als Qualitätsanforderung
-   Leitungsquerschnitt
-   Leitungstyp
-   Terminaltyp (Freigegebene Terminaltypen sind in der Ressource (Werkzeug) hinterlegt)
-   Crimpbreite
-   Crimphöhe
-   Abfrage: Werkzeug passt in Maschine

##### Twist

Benötigte Parameter:

-   Leitungstyp (gibt den Außendurchmesser vor)
-   Min und Max für Leitungslänge (Annahme: Verdrillergebnis wird vorgegeben und Einstellparameter werden von der Maschine berechnet)
-   Min und Max für Leitungsquerschnitt
-   Max. Anzahl der verdrillten Leitungen
-   Schlaglänge + Toleranz
-   Min und Max Länge für unverdrilltes offenes Ende (Komax: Offene Kabelenden Verdrillseite max./min.)  
    \--\> 2x vorhanden für jedes Ende
-   Unterschiedliche offene Enden max.
-   Endlänge verdrillter Leitungen min./max.
-   Vorhandensein der Funktion “Entdrillschutz anbringen” + Position zum Anbringen

##### Montage Einzelleitungsabdichtung (ELA)

Für den Prozess „Montage Einzelleitungsabdichtung“ werden folgende Parameter benötigt:

-   Leitungstyp (gibt den Außendurchmesser vor)
-   Min Leitungslänge
-   Min und Max Leitungsquerschnitt
-   Passendes Werkzeug für ELA vorhanden
-   Abfrage: Werkzeug passt in Maschine

##### Marking

Für den Prozess „Marking“ werden folgende Parameter benötigt:

-   Leitungstyp (nicht auf jedes Material kann man gleich drucken (Bsp. Silikon))
-   Min Leitungslänge
-   Min und Max Leitungsquerschnitt
-   Markingverfahren (Bsp.: Tintenstrahl, Stempel, Hot Stamp)
-   Position der Bedruckung (erstmögliche Bedruckung, z.B. 50mm nach Leitungsende)
-   Druckvarianten (Bsp.: Alphanumerisch + Barcode)
-   Druckfarbe (nur schwarz oder mehrfarbig / mindestens hell und dunkel)
-   Min und Max Schriftgröße (abhängig von Leitungsaußendurchmesser)
-   Wiederholungen (1x/2x/n-mal)

#### Ableitung der Capabilities für Produktionsprozesse

Die notwendigen *Required Capabilities* wurden identifiziert, indem die Prozessliste mit allen Prozessen und den einzelnen Submodel Properties analysiert wurde, um zu identifizieren welche Submodel Properties notwendig für ein Matching mit den *Offered Capabilities* sind.

Die gesamte Liste der Prozesse mit den dazugehörigen Submodel Properties für die *Required Capabilities* ist im Tabellenblatt „Capabilities“ der [Prozessliste](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/Beispieldaten/Prozessliste.xlsx) zu finden.

### <a name="_3.3.5"></a>Prozesssteuerung

Ein Job besteht aus den notwendigen Arbeitsschritten bzw. Prozessen, um einen diskreten Fertigungsschritt abzuschließen. Jeder Prozess verwendet ein Produkt und mindestens eine Ressource, die für die Ausführung des Arbeitsschritts erforderlich sind. Ziel der Prozesssteuerung ist es, die Abfolge der Einzelprozesse eines Jobs zu bestimmen. *Abbildung* 134 zeigt exemplarisch die Arbeitsschritte, die in einem fiktiven Job ausgeführt werden. Dabei werden die einzelnen Prozesse in der Regel sequenziell nacheinander abgearbeitet. Wenn die Umstände es zulassen, können einzelne Arbeitsschritte oder Teilsequenzen, bestehend aus mindestens zwei Prozessen, parallelisiert werden. Auch sind optionale Prozesse möglich, also Prozesse, die nur unter bestimmten Voraussetzungen in dem aktuellen Job ausgeführt werden. Darüber hinaus können einzelne Prozesse eines Jobs auch effektiv unabhängig voneinander sein. Beispielsweise könnte ein Prozess die Dauer eines Jobs messen und diese nach Abschluss dokumentieren.

![image](https://github.com/user-attachments/assets/94cb679f-6435-4551-a139-8d820c46d0ad)    
*Abbildung 3-34: Prozesssequenz*

#### Problemstellung

In modernen Produktionsprozessen ergeben sich zahlreiche Herausforderungen, die eine effiziente und flexible Prozesssteuerung erfordern. Eine der zentralen Schwierigkeiten liegt in der **Parallelisierung von Arbeitsschritten**, die eine gleichzeitige Durchführung mehrerer Tätigkeiten ermöglicht, um die Produktionszeit zu verkürzen und die Effizienz zu steigern. Dabei muss eine dynamische Anpassbarkeit gewährleistet sein, was bedeutet, dass flexibel entschieden werden kann, welcher Schritt zu welchem Zeitpunkt durchgeführt wird. Diese Anpassungsfähigkeit ist essenziell, um auf Veränderungen in der Produktion etwa durch Auftragsanpassungen oder Engpässe bei Material oder Personal schnell reagieren zu können.

Eine weitere Herausforderung besteht im Tracking und der Darstellung der Produktionsabläufe. Es ist notwendig, den tatsächlichen Ablauf mit der digitalen Repräsentation sowie möglichen Visualisierungen zu synchronisieren, um eine genaue und aktuelle Übersicht zu gewährleisten. Ebenso sollen Flaschenhälse in der Produktion durch die Beobachtung des Prozesses identifizierbar gemacht werden, um Engpässe frühzeitig zu erkennen und zu beheben. Hierbei spielt die Dokumentation des Prozesses in digitaler Form eine wichtige Rolle. Die Prozesse müssen maschinenlesbar und ausführbar dokumentiert werden, wozu etwa Daten aus dem Teilmodell „IDTA 02031-1-0 Bill of Process“ [8] genutzt werden, aber auch eine Grundlage für eine Ergebnis-Dokumentation ermöglichen.

Die Konfiguration der Prozesssteuerung stellt ebenfalls eine komplexe Aufgabe dar. Es wird angestrebt, Prozessexperten durch Automatisierung zu ersetzen, um weniger Grundlagenwissen zu den jeweiligen Fertigungsprozessen zu benötigen und gleichzeitig eine anwenderfreundliche Nutzung gewährleisten zu können.

Die Bedeutung einer effizienten Prozesssteuerung ist nicht zu unterschätzen. Sie ermöglicht ein umfassendes Monitoring, Tracking und die Darstellung der Produktionsprozesse. Durch die Vereinfachung der Komplexität wird es möglich, schnell einzugreifen und Anpassungen vorzunehmen, was besonders in dynamischen Umgebungen von Vorteil ist. Die dynamische Konfigurierbarkeit spielt insbesondere bei der Produktion in Losgröße 1 eine wichtige Rolle, da hier individuelle Anpassungen notwendig sind. Zudem wird in Zusammenhang mit den in TP6 erarbeiteten Verhandlungsprozessen auch in der Prozesssteuerung die Verbindung von Aufgaben, Produkten und Ressourcen erzeugt, was die Effizienz und Transparenz weiter erhöht.

Eine Integration der Prozesssteuerung in den digitalen Zwilling der Produktion bringt zahlreiche Vorteile mit sich. Der digitale Zwilling fungiert als Single Source of Truth, wodurch alle relevanten Daten und Informationen an einer zentralen Stelle gebündelt werden. Dies ermöglicht einerseits die Automatisierung durch Ausführungsschritte als Teil des digitalen Zwillings sowie andererseits auch schnelle Anpassungen der Informationen, was die Effizienz und Reaktionsfähigkeit weiter steigert. Darüber hinaus bietet ein digitaler Zwilling eine hohe Konfigurierbarkeit, wodurch Prozesse flexibel an neue Anforderungen angepasst werden können. Dazu werden in diesem Teilprojekt bestehende Konzepte und Lösungen verwendet, um eine Kompatibilität nach außen gewährleisten zu können.

Zusammenfassend lässt sich sagen, dass die Herausforderungen im Produktionsprozess durch eine effiziente und flexible Prozesssteuerung gemeistert werden können. Die Integration dieser Steuerung in den digitalen Zwilling bietet dabei zusätzliche Vorteile, die zur Optimierung und Zukunftsfähigkeit der Produktion beitragen.

#### Digitale Prozessabbildung
![image](https://github.com/user-attachments/assets/cac1aa56-bd26-4ca3-a114-19ef5fe4f971)    
Abbildung 35: Beispiel der Sicherungsbox

Zunächst wurde ein digitales Prozessabbild am Beispiel einer Sicherungsbox (siehe *Abbildung 3-35*) erstellt. Die Sicherungsbox stellt ein überschaubar komplexes Beispiel dar, da verschiedene Prozessschritte parallel ablaufen müssen, während gleichzeitig Schritte grundsätzlich gleich sein könnten. So müssen für jede Sicherung grundsätzlich zwei Verbindungen durch Schrauben befestigt werden. Dieser Prozessschritt ist für alle Positionen gleich, erfolgt aber nicht in einer vordefinierten Reihenfolge, so dass theoretisch Position 3 vor Position 1 verschraubt werden könnte. Ebenso sind im Gesamtprozess parallele Prozesse eingearbeitet. So wird ein elektrischer Test mit jedem Schraubvorgang ausgeführt, um potenzielle Probleme frühzeitig zu erkennen, während der Gesamtprozess einen Überwachungsschritt hat, um diese Informationen zu sammeln und ggfs. zu verwerten.

*Abbildung 3-37* zeigt die einfache Übersicht zum Prozess auf der linken Seite, sowie die Erweiterung um einen Scan-Vorgang auf der rechten, welcher als Sicherheitsschritt eingebaut wird. Als Endausbau des Prozessbeispiels zeigt *Abbildung 3-37* die gesamte Prozesssequenz inkl. der parallel auszuführenden Prozesse. Ebenso sind die Aufgaben für zwei Positionen, bestehend aus einem Scan- sowie Schraub-Vorgang und dem parallel ausgeführten elektrischen Test, sequenziell dargestellt, um die rekursiven Aspekte des Prozessschrittes abzubilden. Diese drei Einzelschritte werden für jegliche Positionen ausgeführt, während der Überwachungsprozess aktiv sein muss, und können in zufälliger Reihenfolge existieren.

![image](https://github.com/user-attachments/assets/c391fb2a-0a03-463d-9f53-b44982444748)    
*Abbildung 3-36: Simple Prozesssequenz zum Schraubvorgang an zwei Positionen*

![image](https://github.com/user-attachments/assets/4565746b-0a8d-487e-92fd-223439777207)        
*Abbildung 3-37: Prozesssequenz am Beispiel Sicherungsbox*

Die „Business Process Model and Notation“ (BPMN) ist in ISO/IEC 19510:2013 [11] standardisiert und erlaubt die grafische Modellierung komplexer Prozesse. Der Standard wird von der gemeinnützigen [Object Management Group (OMG)](https://www.omg.org/spec/BPMN) verwaltet und international in vielen Organisationen eingesetzt, da die visuelle Natur von BPMN ein besseres Verständnis komplexer Abläufe ermöglicht.

Aus diesen Überlegungen wurde für den vorliegenden Fall zunächst manuell ein BPMN-Dokument erstellt (siehe *Abbildung 3-38*), um den Gesamtprozess über eine automatisierte Steuerung mittels der BPMN Engine und Prozess-Orchestration CAMUNDA[^10] auszuführen. In der *Abbildung* sind die automatisierten Prozessschritte zur Überwachung, dem elektrischen Test und den Scan- sowie Schrauben-Vorgängen, besonders gekennzeichnet. Ebenso sind manuelle Schritte hinzugekommen, um zunächst die Position festzulegen und anschließend zu prüfen, ob weitere Schraubvorgänge notwendig sind. Diese Schritte sind ebenfalls anhand des Auftrags automatisierbar.

[^10]: <https://camunda.com/>

In die Struktur des BPMN-Protokolls wurden Konnektoren eingefügt, um Prozesse parallel starten und ablaufen zu lassen, sowie Entweder-Oder-Fälle abhandeln zu können. Diese Konnektoren werden entsprechend vom ausführenden Softwaresystem erkannt und ggfs. Entscheidungen aus den existierenden Daten der Verwaltungsschalen der jeweiligen Geräten, Produkten und Prozessen abgeleitet.

Die BPMN-Struktur bringt auch Vorteile in repetitiven Aufgaben, da Prozessschritte einfach wiederholt werden können und auch Rekursive Prozesse abgebildet werden können. Dies ist im Beispiel in *Abbildung 3-38* durch die Abfrage „Schraubprozess fertig?“ gegeben, wo nach einer entsprechenden Abfrage der Daten der gleiche Schraubprozess für weitere Positionen durchlaufen werden kann, ohne den gesamten Prozess als lineare Reihenfolge durchzuplanen.

![image](https://github.com/user-attachments/assets/665a60ae-4889-4c6f-b0ad-52be61cc51a8)    
*Abbildung 3-38: Darstellung des Prozessbeispiels als BPMN*

#### Prozessausführung als Teil der Produkt-Verwaltungsschale

Im Projekt wurde zur automatisierbaren Ausführung des Prozesses dieser als Teil der Produkt-Verwaltungsschale grundsätzlich integriert. Dies beinhaltet sowohl das BOP-Teilmodell als auch ein Konzept zur Erweiterung der Komponenten der Open-Source Middleware Eclipse BaSyx[^11] um eine Komponente zur automatischen Generierung von BPMN-Strukturen aus dem Teilmodell.

[^11]: <https://github.com/eclipse-basyx/>

In Verbindung mit den in TP6 entwickelten Verhandlungsprozessen werden zu jedem auszuführenden Schritt des Prozesses entsprechende Ressourcen, also Maschinen und Materialien zugewiesen. Somit werden Prozessschritte und digitale Zwillinge der ausführenden Ressource dynamisch verknüpft, so dass zwar eine Vorbelegung stattfindet, diese jedoch vollständig automatisierbar ist.

*Abbildung 3-39* zeigt diese Verknüpfung zwischen den Aufgaben und jeweiligen Ressourcen anhand der vorher dargestellten Prozesse schematisch. So wird in der Prozesssequenz zunächst Position 1 von Ressource 1 gescannt und verschraubt während Ressource 3 den elektrischen Test und Ressource 5 die generelle Überwachung parallel ausführen. Anschließend werden Ressourcen 1 und 3 durch Ressourcen 2 und 4 ersetzt, um den gleichen Arbeitsschritt für Position 2 auszuführen.

![image](https://github.com/user-attachments/assets/e6d62f27-fec0-45b5-8762-1f110ec3809e)    
*Abbildung 3-39: Prozesssequenz am Beispiel Sicherungsbox inkl. Ressourcenzuteilung*

Grundsätzlich wurde dadurch ein direktes Mapping zwischen verfügbaren Funktionalitäten von Ressourcen und benötigten Ressourcen durch den Prozess angelegt, welches als Grundlage für komplexere und größere Prozesse genutzt werden kann. Durch die in der BPMN-Struktur vorgesehenen Prozessgruppen kann ebenfalls ein Prozess hierarchisch aufgebaut werden, um komplexe Herstellungsprozesse zu kapseln und spezifische Arbeitsschritte als Pakete zu verwenden.

Mit dem Einsatz virtueller Ressourcen, die mögliche verknüpfte Prozessschritte bearbeiten können, indem sie diese als eigenen Gesamtprozess bearbeiten, kann so die Komplexität verringert und die dynamische Anpassbarkeit, etwa durch minimale Veränderungen in Prozessteilen aufgrund von Messwerten, die während vorheriger Schritte genommen wurden, erhöht werden.

#### Dokumentation der Prozessparameter

Neben der Ausführung der Prozesse werden die Funktionalitäten der Ressourcen genutzt, um Prozessparameter als Teil der Produkt-Verwaltungsschale zu dokumentieren. *Abbildung 3-40* zeigt dazu einen abgelaufenen Prozess in BPMN-Notation in CAMUNDA, die gewählten Pfade sind blau markiert. So ist auch in der Visualisierung erkennbar, dass ein Scan- und Schraubprozess durchgeführt wurde.

![image](https://github.com/user-attachments/assets/c36fe594-8969-463f-b14d-58f69be57306)    
*Abbildung 3-40: Darstellung eines Prozessablaufs als BPMN*

Alle Komponenten in Form der Verwaltungsschale werden genutzt, um die jeweiligen Prozessdaten, wie bspw. die Crimp-Kraft, produktgenau als Teil des digitalen Produktzwillings festzuhalten. So können Entscheidungen und auch Fehler rückverfolgbar dokumentiert bzw. Abbruchkriterien bereits im laufenden Prozess betrachtet werden. Neben der möglichst frühzeitigen Beendigung des Fertigungsprozesses im Fehlerfall, könnten diese Daten auch für weitergehende Analysen oder auch KI-Fragestellungen verwendet werden, um so die Herstellung noch weiter zu optimieren, bspw. mittels neuer und effizienterer Scheduling-Möglichkeiten eine bessere Maschinenauslastung zu erreichen.

#### Anwendung im Demonstrator

Im Demonstrator des Projektes VWS4LS wird die beschriebene Prozesssteuerung als Ersatz für ein herkömmliches Manufacturing-Execution-System (MES) eingesetzt. Für die Ende-zu-Ende Digitalisierung mit Verwaltungsschalen für alle genutzten Assets können so die notwendigen Daten erhoben und verarbeitet werden.

Der Demonstrator beginnt seine Ablaufsequenz mit dem simulierten MES-System, das als User Interface fungiert und den Gesamtprozess startet, indem zunächst ein Produkt ausgewählt wird. Daraufhin werden die entsprechenden Verwaltungsschalen für *ProductionOrder*, *Batch* und *Lot* angelegt. Anschließend werden die über Node-RED ausgeführten Verhandlungsprozesse aus TP6 angestoßen. Die Ergebnisse dieser Verhandlungen werden dem Nutzer zurückgespielt, damit er zwischen den möglichen Ressourcen auswählen kann. Anschließend wird der Rüstvorgang der Ressourcen gestartet, was ebenfalls in den Ressourcen-Verwaltungsschalen reflektiert wird. Der tatsächliche Fertigungsprozess auf den Produktionsresourcen wird anschließend automatisch gestartet und entsprechend der Auswahl durchgeführt. Schließlich werden die Ergebnisse dokumentiert, bevor der Demonstrationsprozess von Neuem beginnt, um den kontinuierlichen Ablauf und die Anpassungsfähigkeit des Systems zu demonstrieren.

Die während des Prozesses anfallenden Daten werden, wie in Kapitel 1.3.5.4 beschrieben, dokumentiert und eine Visualisierung der Prozessschritte wird als Live-Darstellung in CAMUNDA bereitgestellt.

## <a name="_3.4"></a>AP 3.4 - Proof of Concept

Quellsysteme liefern Daten unterschiedlich strukturiert, d.h. es kann sich um un- bzw. semistrukturierte Daten handeln. Für die zugrunde liegende Datenstruktur in der VWS wurde daher ein Datenmapping Service entwickelt, der die Kompatibilität zwischen bestehenden Systemlandschaften (Brownfield) und der VWS ermöglicht, um in beide Richtungen kommunizieren zu können. Um die Konvertierung zu gewährleisten, ist eine Validierung zwingend erforderlich, welche in verschiedenen Schritten der Datenerhebung und Datenverarbeitung durchgeführt wird.

Die Ziele des generischen Ansatzes für Datenmapping mit anschließender Validierung:

-   Konvertierung von un- bzw. semistrukturierten Daten
-   Unterbrechungen im Datenfluss verhindern
-   Strukturelle Veränderungen erkennen
-   Vermeidung unvollständiger Daten
-   Steigerung der Datenqualität
-   Reduzierung des manuellen Aufwands

![image](https://github.com/user-attachments/assets/606176ff-14ae-481d-8d17-53d1b82bc9ad)    
*Abbildung 3-41: Exemplarische Darstellung des Data Mapping Services mit VWS als Zielsystem*

*Abbildung* 3-41 zeigt einen fiktiven Ablauf eines typischen Anwendungsfalls. Eine aus Datenqualitätssicht unsichere Quelle, in diesem Schaubild eine Ressource, erzeugt semistrukturierte Daten in Form von einem OPC UA Nodeset (XML-Format). Bevor diese Daten in das Zielsystem (Information Storage in Form der Verwaltungsschale) weggeschrieben werden, werden diese validiert. Im positiven Fall erfolgt direkt das Persistieren im Zielsystem. Im negativen Fall erfolgt ein Mapping der Daten zur Zielstruktur. Diese Daten werden erneut validiert und im positiven Fall weggeschrieben.

Die Verwaltung von gültigen Strukturen der Daten von Quell- und Zielsystem erfolgt im Semantic Hub. Der Semantic Hub beinhaltet alle benötigten Konfigurationen, sowohl aus Datensicht aber auch die Systemkonfiguration von Quell und Zielsystem.

### <a name="_3.4.1"></a>Datenvalidierung

#### Quellformate

In der Praxis ist eine Validierung direkt an der Maschine nicht sinnvoll. Die Vielzahl der unterschiedlichen Maschinen Protokolle und eine in der Regel immer später stattfindende Transformation zur Übertragung der Daten, sprechen gegen eine Validierung an der Maschine. ​

Aufgrund der Tatsache das in BaSyx die Daten der Verwaltungsschale per REST API in einem JSON-Format übertragen wird, und JSON als Standard am Markt angesehen werden kann, macht es Sinn im POC die Validierung- und die Mapping Logik auf das JSON-Format zu beschränken.​

Nach der Validierung wird ausschließlich das validierte/gemappte JSON zur Verfügung gestellt.
​

#### Semantic Hub

-   Die Referenz-Struktur eines Submodels muss vorhanden sein. ​
-   Das Identifizieren des Submodels über eindeutige Identifier muss gegeben sein.​
-   Eine Versionierung der Referenzstrukturen muss möglich sein.​
-   Die Semantik des Referenzmodels muss definiert sein.

#### Micro-Service „Datenvalidierung“

-   ​Der Web-Service ist in der Lage die richtige Zielverwaltungsschale zu finden.​
-   Der Web-Service ist in der Lage die Namen, die Struktur und den Datentyp der JSON-Objekte zu validieren.​
-   Im Fehlerfall soll eine für das IT-System verwendbare Fehlerbeschreibung mit Fehlercode zurückgesendet werden​.
​

#### Submodel InformationModelDescription für die Datenvalidierung

Das Submodel InformationModelDescription hat folgende Anforderungen zu erfüllen:

-   Das Identifizieren des Submodels über eindeutige Identifier.
-   Eine Versionierung der Referenzstrukturen.
-   Die Semantik des Referenzmodels muss definierbar sein.
-   Die notwendigen Bearbeitungsfunktionalitäten müssen zur Verfügung stehen.
-   Die Daten müssen persistierbar sein.

    Die *Abbildung* 3-42 zeigt eine Resourcen VWS mit dem verlinkten Submodel *InformationModelDescription*. Das Submodel enthält die SemanticId des Informationsmodells, welche im Semantic Hub als Suchkriterium für die Beschreibung des Informationsmodells dient.

    Das Submodel ‚*InformationModelDescription*‘ wird offengehalten, d.h. die enthaltenen Informationen und Formate der bereitgestellten Informationsmodelle können je nach UseCase erweitert werden. Beispielhaft wurden 3 SMC *InformationModelDescriptionSets* angelegt. Mandatorisch enthält das Submodel die *ModelVersion*

    Das in der *Abbildung* 3-43 dargestellte SMC *InformationModelDescriptionSetJSONSchema* wurde für die Benutzung der Validierung über das JSON-Format angelegt. Das JSON-Schema wurde als String Property mit SemanticId ‚*JSONSchema*‘ hinterlegt.

    In der *Abbildung* 3-44 erfolgte die Umsetzung mit der SMC *InformationModelDescriptionSetAASElement*. Die in einem Template dargestellten Properties werden ohne den eigentlichen Content dargestellt, da die Validierung nur auf die Struktur und nicht auf den Content durchgeführt wird.

![image](https://github.com/user-attachments/assets/883da610-7031-4a25-b10b-396f0891c11d)    
*Abbildung 3-42: AAS Resource mit AAS und SM*

![image](https://github.com/user-attachments/assets/b85cf502-4234-4af2-8c70-55f85619ca5c)    
*Abbildung 3-43: AAS und SM und SMC InformationModelDescriptionSetJSONSchema*

![image](https://github.com/user-attachments/assets/3a3ea2a6-7a55-4796-b71e-0caabdec0ce9)    
*Abbildung 3-44: AAS und SM und SMC InformationModelDescriptionSetAASElement*

#### Out of Scope​

-   Alle Themen, die in der Implementierung in Richtung **Security** gehen, werden ausgeklammert und in den fachlichen Konzepten nicht berücksichtigt. Das Thema Security würde den Rahmen des POC‘s sprengen.​
-   Die **Transformation der unterschiedlichen Maschinenschnittstellen** in das Übertragungsformat JSON ist nicht Bestandteil des Daten Mapping Konzeptes. Die Transformation kann im Demonstrator in das existierende MES-Modul eingebaut werden.​
-   Das **Speichern** der validierten und gemappten Daten in das **Zielsystem** ist nicht Bestandteil des Konzeptes. Dies kann im Demonstrator in das existierende MES-Modul eingebaut werden.

### <a name="_3.4.2"></a>Datenmapping

#### DataBridge: Keine Datensenkenzuordnung im Transformer

Der Data Mapping Service nutzt die [Eclipse BaSyx DataBridge](https://github.com/eclipse-basyx/basyx-databridge), um Daten von einer distinkten Datenquelle an eine oder mehrere Verwaltungsschalen Endpunkt(e) zu transferieren. Dazu ist die DataBridge für das Zuordnen von (physischen) Daten zur logischen Geräteinformationsstruktur der Verwaltungsschale und die Übertragung zuständig. Der Begriff „Datenmapping“ beschreibt hierbei den Prozess dieser Zuordnung, die anhand von vorher festgelegten Mustern erfolgt.

Eine Instanz der DataBridge kann Daten aus einer einzelnen Datenquelle auf mehrere Datensenken übertragen und währenddessen die Daten umwandeln. Diese grundlegende Funktion kann in drei Hauptschritten erklärt werden:

1.  **Datenquelle**: Die Datenquelle ist das physische Gerät oder System, das die Rohdaten generiert. Dies können beispielsweise Sensoren, Aktoren oder Maschinen sein, die verschiedene Informationen wie Temperatur, Druck oder Zustandsdaten liefern. Die Datenquellen liefern kontinuierlich oder in Intervallen ihre Messwerte oder Statusinformationen.
2.  **Transformer**: Der Transformer ist eine zentrale Komponente, die für das Datenmapping verantwortlich ist. Er transformiert die Rohdaten aus der Datenquelle in ein Format, das für die jeweilige Anwendung oder Datensenke geeignet ist. Somit können komplexe Datenobjekte vereinfacht und auf die jeweiligen semantischen Modelle heruntergebrochen werden. Diese Transformation kann verschiedene Formen annehmen und auch verschachtelt werden:
    1.  Skalierung oder Normalisierung der Daten: Rohdaten werden in einem standardisierten Format bereitgestellt.
    2.  Filterung oder Aggregation: Unnötige Informationen werden herausgefiltert, oder Daten werden auf Basis von bestimmten Regeln zusammengefasst.
    3.  Einheitenumrechnung: Daten können in andere Einheiten umgerechnet werden, um Kompatibilität zu gewährleisten (z.B. von Fahrenheit in Celsius). Der Transformer stellt sicher, dass die Daten der Quelle in einem konsistenten, verwertbaren Format an die nächste Komponente weitergegeben werden.
3.  **Datensenke**: Die Datensenke ist das Zielsystem, das die transformierten Daten empfängt und weiterverarbeitet als Teil der Verwaltungsschale.

Zusammengefasst:

-   Eine **Datenquelle** erzeugt Rohdaten.
-   Die **Transformer** wandeln diese Rohdaten in das passende Format um.
-   Die **Datensenken** empfangen die transformierten Daten zur weiteren Nutzung.

Durch diese Pipeline wird eine reibungslose und standardisierte Kommunikation zwischen verschiedenen Systemen und Geräten gewährleistet.

Das nachfolgend aufgeführte Beispiel zeigt die Konfiguration einer Route in der *routes.JSON*, in welcher ein Datenpunkt der Quelle *datasource* auf drei Datensenken (*sink1, sink2, sink3*) zugewiesen wird. Dabei werden in diesem Fall immer alle drei definierten Transformatoren (*transformer1, transformer2, transformer3*) durchlaufen.

Datei: routes.JSON
````
[
	{
		"datasource": "mqttSource",
		"transformers": [
			"transformer1",
			"transformer2",
			"transformer3"
		],
		"datasinks": [
			"sink1",
			"sink2",
			"sink3"		],
		"trigger": "event"
	}
]

![image](https://github.com/user-attachments/assets/d8474341-2cdf-4327-a2ad-c58ff763306f)    
*Abbildung 45: Keine Datensenkenzuordnung*

````
#### DataBridge: Mit Datensenkenzuordnung im Transformer

Im Unterschied zum vorangegangenen Beispiel werden nun für jede Datensenke die zu durchlaufenden Transformatoren angegeben. Im Fall von *sink3* wären dies z.B. *transformer2* und *transformer3*.

Datei: routes.JSON
````
[
	{
		"datasource": "mqttSource",
		"transformers": [
			"transformer1",
			"transformer2",
			"transformer3"
		],
		"datasinks": [
			"sink1",
			"sink2",
			"sink3"
		],
		"datasinkMappingConfiguration":
		{
			"sink1": ["transformer1"],
			"sink2": ["transformer2"],
			"sink3": ["transformer2", "transformer3"]
		},
		"trigger": "event"
	}
]
````
![image](https://github.com/user-attachments/assets/09b50280-06a2-45c2-a3cd-4d0e3610c335)    
*Abbildung 46: Mit Datensenkenzuordnung*

Wurden Routen mit Datensenken (*datasinks*) definiert, die nicht Teil der Datensenkenzuordnung (*datasinkMappingConfiguration*) sind, so durchlaufen diese keine Transformatoren und werden somit nicht innerhalb der Route modifiziert. Wurden mehr Transformatoren definiert, als in der Datensenkenzuordnung (*datasinkMappingConfiguration*) verwendet werden, dann werden diese ignoriert.

#### Mögliche Integration des Datenmapping im Demonstrator

Die Integration der Ergebnisse des Data Mapping Service in den Demonstrator des Projektes wäre möglich, indem die Maschinendaten sowohl über ein MES (Manufacturing Execution System) als auch über OPC UA Knoten ausgelesen werden. Diese Datenquellen ermöglichen es, in Echtzeit auf Produktionsdaten zuzugreifen und diese dynamisch für die weitere Verarbeitung, etwa als Teil der Prozesssteuerung, einzusetzen. Hierbei übernimmt der Data Mapping Service die Aufgabe, die Rohdaten der Maschinen in ein konsistentes, verständliches Format zu transformieren, sodass sie in den digitalen Zwillingen standardisiert abgebildet werden können. Nachfolgende *Abbildung* zeigt den Ablauf als Teil des Demonstrators.

![image](https://github.com/user-attachments/assets/d30d628c-3611-4d80-9294-da80acd635a8)     
*Abbildung 3-48: Mögliche Datenmapping-Integration*

## <a name="_3.5"></a>AP 3.5 - Validierung der Prinzipien

Das AP3.5 „Validierung der Prinzipien“ fokussierte sich auf die systematische Erfassung, Gliederung und digitale Beschreibung der Produktionsprozesse, unter Anwendung des VWS-Teilmodells „IDTA-02031: Bill of Processes“ (BoP) [8], der dynamischen Prozessmodellierung mittels BPMN und der dynamischen Prozessteuerung mittels OPC UA [7].

### <a name="_3.5.1"></a>Prozessablaufsteuerung für Produktionsprozesse

Die Produktion eines Leitungssatzes ist ein komplexer Gesamtprozess und erfordert mehrere zu berücksichtigende Teilbereiche. Sie setzt sich aus mehreren Produktionsschritten zusammen, von denen einige manuelle Tätigkeiten umfassen (siehe *Abbildung* 3-49).

![image](https://github.com/user-attachments/assets/739fdada-d08b-4da5-a832-24cf950d8982)    
*Abbildung 3-49: Übersicht der Produktionsschritte in der Leitungssatzproduktion*

Bevor die eigentliche Leitungssatzproduktion beginnt, kommen alle notwendigen (Roh-)Materialien in der Eingangslogistik oder im Lagerbereich an, wo Komponenten und Rohstoffe gescannt werden.

Der **Schneidprozess und die Leitungsverarbeitung (P1)** weisen einen sehr hohen Automatisierungsgrad auf und erfolgen nach dem Eingang des Rohmaterials. Der Schneidprozess wird derzeit von Leitungsverarbeitungsmaschinen durchgeführt, die von einem MES-System gesteuert werden. In der Regel übernehmen die Maschinen in diesem Schritt die Prozesse des Ablängens, des Abisolierens, des Aufbringens von Dichtungen und Kontaktteilen und bei Bedarf der Kennzeichnung durch Etikettierung, Farbcodierung oder maschinenlesbare Markierungen.

Der **Vormontageprozess (P2)** ist teilautomatisiert. In diesem Schritt finden verschiedene Prozesse statt, wie z. B. Schrumpfen oder Ultraschallschweißen (USW) und viele andere, wie in *Abbildung* 149 dargestellt. Häufig werden auch sog. Produktionsmodule in größerer Stückzahl gefertigt, die im späteren Produktionsverlauf dann in den Gesamtleitungssatz verbaut werden.

Der **Endmontageprozess (P3)** wird überwiegend in Handarbeit durchgeführt, wobei die Teile und Module aus P2 als Input für die Leitungssatzmontage dienen, in der diese Vorprodukte montiert, gewickelt, gesteckt und das Layout fertiggestellt werden.

In der Stufe **„Spezielle Prozesse und Prüfung“ (P4)** ist es möglich, dass spezielle Prozesse wie das Schäumen durchgeführt werden. Am Ende dieser Phase wird der Testprozess durchgeführt, um die Qualität des Leitungssatzes zu überprüfen, wobei die Qualität des gesamten Leitungssatzes und aller seiner Komponenten überprüft wird, einschließlich des Vorhandenseins von Komponenten, elektrischen Anschlüssen, Widerständen, Kondensatoren, Leitungsfarben und Pin-Positionen.

Schließlich wird der Produktionsprozess mit Kommissionierung und Verpackung abgeschlossen, bevor das Produkt das Werk verlässt.

#### Ablaufsteuerung im Sinne einer Sequenzierung (BOP in AAS Product Type)

Bei der Verwaltungsschale kann man zwischen Typen-, also einer abstrakten Beschreibung der Art des Assets, und Instanzen-AAS, also des tatsächlich entstandenen Assets, unterscheiden (siehe *Abbildung* 150).

Bevor die tatsächliche Produktion gestartet wird, befindet man sich auf der Typenebene. D.h. das Produkt ist mit seinen Bestandteilen und den dazugehörigen Produktionsprozessen definiert, jedoch noch nicht produziert.

Sobald ein Produktionsauftrag für einen Leitungssatz und den dazugehörigen Halbfabrikaten angelegt wurde, beginnt die Instanzebene. Das bedeutet, zu diesem Zeitpunkt wird die Produktion eines konkreten Produktes gestartet und alle relevanten Attribute durch die Verwaltungsschale dokumentiert. In der *Abbildung* 150 beschreibt die Verwaltungsschale „Batch01“ eine physische oder logische Unterteilung eines Produktionsauftrages während „Lot01“ Informationen zu allen produzierten Einheiten beinhaltet.

![image](https://github.com/user-attachments/assets/4843aca5-034f-4880-8ff6-e3f4384035d5)    
*Abbildung 3-50: Typ- und Instanzen-AAS*

##### Alle Prozesse für 150%-LS und Ableitung der Fähigkeiten (Required Capabilities)

Der „150%-Leitungssatz“ beschreibt alle Funktionsmodule des Leitungssatzes, die in einem Fahrzeugprojekt existieren rein aus funktionaler Sicht. Dieser Gesamtumfang kann auch nicht in einem konkreten Fahrzeug verbaut werden, da sich Funktionsmodule gegenseitig ausschließen können, wie beispielsweise Xenon- und LED-Scheinwerfer.

Daher muss der 150%-Leitungssatz auch nie in dieser Form produziert werden. Es ist viel mehr die Gesamtheit der technischen Dokumentation, um alle möglichen Funktionsmodule abzubilden und damit später auch produzieren zu können.

Die Daten der Verwaltungsschale für den 150%-Leitungssatz werden von dem Leitungssatzkonfektionär, der mit der Entwicklung des Leitungssatzes betraut ist, erzeugt. Das Vorgehen zur Erzeugung des 150%-Leitungssatzes wurden im Teilprojekt 2 beschrieben.

Diese Zusammensetzung des 150%-Leitungssatz ist also die datentechnische Ausgangsbasis, aus der sich die für die Herstellung notwendigen Prozesse ableiten lassen. So impliziert bspw. ein Crimpkontaktteil an einem Leitungsende den Prozess „Crimp“ oder eine Einzeladerabdichtung an einem Leitungsende den Prozess „Seal“. Mit einer derartigen Zuordnung von Prozessen entsteht dann die Bill of Process (BoP) [8].

Um einen Leitungssatz produktionsoptimiert herstellen zu können, wird neben der Zuweisung von Prozessen des 150%-Leitungssatzes beim Konfektionär eine Gliederung in Baugruppen durchgeführt, also in für die Produktion besser geeignete kleinere Einheiten. In den nachfolgenden Kapiteln wird anhand einer konkreten Baugruppe die *Abbildung* in einer Verwaltungsschale dargestellt. Die Baugruppe entspricht einer geschnittenen Einzelleitung mit Kontaktteilen auf beiden Seiten inklusive einer Einzelleitungsabdichtung (ELA) auf einer Seite (siehe *Abbildung* 3-51).

![image](https://github.com/user-attachments/assets/db82f567-c981-4134-8e5c-16aff78a7d71)    
*Abbildung 3-51: Baugruppe einer geschnittenen Einzelleitung mit Kontaktteilen inklusive ELA*

Die Prozesse, die zur Herstellung aller Module des 150% Leitungssatzes nötig sind, stellen also die Gesamtheit an benötigten Prozessfähigkeiten dar, die ein Leitungssatzkonfektionär bieten muss, um die Kabelsätze produzieren zu können. Enthält eine Baugruppe des Leitungssatzes bspw. einen Crimpkontakt an einer 4mm²-Leitung, so muss dies als Prozessfähigkeit (required capability) hervorgehen. Im Teilprojekt 5 wird das Fähigkeitenmodell inkl. Prozessfähigkeit detaillierter beschrieben, in Teilprojekt 6 die Verhandlungsprozesse.

##### Prozesssequenz anhand von Baugruppen

Die in Kapitel 1.5.1.1.1 beschriebene Beispielbaugruppe einer geschnittenen Einzelleitung mit Kontaktteilen auf beiden Seiten inklusive einer Einzelleitungsabdichtung (ELA) auf einer Seite weist durch die BoP bereits die zur Herstellung notwendigen Prozessen auf. Da einzelne Prozessarten (z.B. Strip) mehrfach auftreten können, wird der Prozessbezeichnung ein Zähler beigefügt (Strip01, Strip02, usw.):

-   Einzelleitung mit gewünschter Länge → Prozess „Cut01“
-   Abisoliertes Isolationsmaterials am Leitungsende, Seite 1 → Prozess „Strip01“
-   Abisoliertes Isolationsmaterials am Leitungsende, Seite 2 → Prozess „Strip02“
-   Aufgezogene Einzelleitungsabdichtung am Leitungsende 2 → Prozess „Seal01“
-   Angecrimptes Kontaktteil am Leitungsende 1 → Prozess „Crimp01“
-   Angecrimptes Kontaktteil am Leitungsende 2 → Prozess „Crimp02“

Die sich aus den Prozessen ergebende Prozesssequenz einer Baugruppe wird später in der AAS des Produktionsauftrages abgebildet inklusive der notwendigen Informationen, wie beispielsweise der Prozessparameter, zu den einzelnen Prozessen.

##### Struktur eines Produktionsauftrags

Für die Produktion werden Produktionsaufträge erstellt und – je nach Anforderung – in kleinere Produktionseinheiten aufgegliedert (vgl. *Abbildung* 3-52). Ein Produktionsauftrag beinhaltet allgemeine Kopfdaten:

-   Auftragsgröße
-   Auftragsstatus
-   Gesamtergebnis der Auftragsbearbeitung
-   Referenz auf den Produkttyp

Vom Produktionsauftrag wird auf Produktionslose verwiesen. Jedes Produktionslos besteht aus einer Teilmenge des Produktionsauftrags und beinhaltet Informationen über:

-   Losgröße
-   Status der Losabarbeitung

Jedes Produktionslos verweist wiederum auf Chargen. Jede Charge besteht aus einer Teilmenge eines Produktionsloses und beinhaltet Informationen über:

-   Chargen-Größe
-   Status der Chargenabarbeitung
-   Anzahl produzierter Einzelerzeugnisse

Zudem verweist jede Charge auf die ausgeführten Jobs der Produkt-Instanz.

Die eindeutige Identifikation der Produkte erfolgt dabei auf Chargenebene. Für Produkte, die nur als Bündel identifizierbar sind (bspw. Einzelleitung), ist die Chargengröße \>1. Für Produkte, die einzeln identifizierbar sind (bspw. Leitungssatz), ist die Chargengröße 1.

![image](https://github.com/user-attachments/assets/4a5b8422-a66c-45a4-92cf-f03e71f8b60f)    
Abbildung 3-52: Struktur eines Produktionsauftrags

#### Beispiele für Produktionsaufträge

##### Beispiel 1: Physische Unterteilung eines Produktionsauftrages in Transporteinheiten

Für die Produktion von Leitungen soll ein Produktionsauftrag mit einer Auftragsmenge von 1000 Stück hergestellt werden. Produktionsbedingt werden die Leitungen mit einer Bündelgröße von 10 hergestellt und in Kisten mit je 10 Bündeln verpackt.

Zunächst wird ein Produktionsauftrag mit einer Auftragsmenge von 1000 Stück erstellt. Für den Gesamtauftrag werden 10 Kisten benötigt, die in Form von Produktionslosen dem Produktionsauftrag zugeordnet werden.

Jedes Produktionslos besteht wiederum aus 10 Leitungsbündeln, die in Form von Chargen dem jeweiligen Produktionslos zugeordnet werden.

Der Produktionsauftrag wird an die Fertigung übergeben, wo die Produktionsmaschinen mit der Herstellung der Leitungen beginnen. Für jede Charge wird eine Produktinstanz erstellt, in der die Produktionsdaten hinterlegt sind und alle ausgeführten Jobs der Produktionsmaschinen dokumentiert werden. Für jede produzierte Leitung werden die Produktionsdaten in der Produktinstanz hinterlegt und mit der Charge verknüpft.

Sobald ein Leitungsbündel (eine Charge) fertiggestellt ist, wird dieses in der Kiste platziert. Wenn alle Leitungsbündel für eine Kiste (ein Los) hergestellt wurden, wird die Kiste auf die Palette gestellt. Sobald sich alle Kisten auf der Palette befinden, ist der Produktionsauftrag abgeschlossen.

##### Beispiel 2: Logische Unterteilung eines Produktionsauftrages auf mehrere Maschinen

Für die Produktion von Leitungen soll ein Produktionsauftrag mit einer Auftragsmenge von 1000 Stück hergestellt werden. Es erfolgt eine logische Unterteilung der Auftragsmenge zu je 200 Stück, die auf 5 gleichartigen Maschinen parallel produziert werden. Produktionsbedingt werden die Leitungen mit einer Bündelgröße von 20 hergestellt.

Zunächst wird ein Produktionsauftrag mit einer Auftragsmenge von 1000 Stück erstellt. Da dieser Produktionsauftrag auf 5 Maschinen ausgeführt wird, wird eine logische Unterteilung des Produktionsauftrages in 5 Batches zu je 200 Stück durchgeführt.

Jedes dieser Batches wird auf einer Maschine in 10 Produktionslosen hergestellt. Jedes Produktionslos wird in Form eines Leitungsbündels (Charge) zu je 20 Leitungen produziert. Jedes Leitungsbündel ist eindeutig identifizierbar (z.B. Barcode) und kann dem jeweiligen Produktionslos zugeordnet werden.

Der Produktionsauftrag wird an die Fertigung übergeben, wo die 5 Produktionsmaschinen mit der Herstellung der Leitungen beginnen. Für jedes Leitungsbündel (Charge) wird eine Produktinstanz erstellt, in der die Produktionsdaten hinterlegt sind und alle ausgeführten Jobs der Produktionsmaschinen dokumentiert werden. Für jede produzierte Leitung werden die Produktionsdaten in der Produktinstanz der zugehörigen Charge hinterlegt. Eine Charge ist identifizierbar (z.B. Barcode), während einzelne Leitungen nicht identifizierbar ist (kein Identifikationsmerkmal an der Leitung vorhanden). Der Produktionsauftrag ist abgeschlossen, wenn alle Batches auf allen Maschinen abgeschlossen sind.

#### Funktionsweise eines Produktionsablaufs

Grundsätzlich kann man zwischen einer Einzelteil- und einer Batchfertigung unterscheiden. Das SM ProductionOrder (Produktionsauftrag) beinhaltet hierfür die Möglichkeit über sog. BatchReferences eine Referenz auf ein zu fertigendes Batch (Batch01) zu setzen (*Abbildung* 3-53). An dieser Stelle ist es auch möglich den Produktionsauftrag in mehrere Batches (Batch01, Batch02, …) zu unterteilen.

![image](https://github.com/user-attachments/assets/a5b08228-4019-44ac-aac7-0fdafae44b51)    
*Abbildung 3-53: Submodel ProductionOrder*

Die oben beschriebene Referenz Batch01 zeigt nun auf eine Verwaltungsschale Batch01, die alle Informationen zu dem gefertigten Batch enthält (*Abbildung* 3-54). In der SMC LotReferences ist zu erkennen, dass ein Lot mit einer Referenz zu Lot01 gefertigt wurde.

![image](https://github.com/user-attachments/assets/ea7e292e-1b76-48a6-b4fd-a6cf4cbfa9dc)    
*Abbildung 3-54: AAS & Submodel Batch*

Die Referenz Lot01 zeigt auf die AAS Lot01, die alle Informationen zu dem gefertigten Lot enthält (*Abbildung* 3-56). Die AAS Lot01 enthält die beiden Submodels „Lot“ und „ExecutedProcesses“.

![image](https://github.com/user-attachments/assets/15976fb0-1c36-41d6-bc65-84e52596e4b4)    
*Abbildung 3-55: AAS Lot / Submodel Lot & Exectued Processes*

Das Submodel Lot beinhaltet zum Lot01 diverse Properties zum Lot und eine SMC RunReferences, die Referenzen zu einzelnen Runs (Run01, Run02, Run03) enthält. Das Submodel ExecutedProcesses enthält die einzelnen referenzierten Runs in Form von SMCs. Jeder einzelne Run beschreibt ein gefertigtes Produkt innerhalb des Lots inklusive aller Produktionsprozesse und dem RunResult. Die Produktionsprozesse und deren Parameter sind Bestandteil der Prozessliste aus AP3.3 und werden dort im Ergebnisdokument detailliert beschrieben.

![image](https://github.com/user-attachments/assets/37e3d2c4-dd58-4453-9430-c62568373b8a)    
*Abbildung 3-56: AAS & Submodel Lot*

Für eine Einzelteilfertigung wird ein Batch (Batch01) und in diesem Batch nur ein Lot (Lot01) verwendet. Im Lot01 definiert man für das Property „PlannedLotSize“ den Wert „1“, damit nur ein einzelnes Produkt für dieses Lot gefertigt wird. Somit lässt sich diese Struktur sowohl für Einzelteil- als auch Batchfertigung nutzen.

#### Ablaufsteuerung für parallel ausgeführte Prozesse

Das Teilmodell „Bill of Process“ (BoP) [8] spielt eine zentrale Rolle bei der Ablaufsteuerung parallel ausgeführter Prozesse. Es liefert die notwendigen Grundlagen für die jeweiligen auszuführenden Prozessschritte, wie beispielsweise *Cutting* oder *Crimping*. Diese Prozessbeschreibungen aus dem BoP-Teilmodell müssen in physikalische Prozesse umgewandelt werden, was eine automatische Transformation des BoP-Teilmodells in ausführbare Prozessmodelle erfordert.

Im allgemeinen Ablauf der Prozesssteuerung (siehe Kapitel 1.5.1.1) wird beschrieben, wie ausgehend von den im BoP-Teilmodell definierten Prozessschritten konkrete Arbeitsabläufe abgeleitet werden. Diese Abläufe werden durch eine detaillierte Planung und Analyse der benötigten Ressourcen, der Abhängigkeiten zwischen den Prozessschritten und der notwendigen Reihenfolge der Ausführung erstellt. Die hier beschriebenen Techniken und Methoden finden auch in der Ablaufsteuerung für parallele und sequenzielle Prozesse Anwendung.

Die Handhabung von parallelen und sequenziellen Prozessen erfordert eine präzise Koordination und Abstimmung der verschiedenen Prozessschritte. Diese Prozesse werden grundsätzlich in Form eines BPMN-Diagramms (Business Process Model and Notation) abgebildet und für eine leichtere Handhabung visualisiert wie in *Abbildung* 3-57 dargestellt. Das Ziel ist es, auf dem bestehenden BoP-Teilmodell aufzubauen und dieses als Basis für das Zielbild der Digitalisierung mittels BPMN zu verwenden.

![image](https://github.com/user-attachments/assets/e4f086bb-8a88-4ed5-8d1f-b1cad73ef6cd)    
*Abbildung 3-57: Überwachung des Schraubprozesses mit parallel abgearbeiteten Aufgaben*

Die Modellierung des Prozesses mithilfe von BPMN beschreibt die einzelnen Prozessschritte zunächst Abstract. Diese jeweiligen Arbeitsschritte werden durch eingehende und ausgehende „Flows“ verbunden. Konnektoren wie Parallel- oder Exklusiv-Gateways verbinden mehrere Prozessschritte und ermöglichen die Steuerung des Ablaufs.

1.  **Parallele Prozesse:** Müssen aufeinander abgestimmt werden. Beispielsweise darf die Überwachung erst enden, sobald alle parallellaufenden Prozesse abgeschlossen sind. Hierfür sind spezielle Koordinationsmechanismen erforderlich als Teil der Implementierung der Ausführungslogik der jeweiligen Schritte notwendig.
2.  **Sequenzielle Prozesse:** Diese Prozesse folgen einer definierten Reihenfolge. In diesem Fall muss die Reihenfolge vordefiniert und strikt eingehalten werden.

Im Projekt VWS4LS werden Prozessschritte im digitalen Zwilling abgebildet und koordiniert. Dazu werden alle Schritte automatisiert mit Operationen der Verwaltungsschale verknüpft. Dies erfolgt über dynamisch festgelegte Schlüssel, welche auf Verhandlungsprozesse aus Teilprojekt 6 aufbauen sollen, um entsprechende Geräte und Aufgaben dynamisch verbinden zu können.

Zusätzlich werden manuelle Teilschritte, etwa für Eingaben von Werkern, mit abgebildet. Dadurch kann etwa, wie in *Abbildung* 3-57 dargestellt, eine Abfrage zur Position durch den Werker behandelt werden. Automatisierte Teilschritte beinhalten Aufgaben für einen bestimmten Teilprozess wie etwa die Steuerung von Maschinen. Dabei handelt es sich um „Microservices“, welche vorher zentrale Services wie ein Manufacturing-Execution-System (MES) ersetzen und die jeweiligen Geräte mit mehr „Intelligenz“ ausstatten. Alle Prozessschritte werden automatisch angesteuert und besitzen einen Automatismus, um eine erfolgreiche (oder auch fehlerhafte) Beendigung des Schrittes zu dokumentieren und darüber zu informieren.

Parallele Prozesse benötigen zusätzliche Events zur Koordination mit den anderen Prozessen. Diese Events sorgen dafür, dass alle parallellaufenden Prozesse synchronisiert sind und korrekt abgeschlossen werden können

Der Prozess selbst wird durch das Anlegen eines neuen Auftrags gestartet. Dieses führt zu einem Event, welches von einem weiteren Service erkannt wird. Ein Beispiel zur Veranschaulichung ist ein Rundtakter, der Prozessschritte nur in einer bestimmten Reihenfolge abarbeiten kann. In diesem Fall muss die Reihenfolge im Vorfeld genau definiert sein, um einen reibungslosen Ablauf zu gewährleisten.

#### Technische Beschreibung der Prozesssteuerung

In der entwickelten prototypischen Erweiterung von [Eclipse BaSyx](https://github.com/VWS4LS/vws4ls-process-service) werden neben dem standardmäßig eingesetzten MQTT-Broker als Event-Mechanismus und der open-source BPMN-Engine Zeebe ([CAMUNDA](https://github.com/camunda)) auch zwei weitere Services, einer „ProcessFactory“, um den Prozess als dynamisches Element in Verbindung mit den Ergebnissen der Verhandlungen aus TP6 verfügbar zu machen und zu starten, und einem „WorkerManager“, um alle notwendigen Operationen der Geräte-Zwillinge (inklusive der virtuellen Geräte-Zusammenschlüssen) mit einem ausführbaren „Worker“ zu versehen. *Abbildung* 3-58 zeigt die dazugehörige Software-Architektur und die Interaktionen der verschiedenen Services.

![image](https://github.com/user-attachments/assets/3f6b9581-c995-45a4-ba46-dda5421fd448)    
Abbildung 3-58: Architektur der Prozesssteuerung

Um ein Beispiel-Szenario auszuführen, müssen zunächst die notwendigen Services auf Basis von Eclipse BaSyx erstellt werden. Im Projekt geschieht das im Rahmen von Docker-Images und dadurch Containern, die nach Ausführung alle Services der ProcessFactory und des WorkerManager verfügbar machen. Technisch wird zum Starten eines Prozesses über das Eventing-System eine „*deploy_operation*“ Nachricht versendet, welches alle registrierten Verwaltungsschalen nach ausführbaren Prozessen durchsucht und jeweils eine Start-Operation zum jeweiligen Teilmodell hinzufügt. Dadurch wird sichergestellt, dass nur beschriebene Prozesse im System ausgeführt werden können, aber auch Änderungen (inkl. Erstellen von neuen und Löschen von existierenden) an Prozessen durchgeführt werden können.

Gleichzeitig gibt es eine „*update_skills*“ Nachricht, welche die Worker alle Geräte aktualisiert und entsprechende Verknüpfungen zwischen der Prozess-Engine Zeebe und der Verwaltungsschale herstellt. Dies ist die Grundlage, um die Prozessschritte automatisiert ausführen zu können, da durch Zeebe automatisch die jeweiligen Worker zu bestimmten Schritten angesteuert werden.

##### ProcessFactory

Die *ProcessFactory* als eigenständiger Service erfüllt die Aufgabe Prozesse aus Verwaltungsschalen zu erkennen und in der Verwaltungsschalenumgebung ausführbar zu machen. *Abbildung* 3-59 zeigt das dazugehörige Sequenzdiagramm und die Interaktion mit den BaSyx-Core-Services und der BPMN Engine selbst. So wird aus dem Digitalen Zwilling ein BPMN-Prozess-Template ausgelesen, welches zuvor aus dem BOP-Teilmodell definiert wurde, während eine *deployProcess*-Operation hinzugefügt wird, um den jeweiligen Prozess zu starten. Sobald ein Nutzer die entsprechende Operation, etwa wie im Demonstrator über das Interface des MES-Systems, startet, wird eine Instanz des Prozesses in der BPMN-Engine registriert und gestartet. Dieser Prozess greift automatisiert auf die Operationen der Geräte/Ressourcen-Verwaltungsschalen in Eclipse BaSyx über den *WorkerManager* zu.

![image](https://github.com/user-attachments/assets/700b544d-41d9-4502-a0c6-d647743475ad)    
Abbildung 3-59: ProcessFactory Sequenzdiagramm

Aktualisierungen der Prozesse können durch eine erneute Nachricht zum Remapping der vorhandenen Prozesse angesteuert werden.

##### WorkerManager

Der WorkerManager, ähnlich zur ProcessFactory, ist ein zunächst autonomer Service auf Basis der Verwaltungsschale und der BPMN-Engine. *Abbildung* 3-60 zeigt auch hier ein Sequenzdiagramm zur Funktionalität des Services. Gleich zur ProcessFactory wird durch ein Event, welches automatisiert, aber auch manuell angesteuert werden kann, aus allen in BaSyx registrierten Verwaltungsschalen von Ressourcen, sofern vorhanden, ausführbare Operationen für potentielle Arbeitsschritte extrahiert. Zu jeder Operation wird automatisch ein Worker in der BPMN-Engine registriert, um nach Prozessstart automatisch die Ressource anzusteuern.

![image](https://github.com/user-attachments/assets/a5e515ad-0d97-4e6a-abbc-dd181b2f8763)    
Abbildung 3-60: WorkerManager Sequenzdiagramm

### <a name="_3.5.2"></aDatenmapping mit Validierung

Quellsysteme im Shopfloor (z.B. Produktionsanlagen) liefern Daten unterschiedlich strukturiert, d.h. es kann sich um un- bzw. semi- strukturierte Daten handeln. Um die Konvertierung zwischen Strukturen und einem digitalen Datenthread zu gewährleisten, ist eine Validierung und ein eventuell notwendiges Mapping zwingend erforderlich. Die Validierung muss in verschiedenen Schritten der Datenerhebung und Datenverarbeitung durchgeführt werden.

Die Ziele des generischen Ansatzes für die Validierung mit Datenmapping:

-   Konvertierung von un- bzw. semi-strukturierten Daten
-   Vermeidung inkonsistenter Daten
-   Unterbrechungen im Datenfluss verhindern
-   Strukturelle Veränderungen erkennen
-   Vermeidung unvollständiger Daten
-   Steigerung der Datenqualität
-   Reduzierung des manuellen Aufwands

Die Validierung betrachtet nicht den Content der Daten.

### <a name="_3.5.3"></a>Micro-Service „Datenvalidierung“

Der Validierungsdienst ist als REST-Service mit Patch-Endpunkt implementiert. Der Service benötigt eine JSON-Datei als Input. Das JSON wird validiert und als Ergebnis wird ein serialisiertes JSON-Objekt zurückgegeben.

Die *Abbildung* 3-61: Testszenario Validation Service zeigt den Aufbau des Testszenarios.

![image](https://github.com/user-attachments/assets/9b18636f-90b7-4f9d-a5ac-ffb086931fd4)    
Abbildung 3-61: Testszenario Validation Service

**Input***: JSON-Datei eines Schraubprozesses*

**Returns***:* Der Dienstaufruf wird mit [HTTP-Statuscode](https://de.wikipedia.org/wiki/HTTP-Statuscode) 200 oder 404 zurückgeben. Wenn der Validierungsdienst erfolgreich ausgeführt wird, gibt der Dienst eine JSON-Zeichenkette mit den Ergebnissen zurück, ansonsten einen Fehlermeldungstext.

Beispiel 1 (Validierung mit positiven Ergebnis):

````{"resultValue":true, "valueType":"boolean","message":" "}````

In der JSON-Zeichenkette ist der resultValue true, wenn die Validierung erfolgreich war. Der Wert von *valueType* ist per default *Boolean*. Die message ist leer, wenn der Dienst erfolgreich ausgeführt wurde

Beispiel 2 (Validierung mit negativen Ergebnis):

````{"resultValue":false,"valueType":"boolean","message":"\$.sealing_30091.ProcessData.MaterialPressure.AV: boolean found, string expected "}````

Die Validierung schlägt fehl, weil die JSON-Datei nicht mit dem JSON-Schema übereinstimmt. Der Dienst gibt ebenfalls 200 (HTTP_OK) zurück. Der Parameter "*resultValue*" liefert *false* zurück. Im Attribut "*message*" wird die Fehlermeldung des Validierungsdienstes angezeigt.

Beispiel 3 (Semantic ID wird nicht gefunden):

````{"The semantic id semantic4567 is not found."}````

Wenn der Dienst mit einer nicht bekannten Semantic ID fehlschlägt, gibt der Dienst 404 mit einer Fehlermeldung zurück.

Der Source Code des Web-Services und eine Installationsanleitung ist abgelegt unter <https://github.com/VWS4LS/vws4ls-data-validation/>.

### <a name="_3.5.4"></a>Traceability

Die Rückverfolgbarkeit aller Aspekte des Leitungssatzes sind ein elementarer Bestandteil der Leitungssatzentwicklung und -produktion. Im Architekturkapitel „Rückverfolgbarkeit“ werden die Konzepte und Use Cases ausführlich beschrieben. Es wird auch auf die Einhaltung gesetzlicher Aufbewahrungsfristen sowie die Datenvorhaltung eingegangen.

### <a name="_3.5.5"></a> Transfer in andere Produktserien

#### Coroplast

Coroplast ist auf die Herstellung von technischen Klebebändern, Kabeln und Leitungen oder Leitungssätze spezialisiert. Zur Validierung der in dieser Arbeit vorgestellten Prinzipien soll der Prozess der Kabelherstellung dargestellt werden. Dabei soll vor allem überprüft werden, inwieweit dieses Konzept in der Praxis anwendbar ist. Der zu bewertende Anwendungsfall befasst sich mit der Bereitstellung und Produktion der Materialien, die für die Herstellung eines Kabels erforderlich sind.

Wie in *Abbildung* 162zu sehen ist, kann das Produkt Kupfer von einem unserer Lieferanten bezogen werden, während das Silikon auf unseren Maschinen hergestellt wird. Aus diesem Grund wird das Silikonprodukt als Typ dargestellt, während das Kupfer durch die Daten des Lieferanten dargestellt wird. Für die Herstellung des Kabels ist es im nächsten Schritt notwendig, das Silikon auf das Kupfer zu extrudieren. Des Weiteren ist zu erkennen, dass das Kabelprodukt aus Silikon und Kupfer besteht und als Typ definiert ist, wobei die Materialien in der Stückliste beschrieben werden.

![image](https://github.com/user-attachments/assets/400dc830-eca9-4c5e-b3dd-219355d96d48)    
*Abbildung 3-62: Repräsentation des Kabelherstellungsprozesses*

Um mit der Validierung der Prinzipien fortzufahren, werden im Folgenden die Konzepte im Ökosystem Verwaltungsschale dargestellt. *Abbildung* 163, zeigt die Darstellung der wichtigsten Materialien, wobei Kabel und Silikon, wie sie von Coroplast hergestellt werden, direkt als "Typ"-Produkte dargestellt werden. Andererseits ist zu erkennen, dass der Werkstoff Kupfer, da er nicht von Coroplast hergestellt wird, aus zwei Teilmodellen besteht: technische Informationen und Lieferantendaten. Darüber hinaus ist jeder Ressource eine Verwaltungsschale zugeordnet, wie z.B. bei der Knetmaschine und der Extrusionsmaschine, die durch die technischen Spezifikationen und die Kapazitäten der jeweiligen Maschine dargestellt werden.

![image](https://github.com/user-attachments/assets/1a032c94-f3a4-49b3-b045-17ff14ea7db8)    
*Abbildung 3-63: Repräsentation des Kabelherstellungsprozesses in der VWS*

##### Prototypische Implementierung zur Konzeptvalidierung

Um das Konzept weiter zu validieren, haben wir eine prototypische Implementierung vorgenommen. *Abbildung* 464 zeigt die Architektur zur Konzeptvalidierung. Für die Darstellung und Speicherung der Verwaltungsschalen nutzen wir die Implementierung des Fraunhofer-Instituts namens BaSyx. Die BaSyx-Implementierung umfasst eine Reihe von essenziellen Services, die zusammen ein leistungsfähiges Ökosystem für die Industrie 4.0 bilden. Im Zentrum steht der *aas-env* Service, der als Asset Administration Shell Environment fungiert und die grundlegende Infrastruktur für die Verwaltung digitaler Zwillinge bereitstellt. Ergänzend dazu operiert der *aas-registry* Service als Asset Administration Shell Registry, der die Registrierung und das Auffinden von Asset Administration Shells ermöglicht. Für die Verwaltung von Submodellen ist der *sm-registry* Service zuständig, der als Submodel Registry dient. Um die Auffindbarkeit von Asset Administration Shells zu gewährleisten, kommt der *aas-discovery* Service zum Einsatz. Abgerundet wird das Serviceportfolio durch die aas-web-ui, eine Asset Administration Shell Web User Interface, die eine benutzerfreundliche Oberfläche für die Interaktion mit den verschiedenen BaSyx-Komponenten bietet. Diese Services arbeiten nahtlos zusammen, um eine umfassende Lösung für die digitale Repräsentation und Verwaltung von industriellen Assets im Kontext der Industrie 4.0 zu schaffen.

Zur persistenten Speicherung der Daten wird eine MongoDB eingesetzt. Diese NoSQL-Datenbank bietet die nötige Flexibilität und Skalierbarkeit für die Verwaltung der komplexen Strukturen der VWS.

Die VWS werden mittels eines Python-Scripts unter Verwendung des basyx-python-sdk Packages erstellt. Der Prozess läuft wie folgt ab:

-   Erstellung der VWS durch das Python-Script
-   Serialisierung der VWS in JSON-Dateien
-   Übertragung der serialisierten Daten über die Web-API des aas-env Service von BaSyx

Anschließend können die Daten über die aas-web-ui betrachtet und evaluiert werden.

Die Quellen für die Daten in unserem System sind vielfältig. In der prototypischen Implementierung werden Daten primär aus zwei Quellen bezogen:

-   OPC-UA-Protokoll
-   Maschinendatenbank

Für Testzwecke und zur Vereinfachung werden in unserem Prototyp Daten durch das Python-Script simuliert und erstellt.

![image](https://github.com/user-attachments/assets/e5e900ee-fed7-4490-903f-c33c2f1911b0)    
*Abbildung 3-64: Architektur für die Konzeptvalidierung*


##### Anwendungsbeispiel 1

Durch Erstellung einer Order mit verzeigertem Batch mit verzeigertem Lot mit Verweisen auf ein erstelltes Produkt wurde prototypisch die Produktionsplanung und das Speichern der Ergebnisse simuliert. Alle Produktionsschritte sind geloggt und im Lot in den Runs hinterlegt. *Abbildung* 3-67 zeigt, wie die VWS vom Lot in BaSyx aussieht. Hier ist eine Referenz auf eine VWS mit Informationen des entsprechenden Batchs zu finden. Theoretisch können hier beliebig viele Batches hinterlegt sein. In der *Abbildung* 3-66 ist eine VWS mit dem Batch zu sehen, in welchem wiederrum ein Verweis auf das Lot zu finden ist. Die *Abbildung* 3-67 zeigt das Lot mit einem Submodell für allgemeine Informationen, aber auch ein Submodell für die Runs. In Jedem Run sind alle Prozess-Steps abgebildet, die sich auch in dem Typ wiederfinden, aber nun mit realen Werten aus der Produktion.

![image](https://github.com/user-attachments/assets/fa065a91-2b14-43d5-acfd-9600676a125f)    
*Abbildung 3-65: Darstellung des Produktionsauftrags in BaSyx*

![image](https://github.com/user-attachments/assets/bc1eb74d-7ceb-42bc-99d5-eaccf454a03d)    
*Abbildung 3-66: Darstellung des Batchs in BaSyx*

![image](https://github.com/user-attachments/assets/35a7cadb-3721-417c-a5c4-e0e253c6d4fa)    
*Abbildung 3-67: Darstellung des Lots in BaSyx*

##### Anwendungsbeispiel 2

Im zweiten Anwendungsbeispiel haben wir die Rückverfolgbarkeit über mehrere Lots hinweg simuliert. Dafür haben wir die Produktion von einem Kabel, wie in *Abbildung* 3-68 zu finden, realisiert. Entscheidend dafür sind zwei Lots. Eines, dass die Prozessschritte beinhaltet, die zur Herstellung von dem Silikon benötigt wurden. Der Einfachheit halber ist das hier mit einem Schritt dargestellt.

![image](https://github.com/user-attachments/assets/1c5a2491-627c-4e12-b665-20201d78c9cd)    
*Abbildung 3-68: Darstellung des Lots zur Kabelproduktion*

In der *Abbildung* 3-69 ist zu sehen, wir wie aus dem Silikon und einer weiteren Komponente schließlich ein Kabel hergestellt wurde. Informationen zur Chargennummer sind in der VWS von dem Produkt zu finden.

![image](https://github.com/user-attachments/assets/8dbf06a0-380e-4816-8acb-54310f46f856)    
*Abbildung 3-69: Darstellung des Lots zur Silikonproduktion*

Stellt ein Nutzer also fest, dass bei seinem Kabel das Silikon gebrochen ist, so kann er die Chargennummer davon beim Hersteller angeben. Dieser kann schauen in welchem Lot dieses Kabel produziert wurde und anschließend die Chargennummer des Silikons herausfinden, dass verwendet wurde. Sobald diese bekannt ist, kann herausgefunden werden in welchem Lot das Silikon produziert wurde. Hier findet er alle relevanten Daten in den Prozessschritten, um nachvollziehen zu können, wie es zu der Schwäche im Material kam. Z.B. kann festgestellt werden, dass die Temperatur, während der Knetzeit lange zu hoch war, oder es kann aufgeklärt werden, dass die Materialschwäche aufgrund von fehlerhaften Komponenten entstanden ist.

##### Zusammenfassung und Ausblick

Diese prototypische Implementierung ermöglicht es uns, die Funktionalität und Effizienz des Konzepts in einer realitätsnahen Umgebung zu testen. Durch die Verwendung von BaSyx und standardisierten Protokollen wie OPC-UA stellen wir sicher, dass unser System interoperabel und zukunftssicher ist. Die Flexibilität bei den Datenquellen erlaubt eine einfache Integration in bestehende Produktionsumgebungen.

#### KOSTAL

KOSTAL Kontakt Systeme ist auf die Entwicklung und Produktion von Steckverbindern spezialisiert. Zur Validierung der in dieser Arbeit vorgestellten Prinzipien soll der Prozess der Steckverbinderherstellung dargestellt werden. Dabei soll vor allem überprüft werden, inwieweit dieses Konzept in der Praxis anwendbar ist.

Der zu bewertende Anwendungsfall befasst sich mit der Bereitstellung und Produktion der Materialien, die für die Herstellung eines Kontaktes erforderlich sind.

Wie in *Abbildung* 3-70 zu sehen ist, werden die Bänder für den Grundkörper und für die Lamelle meist von verschiedenen Lieferanten bezogen.

Für die Herstellung des Kontaktes ist es im nächsten Schritt notwendig, die Lamelle und den Grundkörper aus dem Band umzuformen sowie beide zusammen zu fügen. Beide Materialien sind in der Stückliste eindeutig beschrieben.

![image](https://github.com/user-attachments/assets/78fda7dc-6334-4053-9889-d4c6985174f4)    
*Abbildung 3-70: Repräsentation des Kabelherstellungsprozesses*

Um mit der Validierung der Prinzipien fortzufahren, werden im Folgenden die Konzepte im Ökosystem Verwaltungsschale dargestellt. Nachfolgend sind die wichtigsten Materialien aufgelistet, wobei von den Lieferanten der Bänder nur die technischen Informationen und Lieferantendaten übermittelt werden.

Product Contact

-   Asset Information
-   Manufacturing BOM
-   Bill Of Processs (routing)
-   Manufacturing Capabilities

    Product Strip Body

-   Asset Information
-   Supplier Information
-   Technical Data

    Production Order

-   Material Number + Revision Level + Charge
-   Routing Specification
-   Single Materials
-   Equipment
-   Packaging

Darüber hinaus ist die Ressource der Verwaltungsschale zugeordnet, die durch die technischen Spezifikationen und die Kapazitäten der jeweiligen Maschine dargestellt werden (PPS-Fertigungsauftrag, siehe *Abbildung* 3-71).

![image](https://github.com/user-attachments/assets/0abfa3f1-725d-46fe-881c-73a2db590b30)    
*Abbildung 3-71: Repräsentation des PPS-Fertigungsauftrages*

Das Mapping eines Fertigungsauftrags in eine AAS wird in *Abbildung* 3-72 schematisch dargestellt. Es wird gezeigt an welchen Stellen die einzelnen Bestandteile eines Fertigungsauftrags im pdf-Format in einer AAS („[KKS_Product_TERMINAL_SLK2.8_Type.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/AP3.5/KKS_Product_TERMINAL_SLK2.8_Type.aasx)“[^12]) hinterlegt sind.

[^12]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP03/AP3.5/KKS_Product_TERMINAL_SLK2.8_Type.aasx>

![image](https://github.com/user-attachments/assets/60078257-6df0-44ea-906d-83be1d10945f)    
*Abbildung 3-72: Mapping der Daten eines beispielhaften Fertigungsauftrags in die VWS*

![image](https://github.com/user-attachments/assets/fd46c5e7-9181-4f48-8ad6-c4f857f14bb0)    
*Abbildung 3-73: Repräsentation des Steckers (Terminal) der Verwaltungsschale*

## <a name="_3.6"></a>Fazit

Im Rahmen des TP3 wurden verschiedene Aspekte beleuchtet, um die Produktionsprozesse für Leitungssätze zu automatisieren. Ein wichtiger Grundstein wurde mit der Prozessliste gelegt, die an verschiedenen Stellen im Gesamtprojekt genutzt werden konnte, um erstens eine Sammlung aller identifizierenten Prozesse in einer konsolidierten Liste und zweitens gemeinsam mit den dazugehörigen Parameter in feingranularer Form für eine potenzielle Automatisierung zu haben.

Auf dieser Grundlage wurde anschließend ein Referenzmodell für die Produktionsprozesse erstellt und das VWS-Teilmodell „Bill of Process“ entwickelt sowie seine Anwendung beispielhaft demonstriert. Das Teilmodell enthält alle wesentlichen Strukturen, um die erforderlichen Daten aus dem Teilmodell auszulesen (z.B. Maschinenparameter) bzw. zurückzumelden (z.B. Prozessstatus). Somit dient es als zentrale Datendrehscheibe für alle Produktionsprozesse.

Ein weiterer wichtiger Baustein konnte mit der Entwicklung eines Data Mapping und Validation Service erreicht werden. Der Data Mapping Service stellt sicher, dass die Kompatibilität zwischen bestehenden Systemlandschaften und der VWS besteht, um in beide Richtungen kommunizieren zu können. Hierzu benötigt man einen Validation Service, um bspw. Namen, die Struktur und den Datentyp zu validieren, bevor Daten in die Ziel-VWS geschrieben werden. Im Ergebnis trägt dieser Service zur Vermeidung unvollständiger Daten, zur Steigerung der Datenqualität und zur Reduzierung des manuellen Aufwands bei.

Die Ergebnisse aus TP3 wurden abschließend validiert. An dieser Stelle stand die Anwendung der entwickelten Prinzipien für reale Anwendungsfälle im Vordergrund. Es konnte dadurch bspw. gezeigt werden, dass das „Bill of Process“ Teilmodell nicht nur für die Leitungssatzproduktion Anwendung finden kann, sondern auch bei der Produktherstellung von Zulieferteilen. Hierdurch konnte nachgewiesen werden, dass das Teilmodell eine generelle Anwendungsmöglichkeit für Prozesse in der Produktherstellung bietet.

## <a name="_3.7"></a>Anhang: UML-Diagramm

![image](https://github.com/user-attachments/assets/8ef9e761-03a0-46ab-963f-c0485297fe79)

![image](https://github.com/user-attachments/assets/6977bd31-a92a-4e57-9427-824c1f1d7177)

![image](https://github.com/user-attachments/assets/82396890-7d66-40c4-aebd-857eee399d49)

![image](https://github.com/user-attachments/assets/c9902679-bfb2-43e2-b7d8-d2e899ed5d48)

![image](https://github.com/user-attachments/assets/15f0d866-359c-466e-98e7-eb15b1e5cc84)

# Literaturverzeichnis

|-------|--------------------------------------------------------------------------------|
| [1]   | „ETL-Prozess,“ [Online]. Available: https://de.wikipedia.org/wiki/ETL-Prozess. |
| [2]   | Prostep ivip, „Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.                                                                                                                                                                                                                                      |
| [3]   | Prostep ivip, „ECAD-Wiki,“ 2023. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v202/component-characteristics/geometric-properties-of-connector-housings-definitions/. [Zugriff am 01 6 2023].                                                                                                                                                                        |
| [4]   | OPC Foundation, „OPC 10000-210: Industrial automation - Relative Spatial Location,“ 2023. [Online]. Available: https://reference.opcfoundation.org/RSL/v100/docs/.                                                                                                                                                                                                                            |
| [5]   | ECLASS e.V., „ECLASS-Standard,“ [Online]. Available: https://eclass.eu/eclass-standard/content-suche/search.                                                                                                                                                                                                                                                                                  |
| [6]   | ECLASS e.V., „Technical Specification Conceptual Data Model,“ 2020. [Online]. Available: https://eclass.eu/fileadmin/Redaktion/pdf-Dateien/Wiki/ECLASS_Technical-Specification_11_Conceptual-Data-Model_v_1.0.pdf.                                                                                                                                                                            |
| [7]   | OPC Foundation, „OPC 40570: OPC UA for the Wire Harness Manufacturing Industry,“ https://profiles.opcfoundation.org/workinggroup/88, WiP. [Online]. Available: https://profiles.opcfoundation.org/document/214.                                                                                                                                                                               |
| [8]   | Industrial Digital Twin Association e.V., „IDTA 02031-1-0 Bill of Process (WiP),“ [Online]. Available: https://industrialdigitaltwin.org/content-hub/teilmodelle.                                                                                                                                                                                                                             |
| [9]   | C. Diedrich, A. Belyaev, R. Blumenfeld, J. Bock, S. Grimm, J. Hermann, T. Klausmann, A. Köcher, M. Maurmaier, K. Meixner, J. Peschke, M. Schleipen, S. Schmitt, B. Schnebel, G. Stephan, M. Volkmann, A. Wannagat, K. Watson, M. Winter und P. Zimmermann, „Information Model for Capabilities, Skills & Services,“ 2022. [Online]. Available: http://dx.doi.org/10.13140/RG.2.2.30098.53440. |
| [10]  | Plattform Industrie 4.0, „Capabilities, Skills, Services,“ 11 2022. [Online]. Available: https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/CapabilitiesSkillsServices.pdf?.                                                                                                                                                                                                  |
| [11]  | ISO/IEC, „ISO/IEC 19510:2013: Business Process Model and Notation (BPMN),“ [Online]. Available: https://www.iso.org/standard/62652.html.                                                                                                                                                                                                                                                      |
