# TP 5 - Integration von Verwaltungsschalen (Verbundkomponente)

## Inhalt

[Zielsetzung](#zielsetzung)

[AP 5.1 - Anforderungsdefinition](#ap-51---anforderungsdefinition)

[1.1.1 Allgemeine Anforderungen](#_Toc178820017)

[1.1.2 Verbundkomponenten für den Kabelbaum (AP5.2)](#_Toc178820018)

[1.1.3 Verbundkomponenten Produktionsmittel (AP5.3)](#_Toc178820019)

[1.1.4 Integration der Verwaltungsschalen (AP5.4)](#_Toc178820020)

[1.1.5 Mapping zwischen Produktionsressource und Leitungssatz (AP5.5)](#_Toc178820021)

[1.1.6 Erfassung der Qualitätsdaten (AP5.6)](#_Toc178820022)

[AP 5.2 - Verbundkomponente Produkt (Leitungssatz)](#ap-52---verbundkomponente-produkt-leitungssatz)

[1.2.1 Zielsetzung](#_Toc178820024)

[1.2.2 Ermittelte Beziehungen](#_Toc178820025)

[1.2.3 Typisierte Beziehungen und Merkmalsfestlegungen](#_Toc178820026)

[1.2.4 Umsetzung der ermittelten Beziehungen](#_Toc178820027)

[AP 5.3 - Verbundkomponente Ressource (Produktionsmittel) und VIBN](#_Toc178820028)

[1.3.1 Zielsetzung](#_Toc178820029)

[1.3.2 Beispiel-Ressourcen](#_Toc178820030)

[1.3.3 Betrachtete Use Cases](#_Toc178820031)

[1.3.4 Konzept der Verbundkomponente „Ressource“](#_Toc178820032)

[1.3.5 Virtuelle Inbetriebnahme](#_Toc178820033)

[1.3.6 Ausblick](#_Toc178820034)

[AP 5.4 - Integration der Verwaltungsschalen](#_Toc178820035)

[1.4.1 Zielsetzung](#_Toc178820036)

[1.4.2 Definition und Umsetzung der Use Cases](#_Toc178820037)

[AP 5.5 - Mapping zwischen Produktionsressource und Leitungssatz](#_Toc178820038)

[1.5.1 Zielsetzung](#_Toc178820039)

[1.5.2 Modellierung geforderter Fähigkeiten](#_Toc178820040)

[1.5.3 Modellierung angebotener Fähigkeiten](#_Toc178820041)

[1.5.4 Algorithmus zum Fähigkeitenabgleich](#_Toc178820042)

[1.5.5 Anbindung von Skills](#_Toc178820043)

[1.5.6 Anhang: Liste von Fähigkeiten und zugehörigen Parametern](#_Toc178820044)

[AP 5.6 - Erfassung von Qualitätsdaten](#ap-56---erfassung-von-qualit%C3%A4tsdaten)

[1.6.1 Zielsetzung](#_Toc178820046)

[1.6.2 Relevante Teilmodelle](#_Toc178820047)

[1.6.3 Zusammenspiel der verschiedenen Teilmodelle](#_Toc178820048)

[1.6.4 Prototypische Implementierung](#_Toc178820049)

[1.7 Fazit](#_Toc178820050)

[Literaturverzeichnis](#_Toc178820051)

[Abbildungsverzeichnis](#_Toc178820052)

# **TP5 - Integration der Verwaltungsschale**
## Zielsetzung

Im Teilprojekt 5 "Integration von Verwaltungsschalen (Verbundkomponente)" wurden ausgehend vom Prinzip der Verbundkomponente der Plattform Industrie 4.0 [1] [2], Umsetzungskonzepte zu definieren, wie die Verwaltungsschale einer Teilkomponente, z.B. Steckverbinder, in die Verwaltungsschale des gesamten Leitungssatz einfließt („Matroschka-Prinzip“).

Das Teilprojekt wurde in folgende Arbeitspakete aufgeteilt, deren Resultate in diesem Dokument zusammenfassend erläutert werden:

-   [AP 5.1 - Anforderungsdefinition](#ap-51---anforderungsdefinition)
-   [AP 5.2 - Verbundkomponente Produkt (Leitungssatz)](#ap-52---verbundkomponente-produkt-leitungssatz)
-   AP 5.3 – Verbundkomponente Ressource (Produktionsmittel) und VIBN
-   AP 5.4 – Integration der Verwaltungsschalen
-   AP 5.5 – Mapping zwischen Produktionsressource und Leitungssatz
-   [AP 5.6 - Erfassung von Qualitätsdaten](#ap-56---erfassung-von-qualit%C3%A4tsdaten)

## AP 5.1 - Anforderungsdefinition

Im AP 5.1 wurden die Anforderungen an das TP5 „Integration von Verwaltungsschalen“ auf Basis des PPR-Konzepts ermittelt.

Die Anforderungen wurden auf Basis einer Workshop-Reihe ermittelt, um ein gemeinsames Verständnis für den Fokus und Inhalt von TP5 zu erlangen. Das Ziel der Anforderungen ist es, sicherzustellen, dass das Teilprojekt gemäß den Bedürfnissen und Erwartungen aller Beteiligten geplant und umgesetzt wird. Sie sollen als Leitfaden für das gesamte Teilprojekt dienen und eine erfolgreiche Umsetzung gewährleisten.

Die Workshops wurden auf Basis des PPR-Konzepts durchgeführt, um sicherzustellen, dass keine für die Integration von Verwaltungsschalen relevanten Beziehungen und Anforderungen übersehen werden. Das Ergebnis der Workshops ist [Abbildung 1-1](#Abbildung-1-1) in zu sehen.

![image](https://github.com/user-attachments/assets/bce32381-c038-4483-83d2-75d362df7a45)

<a name="Abbildung-1-1"></a>*Abbildung 1-1: Ergebnis der Workshop-Reihe*

Die Workshop-Ergebnisse wurden anschließend in einem strukturierten Prozess in Anforderungen überführt und den jeweiligen Arbeitspaketen innerhalb von TP5 zugeordnet. Zu jeder Anforderung wurden darüber hinaus sogenannte „Definitions of Done“ (DoDs) formuliert, die die Überprüfbarkeit der Erfüllung einer Anforderung gewährleisten. Einen weiteren wichtigen Punkt stellte die Identifikation von Schnittstellen zu anderen Teilprojekten bzw. Arbeitsgruppen statt. Da im Rahmen von TP5 Verwaltungsschalen vorgelagerter Teilprojekte integriert werden, beschreiben diese Schnittstellen vor allem Randbedingungen an die Arbeit dieser anderen TPs.

Im Folgenden sind die einzelnen Anforderungen inklusive DoD sowie identifizierter Schnittstellen aufgeführt.

### Allgemeine Anforderungen

#### Gesamtarchitektur

1.  Kopplung bzw. Integration von Verwaltungsschalen mit anderen Tools

Es muss definiert werden, wie bzw. ob die Verwaltungsschalen im Projekt mit anderen Tools gekoppelt/integriert werden (z.B. Anbindung MES, OPC UA-Server, etc.) oder ob die VWS nur für sich genutzt werden.

**Definition of Done:**

-   Übersicht über Anbindungsmöglichkeiten erstellt (bspw. REST API)
-   Vor- und Nachteile der verschiedenen Möglichkeiten dargestellt
-   Definition, welche Anbindungen an Werkzeuge im Projekt notwendigerweise berücksichtigt/untersucht werden müssen

**Schnittstellen:**

-   AP3.2 und AP3.3: Architekturübersicht mit allen beteiligten Werkzeugen/Werkzeugtypen erstellt (bspw. MES, …)
1.  Definition Prozessablauf

Es muss ein Prozessablauf definiert werden, welcher Teilnehmer (OEM, Tier x) wann welche Daten generiert bzw. ergänzt.

**Definition of Done:**

-   Übersichtsdiagramm mit allen beteiligten Prozessteilnehmern (Entwicklung, Produktion, Montage), Prozessschritten sowie ausgetauschten Artefakten erstellt

**Schnittstellen:**

-   TP2/PPR-Workshop: Übersicht über den Entwicklungsprozess des Leitungssatzes mit allen beteiligten Akteuren und ausgetauschten Daten
-   UC3: Definition eines Beispiel-Szenarios für das Änderungsmanagement

#### Inhalte von Verwaltungsschalen

1.  Lieferung von Komponenten-Daten

Ein Komponentenlieferant (Tier2) muss für eine gelieferte Komponente (z.B. Gehäuse) eine Beschreibung des Gesamtsystems mit allen benötigten Inhalten liefern. Die Auflistung enthaltener Teil-Komponenten in Form einer vollständigen BOM ist nicht notwendig.

**Definition of Done:**

-   Notwendige Teilmodell(e) für Komponenten sind definiert
-   Beschreibung, welche Teilmodelle (in welcher Ausprägung/Detailtiefe) für die Nutzung in einer Verbundkomponente mindestens bereitgestellt werden müssen

**Schnittstellen:**

-   TP2: Übersicht über den Entwicklungsprozess des Leitungssatzes mit allen ausgetauschten Daten
-   TP1/AP2.4/PPR-Workshop: Definition und Entwicklung benötigter Teilmodelle
1.  Definition von Verwaltungsschalen-Typ und Inhalt

Es ist im Projekt zu definieren, welches Format (z.B. Typ 1, 2, 3) und welchen Inhalt (z.B. welche Teilmodelle) die verschiedenen Verwaltungsschalen besitzen müssen

**Definition of Done:**

-   Übersicht über alle benötigten Verwaltungsschalen erstellt
-   Benötigte Teilmodelle für alle Verwaltungsschalen definiert
-   Inhalte für alle benötigten Teilmodelle definiert
-   Interaktionsmuster zwischen Tools und/oder Verwaltungsschalen definiert
-   Ableitung getroffen, welche Verwaltungsschale (mindestens) in welchem Typ (1, 2 oder 3) ausgeführt sein muss; aufgegliedert nach Lebenszyklusphase der einzelnen Verwaltungsschale

**Schnittstellen:**

-   PPR-Workshop: Übersicht über alle benötigten Verwaltungsschalen sowie deren Inhalte
-   AP2.4/PPR-Workshop: Definition benötigter Teilmodelle
1.  Definition von Teilmodellen für Prozesse

Für jeden Prozess (z.B. Crimpen) ist ein Teilmodell/Daten zu definieren. Es muss möglich sein, Ein- und Ausgabeparameter von verschiedenen Prozessen/Produktionssystemen miteinander zu verknüpfen, um Datenströme/Abhängigkeiten zu kennzeichnen

**Definition of Done:**

-   Betrachtete Prozesse (z.B. Crimpen) definiert
-   Relevante Daten/Parameter für jeden Prozess definiert; sowohl für die Entwicklungs- als auch für die Produktionsphase
-   Teilmodell(e) für jeden Prozess definiert
-   Konzeptbeschreibung:
    -   Der Ausgabeparameter eines Prozesses kann als Eingabeparameter eines anderen Prozesses verwendet werden.
    -   Der Eingabeparameter eines Prozesses kann auf Grundlage von Ausgabeparametern anderer Prozesse berechnet werden.

**Schnittstellen:**

-   TP3: Beschreibung des Produktionsprozesses des Leitungssatzes sowie Entwicklung zugehöriger Teilmodelle

#### Änderung und Versionierung

1.  Transparente Aktualisierung von Verwaltungsschalen

Verwaltungsschalen müssen transparent aktualisiert werden. Änderungen (sowohl auf Seiten eines Produkts als auch auf Seiten einer Ressource) müssen kommuniziert werden (PCN), sodass abhängige Daten aktualisiert werden können.

**Definition of Done:**

-   Analyse durchgeführt, welche Arten Synchronisierung unterstützt werden müssen (Push/Pull)
-   Konzept für Synchronisierung von Änderungen mit anderen Verwaltungsschalen definiert

**Schnittstellen:**

-   Architekturteam: Synchronisierung von Verwaltungsschalen sowie Änderungsmanagement
-   TP6: Änderungsmanagement als Verhandlungsprozess
1.  Versionierung

Die Versionierung von VWS bzw. enthaltenen Daten ist zu berücksichtigen. Dies bedeutet, dass ein Ansatz für die Versionierung von Verwaltungsschalen und/oder Teilmodellen zu entwerfen ist.

**Definition of Done:**

-   Konzept zur Versionierung von VWSen beschrieben, sodass Änderungen zwischen zwei Versionen einer VWS bzw. eines Teilmodells nachvollzogen werden können
-   Ein Teilmodell das Informationen zu Gültigkeiten (Ist dies die aktuelle Version des Teilmodells?), Vor- und Nachgänger, Änderungsbeschreibung der Revision usw. enthält, ist definiert. Definiert ist ein Common-Umfang, der ein übergreifendes Mindestmaß an Information darstellt
-   Falls das Konzept eine strukturelle Erweiterung des bestehenden Konzepts der VWS erfordert, Kommunikation des Konzepts zu relevanten Gremien (bspw. AG1 der PlattformI4.0)

**Schnittstellen:**

-   Architekturteam: Versionierung von Verwaltungsschalen bzw. -inhalten

### Verbundkomponenten für den Kabelbaum (AP5.2)

#### Produktmodell

1.  Integration von KBL/VEC

Es sind Teilmodelle für die Integration von Produktmodellen in Form von KBL-/VEC-Dateien zu definieren.

**Definition of Done:**

-   Teilmodell für VEC definiert
-   Teilmodell für KBL definiert

**Schnittstellen:**

-   Architekturteam: Modularisierung und Verlinkung von Inhalten in Verwaltungsschalen
1.  Erstellung prototypischer Verwaltungsschalen

Es sind (prototypische) VWS von allen relevanten Komponenten und Artefakten eines definierten LS zu erstellen. Die Verwaltungsschalen sollen über die gemäß Anforderung 3: definierten Inhalte verfügen.

**Definition of Done:**

-   Beispielprodukt/-leitungssatz inklusive aller relevanten Halbfabrikate, Komponenten und Varianten definiert
-   Benötigte Verwaltungsschalen definiert; Berücksichtigung unterschiedlicher „Sichten“ z.B. zwischen OEM, Tier1, Tier2
-   Verwaltungsschalen erstellt und relevante Teilmodelle befüllt; Verknüpfungen zwischen Verwaltungsschalen angelegt

**Schnittstellen:**

-   PPR-Workshop: Definition eines Beispiel-Leitungssatzes, benötigter Verwaltungsschalen
-   TP1/AP2.4/PPR-Workshop: Definition und Entwicklung benötigter Teilmodelle

#### Hierarchie und Verweise

1.  Integration der Informationsmodelle von KBL/VEC

Es ist zu definieren, wie/welche Verweise zwischen Einzelkomponenten in VEC/KBL und den entsprechenden Verwaltungsschalen definiert werden können/müssen

**Definition of Done:**

-   Referenzziele aus den Informationsmodellen von VEC und KBL definiert (auf welche Elemente/Elementtypen soll verwiesen werden, um Beziehungen zu anderen Teilmodellen herzustellen)
-   Referenzierungs-Mechanismus definiert

**Schnittstellen:**

-   Architekturteam: Modularisierung und Verlinkung von Inhalten in Verwaltungsschalen
1.  Aggregation von KBL/VEC-Beschreibungen

Es ist zu untersuchen, inwiefern VEC/KBL-Beschreibungen „aggregiert“ werden können, sodass sich ein LS aus mehreren Teil-LS zusammensetzen kann.

**Definition of Done:**

-   Konzept zur Modularisierung von VEC-Beschreibungen definiert
-   Konzept zur Modularisierung von KBL-Beschreibungen definiert

**Schnittstellen:**

-   Architekturteam: Modularisierung und Verlinkung von Inhalten in Verwaltungsschalen

#### Änderungsmanagement

1.  Kommunikation und Integration von Änderungen

Es ist zu definieren, wie Änderungen von Parametern bzw. Produktionsprozessen auf Basis eines Design Changes kommuniziert und konsistent aktualisiert werden können (Change Management).

**Definition of Done:**

-   Konzept für Änderungsfreigabe/-übernahme definiert

**Schnittstellen:**

-   Architekturteam: Synchronisierung von Verwaltungsschalen sowie Änderungsmanagement

### Verbundkomponenten Produktionsmittel (AP5.3)

#### Modellierung von Produktionsressourcen

1.  Definition von Teilmodellen für Ressourcen

Es ist zu definieren, welche Teilmodelle für eine Produktionsressource geliefert werden müssen (z.B. CAD, technische Daten, Teilmodelle für Werkzeuge und Werkzeugumrüstung, Simulationsmodelle, Fähigkeiten und Skills, …).

**Definition of Done:**

-   Benötigte Teilmodelle für Ressourcen-VWSen definiert
-   Beschreibung, welche Teilmodelle (in welcher Ausprägung/Detailtiefe) für die Nutzung in einer Verbundkomponente mindestens bereitgestellt werden müssen --\> „Best Practice“-Dokument

**Schnittstellen:**

-   TP1: Definition von Informationsmodellen

#### Hierarchie

1.  Hierarchien von Produktionsressourcen

Es ist zu definieren, wie/welche Hierarchien von Produktionsressourcen (BOM) definiert werden können/müssen.

**Definition of Done:**

-   Konzept zur Modellierung zusammengesetzter Ressourcen definiert (bspw. Maschine und verfügbare Werkzeuge/Erweiterungsmodule)
-   Konzept zur Modellierung von Capabilities unter Berücksichtigung zusammengesetzter Ressourcen beschrieben

**Schnittstellen:**

-   Architekturteam: Modularisierung und Verlinkung von Inhalten in Verwaltungsschalen
1.  Aggregation von Simulationsmodellen

Es ist zu prüfen, ob/wie Simulationsmodelle für Maschinen aus mehreren Simulationsmodellen für Einzelkomponenten einer Maschine aggregiert werden können („Bill of Simulation“).

**Definition of Done:**

-   Beschreibung anhand eines oder mehrerer konkreten/r Use Cases, welche Art von Simulationsmodellen benötigt werden
-   Beschreibung, welche Art von Simulationsmodellen für die Nutzung in einer Verbundkomponente mindestens bereitgestellt werden müssen
-   Konzept zur automatischen Ableitung einer Gesamt-/Systemsimulation aus Simulationsmodellen von Einzel-/Teilressourcen beschrieben

**Schnittstellen:**

-   \---

### Integration der Verwaltungsschalen (AP5.4)

#### Allgemeines

1.  Synchronisation von Anforderungen

Die Anforderungen aus TP5 sind mit den anderen TPs zu synchronisieren, sodass die dort erstellten Teilmodelle/Verwaltungsschalen in TP5 ohne größeren Aufwand integriert werden können.

**Definition of Done:**

-   Benötigte Teilmodelle sind aufgelistet.
-   Für alle benötigten Teilmodelle sind Anforderungen aus Sicht der Verbundkomponente formuliert.

**Schnittstellen:**

-   TP1/2/3/4: Definition von Informations- und Teilmodellen
1.  Bereitstellen von Verwaltungsschalen in einem Repository

Die VWS der verschiedenen Lebenszyklusphasen müssen in einem für alle Mitglieder der Wertschöpfungskette frei zugänglichen Repository verfügbar sein.

**Definition of Done:**

-   Es ist eine prototypische Infrastruktur aufgesetzt, in der alle bestehenden Verwaltungsschalen über einen oder mehrere Server abgerufen werden können und auf die alle Mitglieder zugreifen können.
-   Über die Infrastruktur können neue Verwaltungsschalen an-/abgelegt werden.
-   Die Infrastruktur unterstützt die Definition und Auswertung von Zugriffsrechten für einzelne VWSen/Teilmodelle/Elemente.

**Schnittstellen:**

-   \---

#### Verknüpfung von Teilmodellen und Verwaltungsschalen

1.  Verknüpfung von CAD-Modellen mit anderen Teilmodellen

Es ist zu definieren, welche Eigenschaften eines CAD-Modells (z.B. eines Verbindungsteils) bekannt sein müssen, damit dieses mit anderen Teilmodellen/Verwaltungsschalen in Beziehung gesetzt werden kann.

**Definition of Done:**

-   Anhand eines bestimmten Beispiels (z.B. automatisiertes Stecken von Terminals in Gehäuse bei der Leitungssatzfertigung) ist definiert, welche Parameter aus dem CAD-Modell lesbar/ableitbar sein müssen, um dies mit geringem Aufwand realisieren zu können
-   Eine Systematik zur Verallgemeinerung des Beispiels ist definiert.

**Schnittstellen:**

-   AP3.2: Betrachtung der benötigten Prozesse bei der LS-Fertigung sowie relevanter Parameter
1.  Verknüpfung von Produkt- und Prozessmodell

Es ist zu definieren, wie Daten aus dem Produktmodell (z.B. KBL/VEC) mit dem Prozessmodell zu verknüpfen sind. Dabei ist auch eine Zuordnung von einzelnen Prozessschritten und resultierenden Halbfabrikaten zu schaffen.

**Definition of Done:**

-   Das Prozessmodell kann direkt auf erforderliche Datenfragmente des Produktmodells verweisen.
-   Konzept zur Verknüpfung des Prozess- und Produktmodells ist definiert, z.B. auf Basis von „Required Capabilities“
-   Das Konzept ermöglicht die Zuordnung von Prozessschritten zu genutzten bzw. resultierenden Komponenten und Halbfabrikaten.

**Schnittstellen:**

-   TP3: Definition des Prozessmodells sowie der zugehörigen Capabilities inkl. Parametern
-   Architekturteam: Verlinkung von Inhalten in Verwaltungsschalen

### Mapping zwischen Produktionsressource und Leitungssatz (AP5.5)

#### Verknüpfung von Produktionsprozess und -ressourcen

1.  Verknüpfung von Prozessmodell und Ressourcen

Es ist ein Teilmodell zu definieren, in dem Zuordnungen zwischen Ressourcen und Prozessschritten beschrieben werden können. Dabei müssen verschiedenen Varianten zur Fertigung von Halbfabrikaten (z.B. vollstufiger Automat vs. Handling über mehrere Automaten) definiert werden können.

**Definition of Done:**

-   Mithilfe des CSS-Modells (Capabilities-Skills-Services) werden verschiedene Zuordnungen (Fertigungswege) herausgefunden und mit weitere Faktoren aggregiert wie z.B. Durchlaufzeit
-   Es existiert eine Spezifikation für ein eigenes Teilmodell oder für die Erweiterung eines existierenden Teilmodells, die beschreibt, wie Prozessschritte mit zugehörigen Ressourcen verknüpft werden können.
-   Im Falle modularer Ressourcen (bspw. Werkzeugmaschine + Werkzeug) ermöglicht die Spezifikation die Beschreibung, welche(s) Modul(e) für den Prozessschritt genutzt werden müssen.

**Schnittstellen:**

-   TP6: Betrachtung automatischer Verhandlungsprozesse als Grundlage für die Ermittlung potenzieller Fertigungswege
1.  Algorithmus zum Fähigkeitenabgleich

Es ist ein Algorithmus zu entwerfen, der auf Basis einer Analyse von Fähigkeiten von Produktionsressourcen eine automatische Abbildung von Ressourcen auf LS-Komponenten/Prozessschritte ableiten kann.

**Definition of Done:**

-   Konzeptbeschreibung für einen Algorithmus zum automatischen Mapping von Prozessschritten auf Ressourcen.
-   Der Algorithmus nutzt als Basis ein Modell von „required capabilties“ für einen (Satz von) Prozessschritten sowie ein Modell von „offered capabilities“ eines (Satzes von) Produktionsressourcen.
-   Es existiert eine prototypische Implementierung des Algorithmus.

**Schnittstellen:**

-   TP3: Definition des Prozessmodells sowie der zugehörigen Capabilities inkl. Parametern
-   TP6: Betrachtung automatischer Verhandlungsprozesse als Grundlage für die Ermittlung potenzieller Fertigungswege
1.  Virtuelle Inbetriebnahme der Produktion

Die virtuelle Inbetriebnahme/Simulation der Produktion auf Basis der definierten Zuordnungen zwischen Ressource und LS-Komponente/Prozessschritt ist zu untersuchen.

**Definition of Done:**

-   Teilmodelle für die virtuelle Inbetriebnahme sind definiert bzw. vorhandene aus der Produktion werden dafür verwendet.
-   Später mit „realen Daten“ aus den Teilmodellen der Produktion vergleichen, um die Datenqualität der virtuelle Inbetriebnahme zu prüfen und zu verbessern
-   Es existiert ein Konzept zur Gesamtsimulation einer Produktion bzw. eines Produktionsschrittes auf Basis einzelner Simulationsmodelle, die z.B. eine (Teil-)Schritt abbilden.

**Schnittstellen:**

-   \---

### Erfassung der Qualitätsdaten (AP5.6)

#### Teilmodelle

1.  Teilmodell für Qualitätsdaten

Es ist ein Teilmodell zu definieren, mit dem relevante Rückmelde-/Qualitätsdaten beschrieben werden können (Stückzahl, Start- und Endzeitpunkt, etc.).

**Definition of Done:**

-   Es existiert eine Teilmodellspezifikation zur Beschreibung von Rückmelde- bzw. Qualitätsdaten eines Produktionsschrittes bzw. einer Gesamtproduktion.
-   Im Teilmodell muss ein Vorhalt berücksichtigt sein, falls eine Charge eines Produktionsauftrags nicht abgeschlossen werden kann (neues Material muss gerüstet werden o.ä.)
-   Dieser Vorhalt muss auch die Verbindung von mehreren Chargen zu einem Produktionsauftrag vorsehen (Nachproduktion zur Erfüllung des Produktionsauftrags)

**Schnittstellen:**

-   TP3: Definition von Teilmodellen für den Produktionsprozess inkl. Parametern als Grundlage für Rückmeldedaten
1.  Teilmodell zur Überwachung von Parametern

Es sind Teilmodelle zu definieren, mit denen qualitätsrelevante Parameter überwacht werden können (z.B. bei der Schraubmontage)

**Definition of Done:**

-   Die Spezifikation für ein Teilmodell zur Beschreibung qualitätsrelevanter Parameter liegt vor. Das Teilmodell muss dabei ermöglichen, für bestimmte Parameter eines Prozessschrittes Qualitätsvorgaben zu definieren (bspw. erlaubte Toleranzen).
-   Es muss möglich sein, Ereignisse zu definieren, die ausgelöst werden sollen, wenn ein qualitätsrelevanter Parameter seinen definierten Grenzwert über- bzw. unterschreitet. Der Grenzwert kann dabei auch eine Funktion sein, um bspw. Tendenzen zu erkennen. Qualitätsrelevante Parameter können sich entweder auf einzelne Messwerte oder ganze Messreihen beziehen.
-   Es existiert eine Implementierung, die demonstriert, dass die entsprechenden Ereignisse ausgelöst werden.

**Schnittstellen:**

TP3: Definition von Teilmodellen für den Produktionsprozess inkl. Parametern als Grundlage für Rückmeldedaten

1.  Teilmodell zur Beschreibung des Nutzungsgrades

Es sind Teilmodelle zur Beschreibung des Nutzungsgrades/Verschleiß von Ressourcen zu definieren (z.B. für Predictive Maintenance).

**Definition of Done:**

-   Es existiert eine Teilmodellspezifikation, mit dem der aktuelle Zustand einer Ressource beschrieben werden kann. Dies kann Werte wie Abnutzungsgrad, Verschleiß oder erwartete Restlaufzeit beinhalten.

    Es existiert ein Teilmodell zur Beschreibung von Wartungszyklen o.ä.

**Schnittstellen:**

-   \---

#### Verknüpfung von Daten

1.  Traceability

Es ist zu definieren, wie Rückmeldedaten mit anderen Elementen/Daten aus dem PPR-Kontext verknüpft werden können („Traceability“). Ein Beispiel hierfür stellt die Zuordnung eines bestimmten Datensatzes zu dem produzierten Halbfabrikat sowie der produzierenden Maschine dar.

**Definition of Done:**

-   Die Rückmeldedaten können auf die verwendeten Produkt-, Prozess- und Ressourcenmodelle zurückgeführt werden.

**Schnittstellen:**

-   TP3: Definition des Prozessmodells sowie der zugehörigen Capabilities inkl. Parametern
-   Architekturteam: Verlinkung von Inhalten in Verwaltungsschalen
1.  Unterstützung von Chargen

Es ist zu definieren, wie mit Chargen umzugehen ist, bei denen nicht jedes einzelne Teil zu identifizieren ist (z.B. Packung mit 200 Schrauben). Wie kann eine Zuordnung zwischen Chargen und anderen Elementen (z.B. Qualitätsdaten) erfolgen?

**Definition of Done:**

-   Definition eines Konzeptes, das sowohl die Definition einer Seriennummer als auch einer bzw. mehrerer Chargennummer(n) zulässt/verarbeiten kann und dies kennzeichnet, wobei die Information möglichst automatisiert aus der VWS (wenn vorhanden) des verwendeten Materials übernommen werden soll

**Schnittstellen:**

-   \---

## AP 5.2 - Verbundkomponente Produkt (Leitungssatz)

### Zielsetzung

Das AP 5.2 behandelt die Ableitung und Definition der Verbundkomponente (VBK) „Produkt“, d.h. des Leitungssatzes.

Grundlage für die VBK sind dabei zunächst die relevanten Beziehungen zwischen den beteiligten Verwaltungsschalen bzw. zwischen Elementen dieser Verwaltungsschalen. Diese Beziehungen wurden im Rahmen von AP5.2 ermittelt, wobei die Analyse notwendiger Beziehungen von den Ergebnissen des PPR-Workshops ausging, in dem relevante Assets und Verwaltungsschalen (unter anderem) für die Abbildung des Leitungssatzes analysiert wurden. [Abbildung 1-2](#Abbildung-1-2)  zeigt eine Übersicht über die relevanten Verwaltungsschalen, welche zur Analyse der Beziehungen herangezogen wurden.

![image](https://github.com/user-attachments/assets/732b3315-d2ea-409f-95e3-15e0ac7e69fe)

<a name="Abbildung-1-2"></a>*Abbildung 1-2: Unterschiedliche Arten von Verwaltungsschalen als Teil der VBK „Produkt“*

Die verschiedenen Beziehungen zwischen den oben abgebildeten Verwaltungsschalen wurden klassifiziert (Quelle, Ziel, Kategorie, Kardinalität) und mit je einem Use Case beschrieben. Dieser Use Case zeigt jeweils auf, warum es sinnvoll ist, die entsprechende Beziehung explizit im Rahmen der VBK „Produkt“ abzubilden.

Abschnitt 1.2.2 führt die einzelnen Beziehungen inklusive Klassifizierung sowie zugeordnetem Use Case auf. Darauf aufbauend erläutert Abschnitt 0 die Umsetzung der verschiedenen Kategorien von Beziehung auf Basis der Verwaltungsschale.

### Ermittelte Beziehungen

In diesem Abschnitt werden die einzelnen Beziehungen inklusive Klassifizierung sowie zugeordnetem Use Case in Bezug auf Abbildung 1--2 aufgeführt.

#### Hierarchische Beziehungen

##### Leitungssatz enthält Komponenten

**Klassifizierung:**

-   Quelle: AAS Leitungssatz Tier 1
-   Ziel: AAS-Komponente Tier 1
-   Kategorie: hierarchisch, top-down
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zwischen einem LS und den enthaltenen Komponenten

**Use Case:**

-   Engineering-Tool kann erkennen, welche Komponenten in einem LS enthalten sind und direkt die benötigten Daten aus deren AASen auslesen, bspw. für die Produktionsplanung
-   MES-Tool kann erkennen, welche Komponenten in einem LS enthalten sind und prüfen, ob die Komponenten auf Lager liegen bzw. deren Beschaffung anstoßen

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.1.4
-   Analoge Beziehung zu 1.2.2.1.2, 1.2.2.1.7, 1.2.2.1.11 und 1.2.2.1.15

##### (OEM-)Leitungssatz enthält (OEM-)Komponenten

**Klassifizierung:**

-   Quelle: AAS Leitungssatz OEM
-   Ziel: AAS-Komponente OEM
-   Kategorie: hierarchisch, top-down
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zwischen einem LS und den enthaltenen Komponenten

**Use Case:**

-   OEM prüft, ob die verwendeten Komponenten freigegeben und noch gültig sind und nach außen gegeben werden dürfen
-   Voraussetzung für die Ersetzung der OEM-Teilenummern durch die Tier1-Teilenummern

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.1.4
-   Analoge Beziehung zu 1.2.2.1.1, 1.2.2.1.7, 1.2.2.1.11 und 1.2.2.1.15

##### Leitungssatz-Instanz enthält Komponenten-Instanzen

**Klassifizierung:**

-   Quelle: AAS Leitungssatz-Instanz Tier 1
-   Ziel: AAS-Komponenten-Instanz Tier 1
-   Kategorie: hierarchisch, top-down
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zwischen einer LS-Instanz und den enthaltenen Komponenten/Chargen von Komponenten

**Use Case:**

-   Traceability

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.1.6
-   Analoge Beziehung zu 1.2.2.1.8, 1.2.2.1.12 und 1.2.2.1.16

##### Komponente wird in Leitungssatz verwendet

**Klassifizierung:**

-   Quelle: AAS-Komponente Tier 1
-   Ziel: AAS Leitungssatz Tier 1
-   Kategorie: hierarchisch, bottom-up
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung der Leitungssätze, in denen eine Komponente verwendet wird

**Use Case:**

-   Komponente hat Lieferengpass -\> benachrichtigt automatisch alle Leitungssätze, in denen sie verwendet wird
-   Daten einer Komponente werden geändert -\> benachrichtigt automatisch alle Leitungssätze, in denen sie verwendet wird

**Kommentar:**

-   Hoher Datenpflege-Aufwand
-   Use Cases können auch über Rückwärtssuche der Beziehung 1.2.2.1.1 realisiert werden

##### (OEM-)Komponente wird in (OEM-)Leitungssatz verwendet

**Klassifizierung:**

-   Quelle: AAS-Komponente OEM
-   Ziel: AAS Leitungssatz OEM
-   Kategorie: hierarchisch, bottom-up
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung der Leitungssätze, in denen eine Komponente verwendet wird

**Use Case:**

-   Komponente hat Lieferengpass -\> benachrichtigt automatisch alle Leitungssätze, in denen Sie verwendet wird
-   Daten einer Komponente werden geändert -\> benachrichtigt automatisch alle Leitungssätze, in denen Sie verwendet wird

**Kommentar:**

-   Hoher Datenpflege-Aufwand
-   Use Cases können auch über Rückwärtssuche der Beziehung 1.2.2.1.2 realisiert werden

##### Komponenten-Instanz wird in LS-Instanz verwendet

**Klassifizierung:**

-   Quelle: AAS-Komponenten-Instanz Tier 1
-   Ziel: AAS Leitungssatz-Instanz Tier 1
-   Kategorie: hierarchisch, bottom-up
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung der Leitungssätze, in denen eine Komponente verwendet wird

**Use Case:**

-   Traceability

**Kommentar:**

-   Hoher Datenpflege-Aufwand
-   Use Cases Könnte auch über Rückwärtssuche der Beziehung 1.2.2.1.3 realisiert werden

##### Leitungssatz enthält Halbfabrikate

**Klassifizierung:**

-   Quelle: AAS Leitungssatz Tier 1
-   Ziel: AAS Halbfabrikat Tier 1
-   Kategorie: hierarchisch, top-down
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zwischen einem LS und den vom Tier 1 definierten Halbfabrikaten, aus denen sich dieser zusammensetzt

**Use Case:**

-   MES-Tool kann erkennen, welche Halbfabrikate in einem LS enthalten sind und prüfen, ob das Halbfabrikat auf Lager liegt bzw. dessen Produktion anstoßen
-   Wenn ein Halbfabrikat zugekauft wird, kann über dessen AAS die Beschaffung angestoßen werden (-\> automatische Verhandlungsprozesse)

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.1.9
-   Analoge Beziehung zu 1.2.2.1.1, 1.2.2.1.2, 1.2.2.1.11 und 1.2.2.1.15

##### Leitungssatz-Instanz enthält Halbfabrikat-Instanzen

**Klassifizierung:**

-   Quelle: AAS Leitungssatz-Instanz Tier 1
-   Ziel: AAS Halbfabrikat-Instanz Tier 1
-   Kategorie: hierarchisch, top-down
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zwischen einer LS-Instanz und den vom Tier 1 definierten Halbfabrikat-Instanzen, aus denen sich dieser zusammensetzt

**Use Case:**

-   Traceability

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.1.9
-   Analoge Beziehung zu 1.2.2.1.3, 1.2.2.1.12 und 1.2.2.1.16

##### Halbfabrikat wird in Leitungssatz verwendet

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat Tier 1
-   Ziel: AAS Leitungssatz Tier 1
-   Kategorie: hierarchisch, bottom-up
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung der Leitungssätze, in denen ein Halbfabrikat verwendet wird

**Use Case:**

-   Zugeliefertes Halbfabrikat hat Lieferengpass -\> benachrichtigt automatisch alle Leitungssätze, in denen es verwendet wird
-   Daten eines Halbfabrikats werden geändert -\> benachrichtigt automatisch alle Leitungssätze, in denen es verwendet wird

**Kommentar:**

-   Hoher Datenpflege-Aufwand
-   Use Cases können auch über Rückwärtssuche der Beziehung 1.2.2.1.7 realisiert werden

##### Halbfabrikat-Instanz wird in Leitungssatz-Instanz verwendet

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat-Instanz Tier 1
-   Ziel: AAS Leitungssatz-Instanz Tier 1
-   Kategorie: hierarchisch, bottom-up
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Zuordnung zur Leitungssatz-Instanz, in der eine Halbfabrikats-Instanz verwendet wird

**Use Case:**

-   Traceability

**Kommentar:**

-   Hoher Datenpflege-Aufwand
-   Use Cases können auch über Rückwärtssuche der Beziehung 1.2.2.1.8 realisiert werden

##### Halbfabrikat enthält Halbfabrikat

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat Tier 1
-   Ziel: AAS Halbfabrikat Tier 1
-   Kategorie: hierarchisch, top-down
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zwischen einem Halbfabrikat und den vom Tier 1 definierten Unter-Halbfabrikaten, aus denen sich dieser zusammensetzt

**Use Case:**

-   MES-Tool kann erkennen, welche Halbfabrikate in einem Halbfabrikat enthalten sind und prüfen, ob das Halbfabrikat auf Lager liegt bzw. dessen Produktion anstoßen
-   Wenn ein Halbfabrikat zugekauft wird, kann über dessen AAS die Beschaffung angestoßen werden (-\> automatische Verhandlungsprozesse)

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.1.13
-   Analoge Beziehung zu 1.2.2.1.1, 1.2.2.1.2, 1.2.2.1.7 und 1.2.2.1.15

##### Halbfabrikat-Instanz enthält Halbfabrikat-Instanz

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat-Instanz Tier 1
-   Ziel: AAS Halbfabrikat-Instanz Tier 1
-   Kategorie: hierarchisch, top-down
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zwischen einer Halbfabrikat-Instanz und den Unter-Halbfabrikat-Instanzen, aus denen sich dieses zusammensetzt

**Use Case:**

-   Traceability

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.1.14
-   Analoge Beziehung zu 1.2.2.1.3, 1.2.2.1.8 und 1.2.2.1.16

##### Halbfabrikat wird in Halbfabrikat verwendet

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat Tier 1
-   Ziel: AAS Halbfabrikat Tier 1
-   Kategorie: hierarchisch, bottom-up
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung der Halbfabrikate, in denen ein Halbfabrikat verwendet wird

**Use Case:**

-   Zugeliefertes Halbfabrikat hat Lieferengpass -\> benachrichtigt automatisch alle Halbfabrikate, in denen es verwendet wird
-   Daten eines Halbfabrikats werden geändert -\> benachrichtigt automatisch alle Halbfabrikate, in denen es verwendet wird

**Kommentar:**

-   Hoher Datenpflege-Aufwand
-   Use Cases können auch über Rückwärtssuche der Beziehung 1.2.2.1.11 realisiert werden

##### Halbfabrikat-Instanz wird in Halbfabrikat-Instanz verwendet

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat Tier 1
-   Ziel: AAS Halbfabrikat Tier 1
-   Kategorie: hierarchisch, bottom-up
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Zuordnung zur Halbfabrikat-Instanz, in der eine Halbfabrikat-Instanz verwendet wird

**Use Case:**

-   Traceability

**Kommentar:**

-   Hoher Datenpflege-Aufwand
-   Use Cases können auch über Rückwärtssuche der Beziehung 1.2.2.1.12 realisiert werden

##### Halbfabrikat enthält Komponente

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat Tier 1
-   Ziel: AAS-Komponente Tier 1
-   Kategorie: hierarchisch, top-down
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zwischen einem vom Tier 1 definierten Halbfabrikat und den enthaltenen Komponenten

**Use Case:**

-   Engineering-Tool kann erkennen, welche Komponenten in einem Halbfabrikat enthalten sind und direkt die benötigten Daten aus deren AASen auslesen, bspw. für die Produktionsplanung
-   MES-Tool kann erkennen, welche Komponenten in einem Halbfabrikat enthalten sind und prüfen, ob die Komponenten auf Lager liegen bzw. deren Beschaffung anstoßen

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.1.17
-   Analoge Beziehung zu 1.2.2.1.1, 1.2.2.1.2, 1.2.2.1.7 und 1.2.2.1.11

##### Halbfabrikat-Instanz enthält Komponenten-Instanzen

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat-Instanz Tier 1
-   Ziel: AAS-Komponenten-Instanz Tier 1
-   Kategorie: hierarchisch, top-down
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zwischen einem vom Tier 1 produzierten Halbfabrikat und den enthaltenen Komponenten-Instanzen

**Use Case:**

-   Traceability

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.1.18
-   Analoge Beziehung zu 1.2.2.1.3, 1.2.2.1.8 und 1.2.2.1.12

##### Komponente wird in Halbfabrikat verwendet

**Klassifizierung:**

-   Quelle: AAS-Komponente Tier 1
-   Ziel: AAS Halbfabrikat Tier 1
-   Kategorie: hierarchisch, bottom-up
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung der Halbfabrikate, in denen eine Komponente verwendet wird

**Use Case:**

-   Komponente hat Lieferengpass -\> benachrichtigt automatisch alle Halbfabrikate, in denen sie verwendet wird
-   Daten einer Komponente werden geändert -\> benachrichtigt automatisch alle Halbfabrikate, in denen sie verwendet wird

**Kommentar:**

-   Hoher Datenpflege-Aufwand
-   Use Cases können auch über Rückwärtssuche der Beziehung 1.2.2.1.15 realisiert werden

##### Komponenten-Instanz wird in Halbfabrikat-Instanz verwendet

**Klassifizierung:**

-   Quelle: AAS-Komponenten-Instanz Tier 1
-   Ziel: AAS Halbfabrikat-Instanz Tier 1
-   Kategorie: hierarchisch, bottom-up
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Zuordnung zur Halbfabrikat-Instanz, in der eine Komponenten-Instanz verwendet wird

**Use Case:**

-   Traceability

**Kommentar:**

-   Beziehung hat die Kardinalität „1-zu-n“, da eine Komponenten-Instanz auch eine Charge repräsentieren kann
-   Hoher Datenpflege-Aufwand
-   Use Cases können auch über Rückwärtssuche der Beziehung 1.2.2.1.16 realisiert werden

#### Typ-Instanz-Beziehungen

##### Leitungssatz ist Instanz aus LS-Typ

**Klassifizierung:**

-   Quelle: AAS Leitungssatz-Instanz Tier 1
-   Ziel: AAS Leitungssatz Tier 1
-   Kategorie: Instanz ist von Typ
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Modellierung, dass eine bestimmte LS-Instanz einem bestimmten Typ genügt

**Use Case:**

-   Bei Auftauchen eines Fehlers, Qualitätsproblems, o.ä. bei einer Instanz kann ermittelt werden, welcher Leitungssatz-Typ genau betroffen sind

**Kommentar:**

-   Analoge Beziehung zu 1.2.2.2.3,  und 1.2.2.2.7

##### Leitungssatz-Typ hat produzierte Instanzen

**Klassifizierung:**

Quelle: AAS Leitungssatz Tier 1

-   Ziel: AAS Leitungssatz-Instanz Tier 1
-   Kategorie: Typ hat Instanz
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Beschreibung, welche Instanzen aus einem Leitungssatz-Typ produziert wurden

**Use Case:**

-   Bei Auftauchen von Fehlern, Qualitätsproblemen, o.ä. kann ermittelt werden, welcher Leitungssatz-Instanzen genau betroffen sind

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.2.1
-   Hoher Datenpflege-Aufwand
-   Use Case Könnte auch über Rückwärtssuche der Beziehung 1.2.2.2.1 realisiert werden
-   Analog zu Beziehung 1.2.2.2.4, 1.2.2.2.6 und 1.2.2.2.8

##### Halbfabrikat ist Instanz aus Halbfabrikat-Typ

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat-Instanz Tier 1
-   Ziel: AAS Halbfabrikat Tier 1
-   Kategorie: Instanz ist von Typ
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Modellierung, dass eine bestimmte Halbfabrikat-Instanz einem bestimmten Typ genügt

**Use Case:**

-   Bei Auftauchen eines Fehlers, Qualitätsproblems, o.ä. bei einer Instanz kann ermittelt werden, welcher Halbfabrikats-Typ genau betroffen sind

**Kommentar:**

-   Analoge Beziehung zu 1.2.2.2.1,  und 1.2.2.2.7

##### Halbfabrikat-Typ hat produzierte Instanzen

**Klassifizierung:**

-   Quelle: AAS Halbfabrikat Tier 1
-   Ziel: AAS Halbfabrikat -Instanz Tier 1
-   Kategorie: Typ hat Instanz
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Beschreibung, welche Instanzen aus einem Halbfabrikat-Typ produziert wurden

**Use Case:**

-   Bei Auftauchen von Fehlern, Qualitätsproblemen, o.ä. kann ermittelt werden, welche Halbfabrikats-Instanzen genau betroffen sind

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.2.3
-   Hoher Datenpflege-Aufwand
-   Use Case Könnte auch über Rückwärtssuche der Beziehung 1.2.2.2.3 realisiert werden
-   Analog zu Beziehung 1.2.2.2.2, 1.2.2.2.6 und 1.2.2.2.8

##### Komponente ist Instanz aus Komponenten-Typ

**Klassifizierung:**

-   Quelle: AAS-Komponenten-Instanz Tier 1
-   Ziel: AAS-Komponenten Tier 1
-   Kategorie: Instanz ist von Typ
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Modellierung, dass eine bestimmte Komponenten-Instanz einem bestimmten Typ genügt

**Use Case:**

-   Scannen einer Komponenten-Instanz vor dem Einbau in einen Leitungssatz -\> Anhand des Typs wird die Freigabe für den Leitungssatz überprüft

**Kommentar:**

-   Analoge Beziehung zu 1.2.2.2.1, 1.2.2.2.3 und 1.2.2.2.7

##### Komponenten-Typ hat produzierte Instanzen

**Klassifizierung:**

Quelle: AAS-Komponente Tier 1

-   Ziel: AAS-Komponenten-Instanz Tier 1
-   Kategorie: Typ hat Instanz
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Beschreibung, welche Instanzen aus einem Komponenten-Typ produziert wurden

**Use Case:**

-   Bei Auftauchen von Fehlern, Qualitätsproblemen, o.ä. kann ermittelt werden, welche Komponenten-Instanzen/Chargen genau betroffen sind

**Kommentar:**

-   Inverse Beziehung zu 
-   Hoher Datenpflege-Aufwand
-   Use Case Könnte auch über Rückwärtssuche der Beziehung  realisiert werden
-   Analog zu Beziehung 1.2.2.2.2, 1.2.2.2.4 und 1.2.2.2.8

##### Tier2-Komponente ist Instanz aus Tier2-Komponenten-Typ

**Klassifizierung:**

-   Quelle: AAS-Komponenten-Instanz Tier 2
-   Ziel: AAS-Komponenten Tier 2
-   Kategorie: Instanz ist von Typ
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Modellierung, dass eine bestimmte Komponenten-Instanz einem bestimmten Typ genügt

**Use Case:**

-   Scannen einer Komponenten-Instanz vor dem Einbau in einen Leitungssatz -\> Anhand des Typs wird die Freigabe für den Leitungssatz überprüft

**Kommentar:**

-   Analoge Beziehung zu 1.2.2.2.1, 1.2.2.2.3 und 

##### Tier2-Komponenten-Typ hat produzierte Instanzen

**Klassifizierung:**

Quelle: AAS-Komponente Tier 2

-   Ziel: AAS-Komponenten-Instanz Tier 2
-   Kategorie: Typ hat Instanz
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Beschreibung, welche Instanzen aus einem Komponenten-Typ produziert wurden

**Use Case:**

-   Bei Auftauchen von Fehlern, Qualitätsproblemen, o.ä. kann ermittelt werden, welche Komponenten-Instanzen/Chargen genau betroffen sind

**Kommentar:**

-   Inverse Beziehung zu 1.2.2.2.7
-   Hoher Datenpflege-Aufwand
-   Use Case Könnte auch über Rückwärtssuche der Beziehung 1.2.2.2.7 realisiert werden
-   Analog zu Beziehung 1.2.2.2.2, 1.2.2.2.4 und 1.2.2.2.6

#### Äquivalenz-/Entsprechungs-Beziehungen

##### Tier2-Komponente realisiert OEM-Komponente

**Klassifizierung:**

-   Quelle: AAS-Komponente Tier 2
-   Ziel: AAS-Komponente OEM
-   Kategorie: Abgeleitet aus/Entspricht
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Tier2 beschreibt für seine Komponente, welche OEM-Komponente(n) diese realisiert

**Use Case:**

-   Tier 1 erhält vom OEM einen Leitungssatz mit (OEM-)Komponenten und kann ermitteln, welchen Lieferanten er für die Realisierung nutzen möchte

**Kommentar:**

-   Je nach Komponente legt der OEM entweder einen oder mehrere Lieferanten fest (s.u.), oder er überlässt die Auswahl dem Tier1

##### Tier1-Komponente realisiert OEM-Komponente

**Klassifizierung:**

-   Quelle: AAS-Komponente Tier 1
-   Ziel: AAS-Komponente OEM
-   Kategorie: Abgeleitet aus/Entspricht
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Tier1 beschreibt für seine Komponente, welche OEM-Komponente(n) diese realisiert

**Use Case:**

-   Grundlage für die Ersetzung von OEM-Sachnummern durch Tier1-Sachnummern

**Kommentar:**

-   \---

##### Tier1-Leitungssatz setzt OEM-Leitungssatz um

**Klassifizierung:**

-   Quelle: AAS Leitungssatz Tier 1
-   Ziel: AAS Leitungssatz OEM
-   Kategorie: Abgeleitet aus/Entspricht
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Beschreibung, dass ein LS beim Tier1 aus einem Leitungssatz beim OEM entstanden ist bzw. diesen realisiert

**Use Case:**

-   Bei Druck von Leitungssatz-Etikett muss OEM-Sachnummer und Zeichnungsstand ermittelt und aufgedruckt werden
-   Änderungen durch den OEM haben einen Änderungsprozess beim Tier1 zur Folge

**Kommentar:**

-   \---

##### Tier1-Komponenten-Instanz entspricht Instanz/Charge bei Tier2

**Klassifizierung:**

-   Quelle: AAS-Komponenten-Instanz Tier 1
-   Ziel: AAS-Komponenten-Instanz Tier 2
-   Kategorie: Abgeleitet aus/Entspricht
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Zuordnung von Komponenten-Instanzen bzw. Chargen beim Tier 1 zu der entsprechenden Instanz/Charge beim Tier 2

**Use Case:**

-   Chargen-bezogene Daten wie bspw. Haltbarkeit müssen nicht separat in der Tier1-AAS gespeichert werden sondern es kann auf die Tier2-AAS verwiesen werden

**Kommentar:**

-   \---

##### Tier1-LS-Instanz firmiert bei OEM als LS-Instanz

**Klassifizierung:**

-   Quelle: AAS Leitungssatz-Instanz Tier 1
-   Ziel: AAS Leitungssatz-Instanz OEM
-   Kategorie: Abgeleitet aus/Entspricht
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Tier 1 beschreibt für seine LS-Instanz, auf Basis welcher Order durch den OEM diese produziert wurde

**Use Case:**

-   Datenhaltung beim Tier1, welche Änderungen bei einer LS-Instanz beinhaltet/berücksichtigt sind
-   Tier 1 muss auskunftsfähig sein, wenn beim OEM Fehler für eine bestimmte LS-Instanz auftreten

**Kommentar:**

-   \---

#### Freigabe-Beziehungen

##### Freigabe von Tier2-Komponente für OEM-Komponente

**Klassifizierung:**

-   Quelle: AAS-Komponente OEM
-   Ziel: AAS-Komponente Tier 2
-   Kategorie: Freigabe
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   OEM beschreibt für seine Komponente, welche Tier2-Komponente(n) zur Verwendung durch den Tier1 freigegeben sind

**Use Case:**

-   Tier 1 erhält vom OEM einen Leitungssatz mit (OEM-)Komponenten und kann ermitteln, welche Lieferanten er für die Realisierung nutzen darf

**Kommentar:**

-   Je nach Komponente legt der OEM entweder einen oder mehrere Lieferanten fest (s.u.), oder er überlässt die Auswahl dem Tier1
-   Analoge Beziehung zu 1.2.2.4.2

##### Freigabe von Tier2-Komponente für Tier1-Komponente

**Klassifizierung:**

-   Quelle: AAS-Komponente OEM
-   Ziel: AAS-Komponente Tier 1
-   Kategorie: Freigabe
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Tier 1 beschreibt für seine Komponente, welche Tier2-Komponente(n) zur Verwendung von ihm selbst freigegeben sind

**Use Case:**

-   Nach der Ersetzung der OEM-Teilenummern durch seine eigenen Tier1-Sachnummern kann der Tier 1 ermitteln, welche Lieferanten er nutzen kann. Dazu nutzt er auch die Beziehung "Freigabe von Tier2-Komponente für OEM-Komponente"

**Kommentar:**

-   Analoge Beziehung zu 1.2.2.4.1

##### Freigabe von OEM-Komponente für Tier2-Komponente

**Klassifizierung:**

-   Quelle: AAS-Komponente Tier 2
-   Ziel: AAS-Komponente OEM
-   Kategorie: Freigabe
-   Kardinalität: 1-zu-n

**Beschreibung:**

-   Tier2 beschreibt für seine Komponente, für welche(n) OEM(s) bzw. welche OEM-Komponente(n) diese freigegeben ist

**Use Case:**

-   Tier 1 kann ermitteln, ob ein als Lieferant ausgewählter Tier 2 für den aktuellen OEM freigegeben ist

**Kommentar:**

-   Resultat des "Approved Production Part Process", den der Tier2 durchläuft

### Typisierte Beziehungen und Merkmalsfestlegungen

#### Zuordnung von Prozessschritten zu verarbeiteten Komponenten

**Klassifizierung:**

-   Quelle: Element aus Teilmodell „Produktionsprozess“ (Tier 1)
-   Ziel: Element aus Teilmodell „Produkt“ (Tier 1)
-   Kategorie: Typisierte Beziehung
-   Kardinalität:

**Beschreibung:**

-   Das Prozessmodell beschreibt die zur Fertigung eines LS/Halbfabrikats durchzuführenden Schritte (bspw. Schneiden, Crimpen, …). Jeder Schritt bezieht sich dabei auf eine oder mehrere Komponente(n), bspw. Schneiden von Leitung x oder Crimpen von Kontaktteil y an Leitung x.

**Use Case:**

-   MES/Verarbeitungsmaschine kann benötigte Parameter (bspw. Leitungslänge) für einen durchzuführenden Schritt automatisch aus der verlinkten Komponente aus dem Produktmodell auslesen

**Kommentar:**

-   Eigentlich nicht Teil der Verbundkomponente, da lediglich Beziehung zwischen zwei Teilmodellen des gleichen Assets; muss aber trotzdem abgebildet werden

#### Prozessparameter festlegen (bspw. Crimp-Kraft)

**Klassifizierung:**

-   Quelle: Element aus Teilmodell „Produktionsprozess“ (Tier 1)
-   Ziel: Element aus Teilmodell „Produkt“ (Tier 1)
-   Kategorie: Merkmalsfestlegung
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Bei der Zuordnung von Prozessschritten zu Komponenten (s.o.) sind manche Parameter bereits aus dem Produktmodell ersichtlich (bspw. Länge Leitung x). Andere Parameter werden jedoch explizit festgelegt (bspw. Leitungszugabe oder Crimp-Kraft).

**Use Case:**

-   MES/Verarbeitungsmaschine kann benötigte Parameter (bspw. Crimp-Kraft) für einen durchzuführenden Schritt automatisch aus der Beziehung auslesen

**Kommentar:**

-   Eigentlich nicht Teil der Verbundkomponente, da lediglich Beziehung zwischen zwei Teilmodellen des gleichen Assets; muss aber trotzdem abgebildet werden
-   Erweiterung der Beziehung 1.2.2.2

#### Required Capability resultiert aus Prozessschritt

**Klassifizierung:**

-   Quelle: Element aus Teilmodell „Produktionsprozess“ (Tier 1)
-   Ziel: Element aus Teilmodell „Required Capabilities“ (Tier 1)
-   Kategorie: Typisierte Beziehung
-   Kardinalität: 1-zu-1

**Beschreibung:**

-   Modellierung, aus welchem Prozessschritt eine "Required Capability" resultiert

**Use Case:**

-   Bei Änderungen am Prozessmodell kann nachvollzogen werden, dass auch die "Required Capabilities" entsprechend angepasst werden müssen

**Kommentar:**

-   Eigentlich nicht Teil der Verbundkomponente, da lediglich Beziehung zwischen zwei Teilmodellen des gleichen Assets; muss aber trotzdem abgebildet werden

### Umsetzung der ermittelten Beziehungen

Um die in Abschnitt 1.2.2 ermittelten Beziehungen im Rahmen der VBK „Produkt“ abbilden zu können, müssen diese im Rahmen der entsprechenden Quell-Verwaltungsschale modelliert werden. Dabei erfordert jede der fünf in Abschnitt 1.2.2 ermittelten Kategorien von Beziehungen eine eigene Art der Umsetzung. Diese sind im Folgenden beschrieben.

#### Hierarchische Beziehungen

Zur Abbildung von hierarchischen Beziehungen bietet sich das Teilmodell „Bill of Material“ [3] der IDTA[^1] an. Dieses ermöglicht sowohl die Abbildung von Top-Down- als auch von Bottom-Up-Beziehungen. Die gleichzeitige Abbildung sowohl von Top-Down- als auch von Bottom-Up-Beziehungen erfordert allerdings einen erhöhten Datenpflege-Aufwand. Daher wurde im Rahmen von AP5.2 entschieden, auf die explizite Abbildung von Bottom-Up-Beziehungen zu verzichten. Werden diese Informationen benötigt, so können diese stattdessen auch über eine Rückwärtssuche der inversen Beziehung realisiert werden.

[^1]: <https://industrialdigitaltwin.org/wp-content/uploads/2023/04/IDTA-02011-1-0_Submodel_HierarchicalStructuresEnablingBoM.pdf>

Abbildung 1--3 zeigt exemplarisch ein BOM-Modell, welche die Beziehungen „Leitungssatz enthält Komponenten“ umsetzt.

![image](https://github.com/user-attachments/assets/f8abcf91-3dde-4181-974c-eae47db6bbf8)

*Abbildung 1-3: Umsetzung hierarchischer Beziehungen mit Hilfe des BOM-Teilmodells*

Unterschiedliche Hierarchien sollen in unterschiedlichen BOM-Teilmodellen umgesetzt werden, um für jedes Teilmodell einen klaren Fokus herzustellen. Dies bedeutet für den Leitungssatz bei einem Tier1 bspw., dass unterschiedliche BOM-Teilmodelle für die Komponentensicht (aus welchen Einzelkomponenten setzt sich der Leitungssatz zusammen), die Modulsicht (welche bestellbaren Module definiert das Produktmodell) sowie die Fertigungs-BOM (aus welchen produzierbaren Halbfabrikaten wird der Leitungssatz bzw. ein einzelnes bestellbares Modul gefertigt) existieren.

#### Typ-Instanz-Beziehungen

Typ-Instanz-Beziehungen können in der Verwaltungsschale nativ mit Hilfe der „derivedFrom“-Referenz aus dem AAS-Metamodell[^2] (s. Abschnitt 4.2.2) umgesetzt werden. Analog zu den hierarchischen Beziehungen sollen aus Gründen des Datenpflege-Aufwands lediglich die Beziehungen „Instanz ist von Typ“ explizit modelliert werden. Die inversen Beziehungen „Typ hat Instanzen“ lassen sich auch hier wiederum durch eine Rückwärtssuche ermitteln.

[^2]: <https://industrialdigitaltwin.org/wp-content/uploads/2023/04/IDTA-01001-3-0_SpecificationAssetAdministrationShell_Part1_Metamodel.pdf>

#### Äquivalenz-/Entsprechungs-Beziehungen

Die Notwendigkeit der expliziten Modellierung von Ableitungs- bzw. Entsprechungsbeziehungen ergibt sich aus den Tatsachen, dass das gleiche Asset in der Regel bei unterschiedlichen Firmen/Tiers unter unterschiedlichen Bezeichnern/Sachnummern firmiert. Darüber hinaus kann es notwendig sein, dass jede Firma zu einem Asset (in ihrer eigenen Verwaltungsschale) eigene Daten wie z.B. spezifische Grenzwerte oder Verarbeitungsspezifikationen hinterlegen möchte.

Für die Modellierung solcher Ableitungs- bzw. Entsprechungsbeziehungen bietet Version 3 des Metamodells der Verwaltungsschale2 das Konzept der „SpecificAssetID“ (s. Abbildung 1-4) an. Mit solchen „specific asset IDs“ können für ein Asset neben der eigentlichen assetID („GlobalAssetID“), die einem bestimmten Format unterliegen muss (IRI/IRDI), beliebig viele weitere Bezeichner ergänzt werden. Solche Bezeichner können dabei z.B. die Sachnummern sein, unter denen das Asset bei anderen Firmen geführt wird.

![image](https://github.com/user-attachments/assets/d29eda21-0729-4025-949b-c5c8970e8aa1)

*Abbildung 1-4: Konzept der "Specific Asset ID" aus dem Metamodell der VWS (s. Abschnitt 5.3.4)*

Für die konkrete Umsetzung bedeutet dies, dass

-   für jeden Verweis auf eine externe Sachnummer bzw. auf ein externes Asset eine „SpecificAssetId“ angelegt wird,
-   das Attribut „name“ der ID auf einen entsprechenden sinnvollen Wert festgelegt wird (bspw. „partNumberOEM1“),
-   das Attribut „value“ auf die entsprechende ID/Sachnummer gesetzt wird und
-   (optional) mit Hilfe der „externalSubjectId“ explizit die referenzierte Firma ausgewiesen wird (z.B. über ihre URL).

Abbildung 1-5 zeigt die exemplarische Umsetzung anhand einer Verwaltungsschale für einen Kontakt „MLK 1,2“ bei einem Tier1, die auf die entsprechenden Sachnummern bei zwei OEMs verweist.

![image](https://github.com/user-attachments/assets/c24292fa-d500-438b-9662-422af2b2c31d)

*Abbildung 1-5: Exemplarische Umsetzung des Sachnummern-Mapping mittels „specificAssetId“*

Neben solchen „globalen“ Äquivalenzbeziehungen zwischen Assets kann es auch noch „lokale“ Äquivalenzbeziehungen geben, die bspw. eine Äquivalenz zwischen Entitäten unterschiedlicher BOM-Teilmodelle ausdrücken. Ein Beispiel hierfür stellt die Äquivalenz zweier Leitungs-Instanzen in unterschiedlichen Halbfabrikaten dar. Solche Beziehungen lassen sich mit Hilfe von „sameAs“-Beziehungen aus dem BOM-Teilmodell beschreiben.

#### Freigabe-Beziehungen

Die Modellierung von Freigabe-Listen ist rein mit Elementen des Metamodells der Verwaltungsschale oder mit existierenden AAS-Teilmodellen nicht umsetzbar. Aus diesem Grund wurde im Rahmen von AP5.2 ein eigenes Teilmodell zur Modellierung solcher Freigabe-Listen umgesetzt, welches im Folgenden beschrieben wird.

Grundlage des Teilmodells ist, dass jede Freigabe für das Asset, welches die aktuelle Verwaltungsschale beschreibt, in einer eigenen SubmodelElementCollection beschrieben wird. Kern dieser Freigabe ist ein Verweis auf das freigegebene Asset (realisiert über eine entsprechende Referenz). Ergänzt wird diese Beschreibung der Freigabe um Metadaten (Zeitpunkt der Freigabe, Stand der Freigabe sowie Informationen über die freigebende Person). Darüber hinaus können für eine Freigabe beliebig viele Bedingungen bzw. Einschränkungen in Form sog. *ConditionSets* angegeben werden. Eine typische Einschränkung ist bspw., dass ein Produkt nicht mehr für Neuentwicklungen freigegeben ist, weil es ausläuft. Weitere Einschränkungen können bspw. länderspezifischer oder zeitlicher Natur sein.

Abbildung 1-6 zeigt die gesamte Struktur des Teilmodells.

![image](https://github.com/user-attachments/assets/ea53fe17-bc8e-499f-a2c4-8e8ff2531e19)

*Abbildung 1-6: Teilmodell "Freigabeliste"*

#### Typisierte Beziehungen und Merkmalsfestlegungen

Wie bereits im Rahmen der Definition der einzelnen Beziehungen im Rahmen von Abschnitt 1.2.3 beschrieben, sind diese Beziehungen nicht Teil der Verbundkomponente, müssen aber nichtsdestotrotz abgebildet werden. Diese Abbildung muss dabei im Rahmen des entsprechenden Teilmodells erfolgen, das die Quelle der Beziehung darstellt. Aus diesem Grund wird an dieser Stelle nicht näher auf die konkrete Umsetzung eingegangen.

## AP 5.3 - Verbundkomponente Ressource (Produktionsmittel) und VIBN

### Zielsetzung

Das AP 5.3 beschäftigte sich mit der Ableitung und Definition der Verbundkomponente (VBK) „Ressource“, d.h. für die Produktionsmittel.

Zur Ableitung wurden zunächst zwei Beispiel-Ressourcen analysiert, die typische Vertreter der Produktionsmittel in der Domäne „Leitungssatz“ darstellen. Diese Beispiel-Ressourcen werden in Abschnitt 1.3.2 genauer vorgestellt. Basierend auf diesen Ressourcen wurden typische Use Cases analysiert, die auf Basis des Konzepts der Verbundkomponente realisiert werden können bzw. für die die Beziehungen zwischen den einzelnen Teilen der Verbundkomponente relevant sind. Diese werden in Abschnitt 1.3.3 vorgestellt. Basierend auf diesen Use Cases wurde in Abschnitt 1.3.4 das Konzept der Verbundkomponente „Ressource“ definiert.

In Abschnitt 0 wurde das Thema „Virtuelle Inbetriebnahme“ (VIBN) als wesentlicher Bestandteil der Digitalen Fabrik für Produktionsresourcen des Leitungssatzes besprochen.

Im Rahmen von AP5.3 wurden insgesamt die folgenden Use Cases definiert:

1.  Finden einer Maschine + Werkzeug für eine bestimmte Fähigkeit
2.  Ermittlung des zur Erfüllung einer Fähigkeit notwendigen Werkzeugs
3.  Konfiguration und Bestellung einer Maschine
4.  VIBN für Antriebseinheit vom Komponentenlieferant
5.  VIBN für Prüfmodul

### Beispiel-Ressourcen

Verbundkomponenten betrachten den Aufbau sowie die Struktur zusammengesetzter Systeme auf Basis von Teilsystemen und Komponenten. Um die relevanten, mit Hilfe der Verwaltungsschale nachzubildenden Strukturen zu ermitteln, lohnt zunächst eine Analyse typischer, zu betrachtender Systeme. Zu diesem Zweck wurden zwei repräsentative Vertreter von Produktionsmitteln in der Domäne „Leitungssatz“ ausgewählt, die im Folgenden kurz beschrieben werden sollen.

![image](https://github.com/user-attachments/assets/41ea263e-0002-4f5e-b3f4-c41d45cfb64a)

*Abbildung 1-7: Beispiel-Ressourcen 2 – Wezag UP 150 (links) und Komax Sigma 688 (rechts)*

Als erstes Beispiel wurde die halbautomatische hydraulische Crimpmaschine *UP 150* von Wezag ausgewählt (s. Abbildung 1-7, links). Diese kann per Fußschalter von einem Mitarbeiter bedient werden und Kontakte bis zu einem relativ großen Querschnitt verarbeiten. Die Maschine an sich realisiert dabei im Prinzip lediglich einen Pressvorgang – erst durch Einsatz eines Werkzeugs (Crimpgesenk) sowie eines zugehörigen Adapters wird durch den Pressvorgang ein Crimpvorgang. Crimpvorgänge können bei der Wezag UP 150 zusätzlich durch eine automatische Crimpkraftanalyse begleitet werden, durch die bspw. auf die Qualität bzw. sdas ordnungsgemäße Ausführen des Crimp-Vorgangs geschlossen werden kann.

Das zweite untersuchte Beispiel stellt die vollautomatische Sigma 688 der Firma Komax dar (s. Abbildung 1-7, rechts). Je nach enthaltenen Modulen kann sie unterschiedliche Fähigkeiten wie z.B. Schneiden, Abisolieren oder Crimpen realisieren und dabei vollautomatisiert komplette Chargen von Produkten herstellen. Eine Übersicht über mögliche Fähigkeiten ist in Abbildung 1-8 dargestellt. Zusätzlich zu den in Abbildung 1-8 dargestellten Fähigkeiten ergeben sich je nach verbauten Modulen noch zugehörige Prüf-/Analysefähigkeiten. So kann z.B. überprüft werden, ob bei einem Abisoliervorgang die Leitung beschädigt wurde. Analog zur oben beschriebenen UP 150 benötigt auch die Sigma 688 für das Crimpen ein entsprechendes Werkzeug, welches hier *Applikator* genannt wird.

![image](https://github.com/user-attachments/assets/94b181bb-9698-4bfe-a654-32aac68632ed)

*Abbildung 1-8: Übersicht möglicher Fähigkeiten Komax Sigma 688*

Für beide Maschinen gilt, dass diese für den Kunden prinzipiell eine Blackbox darstellen – der innere Aufbau ist für den Kunden folglich – mit Ausnahme der Möglichkeiten zum Montieren spezieller Werkzeuge – nicht ersichtlich und auch nicht relevant. Dies bezieht sich vor allem bei der Sigma 688 auch auf die verbauten Module: Diese werden in aller Regel einmal bei der Bestellung der Maschine ausgewählt und sind dann – für den Kunden – fest verbaut und Teil der Maschine.

### Betrachtete Use Cases

Bereits im letzten Abschnitt wurde die Tatsache beschrieben, dass die Maschinen zumindest für den Kunden (Leitungssatzkonfektionär) eine Blackbox darstellen. Der innere Aufbau dieser Maschinen bspw. aus unterschiedlichen Komponenten ist daher für den Hauptfokus dieses Projekts – die Auswahl und Nutzung der Maschinen durch den Kunden zur Produktion eines Leitungssatzes – nicht relevant. Eine Ausnahme stellen dabei die Möglichkeiten und Voraussetzungen zur Montage von Werkzeugen dar.

Folglich sind auch die im Rahmen der Verbundkomponente umzusetzenden Beziehungen entsprechend limitiert und beschränken sich auf die sich daraus ergebenden Use Cases:

#### UC1: Finden einer Maschine + Werkzeug für eine bestimmte Fähigkeit

Haupt-Use Case besteht im Finden einer (beim Kunden vorhandenen) Maschine bzw. Maschinen-Instanz, die eine oder mehrere bestimmte Fähigkeiten ausführen kann. Hierbei ist neben dem Vorhandensein der eigentlichen Maschine falls für die entsprechende Fähigkeit notwendig auch das Vorhandensein eines entsprechenden, mit der Maschine kompatiblen Werkzeugs zu prüfen.

#### UC2: Ermittlung des zur Erfüllung einer Fähigkeit notwendigen Werkzeugs

Eng im Zusammenhang mit UC1 steht die Frage danach, welches Werkzeug in einer Maschine montiert werden muss, um eine bestimmte Fähigkeit ausführen zu können. Im Speziellen ist hierbei auch die Frage interessant, welcher Adapter/Modul evtl. benötigt wird, um das Werkzeug montieren zu können (vgl. Abschnitt 1.3.2).

#### UC3: Konfiguration und Bestellung einer Maschine

Einen verwandten und doch erweiterten Use Case stellt die Bestellung einer neuen Maschine durch einen Leitungssatz-Konfektionär bei einem Maschinenlieferanten dar. Hierbei wird der Konfektionär mit einer oder mehreren benötigten Fähigkeiten an den Maschinenlieferanten herantreten, welche daraufhin alle durch ihn angebotenen Maschinentypen durchsuchen und bewerten muss. Diese Bewertung erstreckt sich dabei vor allem auch auf die möglichen Kombinationen von Maschinen mit Erweiterungsmodulen (vgl. Abschnitt 1.3.2).

### Konzept der Verbundkomponente „Ressource“

Die in Abschnitt 1.3.3 betrachteten Use Cases fokussieren auf die Auswertung von durch eine Maschine im Verbund mit einem Werkzeug bereitgestellte Fähigkeiten. Abbildung 1-9 illustriert dies anhand einer Einordnung in den PPR-Kontext.

![image](https://github.com/user-attachments/assets/f72bab86-4037-4b46-a67f-2c9ceb1d003c)

*Abbildung 1-9: Einordnung in das PPR-Modell*

Für die Bewertung, ob eine Maschine eine bestimmte Fähigkeit ausführen kann, spielen – neben der grundsätzlichen Eignung der Maschine für die Fähigkeit – im Wesentlichen zwei Aspekte eine Rolle:

1.  Welches konkrete Werkzeug wird für die Fähigkeit benötigt?
2.  Kann das Werkzeug in die gewählte Maschine montiert werden?

Entsprechend sind diese beiden Aspekte im Rahmen der Verbundkomponente „Ressource“ abzubilden.

Für die Auswahl eines passenden Werkzeugs ist dessen formale *Freigabe* das entscheidende Kriterium. So werden z.B. am Beispiel *Crimpen* für jedes Kontaktteil durch dessen Hersteller ein oder mehrere zu nutzende Werkzeuge explizit freigegeben und damit vorgegeben. Diese Beziehungen lassen sich durch das bereits im Rahmen von AP5.2 entwickelte Teilmodell „[Freigabeliste](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP05/Beispieldaten/SM_Template_ApprovalList.aasx)“ abbilden. Basierend auf „[Sigma688_ApprovedApplicators_Submodel_withoutFiles.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP05/Beispieldaten/Sigma688_with_ApprovedApplicators_Submodel_without_files.aasx)“[^3] zeigt Abbildung 1-10 dies exemplarisch anhand des Kontaktteils MLK 14,5 der Firma Kostal: Abgebildet sind hier die Freigaben für zwei unterschiedliche Werkzeuge – zum einen ein Applikator der Firma Hanke/Demirel und zum anderen eine Hand-Crimpzange der Firma EHC.

[^3]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP05/Beispieldaten/Sigma688_ApprovedApplicators_Submodel_withoutFiles.aasx>

Der zweite Aspekt – die Kompatibilität eines Werkzeugs mit einer Maschine evtl. unter Nutzung eines entsprechenden Applikators – lässt sich in zwei Teil-Aspekte aufteilen:

Die aktuelle Maschinenstruktur, die eine Aussage über aktuell montierte Werkzeuge und damit über die aktuell, ohne Umbau zu realisierenden Fähigkeiten zulässt, lässt sich einfach mit Hilfe des bereits standardisierten Teilmodells „[IDTA 02011: Hierarchical Structures enabling Bills of Material](https://github.com/admin-shell-io/submodel-templates/tree/main/published/Hierarchical%20Structures%20enabling%20Bills%20of%20Material/1/1)“ (BOM) [3] abbilden. Abbildung 1-10 zeigt dies Anhand der Maschine *Sigma 688*, welche mit einem Crimp-Modul *C1340* ausgestattet ist, in welchem wiederum ein Werkzeug (Applikator) *Schäfer 20* montiert ist. Ob das Crimp-Modul explizit mitmodelliert wird oder nicht, ist dabei abhängig vom konkreten umzusetzenden Use Case (vgl. Abschnitt 1.3.3).

Die Abbildung der theoretisch abbildbaren Maschinenstrukturen ist dagegen komplexer – vor allem da sich je nach konkretem Beispiel eine Vielzahl an möglichen Kombinationen ergeben können. Eine Nutzung des BOM-Teilmodells, wie für den ersten Teilaspekt vorgeschlagen, ist dabei aufgrund des hohen Modellierungsaufwands nicht sinnvoll, wie in Abbildung 1-12 zu sehen ist: So muss bei Einführung eines neuen Crimpmoduls explizit jeder kompatible Applikator angegeben werden bzw. bei Einführung eines neuen Applikators jedes kompatible Cirmp-Modul. Stattdessen ist eine implizite Modellierung sinnvoll, die auf einer Abbildung der – bspw. zwischen Modulen und Applikatoren genutzten – Schnittstellen basiert. Eine solche Modellierung lässt sich bspw. auf Basis der „*specificAssetId*“ umsetzen, die bereits im Rahmen von AP5.2 genutzt wurde.

![image](https://github.com/user-attachments/assets/9b6f6947-1b0d-48ef-84e3-c9e0228b3266)

*Abbildung 1-10: Modellierung von Werkzeug-Freigaben am Beispiel Crimp-Kontakt*

![Ein Bild, das Text, Screenshot, Schrift, Zahl enthält. Automatisch generierte Beschreibung](media/77a0bc495ab8ab7d3dcec8e987a14e5b.png)

*Abbildung 1-11: Abbildung der aktuellen Maschinenstruktur mit Hilfe des BOM-Teilmodells*

![Ein Bild, das Text, Screenshot, Schrift, Zahl enthält. Automatisch generierte Beschreibung](media/58e2ee5b08e2dbf8d3413a33e702e4df.png)

*Abbildung 1-12: Abbildung potenzieller Maschinenstrukturen mit Hilfe des BOM-Teilmodells*

Abbildung 1-13 zeigt eine mögliche Implementierung, wo die Kompatibilität sowohl zwischen Maschinen und Modulen als auch zwischen Modulen und Werkzeugen mit Hilfe von specificAssetIds „offered/requiredSlot“ abgebildet wird. Die Einführung bspw. eines neuen Werkzeugs gestaltet sich so extrem einfach, da lediglich für das Werkzeug der entsprechende „requiredSlot“ angegeben werden muss. Eine Anpassung der Verwaltungsschalen der verschiedenen Module ist nicht notwendig.

![Ein Bild, das Text, Software, Webseite, Computersymbol enthält. Automatisch generierte Beschreibung](media/590903961197439f4a03be99374036f8.png)

*Abbildung 1-13: Modellierung potenzieller Maschinenstrukturen per "specificAssetId"*

### Virtuelle Inbetriebnahme

Die Virtuelle Inbetriebnahme (VIBN) ist ein wesentlicher Bestandteil der Digitalen Fabrik und beschreibt eine Simulationsmethodik im digitalen Engineering. Die Idee dahinter ist, dass ein virtuelles Abbild der Anlage bzw. der Maschine bereits in der frühen Phase der Entwicklung erstellt wird. Mit diesem virtuellen Abbild, dass das Verhalten der realen Anlage hinreichend gut beschreibt, wird die Steuerungstechnik bzw. der Steuerungsablauf über das Prozessdatenbild einer realen Steuerung getestet. Bei dem klassischen, sequenziellen Engineering (ohne VIBN), beispielsweise „Wasserfallmodell", werden alle Phasen nacheinander ausgeführt und Prüfungen erst bei dem Factory Acceptance Test (FAT) bzw. bei der Inbetriebnahme (IBN) durchgeführt, was generell zu einer späten Fehlererkennung führt. Eine Studie des Vereins Deutscher Werkzeugmaschinen-fabriken e.V.[^4] (VDW) besagt, dass die IBN 15 bis 25% der Gesamtdurchlaufzeit eines Anlagenprojekts ausmacht. Davon ist 90% der Zeit für die IBN von Elektronik und Steuerungstechnik aufzuwenden, wovon wiederum 70% auf Softwarefehlern beruhen. Durch die Einführung der VIBN bereits in der frühen Phase des Entwicklungsprozesses können die Tätigkeiten der Disziplinen Mechanik, Elektronik und Software stärker parallelisiert werden. Es entwickelt sich ein viel früheres Systemverständnis der Anlage. Dies ermöglicht eine frühzeitige Absicherung und Optimierung der Steuerungsprogramme und somit eine Verkürzung der Entwicklungs- und Inbetriebnahmezeiten.

[^4]: [VDW-Bericht](https://publications.rwth-aachen.de/record/137669): Abteilungsübergreifende Projektierung komplexer Maschinen und Anlagen. Aachen: WZL 1997.

In dem Prozess der VIBN können alle Partner der Wertschöpfungskette involviert sein. Neben dem Maschinenhersteller, der das virtuelle Abbild der Maschine erstellt, und dem Endanwender/OEM, der die reale wie auch virtuelle Anlage betreibt und verwendet, wird die Rolle des Komponentenherstellers zunehmend wichtiger. Für das Erstellen virtueller Anlagenmodelle wird oft das Wissen über die Verhaltensbeschreibung der eingesetzten Komponenten für die Simulation benötigt. Durch die Bereitstellung von Simulationsmodellen durch die Komponentenhersteller hätten Maschinenhersteller weniger Aufwände bei der Erstellung solcher Modelle und würden Modelle in hoher Qualität erhalten, da sie direkt auf das Domänenwissen des Komponentenherstellers zugreifen können.

Um die Bereitstellung und den Austausch von Simulationsmodellen in einer heterogenen Toollandschaft zu ermöglichen, wurde seitens der [Modelica Association](https://modelica.org/) der Functional Mock-Up Interface-Standard[^5] ([FMI](https://fmi-standard.org/)) erarbeitet. Der FMI-Standard ist für die Simulationswelt das, was das [STEP-Format](https://www.iso.org/standard/57620.html) in der CAD-Welt ist. Simulationsdateien in Form von Functional Mock-Up Units (FMU) besitzen nach außen hin standardisierte Schnittstellen. Im Inneren befindet sich das Verhaltensmodell als Black-Box. Diese FMU kann von allen Softwaretools verwendet werden, die den FMI-Standard unterstützen.

[^5]: <https://fmi-standard.org/>

Um die Entwicklung des Modellaustauschs über die Komponentenebene der FMU/FMI hinaus fortzusetzen, wurde unter dem Dach der Modelica Association ein neues Projekt mit dem Namen "System Structure and Parameterization of Components for Virtual System Design"[^6] ([SSP](https://ssp-standard.org/)) aufgesetzt. Hintergrund war, dass die in vielen Anwendungen bestehende Notwendigkeit zur Simulation eines Verbundes bzw. eines Netzwerks von Simulationsmodellen erkannt wurde.

[^6]: <https://ssp-standard.org/>

Der SSP ist ein werkzeugunabhängiger Standard zur Definition kompletter Systeme bzw. Netzwerke, die aus einer oder mehreren FMUs (siehe Functional-Mockup-Interface) einschließlich ihrer Parametrisierung bestehen und zwischen Simulationswerkzeugen übertragen werden können.

#### Beispiel-Ressourcen

Als exemplarisches Beispiel für die virtuelle Inbetriebnahme wurde das in Abbildung 1-14 dargestellte Prüfmodul von Komax Testing verwendet [(„VWS_Komax_Pruefmodul_ohne_Dateien.aasx“[^7]).](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP05/Beispieldaten/VWS_Komax_Pruefmodul_ohne_Dateien.aasx)

[^7]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP05/Beispieldaten/VWS_Komax_Pruefmodul_ohne_Dateien.aasx>

![A 3d model of a machine Description automatically generated](media/81fed18bcb205aa779da1c80c7634565.png)

*Abbildung 1-14: Prüfmodul mit Gegenstecker (Komax Testing)*

Prüfmodule sind mechatronische Baugruppen, die individuell für jeden Stecker und nach Anforderung angefertigt und modular in einer Prüfmaschine eingebaut werden, um vollständige Leitungssätze zu kontaktieren und prüfen. Das Prüfmodul führt diverse Bewegungen aus, die mittels pneumatischer Antriebseinheiten (bestehend aus Ventilen und Zylindern) angetrieben werden. Hierzu gehören:

-   Verriegelung des Steckergehäuses in der Aufnahme.
-   Vorfahren der Kontaktebene zur elektrischen Kontaktierung des Steckers.
-   Vorfahren von Sensoren für die Erfassung von Steckermerkmalen (z.B. Sekundärverriegelung).

Für diese Baugruppe wurden im Design pneumatische Einheiten von Festo eingesetzt, welche die Bewegungen ausführen.

Mittels „specificAssetId“ (vgl. D5.3 Verbundkomponente Ressource (Produktionsmittel)) verweist die Verwaltungsschale des Prüfmoduls auf die in den verwendeten pneumatischen Einheiten verbauten Komponenten, sodass die zugehörigen Verwaltungsschalen eindeutig identifiziert werden können (s. Abbildung 1-15).

![A screenshot of a computer Description automatically generated](media/81f2e96a672b2dba5f8fb5a9d7d7da4d.png)

*Abbildung 1-15: „specificAssetId“ einer pneumatischen Komponente im Prüfmodul*

#### Betrachtete Use Cases

Eine virtuelle Inbetriebnahme soll unter anderem ermöglichen, den Funktionsablauf des Prüfmoduls und die Kontaktsicherheit im Zusammenspiel mit den Steckern des Leitungssatzes zu überprüfen, bevor die Baugruppe montiert und in die Prüfmaschine eingebaut wird, sodass Fehler im Design frühzeitig erkannt und abgestellt werden können.

##### UC4: VIBN der Antriebseinheit vom Komponentenlieferant

Für die ausgelegten Antriebseinheiten (bestehend aus Ventil + Zylinder) sollen vom Hersteller Verhaltensmodelle für die Simulation in Form von Verwaltungsschalen bereitgestellt werden.

##### UC5: VIBN des Prüfmodul

In der Verwaltungsschale des Prüfmoduls sollen Verhaltensmodelle, Verhaltenssimulationen und das kinematische Modell für die virtuelle Inbetriebnahme bereitgestellt und mit den Simulationsmodellen der Antriebseinheiten in Beziehung gesetzt werden.

#### Vorgehen beim Komponentenlieferant

Der Komponentenlieferant stellt zunächst einmal Verwaltungsschalen für seine Einzelkomponenten mit den relevanten Teilmodellen bereit. Im betrachteten Use Case 4 fungiert er jedoch zusätzlich auch als Teilsystem-Lieferant, denn die oben beschriebenen pneumatischen Antriebseinheiten (Verbundkomponenten) setzen sich jeweils aus mehreren Komponenten zusammen: einem Zylinder, der die eigentliche Bewegung ausführt, einem Ventil, welches für die Ansteuerung des Zylinders notwendig ist, sowie weiteren Komponenten wie Schläuche und Fittings, die im Rahmen der virtuellen Inbetriebnahme in aller Regel nicht separat, d.h. in Form von eigenständigen Simulationsmodellen, betrachtet werden.

Solche Teilsysteme werden oftmals durch den Kunden über spezielle Auslegungstools des Komponentenlieferanten konfiguriert. Ein Beispiel hierfür ist das Tool [*Festo Pneumatic Sizing*](https://www.festo.com/de/de/s/pneumatic-sizing)*[^8]*, welches in der Lage ist, für eine gegebene Masse und eine gewünschte Positionieraufgabe automatisch ein geeignetes pneumatisches System zu konfigurieren.

[^8]: <https://www.festo.com/de/de/s/pneumatic-sizing>

Der Komponentenlieferant bzw. das genutzte Auslegungstool stellt folglich eine System-Verwaltungsschale bereit, die über das Teilmodell „[IDTA 02011: Hierarchical Structures enabling Bills of Material](https://github.com/admin-shell-io/submodel-templates/tree/main/published/Hierarchical%20Structures%20enabling%20Bills%20of%20Material/1/1)“ (BOM) eine Bill of Material beschreibt, welches die verschiedenen Komponenten-Verwaltungsschalen referenziert. Im Rahmen des betrachteten Use Cases wurden diese Verwaltungsschalen händisch erstellt, z.B. „[VWS_Festo_Kombinierte_Baugruppe.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP05/Beispieldaten/VWS_Festo_Kombinierte_Baugruppe.aasx)“ (Abbildung 1-16).

![Ein Bild, das Text, Software, Webseite, Computersymbol enthält. Automatisch generierte Beschreibung](media/523f408ef4ee81e13ae8cd26714a91c2.png)

*Abbildung 1-16: Verwaltungsschale einer pneumatischen Antriebseinheit mit Bill of Material*

Um eine virtuelle Inbetriebnahme für das bereitgestellte Teilsystem zu ermöglichen, ist neben der BOM das Teilmodell „[IDTA 02005: Provision of Simulation Models](https://github.com/admin-shell-io/submodel-templates/tree/main/published/Provision%20of%20Simulation%20Models/1/0)“ [4] der zentrale Bestandteil dieser System-Verwaltungsschale, denn dieses ermöglicht die Bereitstellung eines Simulationsmodells für das System, welches in Folgeprozessen genutzt werden kann. Es ist dabei grundsätzlich unabhängig von der Art bzw. vom Format des bereitgestellten Simulationsmodells. Um die Verwendung dieses Modells in möglichst vielen Zielumgebungen zu ermöglichen, ist es für den Komponentenlieferanten jedoch sinnvoll, Simulationsmodelle in einem anerkannten Standardformat anzubieten. Hierbei eignen sich für Einzelkomponenten der FMI-Standard und für Verbundkomponenten der SSP-Standard.

Für den betrachteten Anwendungsfall wurden zunächst die Simulationsmodelle für die Magnetventile und Zylinder auf Basis des FMI-Standards beschrieben. Darauf aufbauend, wurde eine Antriebseinheit, bestehend aus einem Magnetventil und einem Zylinder, mithilfe des SSP-Standards beschrieben. In Abbildung 1-17 ist das Netzwerk der FMUs in der Simulationsumgebung sowie die Beschreibung des Netzwerks im SSP-Standard.

![A screenshot of a computer program Description automatically generated](media/f8b3a307d0d862c747566fd520876f75.png)

*Abbildung 1-17: Netzwerk aus FMU-Modellen für eine pneumatische Antriebseinheit (rechts).*

#### Vorgehen beim Maschinenhersteller

Ausgangssituation für die Simulation sind mehrere Verwaltungsschalen für die Einzel- und Verbundkomponenten:

-   Magnetventil
-   Zylinder
-   Antriebseinheit (Verbundkomponente)
-   Prüfmodul (Verbundkomponente)

Für die Simulationsumgebung wurden mehrere Teilsysteme beschrieben:

-   Verhaltensmodell für Einzelkomponenten auf Basis des FMI-Standards (siehe Kapitel 1.3.5.3)
-   Verhaltensmodell für Verbundkomponenten (Netzwerk von Einzelkomponenten) auf Basis des SSP-Standards (siehe Kapitel 1.3.5.3).
-   Kinematisches Modell basierend auf dem CAD-Modell
-   Logisches Verhaltensmodell in Form einer SPS-Simulation

Eingesetzte Werkzeuge (siehe Abbildung 1-18):

-   [Siemens TIA-Portal](https://www.siemens.com/de/de/produkte/automatisierung/industrie-software/automatisierungs-software/tia-portal.html)[^9]: SPS-Programmierung.
-   [Siemens SIMATIC S7-PLCSIM Advanced](https://xcelerator.siemens.com/global/en/all-offerings/products/s/s7-plcsim-advanced.html)[^10]: SPS-Simulation.
-   [EDAG iSILOG Toolbox](https://smartfactory.edag.com/en/smart-factory/digitalization-solutions/isilog-toolbox/)[^11]: Verhaltenssimulation des Netzwerks auf Basis des SSP-Standards.
-   [Siemens SIMIT Simulation Plattform[^12]](https://www.siemens.com/global/en/products/automation/industry-software/simit.html): Verhaltenssimulation auf Basis des FMI-Standards.
-   [Siemens NX Mechatronics Concept Designer](https://plm.sw.siemens.com/en-US/nx/cad-online/automation/mechatronic-design/)[^13]: kinematische Simulation.

[^9]: <https://www.siemens.com/de/de/produkte/automatisierung/industrie-software/automatisierungs-software/tia-portal.html>

[^10]: <https://xcelerator.siemens.com/global/en/all-offerings/products/s/s7-plcsim-advanced.html>

[^11]: <https://smartfactory.edag.com/en/smart-factory/digitalization-solutions/isilog-toolbox/>

[^12]: <https://www.siemens.com/global/en/products/automation/industry-software/simit.html>

[^13]: <https://plm.sw.siemens.com/en-US/nx/cad-online/automation/mechatronic-design/>

![Ein Bild, das Text, Screenshot, Software, Design enthält. Automatisch generierte Beschreibung](media/1b105bc41b6410f45fb8b6b5093cfc72.png)

*Abbildung 1-18: Eingesetzte VIBN-Tools*

#### Darstellung in der Verwaltungsschale

In der Verwaltungsschale des Prüfmoduls werden die Antriebseinheiten über eine Stückliste identifiziert. Hierfür wurde das Teilmodell „[IDTA 02011: Hierarchical Structures enabling Bills of Material](https://github.com/admin-shell-io/submodel-templates/tree/main/published/Hierarchical%20Structures%20enabling%20Bills%20of%20Material/1/1)“ (BOM) verwendet.

Für die Simulationsmodelle wurde das Teilmodell „[IDTA 02005: Provision of Simulation Models](https://github.com/admin-shell-io/submodel-templates/tree/main/published/Provision%20of%203D%20Models/1/0)“ [4] eingesetzt. Insgesamt wurden vier Modelle hinterlegt:

-   Das kinematische Modell aus Siemens NX Mechatronics Concept Designer
-   Das logische Verhaltensmodell aus Siemens SIMIT Simulation Plattform
-   Das SPS-Verhaltensmodell aus Siemens SIMATIC S7-PLCSIM Advanced
-   Die Konfiguration für die Co-Simulation aus PLCConnect (EDAG iSILOG Toolbox)

Damit wird UC2 erfüllt. Anhand der Stückliste sind die Antriebseinheiten auffindbar und werden eindeutig mit der Verwaltungsschale des Prüfmoduls verknüpft. Alle Simulationsmodelle werden im Teilmodell „*SimulationModels*“ bereitgestellt.

![A screenshot of a computer Description automatically generated](media/cb917a8b8bd6f896fbc14f895d415d8d.png)

*Abbildung 1-19: Simulationsmodelle in der Verwaltungsschale des Prüfmoduls*

### Ausblick

Auf Grundlage der in AP5.3 beschriebenen Lösungsansätze können Simulationsmodelle partnerübergreifend vernetzt und zu komplexen Verbundsimulationen zusammengeführt werden.

Damit Teilmodelle auch in den Simulationswerkzeugen referenziert werden können, müssen die entsprechenden Werkzeuge und Standards (SSP, FMU, etc.) angepasst werden, sodass die Simulationen in verteilten Systemen bereitgestellt werden können. Beispiel: Der SSP-Standard erfordert aktuell, dass alle Teilmodelle sich in der Simulationsdatei (.ssp) befinden – eine Referenzierung externer Simulationsmodelle bspw. innerhalb einer separaten Verwaltungsschale wäre wünschenswert und würde einer Daten-/Modelldopplung entgegenwirken.

## AP 5.4 - Integration der Verwaltungsschalen

### Zielsetzung

Zum Aufzeigen der sich aus der verknüpften Verbundstruktur von Verwaltungsschalen ergebenden Mehrwerte wurden im Rahmen von AP5.4 die folgenden vier Use Cases definiert:

1.  Rückverfolgbarkeit im Fehlerfall
2.  Synchronisierung von Verwaltungsschalen
3.  Sachnummern-Mapping
4.  Fähigkeitenabgleich

Darauf aufbauend behandelt dieses Dokument die Integration der Verwaltungsschalen über die verschiedenen Aspekte des PPR-Modells mit dem Ziel, eine durchgehende Erkundbarkeit der Verbundstruktur zu erreichen. Hierzu werden vier verschiedene Use Cases definiert und deren Umsetzbarkeit auf Basis der miteinander verknüpften Verwaltungsschalen analysiert.

In Kooperation der Teilprojekte 2, 3 und 5 sowie des Architekturteams wurden für alle betrachteten Aspekte aus den Bereichen Produkt, Prozess und Ressource exemplarische Verwaltungsschalen für das im Rahmen des PPR-Workshop definierte Beispielprodukt angelegt und gemäß der entwickelten Konzepte miteinander verknüpft. Ein Ausschnitt aus den resultierenden Verwaltungsschalen zeigt Abbildung 1-20. An dieser Stelle soll dabei nicht näher auf Spezialthemen aus den einzelnen Teilprojekten bzw. Themenbereichen eingegangen werden, da diese jeweils im Rahmen der zugehörigen Arbeitspakete beschrieben sind. Stattdessen sollen im Folgenden exemplarische Use Cases sowie deren Umsetzung diskutiert werden, die die sich aus der verknüpften Verbundstruktur ergebenden Mehrwerte aufzeigen.

![Ein Bild, das Text, Screenshot, Zahl, parallel enthält. Automatisch generierte Beschreibung](media/ea20f81d8ce917f2c9902226c8103444.png)

*Abbildung 1-20: Ausschnitt der erstellten Verwaltungsschalen*

### Definition und Umsetzung der Use Cases

Im Folgenden sollen die eingangs genannte vier Use Cases, deren Umsetzung sowie der sich ergebende Mehrwert genauer beschrieben werden.

#### Use Case 1: Rückverfolgbarkeit im Fehlerfall

Bei der Rückverfolgbarkeit im Fehlerfall geht es darum, bei Auftreten eines Fehlers dessen Ursachen ermitteln zu können und entsprechende Auswirkungen gering zu halten bzw. gezielt zu korrigieren. Dadurch können beispielsweise Rückrufe verringert werden, wodurch dieser Use Case eine enorme wirtschaftliche Relevanz besitzt.

Eine typische Ausprägung sieht dabei wie folgt aus: Bei einem ausgelieferten Fahrzeug bzw. dem enthaltenen Leitungssatz wird ein Mangel festgestellt – bspw. eine fehlerhafte Crimpverbindung. Mögliche Fehlerursachen können hierbei eine fehlerhafte Charge einer Komponente (z.B. eines Kontaktteils) oder ein fehlerhaft ausgeführter Prozess der entsprechenden Crimp-Maschine sein. Im Folgenden geht es nun darum, die Ursache der fehlerhaften Verbindung zu ermitteln und – falls ähnliche Fehler in anderen ausgelieferten Leitungssätzen nicht ausgeschlossen werden können – die betroffenen Fahrzeuge zurückzurufen und zu kontrollieren bzw. zu reparieren. Durch eine fehlende oder mangelhafte Rückverfolgbarkeit können in diesem Fall sehr hohe Kosten entstehen, da im Zweifelsfall sehr viele Fahrzeuge zurückgerufen werden müssen. Je besser die Rückverfolgbarkeit, desto besser lässt sich der Kreis der potenziell betroffenen Fahrzeuge einschränken, die zurückgerufen werden müssen. Im Folgenden soll allgemein beschrieben werden, wie eine Rückverfolgbarkeit für das beschriebene Szenario realisiert werden kann. Eine detailliertere Beschreibung zur konkreten Umsetzung anhand zweier weiterer Use Cases wurde in der AG „Rückverfolgbarkeit“ des Architekturteams entwickelt und ist im entsprechenden Dokument zu finden.

Im oben geschilderten Beispiel ist dazu die folgende „Spur“ durch das Netzwerk verknüpfter Verwaltungsschalen zu verfolgen: Zunächst ist anhand der Serien- bzw. Fahrzeugidentifikationsnummer (FIN) die zu der Produktinstanz gehörige Verwaltungsschale des Leitungssatzes zu ermitteln. In dieser Verwaltungsschale befindet sich wie in TP 2 definiert die Produktspezifikation in Form von Zeichnungen sowie eines formalen Modells (VEC bzw. KBL). Abbildung 1-21 zeigt exemplarisch eine solche Zeichnung eines Leitungssatzes. Anhand dieser Informationen kann dann die fehlerhafte Verbindung bzw. die betroffenen Komponenten-Vorkommen eindeutig identifiziert werden. In Abbildung 1-21 könnte bspw. die Crimp-Verbindung am Kontaktteil fehlerhaft sein, welches in Kammer 1 des Gehäuses „A2\*1-B“ gesteckt wird.

![Ein Bild, das Text, Messschieber, Diagramm, Reihe enthält. Automatisch generierte Beschreibung](media/3d04feb8feea5b9f444ad032e8b44443.png)

*Abbildung 1-21: Exemplarische Zeichnung Leitungssatz inkl. Komponentenbezeichnungen*

Durch die im Rahmen der AG „Verlinkung“ im Architekturteam geschaffenen Strukturen kann anschließend genau dieses Komponenten-Vorkommen bis hin zur Verwaltungsschale des Halbfabrikats verfolgt werden, im Rahmen dessen Herstellungsprozesses die entsprechende Verbindung hergestellt wurde. In dieser Verwaltungsschale finden sich wie in TP 3 definiert die Liste der bei der Herstellung des Halbfabrikats durchgeführten Prozesse sowie die im Rahmen der Prozesse verwendeten Materialien.

An dieser Stelle kann nun die eigentliche Fehlersuche bzw. die Ermittlung der Auswirkungen beginnen. So können bspw. die als Teil der ausgeführten Prozesse gespeicherten Parameter (bspw. Crimp-Kraft-Verläufe) analysiert werden. Durch die konsistente Verknüpfung der Verwaltungsschalen für den Produktionsprozess kann anschließend unter anderem auch ermittelt werden, welche Halbfabrikate noch als Teil der gleichen Charge (Lot bzw. Batch) produziert wurden. Da jede Verwaltungsschale für einen Produktionsprozess außerdem auch eindeutig die genutzte(n) Chargen von Ausgangsmaterialien ausweist, kann durch eine Rückwärtssuche im Folgenden ermittelt werden, welche anderen Halbfabrikate ebenfalls Vorkommen einer möglicherweise fehlerhaften Charge enthalten.

Auf Basis einer solchen Menge potenziell ebenfalls betroffener Halbfabrikate kann anschließend durch ähnliche Mechanismen wie oben beschrieben zunächst auf die betroffenen Leitungssätze sowie auf die genaue Position der verbauten möglicherweise fehlerhaften Halbfabrikate in diesen Leitungssätzen geschlossen werden. Auf Basis dieser Informationen können durch die Seriennummer der Leitungssätze zunächst die betroffenen Fahrzeuge ermittelt und zurückgerufen sowie die potenziell fehlerhaften Crimp-Verbindungen gezielt überprüft werden.

#### Use Case 2: Synchronisierung von Verwaltungsschalen

Im Rahmen der AG „Modularisierung“ des Architekturteams wurde bereits beschrieben, dass jeder Partner der Wertschöpfungskette die für ihn relevanten Daten normalerweise in einem eigenen Server/Repository aufbewahren will, damit eine durchgängige Datenverfügbarkeit gewährleistet ist. Dies führt zu vielfältigen Dopplungen von Daten, die für mehrere Partner der Wertschöpfungskette relevant sind.

Wie im Rahmen von TP 2 beschrieben, existiert darüber hinaus in aller Regel nicht die „eine Wahrheit“ (Single Source of Truth) für Informationen bspw. zu einer Komponente oder einer Produktspezifikation für einen Leitungssatz. Stattdessen haben verschiedene Partner der Wertschöpfungskette eine teilweise unterschiedliche – unter Umständen sogar widersprüchliche – Datenbasis.

Für Komponenten können dies bspw. unterschiedliche Grenzwerte sein, im Rahmen derer die Komponente verwendet werden darf: So schreibt bspw. der Komponentenhersteller (Tier 2) bestimmte Grenzwerte vor, die von unterschiedlichen OEMs ggf. weiter eingeschränkt werden. Ein weiteres Beispiel ist eine Produktspezifikation, für die grundsätzlich unterschiedliche Daten bei OEM und Konfektionär (Tier 1) existieren, weil der Konfektionär in aller Regel noch zusätzliche Teile ergänzt, die lediglich für die Produktion bzw. Montage relevant sind (bspw. Klebebänder).

In solch einem heterogenen Umfeld ist die (semi-)automatische Synchronisierung bzw. Änderung von Daten essenziell. Nur so kann gewährleistet werden, dass Änderungen von Datenständen anderen Partnern bekannt gemacht und von diesen – unter Umständen nach einer manuellen Überprüfung oder Anpassung – übernommen werden können. Dadurch wird die Gefahr nicht-konsistenter Daten reduziert und die gemeinsame Wertschöpfung erleichtert

Heutzutage erfolgt eine solche Synchronisierung in aller Regel manuell. So werden Änderungen bspw. per E-Mail kommuniziert. Durch den Verbund verknüpfter Verwaltungsschalen ergibt sich nun die Möglichkeit, Änderungen automatisiert zu kommunizieren und falls notwendig zu übernehmen. Dazu wurde im Rahmen der AG „Synchronisierung“ des Architekturteams ein auf dem Publish-Subscribe-Modell basierendes Konzept entwickelt, um Änderungen an bestimmten Verwaltungsschalen bzw. Teilmodellen zu „abonnieren“. Eine entsprechende Änderungsnachricht kann dann automatisiert ausgewertet werden und die entsprechende Änderung automatisch oder bspw. nach einer manuellen Prüfung übernommen werden.

#### Use Case 3: Sachnummern-Mapping

Für eine Komponente – bspw. einen bestimmten Crimp-Kontakt – existieren in aller Regel mehrere Teile- bzw. Sachnummern: So gibt es für eine Komponente oftmals mehrere Lieferanten (Tier 2), die jeweils eine eigene Teilenummer vergeben. Darüber hinaus hat auch jeder OEM sowie jeder Konfektionär (Tier 1) eine eigene Sachnummer, unter der er die Komponente in seinem ERP-System führt. Eine Herausforderung bei der Leitungssatz-Entwicklung ist daher das sogenannte „Sachnummern-Mapping“: So erstellt bspw. der OEM eine Produktspezifikation für einen Leitungssatz und verwendet dabei seine internen Sachnummern für die verwendeten Komponenten. Anschließend wird ein Konfektionär mit der Produktion des Leitungssatzes beauftragt. Daraufhin muss dieser zunächst für jede OEM-Sachnummer seine entsprechende eigene Sachnummer ermitteln und diese in der Produktspezifikation ersetzen. Bei der anschließenden Ermittlung möglicher Lieferanten müssen wiederum für die internen Sachnummern des Konfektionärs die entsprechenden Sachnummer möglicher Zulieferer ermittelt werden.

Derzeit sind solche „Mapping-Tabellen“ in aller Regel informell auf sog. „Zeichnungen“ der verschiedenen OEMs spezifiziert wie in Abbildung 1-22 dargestellt. Diese informellen Informationen müssen dann in einem aufwändigen Prozess häufig noch von Hand in die ERP-Systeme der verschiedenen Konfektionäre eingepflegt werden.

Im Rahmen von TP5.2 wurde daher ein Mechanismus beschrieben, wie man diese bisher informell im Rahmen von Zeichnungen ausgetauschten Informationen formal und explizit im Rahmen der entsprechenden Verwaltungsschalen abbilden kann, um somit den Prozess des Sachnummern-Mappings zu erleichtern. Dazu können in einer Verwaltungsschale bspw. einer Komponente neben der eigenen auch noch eine beliebige Anzahl „externer“ Sachnummern hinterlegt werden, wodurch der Prozess des Sachnummern-Mappings automatisiert werden kann.

![Ein Bild, das Text, Reihe, Screenshot, Zahl enthält. Automatisch generierte Beschreibung](media/91afba3f2b46239102eee3d7a81ce19a.png)

*Abbildung 1-22: Exemplarische OEM-Komponentenspezifikation inkl. Sachnummern*

#### Use Case 4: Fähigkeitenabgleich

Eine entscheidende Voraussetzung für die Produktion eines Leitungssatzes bzw. der enthaltenen Halbfabrikate ist die Ermittlung möglicher Ressourcen, auf denen die für die Produktion des Leitungssatzes/Halbfabrikats notwendigen Prozesse umgesetzt werden können. Grundlage dafür ist ein Fähigkeitenabgleich, der die zur Produktion eines Halbfabrikats benötigten Fähigkeiten mit den von Ressourcen angebotenen Fähigkeiten vergleicht und auf Basis dieses Vergleiches ein bestimmtes Subset an geeigneten Maschinen ermittelt.

Ein solcher Algorithmus zum Fähigkeitenabgleich wurde im Rahmen von TP5.5 entwickelt und basiert auf Informationen aus verschiedenen Verwaltungsschalen aus dem gesamten PPR-Kontext:

Ausgangspunkt ist dabei die Produktspezifikation eines Halbfabrikats bzw. eines Leitungssatzes, in der die eingesetzten Komponenten sowie die benötigten Verbindungen beschrieben sind. Auf dieser Basis können anschließend die zur Herstellung des Produkts benötigten Prozesse ermittelt und in Form der sog. „Bill of Process“ beschrieben werden (s. TP 3). Für eine durchgängige Verknüpfung verweisen dabei die Prozesse auf die verarbeiteten Komponenten, wie bereits in Abschnitt 1.4.2.1 beschrieben. Für jeden Prozess wird anschließend eine sog. „Required Capability“ beschrieben, die die zur Durchführung des Prozesses benötigte Fähigkeit beschreibt. Die entsprechenden Parameter (bspw. die Leitungslänge bei einem Schneidprozess) ergibt sich dabei aus dem Prozessmodell bzw. indirekt aus der Produktspezifikation.

Auf der anderen Seite stehen Ressourcen, die bestimmte Fähigkeiten anbieten und dabei bestimmte Randbedingungen für Parameter beschreiben (bspw. die maximal mögliche Länge bei einem Schneid-Prozess). Ein weiterer wichtiger Punkt ist die explizite Modellierung eventuell notwendiger Werkzeuge zur Durchführung eines Prozesses (z.B. eines Crimp-Applikators zum Herstellen einer Crimp-Verbindung durch eine Maschine). Hierdurch werden Ressourcen-Verwaltungsschalen im Rahmen einer Verbundkomponente miteinander verbunden.

Im Rahmen des Fähigkeitenabgleichs werden nun diese Informationen aus den Bereichen Produkt, Prozess und Ressource genutzt und automatisiert ausgewertet. Das Netzwerk verknüpfter Verwaltungsschalen kann dabei entweder im Rahmen einer Typ- oder einer Instanz-Abfrage ausgewertet werden: Bei einer Typ-Abfrage werden mögliche Maschinen inkl. evtl. zu montierender Werkzeuge ermittelt während bei einer Instanz-Abfrage die in einer Maschine montierten Werkzeuge ausgewertet werden.

Somit bietet der automatisierte Fähigkeitenabgleich das Potenzial für eine effiziente Produktionssteuerung auf Basis der im Rahmen von Verwaltungsschalen bereitgestellten Informationen, bei der bspw. auch weitere, evtl. in zusätzlichen Teilmodellen bereitgestellte Informationen wie Energieverbräuche oder Rüstzeiten mitberücksichtigt werden können.

## AP 5.5 - Mapping zwischen Produktionsressource und Leitungssatz

### Zielsetzung

Das AP 5.5 befasst sich mit dem Mapping zwischen Produktionsressource und Leitungssatz, d.h. mit der automatisierten Auswahl bestimmter Produktionsressourcen zur Fertigung eines Leitungssatzes oder eines Halbfabrikats.

Im Rahmen einer solchen Fertigung sind Prozesse auszuführen. Kern einer Bewertung, ob eine bestimmte Ressource ein bestimmtes Produkt fertigen kann, sind daher die Fähigkeiten, die zur Fertigung eines bestimmten Produktes benötigt werden, sowie die Fähigkeiten, die von einer bestimmten Produktionsressource bereitgestellt werden.

Basierend auf diesen Informationen kann ein Fähigkeitenabgleich („Capability Matching“) durchgeführt werden, im Rahmen dessen eine Bewertung der Erfüllbarkeit einer geforderten Fähigkeit durch eine Ressource durchgeführt wird. Besonders zu beachten ist, dass eine Ressource zur Bereitstellung einer Fähigkeit oftmals noch weitere Ressourcen benötigt: Ein Beispiel hierfür ist eine Crimp-Maschine, die zum Crimpen noch mit einem bestimmten Crimp-Gesenk bzw. einem entsprechenden Applikator ausgestattet werden muss. Für diese Montage kann dann evtl. noch ein entsprechendes Modul oder ein Adapter benötigt werden. Die verschiedenen Teilressourcen bieten dann gemeinsam eine bestimmte kombinierte Fähigkeit an.

Die Abbildung solcher – sowohl aktueller als auch theoretisch realisierbarer – Maschinenstrukturen wurden bereits im Rahmen von D5.3 beschrieben und können an dieser Stelle genutzt werden.

Abbildung 1-23 zeigt diese Zusammenhänge am Beispiel eines Crimp-Prozesses. Die dargestellten Prinzipien gelten aber auch für die anderen im Rahmen von TP3 abgeleiteten Prozesse, wobei für manche Prozesse in der Regel keine Werkzeuge benötigt werden (z.B. Schneiden).

![](media/795c9156781651d6fbdddb03f5fbe1ee.png)

*Abbildung 1-23 Capability-Matching am Beispiel eines Crimp-Prozesses*

Entsprechend der Abbildung werden im Rahmen dieses Dokuments zunächst in den Abschnitten 1.5.2 und 1.5.3 die Modellierung von geforderten und angebotenen Fähigkeiten diskutiert. Darauf aufbauend wird in Abschnitt 1.5.4 anschließend das Konzept für einen Algorithmus zum Fähigkeitenabgleich entwickelt. Abschließend wird in Abschnitt 0 die Frage diskutiert, wie von einer Fähigkeit auf den ausführbaren *Skill* verwiesen werden kann.

### Modellierung geforderter Fähigkeiten

Für die Beschreibung von Fähigkeiten ist das Teilmodell „[IDTA 02020 Capability Description](https://github.com/admin-shell-io/submodel-templates/tree/main/development/Capability/1/0)“ [5] bei der IDTA in Entwicklung, konnte jedoch noch nicht in VWS4LS verwendet werden. Allerdings wurde im Rahmen des Forschungsprojektes [*BaSys 4.2*](https://www.iese.fraunhofer.de/blog/basys-4-2-das-basissystem-fuer-industrie-4-0-geht-in-die-naechste-runde/)[^14] ein erster Vorschlag für ein solches Teilmodell erarbeitet, welches die generische Beschreibung von beliebigen *Capabilities* (z.B. „Cut“) und deren Parameter bzw. *Properties* (z.B. „Länge“) ermöglicht. Für *Properties* können darüber hinaus entweder feste Werte vorgegeben oder Einschränkungen formuliert werden, wobei letzteres im Rahmen von BaSys 4.2 nicht bis ins letzte Detail ausgearbeitet wurde.

[^14]: <https://www.iese.fraunhofer.de/blog/basys-4-2-das-basissystem-fuer-industrie-4-0-geht-in-die-naechste-runde/>

Im Rahmen von TP5 wurde beschlossen, das im Rahmen von BaSys 4.2 entwickelte Modell als Ausgangspunkt zu nutzen und um fehlende Aspekte zu erweitern. Ein erster im Rahmen von BaSys 4.2 nicht betrachteter Aspekt ist die Unterscheidung zwischen (zur Herstellung eines Produkts) *benötigten* und (von einer Ressource) *angebotenen* Fähigkeiten. Um klarzustellen, welche Art von Fähigkeiten ein bestimmtes Teilmodell abbildet, müsste im Rahmen einer möglichen Standardisierung bei der IDTA konkrete semantische IDs (z.B. *supplementalSemanticIds*) oder zusätzliche Eigenschaften (z.B. *TypeOfCapability*) für die Unterscheidung der Fähigkeit-Arten bereitgestellt werden. Für die Zwecke dieses Dokuments wurde beschlossen, den Namen (Eigenschaft *idShort*) des entsprechenden Teilmodells entweder auf „*RequiredCapabilities*“ oder „*OfferedCapabilities*“ zu setzen, um so bereits auf den ersten Blick eine Unterscheidung zu ermöglichen.

Innerhalb des Teilmodells kann dann zunächst die in BaSys 4.2 definierte Grundstruktur genutzt werden, wie exemplarisch in Abbildung 1-24 dargestellt. Es lassen sich folglich eine beliebige Anzahl von Fähigkeiten im Rahmen von „CapabilityContainer“-Elementen abbilden, wobei jeder dieser Container ein „Capability“-Element enthält, welches per *SemanticID* eine bestimmte Fähigkeit ausweist.

Für die Leitungssatz-Produktion relevanten Fähigkeiten, die im Rahmen der Zusammenarbeit mit TP3 ausgearbeitet wurden, sind entsprechende *SemanticIDs* nach dem Muster „https://arena2036.de/vws4ls/capability/1/0/\<capability-name\>“ festgelegt worden, also z.B. „https://arena2036.de/vws4ls/capability/1/0/CutCapability“. Eine vollständige Liste der definierten SemanticIDs findet sich in *  
*

*Anhang: Liste von Fähigkeiten und zugehörigen* Parametern.

Für eine Fähigkeit relevante Parameter lassen sich im „*PropertySet*“ beschreiben, wie ebenfalls in Abbildung 1-24 zu sehen. Die im Rahmen der Zusammenarbeit mit TP3 für jede Fähigkeit abgeleiteten relevanten Parameter sind ebenfalls aufgelistet. Der für einen bestimmten Parameter relevante Wert ergibt sich dabei in aller Regel entweder aus dem Produktmodell (bspw. die Länge beim Schneiden einer Leitung) oder aus Anforderungen an die Prozessdurchführung (bspw. ob beim Abisolieren einer Leitung eine Einschneide-Überwachung durchzuführen ist).

![Ein Bild, das Text, Screenshot, Schrift, Zahl enthält. Automatisch generierte Beschreibung](media/458ba63d4375440110caafc264aaf9c5.png)

*Abbildung 1-24: Exemplarisches Teilmodell "RequiredCapabilities"*

### Modellierung angebotener Fähigkeiten

Wie bereits in Abschnitt 1.5.2 erläutert wurde, kann für die Modellierung von durch Ressourcen angebotenen Fähigkeiten grundsätzlich die gleiche Teilmodellstruktur verwendet werden. Gegenüber der Modellierung von benötigten Fähigkeiten ergeben sich hier aber vor allem zwei Unterschiede bzw. Erweiterungen, die im Folgenden genauer diskutiert werden sollen:

-   die Einschränkung von Eigenschaftswerten über sogenannte „*Constraints*“ und
-   die Beschreibung von Fähigkeiten, die sich erst aus dem Zusammenschluss zweier oder mehrerer Ressourcen ergeben.

#### Einschränkung von Parameterwerten

Bei der Beschreibung geforderter Fähigkeiten werden für Parameter in aller Regel feste Werte vorgegeben. Ein Beispiel ist das Schneiden einer Leitung auf eine bestimmte Länge (bspw. 500 mm).

Im Gegensatz dazu kommt es bei der Beschreibung angebotener Fähigkeiten häufig vor, dass für einen Parameter kein einzelner, konkreter Wert definiert werden kann. So kann eine Schneidmaschine Leitungen in der Regel in einem bestimmten, durch die physikalischen Eigenschaften der Maschinen bestimmten, Bereich schneiden (z.B. 50 – 5000 mm).

Um solche Einschränkungen beschreiben zu können, sieht das im Rahmen von BaSys 4.2 definierte Teilmodell bereits das Konzept der *Constraints* vor, die sich auf ein bestimmtes *Property* beziehen, wie in Abbildung 1-25 dargestellt. Die konkrete Modellierung der eigentlichen *Constraints* jedoch wurde im Rahmen von BaSys 4.2 nicht bis ins letzte Detail festgelegt, sodass entsprechende Festlegungen im Rahmen der Arbeit zu AP5.5 getroffen wurden. Die Parameter von Eigenschaften beschreiben in der Regel numerische Werte, Zeichenketten oder boolesche Werte. Dabei sind für unterschiedliche Datentypen von Parametern unterschiedliche Einschränkungen sinnvoll:

-   Für boolesche Werte können bei angebotenen Fähigkeiten in der Regel konkrete Werte angegeben werden (Parameter erfüllt oder nicht erfüllt) – es müssen folglich keine Einschränkungen beschrieben werden.
-   Für numerische Werte ist, wie oben beschrieben, die Vorgabe eines oberen und unteren Grenzwertes sinnvoll. Hierfür kann das AAS-Element *Range* genutzt werden (vgl. Abbildung 1-25).
-   Für Zeichenketten ist oftmals die Vorgabe einer bestimmten Liste von Werten sinnvoll (z.B. die Liste von Teilenummern, für die ein Crimp-Gesenk verwendet werden kann). Hierzu kann das AAS-Element *SubmodelElementList* genutzt werden.

Weitere Arten von *Constraints* sind theoretisch denkbar (bspw. die Vorgabe einer bestimmten *Regular Expression* für Zeichenketten), wurden im Rahmen dieses Projekts aber nicht weiter betrachtet. Das beschriebene Konzept lässt sich aber entsprechend erweitern.

![Ein Bild, das Text, Screenshot, Schrift, Zahl enthält. Automatisch generierte Beschreibung](media/95c1660ece832b6ca2ac5875c966eeb7.png)

*Abbildung 1-25: Exemplarisches Teilmodell "OfferedCapabilities"*

Eine Besonderheit stellen allerdings dynamische Einschränkungen dar, die nicht pauschal bspw. durch Vorgabe eines bestimmten Wertebereichs beschrieben werden können. Beispiele hierfür sind Toleranzbereiche, die sich in Abhängigkeit des geforderten Wertes ändern. So kann eine Schneidmaschine bspw. bei kleinen Schneidlängen einen geringen Toleranzbereich aufweisen, der sich aber bei größeren Längen aufweitet.

Zur Abbildung solcher komplexen Abhängigkeiten wurde zusätzlich ein *Operation*-Constraint definiert, welches die dynamische Beurteilung der Erfüllbarkeit eines bestimmten geforderten Parameter-Wertes auf Basis eines Operationsaufrufs ermöglicht. Somit kann durch Instanziieren eines AAS-Elements *Operation* ein beliebig komplexe Berechnungsvorschrift hinterlegt werden, die theoretisch sogar weitere Parameter wie den aktuellen Maschinenzustand mit einbeziehen könnte.

#### Beschreibung zusammengesetzter Fähigkeiten

Individuelle Ressourcen können ihre Fähigkeiten oftmals nicht eigenständig realisieren. So benötigt bspw. eine Crimp-Maschine ein auf das Kontaktteil zugeschnittenes Crimp-Werkzeug, um einen Crimp-Prozess auszuführen. Das Crimp-Werkzeug wiederum benötigt eine entsprechende Maschine, die es verwendet. Diese Zusammenhänge sind auf der linken Seite von Abbildung 1-23 dargestellt.

Dies wirft die Frage auf, welche dieser beiden Ressourcen nun eigentlich die Fähigkeit besitzt – und folglich, in welcher Verwaltungsschale das entsprechende Fähigkeiten-Teilmodell angelegt werden sollte.

![Ein Bild, das Text, Screenshot, Schrift, Design enthält. Automatisch generierte Beschreibung](media/30a89168ca78e2cb52b05ff6b739fa24.png)

*Abbildung 1-26. Konzept zur Modellierung zusammengesetzter Fähigkeiten*

Sowohl eine Modellierung lediglich auf Seiten der Maschine als auch eine Modellierung lediglich auf Seiten des Werkzeugs bringt dabei gravierende Nachteile mit sich, da bestimmte Parameter oftmals sowohl von Maschinen- als auch von Werkzeugseite her eingeschränkt werden. Hierdurch wird eine kombinierte Modellierung dieser Einschränkungen sehr schnell sehr komplex, da viele Abhängigkeiten berücksichtig werden müssen.

Aus diesem Grund bietet es sich stattdessen an, eine geteilte Modellierung vorzunehmen. Dabei können Fähigkeiten und entsprechende Einschränkungen auf allen relevanten Ebenen modelliert werden, wie auf der rechten Seite von Abbildung 1-26 dargestellt.

Auf allen Ebenen können dabei die in Abschnitt 1.5.3.1 beschriebenen Konzepte genutzt werden. Einzig zur Abbildung der Notwendigkeit der Verknüpfung von Maschine und Werkzeug wird ein zusätzliches Modellierungskonzept benötigt. Hierzu kann das auch bereits in BaSys 4.2 angedachte Konzept der *CapabilityConditions* weiterentwickelt bzw. konkretisiert und eine spezielle Bedingung *RequiresToolCondition* definiert werden.

Wie in Abbildung 1-27 dargestellt, kann mit dieser Bedingung auf Maschinenebene beschrieben werden, dass zur Ausführung einer Fähigkeit ein bestimmter Werkzeugtyp benötigt wird. Statt hier explizit – bspw. per Referenz – auf ein konkretes Werkzeug zu verweisen, was bei mehreren möglichen Werkzeugen schnell zu einer hohen Komplexität führen würde, kann dabei explizit ein Typ von Werkzeugen angegeben werden. Das in Abbildung 1-27 dargestellte Modell erfordert bspw. ein Werkzeug des Typen *CrimpingApplicator*.

![A screenshot of a computer Description automatically generated](media/ac28482946e74c2eb0f1ff0bf09e227f.png)

*Abbildung 1-27: Bedingung "RequiresToolCondition"*

Auf Seiten der Werkzeuge kann der entsprechende Werkzeugtyp einfach über ein entsprechendes *Extension*-Element beschrieben werden, wie in Abbildung 1-28 gezeigt. Diese indirekte Modellierung erlaubt die dynamische Ermittlung möglicher Maschine-Werkzeug-Kombinationen, ohne bspw. im Voraus bereits sämtliche in einer Fabrik vorhandene Werkzeuginstanzen zu kennen.

![Ein Bild, das Text, Screenshot, Schrift, Zahl enthält. Automatisch generierte Beschreibung](media/b1697c4b162393f1b36aa110819386d1.png)

*Abbildung 1-28: Beschreibung von Werkzeugtypen per "toolType"-Extension*

### Algorithmus zum Fähigkeitenabgleich

Aufbauend auf den in den Abschnitten 1.5.2 und 1.5.3 dargelegten Konzepten zur Beschreibung von geforderten und angebotenen Fähigkeiten lässt sich nun ein Algorithmus ableiten, mit dessen Hilfe ein Fähigkeitenabgleich durchgeführt werden kann. Ein solcher Algorithmus soll dabei ermitteln, ob eine bestimmte Maschine (evtl. unter der Zuhilfenahme entsprechender Werkzeuge) in der Lage ist, eine bestimmte Fähigkeit anzubieten bzw. auszuführen.

Eingangsvoraussetzung für den Algorithmus ist folglich eine bestimmte geforderte Fähigkeit – also der Verweis auf einen *CapabilityContainer*, der Teil eines *RequiredCapability*-Teilmodells ist (vgl. Abschnitt 1.5.2) – und eine (Liste von) Maschine(n), die beurteilt werden soll – also eine bestimmte (Liste von) Asset- bzw. AAS-IDs.

Auf Basis dieser Informationen kann der Algorithmus dann sequenziell die folgenden Schritte ausführen bzw. Fragen beantworten:

1.  *Kann die Maschine die Fähigkeit grundsätzlich erfüllen?*

    Hierzu wird das *OfferedCapabilities*-Teilmodell der Maschine ausgewertet. Es wird zunächst überprüft, ob dieses grundsätzlich die geforderte Fähigkeit beschreibt, und ob darüber hinaus auch die entsprechenden Parametereinschränkungen erfüllt sind. Hierzu werden die definierten Constraints mit den geforderten Werten verglichen.

    Falls für die entsprechende Fähigkeit nicht zusätzlich noch eine *RequiredToolCondition* spezifiziert ist, kann nach diesem Schritt bereits eine Aussage über die Erfüllbarkeit der geforderten Fähigkeit getroffen werden.

2.  *Welche Werkzeuge sind bekannt, die zur Realisierung der Capabilities genutzt werden können?*

    Ist auf Seiten der Maschine für die geforderte Fähigkeit eine *RequiredToolCondition* spezifiziert, müssen zunächst alle bekannten Werkzeuge vom entsprechenden *toolType* ermittelt werden. Dies kann bspw. durch Abfrage eines entsprechenden AAS-Repositories erfolgen.

    Für jedes gefundene Werkzeug ist anschließend analog zu Schritt 1 zu beurteilen, ob dieses Werkzeug grundsätzlich in der Lage ist, die entsprechende geforderte Fähigkeit bereitzustellen.

3.  *(Wie) können die möglichen Werkzeuge in die Maschine montiert werden?*

    Für jedes in Schritt 2 identifizierte mögliche Werkzeug muss anschließend geprüft werden, ob bzw. wie dieses Werkzeug in die Maschine montiert werden kann. Hierzu kann das im Rahmen von AP5.3 entwickelte Konzept der *Abbildung möglicher Maschinenstrukturen* die Grundlage bieten, indem es die Voraussetzung zur Ableitung möglicher Montagepfade bietet.

4.  *Welche der gefundenen Kombinationen erfüllen alle Constraints?*

    Für jeden der gefundenen möglichen Montagepfade müssen abschließend noch einmal die entsprechenden *Constraints* ausgewertet werden. Ein Montagepfad muss zudem nicht immer direkt sein (Maschine ↔ Werkzeug), sondern kann eventuell Zwischenebenen besitzen (z.B. Maschine ↔ Adapter ↔ Werkzeug). Gemäß des in Abschnitt 1.5.3.2 entwickelten Konzeptes können für diese Zwischenebenen theoretisch ebenfalls Einschränkungen für die Fähigkeiten-Parameter beschrieben werden. Diese sind folglich ebenfalls gegenüber den geforderten Parametern zu prüfen.

Nach durchlaufen dieser Schritte kann der Algorithmus nicht nur eine Aussage liefern, ob eine geforderte Fähigkeit von einer Maschine erfüllt werden kann oder nicht, sondern auch, welche Werkzeuge hierzu benötigt werden und wie diese Werkzeuge in die Maschine verbaut werden können. Diese Informationen können bspw. zur Planung von Rüstvorgängen durch Produktionsmitarbeiter oder zum Abgleich von vorhandenen und benötigten Maschinenstrukturen genutzt werden.

Eine prototypische Implementierung des in diesem Abschnitt beschriebenen Algorithmus steht unter <https://github.com/VWS4LS/vws4ls-capability-matching> bereit.

### Anbindung von Skills

Die bisher in diesem Dokument betrachteten angebotenen *Fähigkeiten* bzw. *Capabilities* ermöglichen eine Bewertung, ob eine bestimmte Fähigkeit von einer Ressource umgesetzt werden kann – sie stellen folglich den Einstiegspunkt bei der Suche nach Maschinen zur Umsetzung bestimmter Prozesse dar.

Nachdem bspw. durch ein MES auf Basis eines Fähigkeitenabgleichs eine passende Maschine gefunden wurde, stellt sich als nächstes allerdings die Frage, wie diese Fähigkeit nun abgerufen werden kann. Es stellt sich folglich die Frage nach einer konkret ausführbaren *Fertigkeit* bzw. *Skill*.

Im Rahmen von TP1 wurde zur Implementierung solcher konkret ausführbaren Fertigkeiten eine *OPC UA Companion Specification* für die Prozesse der Leitungssatz-Produktion entwickelt (OPC 40570) [6]. Wie in Abbildung 1-29 dargestellt, muss daher ein automatischer Übergang von der im Rahmen einer Verwaltungsschale beschriebenen Fähigkeit zu einer durch einen OPC UA-Server auf einer Maschine bereitgestellten Fertigkeit ermöglicht werden.

![Ein Bild, das Text, Screenshot, Logo, Schrift enthält. Automatisch generierte Beschreibung](media/200335bcac6be308ee6b1d022c8ff171.png)

*Abbildung 1-29: Zusammenhang zwischen Fähigkeit (Capability) und Fertigkeit (Skill)*

Um eine solche automatische Durchgängigkeit realisieren zu können, bietet das im Rahmen von BaSys 4.2 entwickelte Teilmodell bereits die Möglichkeit, mit Hilfe einer *realizedBy*-Beziehung auf einen entsprechenden *Skill* zu verweisen (vgl. Abbildung 1-29). Im Rahmen des Teilmodells ist allerdings nicht festgelegt, wie solch ein Skill konkret aussieht.

Daher wurden im Rahmen von AP5.5 verschiedene bestehende und in Entwicklung befindliche Teilmodelle daraufhin analysiert, inwiefern sie eine adäquate Beschreibung des OPC UA Servers einer Maschine ermöglichen. Hierfür wurde das Teilmodell „IDTA 02017: *Asset Interface Description*„ [7] ausgewählt, welches die Beschreibung von Datenquellen ermöglicht, die von einem Asset angeboten werden. Da in der aktuellen Version 1.0 allerdings noch keine Unterstützung von OPC UA enthalten ist, wurde diese prototypisch ergänzt (vgl. Abbildung 1-30) – bei einer offiziellen Ergänzung in einer zukünftigen Version kann diese prototypische Umsetzung dann entsprechend ausgetauscht werden.

Relevante Punkte für den Übergang aus der Verwaltungsschale zum OPC UA-Server sind dabei vor allem:

-   der Endpunkt des OPC UA-Servers (siehe Element *EndpointMetadata* in Abbildung 1-30),
-   dass der OPC UA-Server die oben erwähnte *Companion Specification* für die Leitungssatzproduktion umsetzt (siehe *supplementalSemanticId,* „<http://www.w3.org/2011/opc40570>“ in Abbildung 1-30), sowie
-   Identifizierbarkeit des für die Ausführung des Skill relevanten *Nodes* (siehe. z.B. *Node* „CutToLengthInstance01“ in Abbildung 1-30) – dieser ist auch gleichzeitig das Ziel der *realizedBy*-Beziehung.

![Ein Bild, das Text, Screenshot, Zahl, Software enthält. Automatisch generierte Beschreibung](media/48cadda22b2726571881e451f7816e2a.png)

*Abbildung 1-30: Prototypische Ergänzung des AID-Teilmodells* [7] *für OPC UA*

### Anhang: Liste von Fähigkeiten und zugehörigen Parametern

In den nachfolgenden Kapiteln sind die Parameter der Fähigkeiten der jeweiligen Produktionsprozesse des Leitungssatzes definiert. Dieser Abschnitt ist nicht normativ und soll als Vorschlag für eine mögliche Standardisierung dienen. Siehe auch <https://github.com/VWS4LS/vws4ls-aaspe-plugin/blob/main/src/AasxPluginVws4ls/Utils/Vws4lsCapabilitySMUtils.cs> [8].

#### Cut

SemanticId: https://arena2036.de/vws4ls/capability/1/0/CutCapability

Parameter:

-   NominalLength (xs:double)
-   LengthUpperLimit (xs:double)
-   LengthLowerLimit (xs:double)

#### Cut Wire

SemanticId: https://arena2036.de/vws4ls/capability/1/0/CutWireCapability

Parameter:

-   NominalLength (xs:double)
-   LengthUpperLimit (xs:double)
-   LengthLowerLimit (xs:double)
-   WireType (xs:string)
-   WireCrossSectionArea (xs:double)

#### Cut Tube

SemanticId: https://arena2036.de/vws4ls/capability/1/0/CutTubeCapability

Parameter:

-   NominalLength (xs:double)
-   LengthUpperLimit (xs:double)
-   LengthLowerLimit (xs:double)
-   TubeType (xs:string)
-   TubeDiameter (xs:double)

#### Strip

SemanticId: https://arena2036.de/vws4ls/capability/1/0/StripCapability

Parameter:

-   NominalStrippingLength (xs:double)
-   StrippingLengthUpperLimit (xs:double)
-   StrippingLengthLowerLimit (xs:double)
-   CenterStripping (xs:boolean)
-   Layer (xs:boolean)
-   IncisionMonitoring (xs:boolean)
-   WireEnd (xs:string)

#### Slit

SemanticId: https://arena2036.de/vws4ls/capability/1/0/SlitCapability

Parameter:

-   NominalSlittingLength (xs:double)
-   Layer (xs:boolean)
-   WireEnd (xs:string)

#### Crimp

SemanticId: https://arena2036.de/vws4ls/capability/1/0/CrimpCapability

Parameter:

-   WireType (xs:string)
-   WireCrossSectionArea (xs:double)
-   TerminalPartNumber (xs:string)
-   CrimpForceMonitoring (xs:boolean)
-   CrimpHeightUpperLimit (xs:double)
-   CrimpHeightLowerLimit (xs:double)
-   CrimpWidthUpperLimit (xs:double)
-   CrimpWidthLowerLimit (xs:double)

#### Mark Wire

SemanticId: https://arena2036.de/vws4ls/capability/1/0/MarkWireCapability

Parameter:

-   MarkingType (xs:string)
-   ContentType (xs:string)
-   CharHeight (xs:double)
-   Color (xs:string)

#### Tinning

SemanticId: https://arena2036.de/vws4ls/capability/1/0/TinningCapability

Parameter:

-   TemperatureAccuracyUpperLimit (xs:double)
-   TemperatureAccuracyLowerLimit (xs:double)

#### Refinement Of Cable Lugs

SemanticId: https://arena2036.de/vws4ls/capability/1/0/RefinementOfCableLugsCapability

Parameter:

-   SolderDurationUpperLimit (xs:double)
-   SolderDurationLowerLimit (xs:double)

#### Seal

SemanticId: https://arena2036.de/vws4ls/capability/1/0/SealCapability

Parameter:

-   SealPartNumber (xs:string)
-   SealPositionUpperLimit (xs:double)
-   SealPositionLowerLimit (xs:double)

#### Sleeve

SemanticId: https://arena2036.de/vws4ls/capability/1/0/SleeveCapability

Parameter:

-   SleevePartNumber (xs:string)
-   PullOutCheck (xs:boolean)

#### Strand Twist

SemanticId: https://arena2036.de/vws4ls/capability/1/0/StrandTwistCapability

Parameter:

-   WireCrossSectionArea (xs:double)

#### Shield Twist

SemanticId: https://arena2036.de/vws4ls/capability/1/0/ShieldTwistCapability

Parameter:

-   \---

#### Blockload

SemanticId: https://arena2036.de/vws4ls/capability/1/0/BlockloadCapability

Parameter:

-   \---

#### Connector And Housing

SemanticId: https://arena2036.de/vws4ls/capability/1/0/ConnectorAndHousingCapability

Parameter:

-   ConnectorPartNumber (xs:string)
-   InsertionForceCurveMonitoring (xs:boolean)

#### Ultra Sonic Weld

SemanticId: https://arena2036.de/vws4ls/capability/1/0/UltraSonicWeldCapability

Parameter:

-   SumCrossSectionArea (xs:double)

#### Terminal

SemanticId: https://arena2036.de/vws4ls/capability/1/0/TerminalCapability

Parameter:

-   TerminalPartNumber (xs:string)

#### Cover

SemanticId: https://arena2036.de/vws4ls/capability/1/0/CoverCapability

Parameter:

-   BundleDiameter (xs:double)
-   StartNode (xs:string)
-   EndNode (xs:string)

#### Shrink

SemanticId: https://arena2036.de/vws4ls/capability/1/0/ShrinkCapability

Parameter:

-   NominalTemperature (xs:double)

#### Spot Tape

SemanticId: https://arena2036.de/vws4ls/capability/1/0/SpotTapeCapability

Parameter:

-   \---

#### Tape

SemanticId: https://arena2036.de/vws4ls/capability/1/0/TapeCapability

Parameter:

-   TapingMethod (xs:string)

#### Tube

SemanticId: https://arena2036.de/vws4ls/capability/1/0/TubeCapability

Parameter:

-   TubeType (xs:string)

#### Wire Twist

SemanticId: https://arena2036.de/vws4ls/capability/1/0/WireTwistCapability

Parameter:

-   NominalWireEndLength (xs:double)
-   NominalTensionForce (xs:double)
-   NominalOpenEndSide1 (xs:double)
-   NominalTrimmedOpenEndLengthSide1 (xs:double)
-   SpotTapeSide1 (xs:boolean)
-   NominalOpenEndSide2 (xs:double)
-   NominalTrimmedOpenEndLengthSide2 (xs:double)
-   SpotTapeSide2 (xs:boolean)
-   WireEndLengthUpperLimit (xs:double)
-   WireEndLengthLowerLimit (xs:double)
-   LayLengthUpperLimit (xs:double)
-   LayLengthLowerLimit (xs:double)
-   OpenEndLowerLimitSide1 (xs:double)
-   OpenEndUpperLimitSide1 (xs:double)
-   OpenEndLowerLimitSide2 (xs:double)
-   OpenEndUpperLimitSide2 (xs:double)

#### Simple Twist

SemanticId: https://arena2036.de/vws4ls/capability/1/0/SimpleTwistCapability

Parameter:

-   NominalElasticity (xs:double)

#### Route

SemanticId: https://arena2036.de/vws4ls/capability/1/0/RouteCapability

Parameter:

-   \---

#### Fuse Box Assembly

SemanticId: https://arena2036.de/vws4ls/capability/1/0/FuseBoxAssemblyCapability

Parameter:

-   FuseBoxPartNumber (xs:string)
-   MountForceAccuracyLowerLimit (xs:double)
-   MountForceAccuracyUpperLimit (xs:double)

#### Foam

SemanticId: https://arena2036.de/vws4ls/capability/1/0/FoamCapability

Parameter:

-   FoamObjectPartNumbers (xs:string)

#### Screw

SemanticId: https://arena2036.de/vws4ls/capability/1/0/ScrewCapability

Parameter:

-   FuseBoxPartNumber (xs:string)
-   PositionName (xs:string)
-   WrenchSize (xs:double)
-   NominalTorque (xs:double)
-   TighteningCurve (xs:boolean)
-   TorqueLowerLimit (xs:double)
-   TorqueUpperLimit (xs:double)
-   AngleLowerLimit (xs:double)
-   AngleUpperLimit (xs:double)

#### Scan

SemanticId: https://arena2036.de/vws4ls/capability/1/0/ScanCapability

Parameter:

-   ComponentPartNumber (xs:string)
-   BarcodePosition (xs:string)
-   BarcodeType (xs:string)
-   Grading (xs:boolean)

#### Test

SemanticId: https://arena2036.de/vws4ls/capability/1/0/TestCapability

Parameter:

-   TestSpecificationId (xs:string)

## AP 5.6 - Erfassung von Qualitätsdaten

### Zielsetzung

Das AP 5.6 befasst sich mit der Erfassung und Auswertung von Qualitätsdaten von bei der Leitungssatz-Produktion ausgeführten Prozessen. Besonderes Augenmerk wurde daraufgelegt, wie eine solche Erfassung und Auswertung vor dem Hintergrund von Verbundkomponenten erfolgen kann: Wie bereits im Rahmen der Beschreibung angebotener Fähigkeiten erläutert (s. AP5.5), führen Fertigungsmaschinen bestimmte Prozesse häufig nicht allein aus, sondern benötigen hierzu spezielle Werkzeuge. Eine Ermittlung von Qualitätsdaten vor diesem Hintergrund ist besonders herausfordernd, da (1) Maschine und Werkzeug oftmals nicht vom gleichen Hersteller stammen und (2) Werkzeuge oftmals passive Komponenten sind, welche über keine eigene Kommunikationsschnittstelle verfügen.

Um zu zeigen, wie diesen Herausforderungen mit Hilfe der Verwaltungsschale begegnet werden kann wurde im Rahmen von AP5.6 folgender Use Case umgesetzt: Betrachtet wird ein Crimp-Prozess, der durch eine Maschine unter Nutzung eines speziellen Werkzeugs (Applikator) ausgeführt wird. Da der Applikator über die Zeit verschleißt und irgendwann ausfällt, sollen Qualitätsdaten ermittelt werden. Auf Basis dieser Qualitätsdaten kann der Hersteller des Applikators dann durch einen speziellen Algorithmus ermitteln, wann ein Ausfall zu befürchten ist und entsprechend frühzeitig eine Warnung auslösen, woraufhin der Applikator rechtzeitig gewartet/ausgetauscht werden kann („Predictive Maintenance“).

Da der Applikator eine passive Komponente ohne Kommunikationsschnittstelle und ohne Sensorik ist, kann er nicht selbstständig feststellen, ob er „benutzt“ wurde. Die Auswertungsalgorithmen wiederum sind geistiges Eigentum des Herstellers des Applikators und können somit nicht einfach durch den Hersteller/Betreiber der Maschine implementiert/bereitgestellt werden. Aus diesem Grund soll der Applikator über eine aktive Verwaltungsschale verfügen, in der durch die (Verwaltungsschale der) Maschine relevante Qualitäts- bzw. Nutzungsdaten hinterlegt werden und die daraufhin selbstständig die entsprechenden Algorithmen zur Auswertung dieser Daten ausführen kann.

Als plakatives Beispiel wurde im Rahmen von AP5.6 davon ausgegangen, dass der Applikator unabhängig von anderen Faktoren typischerweise eine bestimmte Anzahl von Crimp-Vorgängen aushält und danach getauscht werden muss. Die entsprechenden Qualitätsdaten lassen sich somit in Form einer einfachen „Zählervariable“ in der Verwaltungsschale des Applikators hinterlegen, die durch die Maschine bei Ausführung eines Crimp-Prozesses erhöht wird. Die Verwaltungsschale des Applikators kann diese „Zählervariable“ überwachen und bei Überschreiten eines vorher festgelegten Grenzwertes ein entsprechendes Wartungs-Event auslösen. Die folgende Abbildung zeigt das Grundprinzip des beschriebenen Use Cases:

![Ein Bild, das Cartoon, Kunst, Screenshot, Grafikdesign enthält. Automatisch generierte Beschreibung](media/03cf3a0168f3120b613c2d376703c67a.png)

*Abbildung 1-31: Konzept Use Case "Predictive Maintenance"*

### Relevante Teilmodelle

Für die Umsetzung des Use Cases „Predictive Maintenance“ wurde zunächst untersucht, welche bestehenden IDTA-Teilmodelle hierfür genutzt werden können. Dabei wurden die folgenden drei Teilmodelle als relevant eingestuft:

-   **IDTA 02008 Time Series Data** [9]

    Mit Hilfe dieses Teilmodells können beliebige Zeitreihendaten abgebildet werden. Für den oben beschriebenen Use Case kann es genutzt werden, um den zeitlichen Verlauf der „Zählervariable“ abzubilden. Es wird folglich für jeden ausgeführten Crimp-Prozess ein entsprechender Datenpunkt mit dem neuen Zählerstand (und dem zugehörigen Zeitstempel) angelegt.

-   **IDTA 02048 Predictive Maintenance** [10]

    Dieses im Rahmen des Forschungsprojektes [InterOpera](https://interopera.de/)*[^15]* erstellte Teilmodell deckt verschiedene Aspekte rund um den Bereich „Predictive Maintenance“ ab. Für den oben beschriebenen Use Case sind vor allem die folgenden beiden Bereiche relevant:

    „**Condition Indicators**“ mit entsprechenden „**Condition Levels**“. Im Rahmen des betrachteten Use Cases ist der im Rahmen des Zeitreihenmodells abgebildete „Zählerstand“ ein solcher Indikator – im Rahmen des Teilmodells lässt sich ein Verweis auf das entsprechende *Time Series Data*-Teilmodell hinterlegen. Mit Hilfe von „Condition Levels“ lassen sich dann mit Bezug auf den referenzierte Wert bestimmte Intervalle definieren – bspw. ein Intervall „Normalbetrieb“ und ein Intervall, welches besagt, dass der Applikator ausgetauscht werden soll.

    „**Remaining Useful Life**“: Für den betrachteten Use Case stellt dieses die voraussichtlich verbleibende Anzahl an möglichen Crimp-Vorgängen bis zum Ausfall des Werkzeugs dar.

-   **IDTA 02010 Service Request Notification** [11]

    Das Teilmodell „Service Request Notification” erlaubt die Beschreibung von Aufforderungen zu Wartungstätigkeiten. Für den betrachteten Use Case kann dieses Teilmodell dazu genutzt werden, den durchzuführenden Werkzeugwechsel zu kommunizieren und dann bspw. in einem MES-System anzuzeigen.

[^15]: <https://interopera.de/>

### Zusammenspiel der verschiedenen Teilmodelle

Für den betrachteten Use Case spielen die in Abschnitt 1.6.2 beschriebenen Teilmodelle wie folgt zusammen: Die (Verwaltungsschale der) Maschine legt bei Ausführung eines Crimp-Prozesses im Teilmodell „Time Series Data“ des aktuell montierten Werkzeugs einen neuen Eintrag an. Der neue Eintrag enthält dabei einen gegenüber dem letzten Wert inkrementierten Zählerstand.

Die Verwaltungsschale des Werkzeugs überwacht Änderungen in ihrem Teilmodell „IDTA 02008: Time Series Data“ [9] und aktualisiert die „Remaining Useful Live“ im Teilmodell IDTA 02048: Predictive Maintenance“ [10], welche sich aus der erwarteten Lebensdauer abzüglich des aktuellen Zählerstandes ergibt.

Zusätzlich prüft die Verwaltungsschale des Werkzeugs den Eintritt in das „Condition Level“, welches die vorsorgliche Wartung bzw. den Austausch des Applikators vorsieht. Bei Erreichen dieses Levels wird im Teilmodell „Service Request Notification“ ein neuer Service-Antrag angelegt, welcher die Wartung bzw. den Austausch des Applikators fordert.

Die folgende Abbildung fasst die beschriebenen Zusammenhänge zusammen und zeigt die Strukturen der unterschiedlichen Teilmodelle:

![](media/ad037c63dffac9f1e46cbb28e3ba0cfd.png)

*Abbildung 1-32: Zusammenhang der verschiedenen Teilmodelle*

### Prototypische Implementierung

Der in den bisherigen Abschnitten dieses Dokuments aufgezeigte Use Case wurde im Rahmen von AP 5.6 prototypisch umgesetzt. Hierzu wurden einerseits die entsprechenden Verwaltungsschalen und Teilmodelle aufgesetzt (vgl. Abbildung 1-32) und per Basyx[^16]-Server bereitgestellt. Darüber hinaus wurden aktive Verwaltungsschalen sowohl für eine Maschine als auch für einen Applikator aufgesetzt, um die in Abbildung 1-31 dargestellte Interaktion umsetzen zu können. Die aktiven Verwaltungsschalen wurden dabei durch zwei Node-RED[^17]-Instanzen umgesetzt, die die in Abschnitt 1.6.3 Algorithmen umsetzen. Abbildung 1-33 zeigt exemplarisch die Node-RED-Umsetzung zur Auswertung des Teilmodells „Predictive Maintenance“ inklusive der Abonnierung von Änderungen am Teilmodell „Predictive Maintenance“ per MQTT sowie der Reaktion auf entsprechende Änderungen durch Anpassen der „Remaining Useful Life“ sowie des Aufrufs eines entsprechenden Handlers bei Eintritt in ein neues „Condition Level“.

[^16]: <https://basyx.org/>

[^17]: <https://nodered.org/>

Die Konfigurationsdateien hierfür finden sich in „[basyx-predictive-maintenance-multiple-node-red-instances.zip](https://github.com/VWS4LS/vws4ls-subproject-results/upload/main/TP05/Beispieldaten/basyx-predictive-maintenance-multiple-node-red-instances.zip)“

![Ein Bild, das Text, Screenshot, Diagramm, Reihe enthält. Automatisch generierte Beschreibung](media/b01dab6a98b005b33330d5ab8fa328a3.png)

*Abbildung 1-33: NodeRed-Flow zur Auswertung des Teilmodells "Predictive Maintenance"*

## Fazit

Im Rahmen von TP5 wurde das Konzept der *Verbundkomponente* genutzt, um vernetzte Verwaltungsschalenstrukturen zu realisieren. Hierzu wurden zunächst sowohl für Produkte als auch Ressourcen relevante Beziehungen zwischen den unterschiedlichen Typen von Verwaltungsschalen analysiert sowie für jede gefundene Beziehungsart entsprechende Modellierungsmöglichkeiten ermittelt bzw. entworfen. Mithilfe dieser Modellierungsmöglichkeiten kann dann ein Netzwerk von verknüpften Verwaltungsschalen erstellt werden, welches vor allem auch die im Rahmen der anderen Teilprojekte entworfenen Verwaltungsschalen und Teilmodelle miteinander in Beziehung setzt. Ein solches Netzwerk wurde exemplarisch unter anderem für das im Rahmen des „PPR-Workshops“ definierte Beispielprodukt erstellt.

Der zweite Teil von TP5 hat sich dann mit der Schaffung bzw. dem Aufzeigen von Mehrwerten befasst, die auf Basis aus einer entsprechenden vernetzten Struktur von Verwaltungsschalen realisieren lassen. Hierzu wurden die folgenden vier Use Cases definiert sowie deren Umsetzung analysiert:

1.  Rückverfolgbarkeit im Fehlerfall
2.  Synchronisierung von Verwaltungsschalen
3.  Sachnummern-Mapping
4.  Fähigkeitenabgleich

Besonderes Augenmerk wurde auf das Thema „Fähigkeitenabgleich“ gelegt. Entsprechende Modellierungsmöglichkeiten und Algorithmen wurden im Rahmen von AP5.5 entworfen, wobei ein besonderer Fokus auf der „gemeinsamen“ Realisierung von Fähigkeiten aus einer Kombination aus Maschine und Werkzeugt lag. Abschließend wurde im Rahmen eines „Predictive Maintenance“-Use Cases gezeigt, wie sich Mehrwerte durch eine Firmen- und VWS-übergreifende Zusammenarbeit generieren lassen.

# Literaturverzeichnis

| [1]   | Plattform Industrie 4.0, „Verwaltungsschale in der Praxis,“ 2021. [Online]. Available: https://industrialdigitaltwin.org/wp-content/uploads/2021/09/08_verwaltungsschale_in_der_praxis_de_2020.pdf.                                                                                       |
|-------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [2]   | Plattform Industrie 4.0, „Beziehungen zwischen I4.0-Komponenten – Verbundkomponenten und intelligente Produktion,“ 2017. [Online]. Available: https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/beziehungen-i40-komponenten.pdf.                                         |
| [3]   | Industrial Digital Twin Association e.V., „IDTA 02011-1-1 Hierarchical Structures enabling Bills of Material,“ 2024 June. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Hierarchical%20Structures%20enabling%20Bills%20of%20Material/1/1. |
| [4]   | Industrial Digital Twin Association e.V., „IDTA 02005 Provision of Simulation Models,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Provision of Simulation Models/1/0.                                                                  |
| [5]   | Industrial Digital Twin Association e.V., „IDTA 02020-1-0 Capability Description (WiP),“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/development/Capability/1/0.                                                                                  |
| [6]   | OPC Foundation, „OPC 40570: OPC UA for the Wire Harness Manufacturing Industry,“ https://profiles.opcfoundation.org/workinggroup/88, WiP. [Online]. Available: https://profiles.opcfoundation.org/document/214.                                                                           |
| [7]   | Industrial Digital Twin Association e.V., „IDTA 02017-1-0 Asset Interfaces Description,“ January 2024. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Asset%20Interfaces%20Description/1/0.                                                |
| [8]   | „VWS4LS-Github,“ ARENA2036 e.V., [Online]. Available: https://github.com/VWS4LS.                                                                                                                                                                                                          |
| [9]   | Industrial Digital Twin Association e.V., „IDTA 02008-1-1 Time Series Data,“ 2023. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Time%20Series%20Data/1/1.                                                                                |
| [10]  | Industrial Digital Twin Association e.V., „IDTA 02048 Predictive Maintenance (WiP),“ [Online]. Available: https://interopera.de/wp-content/uploads/2023/07/230705-Predictive-Maintenance-Abschlusspraesentation.pdf.                                                                      |
| [11]  | Industrial Digital Twin Association e.V., „IDTA 02010-1-0 Service Request Notification,“ 2023. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Service%20Request%20Notification/1/0.                                                        |
| [12]  | Industrial Digital Twin Association e.V. (IDTA), Specification of the Asset Administration Shell Part 2: Application Programming Interfaces – IDTA Number: 01002-3-0, 2023, Frankfurt.                                                                                                    |
| [13]  | „Verband der Automobilindustrie (VDA),“ [Online]. Available: https://www.vda.de/de.                                                                                                                                                                                                       |
| [14]  | „Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.                                                                                                                                                |
| [15]  | OPC Foundation, „OPC 40001-3: Machinery Job Mgmt,“ OPC Foundation, [Online]. Available: https://reference.opcfoundation.org/Machinery/Jobs/v100/docs/.                                                                                                                                    |
| [16]  | OPC Foundation, „OPC 30270: Industry 4.0 Asset Administration Shell,“ [Online]. Available: https://reference.opcfoundation.org/I4AAS/v100/docs/.                                                                                                                                          |
| [17]  | OPC Foundation, „OPC 40001-1: Machinery Basic Building Blocks,“ [Online]. Available: https://reference.opcfoundation.org/Machinery/v103/docs/.                                                                                                                                            |
| [18]  | OPC Foundation, „OPC 40001-101: Machinery Result Transfer,“ [Online]. Available: https://reference.opcfoundation.org/Machinery/Result/v100/docs/.                                                                                                                                         |
| [19]  | OPC Foundation, „OPC UA Nodesets,“ [Online]. Available: https://github.com/OPCFoundation/UA-Nodeset.                                                                                                                                                                                      |
| [20]  | Platform Industrie 4.0, „RAMI 4.0: Ein Referenzarchitekturmodell als Kommunikationsgrundlage in der Industrie 4.0,“ 11 04 2022. [Online]. Available: https://www.dke.de/de/arbeitsfelder/industry/rami40.                                                                                 |
| [21]  | „DIN SPEC 91345:2016-04 - Referenzarchitekturmodell Industrie 4.0 (RAMI4.0),“ 2016. [Online]. Available: https://dx.doi.org/10.31030/2436156.                                                                                                                                             |
| [22]  | „VEC Release Notes - Version 2.1.0,“ prostep ivip, 08 01 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/release-notes/.                                                                                                                                 |
| [23]  | „VWS4LS-Github,“ ARENA2036 e.V., [Online]. Available: https://github.com/VWS4LS.                                                                                                                                                                                                          |
| [24]  | KEBA, „OPC UA – der zentrale Standard für Industrie 4.0 im Überblick,“ [Online]. Available: https://www.keba.com/de/news/industrial-automation/ueberblick-opc-ua-zentraler-standard-industrie-4-0.                                                                                        |
| [25]  | IEC, „IEC 61360-4 - IEC/SC 3D - Common Data Dictionary,“ [Online]. Available: https://cdd.iec.ch/cdd/iec61360/iec61360.nsf/TreeFrameset?OpenFrameSet.                                                                                                                                     |
| [26]  | Industrial Digital Twin Association e.V., „IDTA 02005: Provision of Simulation Models,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Provision of Simulation Models/1/0.                                                                 |
| [27]  | ECLASS e.V., „ECLASS-Standard,“ [Online]. Available: https://eclass.eu/eclass-standard/content-suche/search.                                                                                                                                                                              |
| [28]  | Plattform Industrie 4.0, „Interoperability at Runtime - Exchanging Information via Application Programming Interfaces,“ 2021. [Online]. Available: https://www.plattform-i40.de/IP/Redaktion/EN/Downloads/Publikation/Details_of_the_Asset_Administration_Shell_Part2_V1.pdf.             |

# **Abbildungsverzeichnis**

[*Abbildung 1-1: Ergebnis der Workshop-Reihe*](#_Toc178820053)

[*Abbildung 1-2: Unterschiedliche Arten von Verwaltungsschalen als Teil der VBK „Produkt“*](#_Toc178820054)

[*Abbildung 1-3: Umsetzung hierarchischer Beziehungen mit Hilfe des BOM-Teilmodells*](#_Toc178820055)

[*Abbildung 1-4: Konzept der "Specific Asset ID" aus dem Metamodell der VWS (s. Abschnitt 5.3.4)*](#_Toc178820056)

[*Abbildung 1-5: Exemplarische Umsetzung des Sachnummern-Mapping mittels „specificAssetId“*](#_Toc178820057)

[*Abbildung 1-6: Teilmodell "Freigabeliste"*](#_Toc178820058)

[*Abbildung 1-7: Beispiel-Ressourcen 2 – Wezag UP 150 (links) und Komax Sigma 688 (rechts)*](#_Toc178820059)

[*Abbildung 1-8: Übersicht möglicher Fähigkeiten Komax Sigma 688*](#_Toc178820060)

[*Abbildung 1-9: Einordnung in das PPR-Modell*](#_Toc178820061)

[*Abbildung 1-10: Modellierung von Werkzeug-Freigaben am Beispiel Crimp-Kontakt*](#_Toc178820062)

[*Abbildung 1-11: Abbildung der aktuellen Maschinenstruktur mit Hilfe des BOM-Teilmodells*](#_Toc178820063)

[*Abbildung 1-12: Abbildung potenzieller Maschinenstrukturen mit Hilfe des BOM-Teilmodells*](#_Toc178820064)

[*Abbildung 1-13: Modellierung potenzieller Maschinenstrukturen per "specificAssetId"*](#_Toc178820065)

[*Abbildung 1-14: Prüfmodul mit Gegenstecker (Komax Testing)*](#_Toc178820066)

[*Abbildung 1-15: „specificAssetId“ einer pneumatischen Komponente im Prüfmodul*](#_Toc178820067)

[*Abbildung 1-16: Verwaltungsschale einer pneumatischen Antriebseinheit mit Bill of Material*](#_Toc178820068)

[*Abbildung 1-17: Netzwerk aus FMU-Modellen für eine pneumatische Antriebseinheit (rechts).*](#_Toc178820069)

[*Abbildung 1-18: Eingesetzte VIBN-Tools*](#_Toc178820070)

[*Abbildung 1-19: Simulationsmodelle in der Verwaltungsschale des Prüfmoduls*](#_Toc178820071)

[*Abbildung 1-20: Ausschnitt der erstellten Verwaltungsschalen*](#_Toc178820072)

[*Abbildung 1-21: Exemplarische Zeichnung Leitungssatz inkl. Komponentenbezeichnungen*](#_Toc178820073)

[*Abbildung 1-22: Exemplarische OEM-Komponentenspezifikation inkl. Sachnummern*](#_Toc178820074)

[*Abbildung 1-23 Capability-Matching am Beispiel eines Crimp-Prozesses*](#_Toc178820075)

[*Abbildung 1-24: Exemplarisches Teilmodell "RequiredCapabilities"*](#_Toc178820076)

[*Abbildung 1-25: Exemplarisches Teilmodell "OfferedCapabilities"*](#_Toc178820077)

[*Abbildung 1-26. Konzept zur Modellierung zusammengesetzter Fähigkeiten*](#_Toc178820078)

[*Abbildung 1-27: Bedingung "RequiresToolCondition"*](#_Toc178820079)

[*Abbildung 1-28: Beschreibung von Werkzeugtypen per "toolType"-Extension*](#_Toc178820080)

[*Abbildung 1-29: Zusammenhang zwischen Fähigkeit (Capability) und Fertigkeit (Skill)*](#_Toc178820081)

[*Abbildung 1-30: Prototypische Ergänzung des AID-Teilmodells* [7] *für OPC UA*](#_Toc178820082)

[*Abbildung 1-31: Konzept Use Case "Predictive Maintenance"*](#_Toc178820083)

[*Abbildung 1-32: Zusammenhang der verschiedenen Teilmodelle*](#_Toc178820084)

[*Abbildung 1-33: NodeRed-Flow zur Auswertung des Teilmodells "Predictive Maintenance"*](#_Toc178820085)

