# Architekturkonzepte für die AAS

Ausformulierung der Grundbausteine für die Anwendung der VWS in der Leitungssatz-Wertschöpfungskette. Die Architektur-Diskussion hat sich in VWS4LS als wichtiges Querschnittsthema etabliert. Analog zu den Usecases wurde daher schon Anfang 2023 ein Architekturteam ins Leben gerufen, dessen Arbeit seitdem andauert.

## Inhalt

[1 Einführung Verwaltungsschale für den Leitungssatz (VWS4LS)](#_1)

[2 Einführung Architektur](#_2)
- [2.1 Zentrale vs. dezentrale Architektur](#_2.1)
- [2.2 Single Point of Truth](#_2.2)
- [2.3 Gestaltungsfelder](#_2.3)

[3 Modularisierung](#_3)
- [3.1 Aufteilung des Leitungssatzes in Module](#aufteilung-des-leitungssatzes-in-module)
- [3.2 Verwaltungsschalen im Entwicklungsprozess](#_3.2)
- [3.3 Verwaltungsschalen im Produktionsprozess](#_3.3)
- [3.4 Inhalte und Verknüpfung der Stakeholder-Verwaltungsschalen](#_3.4)
- [3.4.1 VWS für die Ressource](#vws-für-die-ressource)
- [3.4.2 VWS für die Komponenten](#vws-für-die-komponenten)
- [3.4.3 VWS für den Leitungssatz](#vws-für-den-leitungssatz)

[4 Verlinkung](#_4)
- [4.1 Typ-Verwaltungsschale des OEM](#typ-verwaltungsschale-des-oem)
- [4.1.1 Teilmodell ProductSpecification](#teilmodell-productspecification)
- [4.1.2 Teilmodell ProductBoM](#teilmodell-productbom)
- [4.1.3 Teilmodell ProductConfigurationBoM](#teilmodell-productconfigurationbom)
- [4.2 Typ-Verwaltungsschale (Konfektionär)](#typ-verwaltungsschale-konfektionär)
- [4.2.1 Teilmodell ManufacturingBoM (Konfektionär)](#teilmodell-manufacturingbom-konfektionär)
- [4.2.2 Teilmodell ManufacturingConfigurationBoM (Konfektionär)](#teilmodell-manufacturingconfigurationbom-konfektionär)
- [4.2.3 Teilmodell ProductBoM (Konfektionär)](#teilmodell-productbom-konfektionär)
- [4.3 Instanz-Verwaltungsschale des OEM](#instanz-verwaltungsschale-des-oem)
- [4.4 Instanz-Verwaltungsschale des Konfektionärs](#instanz-verwaltungsschale-des-konfektionärs)
- [4.5 Verlinkung des VEC](#_4.5)
- [4.5.1 Referenzieren von Informationsfragmenten des VEC](#referenzieren-von-informationsfragmenten-des-vec)
- [4.5.2 Verlinkung von Typinformationen](#verlinkung-von-typinformationen)

[5 Versionierung](#_5)
- [5.1 VWS-Aufbau für den Leitungssatz](#vws-aufbau-für-den-leitungssatz)
- [5.2 Versionierungskonzept der Verwaltungsschale](#versionierungskonzept-der-verwaltungsschale)
- [5.3 Zugriff mit Registry und Discovery](#zugriff-mit-registry-und-discovery)
- [5.4 Zugriff ohne Discovery](#zugriff-ohne-discovery)
- [5.5 Zugriff ohne Registry](#_5.5)

[6 Synchronisation](#_6)
- [6.1 Rahmenbedingungen für den gewählten Lösungsansatz](#_6.1)
- [6.2 Konfiguration der Synchronisationsbeziehung](#_6.2)
- [6.3 Senden von I4.0-Nachrichten zur Synchronisation](#_6.3)
- [6.4 Inhalte der I4.0-Nachrichten zur Synchronisation](#_6.4)
- [6.5 Verarbeiten von I4.0-Nachrichten zur Synchronisation](#_6.5)
- [6.6 Umgang mit Fehlerzuständen](#_6.6)

[7 Änderungsmanagement](#_7)
- [7.1 Ablauf](#_7.1)
- [7.1.1 Szenario 1: Änderungsbedarf seitens des OEM](#_7.1.1)
- [7.1.2 Szenario 2: Änderungsbedarf seitens des Tier X](#_7.1.2)
- [7.2 Änderungsmanagement in der Verwaltungsschale](#_7.2)
- [7.2.1 Teilmodell EngineeringChangeRequests](#_7.2.1)
- [7.2.2 Teilmodell EngineeringChangeProposals](#_7.2.2)
- [7.2.3 Teilmodell EngineeringChangeOrders](#_7.2.3)
- [7.2.4 Teilmodell Bezugskonfigurationen](#_7.2.4)

[8 Rückverfolgbarkeit](#_8)
- [8.1 Szenario 1: Rückverfolgbarkeit über mehrere Tier-Stufen](#_8.1)
- [8.1.1 Anforderungen](#_8.1.1)
- [8.1.2 Lösungsweg](#_8.1.2)
- [8.2 Szenario 2: Rückverfolgbarkeit beim Kabelkonfektionär](#_8.2)
- [8.2.1 Anforderungen](#_8.2.1)
- [8.2.2 Lösungsweg](#_8.2.2)
- [8.3 Datenvorhaltung](#_8.3)

[9 Fazit](#fazit)

[10 Literaturverzeichnis](#literaturverzeichnis)

## <a name="_1"></a>1. Einführung Verwaltungsschale für den Leitungssatz (VWS4LS)

Der Leitungssatz ist das Nervensystem des Fahrzeugs, welches Energie und Daten im gesamten Fahrzeug verteilt. Als eine der teuersten und komplexesten Einzelkomponente steht die bisherige stark manuell geprägte Wertschöpfung der Leitungssatz-Konfektion vor großen Herausforderungen. Für viele dieser Herausforderungen ist die digitale Durchgängigkeit der Prozessketten eine wesentliche Lösungsvoraussetzung – insbesondere unternehmensübergreifend. Der Beitrag von VWS4LS zur Transformation dieser Wertkette legt eine Grundlage für eine standardisierte digitale Beschreibung des Leitungssatzes, seinen Komponenten, den Maschinen, mit denen der Leitungssatz produziert wird, und die Prozesse, entlang derer die Einzelschritte verkettet werden.

Im Projekt wurden die folgenden wesentlichen Use Cases (UC) betrachtet:

**UC1**: Kollaborative Entwicklung (Original Equipment Manufacturer (OEM), Konfektionär, Komponentenlieferanten)

**UC2**: Berücksichtigung der automatisierten Produktionsfähigkeit im Engineering

**UC3**: Automatisierung des Änderungsmanagement entlang der gesamten Wertkette

**UC4**: Automatisierung von flexiblen und modularen Produktionsabläufen

**UC5**: Rückverfolgung aller Komponenten, Produktions- und Qualitätsdaten

VWS4LS betrat mit dieser Positionierung zumindest aus Sicht der Verwaltungsschale (VWS) wenig erschlossenes Terrain in mehrerlei Hinsicht:

-   VWS4LS bezieht mit dem Engineering-Prozess die Entstehung des gesamten Lifecycles mit ein. Hier entsteht das Asset und hier muss auch die Verwaltungsschale entstehen.
-   VWS4LS betrachtet mit dem Leitungssatz einen Bereich klassischer Serienfertigung schlechthin. Zugleich stellt der Leitungssatz mit seiner nahezu unendlichen Kombinatorik aus Einzelkomponenten eine prädestinierte Industrie 4.0-Komponente in Losgröße 1 dar.
-   Mit der Perspektive auf der späteren Umsetzung der VWS in realen Lieferbeziehungen ergeben sich Ansätze und Fragestellungen, die bisher wenig Beachtung in der allgemeinen Entwicklung der VWS fanden und für die Skalierung dieser essenziell sind.
-   Mit dem Einsatz von verteilten Verwaltungsschalen in einem Datenraum legt VWS4LS eine Grundlage für den Einsatz von Catena-X in der Wertkette „Leitungssatz“.
-   Im Projekt VWS4LS erfolgte eine der ersten Implementierungen des Konzepts der Verbundkomponente sowie der automatisierten Verhandlung nach den Ansätzen der vernetzten Verwaltungsschalen.
-   Mit der Versionierung von VWS werden Fragen aufgeworfen, die Impulse für die weitere Arbeit in der Industrial Digital Twin Association (IDTA) liefern.

Aus dieser Positionierung ergaben sich für das Projekt relevante Chancen, aber auch Herausforderungen, die während der Projektlaufzeit gelöst werden sollen. Folgende Kernfragen müssen dabei geklärt werden:

-   Wie sieht der aktuelle Wertschöpfungsprozess des Leitungssatzes aus? Wer trägt welche Verantwortungen? Welche Daten müssen wann zu wem?
-   Wo liegen die Digitalisierungslücken und wie können diese durch die Anwendung der VWS reduziert oder geschlossen werden?
-   Gibt es im System nur ein einziges unternehmensübergreifendes VWS-Repository (Konsortium- oder OEM-spezifisch) oder eher ein dezentrales System, in dem jedes beteiligte Unternehmen ein eigenes VWS-Repository betreiben kann?
-   Was sind die Herausforderungen des Identity Managements?
-   

## <a name="_2"></a>2. Ausgangspunkt und Leitfragen für die Konzeptentwicklung

Im Rahmen eines projektinternen Workshops am 16.02.2023 wurde ein Big-Picture zur Orientierung für das Gesamtprojekt erstellt. Als Orientierungsrahmen diente dabei das Themenpuzzle in *Abbildung* 121. Die Teilnehmer, sowohl Experten aus dem Bereich der Leitungssatzbranche als auch aus dem Bereich der Verwaltungsschale, sollten klären, welche Lücken für die Anwendbarkeit der Verwaltungsschale in einer realen Wertkette geschlossen werden müssen und was aus Sicht der führenden Institute aus dem Bereich der Verwaltungsschalenanwendung schon möglich ist, bzw. in naher Zukunft umgesetzt werden kann.

![image](https://github.com/user-attachments/assets/1c462a99-ed29-47b9-9453-1a8c216a1b32)   
Abbildung 12-1: Ausgangspunkt Big Picture Workshop – Leitfragen und Erkenntnisziele

Um die Ausarbeitung voranzutreiben, wurde zu Beginn als gemeinsamer Startpunkt ein konkreter Use Case festgelegt, hier der Crimp-Prozess, anhand dessen die relevanten umsetzungstechnischen Fragen an die VWS formuliert wurden.

Wesentliche identifizierte Kernpunkte für die architektonischen Gestaltungsfelder waren zum einen die IT-Architektur bzgl. der VWS-Verwaltung, sowie der sog. „Single Point of Truth“ [1], auf welche in den Folgekapiteln näher eingegangen wird.

### <a name="_2.1"></a>2.1 Zentrale vs. dezentrale Architektur

Ein typischer **zentral orientierter Architekturansatz** ist in *Abbildung* 122 dargestellt. Bei der Diskussion dieses Ansatzes wurde jedoch deutlich, dass er nicht in jeder Situation der Leitungssatzentwicklung und -produktion genutzt würde und sich außerdem die Frage stellt, wer für die Verwaltung des zentralen VWS-Repositories zuständig wäre.

![image](https://github.com/user-attachments/assets/ab7149a5-6b64-4ff8-9504-c450a8db38b5)   
Abbildung 12-2: Zentrale VWS-Architektur

Bei einer **dezentralen Architektur** wird davon ausgegangen wird, dass der OEM und jeder Zulieferer ihr eigenes Repository hosten, d.h. es im System mehr als eine VWS-Registry und ein VWS-Repository gibt [2]. Jeder Auftraggeber in der Wertkette betreibt eine Registry, um es den Auftragnehmern zu ermöglichen, sich an der jeweiligen VWS des Auftraggebers anzumelden. Die resultierende IT-Architektur könnte sich wie in *Abbildung* 123 dargestellt an der entwickelten VWS-Struktur des Bordnetzes orientieren und eine entsprechende Vernetzung von VWS-Repositories und -Registries in einem vermaschten Netzwerk ergeben, in der jedes Unternehmen seine VWS anderen Unternehmen zur Verfügung stellen kann. Das geschieht über die Bereitstellung von VWS-Registries auf der Seite der Unternehmen, die Daten nach außen geben wollen. Durch entsprechende Zugriffsbeschränkungen können dann externe Unternehmen auf die für sie freigegebenen VWS zugreifen. Diese Informationen aus der Referenzierung können später für die Synchronisation genutzt werden.

Anmerkung: *Abbildung* 123 zeigt die erweiterte dezentrale Architektur beispielhaft mit nur einem OEM

![image](https://github.com/user-attachments/assets/c33de2a5-2699-460b-8da9-e5c31581b0d9)   
Abbildung 12-3: Dezentrale VWS-Architektur

Bei diesem dezentralen Ansatz setzen sich die Informationen der VWS einer Leitungssatz-Komponente (LS-Komponente) also über die Hierarchiestufen mehrerer Unternehmen zusammen, deren VWS aufeinander verweisen. Beispielsweise werden die Daten für LS-Komponenten von den Komponentenherstellern initial erzeugt und später von dem Konfektionär oder OEM genutzt, jedoch mit einer reduzierten Sicht auf die Inhalte (bspw. werden lediglich Informationen wie bzw. Digital Nameplate [3] und Produktdaten [4] weitergegeben).

### <a name="_2.2"></a>2.2 Single Point of Truth

Ein wichtiger Punkt im Kontext der Architektur ist die Definition des sog. „Single Point of Truth“ (SPoT) [1], also wo die aktuell gültige Version der VWS abgelegt ist, bzw. bezogen werden kann.

Aus den bisherigen Ergebnissen des VWS4LS-TP2 „Entwicklung des Leitungssatzes“, geht hervor, dass der SPoT in den verschiedenen Lebenszyklen des Leitungssatzes immer bei einem anderen Teilnehmer liegt und deshalb eine entsprechende Rückverfolgbarkeit durch die Schichten gewährleistet sein muss. In der Entwicklungsphase bspw. besitzt der OEM den SPoT, während in der Produktion der Konfektionär den SPoT besitzt (*Abbildung* 124).

![image](https://github.com/user-attachments/assets/6532990c-3f7b-4c9e-841b-55957af61347)   
Abbildung 12-4: Wechselnder SPoT im Lebenszyklus des Leitungssatzes

Wobei sich die Frage stellt, ob diese Festlegung über alle Schichten (Tier-1 bis Tier-n) hinweg gültig ist, oder es in jeder Schicht SPoT’s geben kann, die nur an die dortige LS-Komponente gebunden sind.

Der SPoT wurde anhand des folgenden konkreten Beispiels näher betrachtet, der Reaktionskette in einem Schadensfall an einem Auto:

Ist ein Schaden in der Elektronik an einem Auto aufgetreten, wendet sich der Kunde zuerst mit der Seriennummer des Autos an den OEM. Der OEM ist für den Kunden die erste Anlaufstelle, da er alle Herstellungsdaten zusammenführt und somit sein SPoT ist. Der OEM wiederum betrachtet den Schadensfall und kann den betroffenen Leitungssatz einem Konfektionär zuordnen. Hier ist der Konfektionär der SPoT für den OEM. Dieses Verfahren geht bis in die unterste Ebene.

Das Beispiel in *Abbildung* 125 verdeutlicht, wie die VWS-Struktur den Aufbau des Leitungssatzes abbildet und wo die kontextabhängigen SPoTs liegen, die zusammen ein sog. „Network of Truth“ bilden.

![image](https://github.com/user-attachments/assets/c8738dc6-4fd0-4953-95c5-b05cc06c37d2)   
Abbildung 12-5: Network of Truth

### <a name="_2.3"></a>2.3 Gestaltungsfelder

Es wurden sechs grundsätzliche architektonische Gestaltungsfelder in Verbindung mit der VWS identifiziert, diese sind in Tabelle 121 aufgelistet.

Tabelle 121: Architektonische Grundfragestellungen

| **Gestaltungsfelder für Architektur der VWS** | **Kurzerklärung**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modularisierung                               | Strukturierung von VWS und Teilmodellen, d.h. die Partitionierung und Vernetzung von VWS untereinander.                                                                                                                                                                                                                                                                                                                                                                                                             |
| Verlinkung                                    | Verlinkung als technische Lösung zur Vernetzung von Teilmodellen, wie zum Beispiel dem Teilmodell „Leitungssatzspezifikation“ und dem Teilmodell „Crimpprozess“, sowie Teilmodell-Versionen und VWS. Verlinkungen können sowohl innerhalb einer VWS als auch zwischen mehreren Verwaltungsschalen entstehen.                                                                                                                                                                                                        |
| Versionierung                                 | Versionierung in der VWS dient zur Verwaltung und Nachverfolgung von Änderungen an Daten und Teilmodellen. Damit können unterschiedliche Versionen erstellt und verwaltet werden, denn es wird sichergestellt, dass alle Änderungen nachvollziehbar und abgrenzbar sind. Dies ist besonders wichtig, wenn mehrere Akteure beteiligt sind, um Klarheit darüber schaffen zu können, welche Variante gültig ist und welche Version zu einem bestimmten Zeitpunkt für bestimmte Anwendungen oder Benutzer relevant ist. |
| Synchronisation                               | Synchronisation im Bereich der VWS bezieht sich auf die technische Lösung zur Aktualisierung abhängiger Daten, um sicherzustellen, dass alle Informationen konsistent und aktuell sind. Dabei ergeben sich einige wichtige Fragestellungen: Wie identifiziert man die Verlinkungen oder referenzierten Daten? Wie wird die Übereinstimmung zwischen dem physischen Asset und den Daten in den VWS gewährleistet? Diese Aspekte sind entscheidend, um eine verlässliche Synchronisation sicherzustellen.             |
| Rückverfolgbarkeit                            | Wie kann die durchgängige Rückverfolgbarkeit von Daten in der Wertschöpfungskette auch über Unternehmensgrenzen hinweg sichergestellt werden?                                                                                                                                                                                                                                                                                                                                                                       |
| Änderungsmanagement                           | Wie können in Bezug auf die Engineering-Prozesse in der Leitungssatzentwicklung Änderungen an VWS teilautomatisiert umgesetzt werden?  Wie werden Änderungen einer übergeordneten Instanz lokalisiert und dokumentiert?                                                                                                                                                                                                                                                                                             |

Diese sechs Grundbausteine werden in den Folgekapiteln besprochen und sollen anschließend den führenden VWS-Initiativen zur Verfügung gestellt und von diesen bewertet werden.

## <a name="_3"></a>3. Modularisierung

Da jede VWS über spezifische Teilmodelle verfügt, befasst sich die Modularisierung mit der inhaltlichen Struktur der definierten VWS.

Der Leitungssatz wird dabei sinnvoll in mehrere, eigenständige Module aufgeteilt, die ihre eigenen VWS und Teilmodelle besitzen können. Jede im Leitungssatz verbaute Komponente oder Halbfabrikat kann als Modul definiert werden.

• Ein **Halbfabrikat im Bordnetz** ist ein vorgefertigtes, teilweise bearbeitetes Bauteil oder eine Baugruppe, die im Herstellungsprozess eines Fahrzeugkabelbaums verwendet wird.

• Ein **Funktionsmodul** ist eine vorkonfigurierte, eigenständige Komponente oder Einheit innerhalb eines Kabelbaums, die spezifische elektrische oder elektronische Funktionen erfüllt. Diese Module sind so gestaltet, dass sie sich nahtlos in den Gesamtleitungssatz integrieren lassen und bestimmte Aufgaben wie die Verbindung von Sensoren, Aktoren, Steuergeräten und anderen elektrischen Komponenten übernehmen.

In der Analyse der erforderlichen VWS und Teilmodelle für die *Abbildung* des Leitungssatzes ist es von entscheidender Bedeutung, die verschiedenen Stakeholder im Entwicklungs- und Produktionsprozess zu berücksichtigen für eine detaillierte Betrachtung darüber,

• welche Informationen über den Leitungssatz benötigt werden,

• welche Stakeholder VWS mit diesen Informationen besitzen sollen, und

• welche spezifischen Inhalte diese VWS für die Stakeholder haben sollen.

Ebenso wichtig ist die Klärung, mit wem diese Inhalte geteilt werden müssen und in welchem Umfang dies geschehen muss.

Als Orientierungshilfe diente auch das PPR-Modell) [5], um festzulegen, welches Asset eine VWS erhält und wer im Lebenszyklus des Leitungssatzes Informationen dieses Assets benötigt bzw. beiträgt (*Abbildung* 126).

![image](https://github.com/user-attachments/assets/aa140b46-d5be-4f1a-bd53-df66643ef8c1)   
Abbildung 12-6: Ermittlung der Assets und Nicht-Assets mit Stakeholderzuweisung

Es hat sich dabei als zielführend herausgestellt, zwischen den beiden im Projekt überwiegend betrachteten Lebensphasen des Leitungssatzes zu unterscheiden: Im **Entwicklungsprozess** stehen die Typ-Beschreibungen von Modulen des Leitungssatzes im Mittelpunkt und dementsprechend deren VWS. Im **Produktionsprozess** geht es hingegen um die Instanzen der verbauten Module, also die konkreten Umsetzungen der im Entwicklungsprozess definierten Assets. Dementsprechend werden für den Produktionsprozess Verwaltungsschalen für die Instanzen von Modulen benötigt.

### Aufteilung des Leitungssatzes in Module

Die Analyse beginnt mit der Identifizierung der verschiedenen Funktionsmodule und ihrer Beziehungen zueinander, aus denen der Leitungssatz besteht. Ein **Funktionsmodul** ist eine vorkonfigurierte, eigenständige Komponente oder Einheit eines Bordnetzes, die spezifische elektrische oder elektronische Funktionen erfüllt. Diese Module sind so gestaltet, dass sie sich nahtlos in den Gesamtleitungssatz integrieren lassen und bestimmte Aufgaben wie die Verbindung von Sensoren, Aktoren, Steuergeräten und anderen elektrischen Komponenten übernehmen.

Ein Funktionsmodul lässt sich wiederum in mehrere Halbfabrikate unterteilen. Ein **Halbfabrikat** im Bordnetz ist ein vorgefertigtes, teilweise bearbeitetes Bauteil oder eine Baugruppe, die im Herstellungsprozess eines Fahrzeugkabelbaums verwendet wird. Diese Halbfabrikate sind im Gegensatz zu Funktionsmodulen keine Endprodukte, sondern Zwischenstufen, die noch weiterverarbeitet werden müssen, um in das Gesamtsystem des Fahrzeugbordnetzes eingebaut zu werden.

Zudem werden die **Ressourcen** mit ihren Informationen betrachtet, die im Produktionsprozess zur Herstellung des Leitungssatzes genutzt werden (siehe *Abbildung* 127).

![image](https://github.com/user-attachments/assets/e3c131f8-e4b3-49ae-9921-377fa9c85af5)   
Abbildung 12-7: Modularisierung des Leitungssatzes

### <a name="_3.2"></a>3.2 Verwaltungsschalen im Entwicklungsprozess

Im Entwicklungsprozess des Leitungssatzes entstehen bei den verschiedenen Stakeholdern eigene VWS für ein und dasselbe Asset, was in *Abbildung* 128 schematisch dargestellt ist.

![image](https://github.com/user-attachments/assets/9d3cc8d6-cb94-4bce-8e22-e851beb28270)   
Abbildung 12-8: Übersicht über VWS der jeweiligen Stakeholder im Entwicklungsprozess

Hierbei kann davon ausgegangen werden, dass die Stakeholder sowohl Asset-Informationen aus den VWS anderer Stakeholder beziehen als auch selbst Informationen zum Asset hinzufügen wollen. Deshalb wurde entschieden, die Möglichkeit der Existenz mehrerer VWS zu einem Asset zuzulassen und die Zuordnung der VWS untereinander über Versionierung und Verlinkung zu lösen.

### <a name="_3.3"></a>3.3 Verwaltungsschalen im Produktionsprozess

Ähnlich wie im Entwicklungsprozess, gibt es auch für den Produktionsprozess des Leitungssatzes mehrere Stakeholder-spezifische VWS für ein und dasselbe Asset. Im Produktionsprozess entstehen somit mehrere VWS zu einem Asset, was in *Abbildung* 129 dargestellt ist.

![image](https://github.com/user-attachments/assets/94149cbc-7cf2-493b-bdc2-16efa15f752a)     
Abbildung 12-9: Übersicht über VWS der jeweiligen Stakeholder im Produktionsprozess

### <a name="_3.4"></a>3.4 Inhalte und Verknüpfung der Stakeholder-Verwaltungsschalen

Die Stakeholder-spezifischen VWS enthalten Informationen, die den Anforderungen und Erwartungen des jeweiligen Stakeholders gerecht werden. Dies können technische Spezifikationen, Sicherheitsrichtlinien, Qualitätsstandards, Produktionsinformationen, Dokumentationen und andere relevante Informationen sein, die in Form von Teilmodellen oder verlinkten proprietären Dateiformaten vorliegen. Ein Abgleich der abzubildenden Informationen mit den bereits bei der IDTA vorhandenen Teilmodellen [6], zeigt die Lücken für weiteren Entwicklungsbedarf seitens des Projektes auf. Neu zu entwickelnde Teilmodelle werden in den folgenden Abschnitten explizit genannt.

Durch die kollaborative Zusammenarbeit der Stakeholder war zu klären, welche VWS-Inhalte untereinander geteilt werden. Dazu wurde eine tabellarische Anforderungsanalyse durchgeführt, die bis zur Ebene des Inhalts eines Teilmodells die Zugriffsrechte definiert (siehe Datei „[Anforderungsanalyse_Architektur_20230713.xlsx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/General/Anforderungsanalyse_Architektur_20230713.xlsx)“[^1].

[^1]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/General/Anforderungsanalyse_Architektur_20230713.xlsx>

In den folgenden *Abbildung*en werden die VWS aus *Abbildung* 128 und *Abbildung* 129 mit Teilmodellen angereichert. Grüne und rote Markierungen vor den Teilmodellen kennzeichnen die Zugriffsrechte. Grüne Teilmodelle werden extern geteilt, die Roten dürfen nur durch den Stakeholder gelesen und bearbeitet werden. Zu einigen Teilmodellen, wie bspw. dem Teilmodell „IDTA 02204: *Handover Documentation“* [7] [7] ist zusätzlich beschrieben, welche Dokumente dort abgelegt werden. Weiterhin zeigen die *Abbildung*en die Verknüpfung der unterschiedlichen Stakeholder-VWS in dem Entwicklungs- und Produktionsprozess des Leitungssatzes. Ein Hosting der VWS auf verschiedenen Servern wird ebenfalls angedeutet.

#### VWS für die Ressource

Sowohl die VWS zu den Ressourcen-Typen, aus denen sich der Konfektionär eine Ressource konfigurieren kann, als auch die VWS zu den Ressourcen-Instanzen, die später beim Konfektionär betrieben werden, erhalten ein Repository (*VWS Repo-Typen* und *VWS Repo-Instanzen*) bei dem Maschinenhersteller (*Abbildung* 1210).

Die *Abbildung* des modularen Aufbaus der Ressourcen wird in der Ressourcen-VWS mit Hilfe des Teilmodells *„*IDTA 02011*: Hierarchical Structures enabling Bills of Material“* [8] [8] vorgenommen, dass Referenzen auf die einzelnen VWS der Ressourcenmodule beinhaltet. In den Modul-VWS ist lediglich das digitale Typenschild [3] zur Identifizierung des Moduls vorhanden.

![image](https://github.com/user-attachments/assets/8154a64d-7087-427d-99a6-ef12779fbe15)   
Abbildung 12-10: VWS und deren Verknüpfung für die Ressource

Hat der Konfektionär mit Hilfe der VWS der Ressourcen-Typen seine Maschine im Entwicklungsprozess des Leitungssatzes konfiguriert und wurde diese errichtet, erhält der Konfektionär mit Anlieferung der Maschine auch die VWS der Ressourcen-Instanz und kann diese in seinem eigenen Repository abspeichern. Hierbei erhält der Konfektionär nur die Teilmodelle, die für ihn vom Maschinenhersteller freigegeben sind. Damit bei Änderungen durch den Maschinenhersteller auch die Informationen bei dem Konfektionär aktuell gehalten werden können, wird mit Hilfe der Verlinkung zwischen den beiden VWS der Ressourcen-Instanz eine Beziehung gelegt.

Möchte der Konfektionär eigene Informationen zu den Maschinen hinzufügen ist eine Möglichkeit, eine weitere VWS für die Ressource im eigenen System anzulegen und diese über die *specificAssetID* des VWS-Metamodells Version 3 zu verknüpfen. Zu sehen ist der beschriebene Aufbau in *Abbildung* 1210.

#### VWS für die Komponenten

Die Informationen sowohl zu den Komponenten-Typen als auch -Instanzen beinhalten das *Produktmodell*, bei dem die Branchenstandards KBL [9] bzw. VEC [10] in Dateiform als *Product Specification* an die Komponente angehangen wird. Das bei der IDTA in Entwicklung befindliche Teilmodell „*BillOfProcess*“ [11] wird für die *Produktionsdaten* verwendet.

Im **Entwicklungsprozess** des Leitungssatzes stellt der Komponentenhersteller seine VWS zum Komponenten-Typen dem OEM, den Konfektionär und den Werkzeugherstellern zur Verfügung. Die betroffenen Stakeholder legen sich diese VWS typischerweise in einem internen Repository ab („VWS-Repository fremde Komponenten-Typen“). Die Verbindung mit der originalen VWS erfolgt mit Hilfe der Verlinkung.

Der OEM möchte im Entwicklungsprozess Ergänzungen (z.B. Freigabe von Komponenten für eine spezielle Baureihe) oder Einschränkungen (z.B. ein Kontaktteil wurde für einen bestimmten Querschnittsbereich ausgelegt, darf bei einem OEM jedoch nur für einen geringeren Querschnittsbereich eingesetzt werden) zu der Komponente vornehmen. Dafür legt er eine eigene VWS an und speichert diese in einem Repository mit den eigenen Komponenten-VWS. Durch die *specificAssetID* kann er die VWS des Komponentenherstellers, die bereits in seinem System bekannt ist, mit seiner eigenen VWS verknüpfen und somit die Informationen erweitern.

Im Austausch mit dem Konfektionär gibt der OEM seine VWS *OEM-Komponente* an den Konfektionär weiter. Diese VWS kann der Konfektionär sich in seinem System speichern. Durch die vom OEM bereitgestellte *specificAssetID* kann der Konfektionär die VWS-Komponente vom Komponentenhersteller direkt anfragen. Ähnlich dem OEM kann dann auch der Konfektionär seine VWS für die Komponenten hinzufügen.

Der Werkzeughersteller, der nur an den Komponenteninformationen interessiert ist, ohne diese verändern zu wollen, kann die Informationen immer direkt vom Server des Herstellers abgreifen oder sie sich in seinem eigenen System ablegen. Der beschriebene Aufbau für den Entwicklungsprozess ist in *Abbildung* 1211 zu sehen.

![image](https://github.com/user-attachments/assets/545394a5-f9bc-47f7-af29-ad3b3aaaac14)   
Abbildung 12-11: VWS und deren Verknüpfung für die Komponente im Entwicklungsprozess

Im **Produktionsprozess** des Leitungssatzes sind nur noch der Komponentenhersteller und Konfektionär beteiligt, weshalb sich die Systemarchitektur weniger komplex als im Entwicklungsprozess gestaltet. Jede VWS der Komponenten-Instanzen werden beim Komponentenhersteller in einem dafür vorgesehen Repository abgelegt. Bei Auslieferung der Komponente, wird eine Kopie dieser VWS an den Konfektionär übergeben und zusätzlich eine Verlinkung zwischen dem Original und der Kopie eingefügt. Eine Synchronisation der kopierten VWS ist hierbei nicht vorgesehen, da Änderungen an den Informationen zu einer bereits produzierten Komponente unwahrscheinlich sind. Prinzipiell ist jedoch eine manuelle Synchronisation möglich. Zu sehen ist der Aufbau in *Abbildung* 1212.

![image](https://github.com/user-attachments/assets/161bc4f4-d99c-410d-a78f-900019b80fbd)   
Abbildung 12-12: VWS und deren Verknüpfung für die Komponente im Produktionsprozess

#### VWS für den Leitungssatz

Im Entwicklungsprozess übergibt der OEM dem Konfektionär einen vordefinierten Leitungssatz-Typ, den der Konfektionär zum Produkt entwickeln soll. Die Informationen zu dem Leitungssatz-Typ beinhalten neben den Standardinformationen wie den Dokumentationen und Kontaktdaten auch das selbst entwickelte *Produktmodell* mit der VEC- bzw. KBL-Datei und verschiedene Stücklisten (*Configuration BoM*, *Product BoM*) zu der Zusammensetzung des Leitungssatzes. Die Stücklisten wurde dabei von dem *Hierachical Structures Enabling Bill of Material* Teilmodell abgeleitet.

Der OEM stellt über sein eigenes Repository die VWS zu dem Leitungssatz mit verringertem Informationsgehalt dem Konfektionär bereit. Dieser wiederum speichert diese VWS *OEM-Leitungssatz* bei sich im System ab. Danach kann der Konfektionär die Entwicklung des Leitungssatzes, basierend auf der Vorgabe des OEM, beginnen. Dabei entstehen neben der Leitungssatz-VWS auch VWS zu den einzelnen Funktionsmodulen und Halbfabrikaten. Die Verlinkung unterhalb dieser VWS ist in dem Kapitel 12.3 näher beschrieben.

In den VWS, die der Konfektionär erstellt, kommt als Teilmodell die Manufacturing BoM hinzu. Der Zweck dieses Teilmodells ist ebenso in Kapitel 12.3 beschrieben. Zudem wird das BoM-Teilmodell (150%) eingeführt, dass eine Modellierung der notwendigen Prozessschritte zur Herstellung der Leitungssatzinstanzen erlaubt. Das Teilmodell steht eng mit dem Teilmodell *Bill of Process* (ID: 02031-1) in Verbindung. Der beschriebene Aufbau ist in *Abbildung* 1213 zu sehen.

Während des Produktionsprozesses, werden die VWS für die Instanzen aus den VWS des Leitungssatzes und seiner Funktionsmodule und Halbfabrikate aus dem Entwicklungsprozess abgeleitet und mit Instanz-Informationen angereichert. Die VWS zu den Instanzen werden in einem separaten Server gespeichert, auf den der OEM später Zugriff hat. Außer dem Produktmodell und der dazugehörigen Dokumentation, verbleiben alle weiteren Informationen bei dem Konfektionär allein. Zu sehen ist der Aufbau in *Abbildung* 1214.

![image](https://github.com/user-attachments/assets/1d410311-09fd-4b97-906d-43dc34ddf338)   
Abbildung 12-13: VWS und deren Verknüpfung für den Leitungssatz im Entwicklungsprozess

![image](https://github.com/user-attachments/assets/5fd5b883-1f58-4a7e-a243-717123a1b88f)   
Abbildung 12-14: VWS und deren Verknüpfung für den Leitungssatz im Produktionsprozess

Wird mit Auslieferung des Leitungssatzes der Montageprozess für diesen angestoßen, erhält der OEM eine VWS mit lediglich dem Produktmodell und der Übergabedokumentation (siehe *Abbildung* 1215). Diese kann der OEM in seinem eigenen System ablegen. Alle anderen Informationen stehen dem OEM nicht direkt zur Verfügung. Jedoch kann der OEM in Spezialfällen einzelne dieser Informationen beim Konfektionär anfordern.

![image](https://github.com/user-attachments/assets/35b28018-d786-4160-b2ee-0915d18ed9a4)   
Abbildung 12-15: VWS und deren Verknüpfung für den Leitungssatz im Montageprozess

## <a name="_4"></a>4. Verlinkung

Das Produktmodell beschreibt den Aufbau des Leitungssatzes. Ausgehend von der Produktspezifikation erzeugt der OEM eine Verwaltungsschale für den sog. „150% Leitungssatz“ und verlinkt diesen mit seinen Komponenten (vgl. Kapitel 6).

Der Konfektionär erzeugt eine Kopie dieser Verwaltungsschale und verlinkt diese mit der Verwaltungsschale des OEM sowie den eigenen Verwaltungsschalen der Komponenten („Umschlüsselung“). Auf dieser Grundlage leitet der Konfektionär eine mehrstufige Zerlegung in weitere Halbfabrikate nach Bedarf ab. Die Definition der Halbfabrikate kann ebenfalls varianzbehaftet sein (150% Halbfabrikate).

Im Falle einer Bestellung erhält der Konfektionär vom OEM eine Beauftragung mit genauen Informationen über die gewünschte Ausstattung. Der Konfektionär erzeugt eine Verwaltungsschale für jede Leitungssatzinstanz und verknüpft diese mit der Verwaltungsschale des OEM, um eine durchgehende Rückverfolgbarkeit zu gewährleisten.

Alle Verlinkungen, die hierbei zwischen Konfektionär und OEM entstehen, zeigen vom Konfektionär zum OEM. Damit wird sichergestellt, dass der Konfektionär unabhängig vom OEM auf Informationselemente verlinken kann und somit keinen Schreibzugriff auf die Verwaltungsschale des OEM benötigt.

Das Produktmodell besteht aus den folgenden Teilmodellen:

-   *ProductSpecification*
-   *ProductBoM*
-   *ProductConfigurationBoM*
-   *ManufacturingBoM*
-   *ManufacturingConfigurationBoM*



### Typ-Verwaltungsschale des OEM

Die *ProductSpecification*, *ProductConfigurationBoM* und *ProductBoM* werden in der Typ-Verwaltungsschale des Leitungssatzes zusammengefasst (*Abbildung* 1216).

![image](https://github.com/user-attachments/assets/45ad3fd0-0b29-4efc-b9cc-9ff57d5fb8c3)   
Abbildung 12-16: Typ-VWS des Leitungssatzes aus Sicht des OEM

Diese VWS beschreibt den kompletten Aufbau des 150% Leitungssatzes aus Sicht des OEM. Der Konfektionär erstellt von dieser VWS eine Kopie und reichert diese mit seiner *ManufacturingBoM* an.

#### Teilmodell ProductSpecification

Die *ProductSpecification* beinhaltet eine vollständige Spezifikation des Assets als KBL-, VEC- oder vergleichbares Informationsmodell mit *Relationship*-Elementen, um Beziehungen zwischen dem Informationsmodell und anderen Teilmodellen herzustellen (*Abbildung* 1217). Es dient in erster Linie als Bindeglied zwischen Informationsfragmenten des serialisierten Informationsmodells (z.B. XML) und anderen Teilmodellen der Verwaltungsschale. Da für die *ProductSpecification* zum aktuellen Zeitpunkt keine geeignete Teilmodellvorlage der IDTA existiert, wird hilfsweise direkt die KBL- oder VEC-Datei als solche in der VWS mitgeführt. Das könnte zukünftig als Best-Practice-Ansatz in eine IDTA-Submodell-Definition übernommen.

![image](https://github.com/user-attachments/assets/cd079082-ec15-430c-8120-8420f5df7297)   
Abbildung 12-17: Teilmodell "ProductSpecification"

#### Teilmodell ProductBoM

Ausgehend von der Produktspezifikation werden die *ProductBoM* und die *ProductConfigurationBoM* abgeleitet.

Die *ProductBoM* beinhaltet alle Komponenten, die in einem Asset verwendet werden. Jedes Vorkommen einer Komponente wird in der *ProductBoM* einzeln aufgeführt, um eine eindeutige Identifikation für jede Komponentenverwendung zu ermöglichen (*Abbildung* 1218). Für dieses Teilmodell wird die Teilmodellvorlage „IDTA 02011: Hierarchical Structures enabling Bills of Material“verwendet. Gemäß dieser Struktur wird für jede Komponentenverwendung eine *Self-Managed Entity* erzeugt und im Teilmodell hinterlegt. Diese verweisen auf die jeweiligen Verwaltungsschalen des Komponententyps.

Die *ProductBoM* kann auch zusammengesetzte Komponenten enthalten. In diesem Fall besteht eine zusammengesetzte Komponente aus einer oder mehreren Teilkomponenten, die jeweils auf die Verwaltungsschalen des Komponententyps verweisen.

![image](https://github.com/user-attachments/assets/91d0072a-8dec-47da-9f3e-0719ab89684c)   
Abbildung 12-18: Teilmodell "ProductBoM"

#### Teilmodell ProductConfigurationBoM

Die *ProductConfigurationBoM* beinhaltet alle Optionen bzw. Varianten, aus denen spätere Asset-Instanzen zusammengesetzt werden können. Hierfür wird die Teilmodellvorlage „IDTA 02011: Hierarchical Structures enabling Bills of Material“verwendet und für jede Option bzw. Variante eine *Co-Managed Entity* erzeugt, die wiederum aus einer oder mehreren Halbfabrikaten oder Komponenten besteht (*Abbildung* 1219).

![image](https://github.com/user-attachments/assets/64af2df9-8176-4780-a80a-b30a3f1530c6)   
Abbildung 12-19: Teilmodell "ProductConfigurationBoM"

Sowohl die *ProductBoM* als auch die *ProductConfigurationBoM* werden durch die *ProductSpecification* referenziert. Des Weiteren bestehen zwischen den Entitäten der *ProductConfigurationBoM* und der *ProductBoM* *sameAs*-Beziehungen, um die semantische Äquivalenz der Komponenten eindeutig zu definieren.

### Typ-Verwaltungsschale (Konfektionär)

Aus den Teilmodellen *ProductSpecification*, *ProductBoM*, *ManufacturingBoM* und *ManufacturingConfigurationBoM* ergibt sich ein Gesamtmodell der Typ-Verwaltungsschale des 150% Leitungssatzes aus Sicht des Konfektionärs (*Abbildung* 1220).

![image](https://github.com/user-attachments/assets/76894c68-38b3-4e3f-acb8-4571fe927c21)   
Abbildung 12-20: Typ-VWS des Leitungssatzes aus Sicht des Konfektionärs

Die hier dargestellte Struktur wird rekursiv für alle Halbfabrikate des Konfektionärs angewendet. Bei Halbfabrikaten ohne Varianz kann die *ManufacturingConfigurationBoM* entfallen (die *sameAs*-Beziehung zwischen Halbfabrikat der *ManufacturingBoM* und *ConfigurationElement* der *ManufacturingConfigurationBoM* des nächsten Halbfabrikats ist optional).

Aus Gründen der Wiederverwendbarkeit von Typ-Verwaltungsschalen (beispielsweise eines Halbfabrikats, welches bereits für einen anderen Leitungssatz beschrieben wurde), müssen zwischen den Komponenten der Verwaltungsschalen entsprechende *sameAs*-Beziehungen hergestellt werden (*sameAs*-Beziehung zwischen Komponente der *ManufacturingBoM* und Komponente der *ProductBoM* des nächsten Halbfabrikats). Für Halbfabrikate der untersten Ebene (nicht weiter aufgeteilt in weitere Halbfabrikate) gilt diese Regel nicht. Deswegen ist die *sameAs*-Beziehung zwischen den Komponenten der *ManufacturingBoM* und *ProductBoM* des nächsten Halbfabrikats optional.

Aufgrund der *sameAs*-Beziehungen kann bei wiederverwendeten Halbfabrikaten von einer Äquivalenz der Produktspezifikation ausgegangen werden, auch wenn sich die konkreten Bezeichnungen (z.B. Komponentenbezeichnungen) unterscheiden.

Um den Zusammenhang mit den Komponenten und Entitäten des OEM darzustellen, hinterlegt der Konfektionär bei seinen Verwaltungsschalen die *specificAssetId* des OEM und verlinkt die Komponenten der *ProductBoM* und die Module der *ConfigurationBoM* mittels *sameAs*-Beziehungen (*Abbildung* 1221). Da der Konfektionär zusätzliche Komponenten zur *ProductBoM* hinzufügen kann, ist die *sameAs*-Beziehung zwischen der *ProductBoM* des Konfektionärs und OEM optional.

Sollte vom OEM keine Verwaltungsschale zur Verfügung stehen, hat der Konfektionär grundsätzlich die Möglichkeit auf diese Verknüpfungen zu verzichten und unabhängig zu agieren.

![image](https://github.com/user-attachments/assets/c913d353-831b-4871-a27b-5dde1e0f0fbc)   
Abbildung 12-21: Typ-VWS des Leitungssatzes aus Sicht des Konfektionärs

#### Teilmodell ManufacturingBoM (Konfektionär)

Die *ManufacturingBoM* beschreibt den Zusammenbau des Leitungssatzes bzw. eines Halbfabrikats aus Komponenten und Halbfabrikaten (*Abbildung* 1222). Hierfür wird die Teilmodellvorlage „IDTA 02011: Hierarchical Structures enabling Bills of Material“ [8] verwendet. Für jedes Halbfabrikat und für jede Komponente werden entsprechende *Self-Managed Entities* erzeugt. Diese verweisen auf die VWS der Halbfabrikate bzw. Komponenten.

![image](https://github.com/user-attachments/assets/959405a8-f566-47f5-8c26-187da3efbdb6)   
Abbildung 12-22: Teilmodell "ManufacturingBoM"

#### Teilmodell ManufacturingConfigurationBoM (Konfektionär)

Die *ManufacturingBoM* wird mit der *ManufacturingConfigurationBoM* verlinkt, die an Stelle der *ProductConfigurationBoM* des OEM tritt (*Abbildung* 1223). Hierdurch kann von einer konkreten Leitungssatz-Konfiguration auf die notwendigen Halbfabrikate und Komponenten der *ManufacturingBoM* geschlossen werden.

![image](https://github.com/user-attachments/assets/91ff133d-2bc4-47ec-8129-4951ff142bff)   
Abbildung 12-23: Beziehungen "ManufacturingConfigurationBoM" und "ManufacturingBoM"

#### Teilmodell ProductBoM (Konfektionär)

Die *ProductBoM* des OEM bleibt weitestgehend unverändert bestehen. Der Konfektionär fügt bei Bedarf zusätzliche Komponenten hinzu und ändert die *AssetReferenzen* auf entsprechende Typ-Verwaltungsschalen seiner eigenen Komponenten, die wiederum mittels *specificAssetId* auf die Typ-Verwaltungsschalen des OEM verweisen. Des Weiteren werden *sameAs*-Beziehungen zwischen den Komponenten der *ManufacturingBoM* und der *ProductBoM* hergestellt, um semantisch klarzustellen, dass es sich hierbei um dieselbe Komponente handelt (*Abbildung* 1224).

![image](https://github.com/user-attachments/assets/cc2c0049-b6db-4756-b04c-99306791dfb5)   
Abbildung 12-24: Verlinkung mit dem Teilmodell "ProductBoM“

### Instanz-Verwaltungsschale des OEM

Im Auftragsfall erzeugt der OEM eine Instanz-Verwaltungsschale des Leitungssatzes und hinterlegt eine *ConfigurationBoM* mit der gewünschten Ausstattung. Mittels *sameAs*-Beziehung werden die *Configuration*-Elemente mit den entsprechenden *Configuration*-Elementen der Typ-Verwaltungsschale verlinkt (*Abbildung* 1225).

![image](https://github.com/user-attachments/assets/4a7236c0-1744-4068-85d9-8bbfe239d50b)   
Abbildung 12-25: Verlinkung Typ/Instanz-VWS beim OEM

### Instanz-Verwaltungsschale des Konfektionärs

Der Konfektionär erstellt eine Kopie der Instanz-Verwaltungsschale mit Beziehung auf seine eigene Typ-Verwaltungsschale. Zudem wird mittels *specificAssetId* auf die Verwaltungsschale des OEM verwiesen. Die *ConfigurationBoM* der Instanz-Verwaltungsschale wird sowohl mit der *ConfigurationBoM* der Typ-Verwaltungsschale als auch mit der Instanz-Verwaltungsschale des OEM verknüpft. Damit wird sichergestellt, dass der bestellte Umfang vollständig abgebildet ist.

Die Instanz-Verwaltungsschale des Konfektionärs beinhaltet zudem eine *ManufacturingBoM*, welche auf die entsprechenden Instanz-Verwaltungsschalen der Halbfabrikate und Komponenten verweist. Die *ManufacturingBoM* der Instanz-Verwaltungsschale ist wiederum mittels *sameAs*-Beziehungen mit der *ManufacturingBoM* der Typ-Verwaltungsschale verknüpft.

Sollte vom OEM keine Verwaltungsschale zur Verfügung stehen, hat der Konfektionär grundsätzlich die Möglichkeit auf diese Verknüpfungen zu verzichten.

Die Zusammenhänge der verschiedenen Typ- und Instanz-Verwaltungsschalen sind in *Abbildung* 1226 dargestellt.

![image](https://github.com/user-attachments/assets/8a5f34fd-5b9b-414a-9c0e-b664713808bd)    
Abbildung 12-26: Typ- und Instanz-VWS für den Leitungssatz

### <a name="_4.5"></a>4.5 Verlinkung des VEC

Ziel der Verlinkung des VEC ist es, die Typ- und Instanzinformationen mit entsprechenden Assets bzw. Verwaltungsschalen zu verknüpfen, sodass der VEC in einer VWS integriert und die Notwendigkeit zur Interpretation des VEC reduziert werden kann.

Im VEC sind identifizierbare Element mandatorisch und im jeweiligen Namensraum einzigartig und persistent. Das bedeutet, dass diese Elemente für eine eindeutige Zuordnung genutzt und auch bei Änderungen beibehalten werden können.

Unterschieden werden muss hierbei zwischen Typ- und Instanzinformationen, nachfolgend am Beispiel von Komponenten (engl. Parts) erläutert:

Bauteile werden im VEC durch Elemente vom Typ *PartVersion[^2]* identifiziert. Dazu gehört potenziell alles, was in klassischen PDM-Prozessen durch eine Sachnummer identifizierbar ist. Dies können zum Beispiel Komponenten und Leitungssatzmodule sein, aber auch andere Zusammenbauten bzw. Stücklistenteile. Alle Beschreibungen eines Teils (z.B. Stückliste und technische Daten) beziehen sich auf eine *PartVersion*.

[^2]: <https://ecad-wiki.prostep.org/specifications/vec/v202/classes/partversion/>

Komponentenvorkommen werden im VEC durch Elemente vom Typ *PartOccurrence[^3]* dargestellt. Hierbei handelt es sich um jeweils ein Vorkommen einer Komponente eines spezifischen Typs (*PartVersion*). Alle Komponenten eines (150%-)Leitungssatzes sind in einer *CompositionSpecification[^4]* enthalten. Die *PartOccurrence*s, die einem Modul enthalten sind, werden durch eine *PartStructureSpecification* definiert. Diese referenziert die *PartVersion* des Moduls als beschriebenes Teil.

[^3]: <https://ecad-wiki.prostep.org/specifications/vec/v202/classes/partoccurrence/>

[^4]: <https://ecad-wiki.prostep.org/specifications/vec/v202/classes/compositionspecification/>

Um die Typ- bzw. Instanzinformationen der VEC nutzen zu können, müssen einige Fragestellungen beantwortet werden:

1.  Wie können spezifische Informationsfragmente des VEC referenziert werden?
2.  Wie können Typeninformationen des VEC mit Assets verknüpft werden?

#### Referenzieren von Informationsfragmenten des VEC

Grundlage für die Verlinkung des VEC ist die Möglichkeit Informationsfragmente zu referenzieren. Da es sich beim VEC um eine XML-Struktur handelt, bietet sich hierfür die Abfragesprache XPath[^5] an.

[^5]: <https://www.w3.org/TR/xpath-31/>

Auf Seiten der Verwaltungsschale kann mittels *RelationshipElement* in eine entsprechende Zieldatei referenziert werden. Hierfür wird zunächst die VEC als *File*-Element (oder alternativ als *Blob*-Element) in der Verwaltungsschale hinterlegt. Anschließend wird ein *RelationshipElement* verwendet, um als *FragmentReference* mittels XPath in die Datei zu verweisen.

Das *File*- (oder *Blob*-)Element sollte dabei den Medientyp (*mimeType*) text/xml besitzen, damit entsprechende Softwarewerkzeuge die Datei korrekt einlesen können.

*Anmerkung:* In einer der nächsten Versionen des VEC sollen Elemente die Fähigkeiten erhalten global eindeutige IDs zu tragen; voraussichtlich URNs. Ab dann können diese als Referenzierungsanker verwendet werden und die Notwendigkeit zur Bildung hierarchischer XPath Ausdrücke entfällt.

**Beispiel**

Zunächst muss der XPath auf Grundlage der VEC-Datei abgeleitet werden. Die folgende Struktur soll dabei das exemplarische Vorgehen demonstrieren. In diesem Beispiel könnten die Elemente *DocumentVersion*, *Specification* sowie *Component* prinzipiell mehrmals vorkommen, worauf aus Gründen der Lesbarkeit verzichtet wurde:

Um in dieser Struktur auf das *Component*-Element zu verweisen, muss eine eindeutige Identifikation ermöglicht werden. Das Geschieht mittels der jeweiligen *Identification*-Elemente, bzw. der Dokumenteninformationen (*CompanyName*, *DocumentNumber*, *DocumentVersion*). Nachfolgend ist der zugehörige XPath definiert:

Um in der Verwaltungsschale auf das Element zu verweisen, wird die VEC-Datei zunächst als *File*-Element hinterlegt (*Abbildung* 1227). Anschließend wird ein *Entity*-Element erstellt, welches als Ankerpunkt dient und auf ein Asset verweist (*Abbildung* 1228). Zuletzt wird mittels eines *Relationship*-Elements eine Verlinkung zwischen dem *Entity*-Element und der VEC-Komponente hergestellt (*Abbildung* 1229).

![image](https://github.com/user-attachments/assets/f29b4f4c-bed9-4549-a34e-34bf95b142b5)   
Abbildung 12-27: VEC-Datei als File-Element in der Verwaltungsschale.

![image](https://github.com/user-attachments/assets/3bd75504-ebc6-4bf2-8fcb-7321855bd732)   
Abbildung 12-28: Entity-Element einer Komponente.

![image](https://github.com/user-attachments/assets/bc9272f4-4ad9-4c0f-b02c-12dd056c4247)   
Abbildung 12-29: Relationship-Element mit FragmentReference in VEC-Datei

#### Verlinkung von Typinformationen

Um die Typinformationen des VEC zu verlinken, bestehen grundsätzlich drei Möglichkeiten:

1.  Ableitung globaler Asset Identifier aus dem VEC

    Diese Möglichkeit setzt voraus, dass die globalen Asset IDs mithilfe eines Logikbausteins und definierten Konventionen aus den Komponenteninformationen errechnet werden können. Die hierfür notwendigen Konventionen können dabei, je nach gewünschter Granularität, unternehmens- oder projektspezifisch ausgelegt werden.

    **Beispiel:**

    *http://\<CompanyName\>/\<PrimaryPartType\>/\<PartNumber\>/\<PartVersion\>*

2.  Verwendung des Attributs *aliasId* aus dem VEC

    Diese Möglichkeit setzt voraus, dass der Ersteller der VEC für alle Komponenten die zugehörigen Asset Identifier pflegt.

    *aliasId* ist ein optionales Attribut der *PartVersion[^6]*-Klasse im VEC . Es dient in erster Linie dazu, einer Komponente zusätzliche Identifizierungsmerkmale mitzugeben.

    Für unsere Zwecke kann dieses Attribut verwendet werden, um die global eindeutige Identifikation des Assets zu hinterlegen. Dadurch besteht kein Interpretationsbedarf bei einem Import des VEC in die Verwaltungsschale.

    *aliasId* ist vom Typ *AliasIdentification[^7]*, welches mehrere Attribute für die Beschreibung eines Identifikationsmerkmals bietet . Für unsere Zwecke sind zwei Attribute entscheidend:

[^6]: [https://ecad-wiki.prostep.org/specifications/vec/v202/classes/partversion/\#Attributes](https://ecad-wiki.prostep.org/specifications/vec/v202/classes/partversion/#Attributes)

[^7]: <https://ecad-wiki.prostep.org/specifications/vec/v202/classes/aliasidentification/>

-   *identificationValue*  
    Dieses Attribut enthält das Identifikationsmerkmal als Zeichenfolge. Für unsere Zwecke muss dieses Attribut die global eindeutige Asset ID beinhalten.
-   *type*  
    Dieses Attribut definiert den Typ des Identifikationsmerkmals. Es handelt sich hierbei um eine Enumeration vom Typ *AliasIdentificationType[^8]* . Da wir grundsätzlich auf die global eindeutige Asset ID verweisen wollen, ist dieses Attribute immer mit dem Typ *UUID* (global eindeutiges Identifikationsmerkmal) zu befüllen.

    **Beispiel:**

-   *identificationValue  
    *"http://www.example.com/vws4ls/aas/1/0/demo_vec_asset"
-   *type*  
    "UUID"

[^8]: <https://ecad-wiki.prostep.org/specifications/vec/v202/classes/aliasidentificationtype/>

1.  VEC Identifier als spezifische Asset ID in der VWS

    Diese Möglichkeit setzt voraus, dass Elemente im VEC eindeutig identifizierbar sind und mindestens das VWS-Metamodel in der Version 3 verwendet wird.

    Hierfür wird ein eindeutiges Identifikationsmerkmal sowohl im VEC als auch in der VWS definiert, sodass diese zugeordnet werden können. Dieses Identifikationsmerkmal kann dann auch als Filterkriterium in einer VWS-Registry genutzt werden.

## <a name="_5"></a>5. Versionierung

Ein erster Ansatz zur Versionierung der Verwaltungsschale (VWS) wäre es, eine Versionsnummer zu den jeweiligen Verwaltungsschalen hinzuzufügen (Version/Revision) und immer auf eine spezifische Version zu verweisen. Bei Änderungen müsste dann zunächst ein manueller Eingriff erfolgen, um entlang der Lieferkette die neuen Versionen einzubinden, sofern dies notwendig oder sinnvoll ist. Dieser Ansatz kann durch die Einführung eines standardisierten Versionierungsschemas, wie zum Beispiel der semantischen Versionierung (MAJOR.MINOR.PATCH), weiter verbessert werden. Durch dieses strukturierte Schema lassen sich unterschiedliche Arten von Änderungen klar kennzeichnen: Major-Versionen signalisieren tiefgreifende Änderungen, die die Rückwärtskompatibilität brechen, während Minor-Versionen neue Funktionen hinzufügen, aber weiterhin kompatibel bleiben. Patch-Versionen hingegen beschränken sich auf Fehlerkorrekturen, ohne die Kompatibilität zu beeinflussen. Eine solche Struktur würde nicht nur die Nachvollziehbarkeit von Änderungen erhöhen, sondern auch die Implementierung von Updates in der gesamten Lieferkette erleichtern.

Darüber hinaus könnte dieser Mechanismus automatisiert werden, indem die Versionen anhand der Fähigkeiten (Capabilities/Skills) des Assets abgeglichen werden. Ein solches System könnte automatisch feststellen, ob ein Asset die Anforderungen einer neuen Version erfüllt oder ob ein Update notwendig ist. Dies könnte durch die Integration von Versionierungssystemen in digitale Plattformen unterstützt werden, die die Fähigkeiten der Assets mit den aktuellsten Versionen der Verwaltungsschale synchronisieren. Digitale Zertifikate oder Kompatibilitätsprüfungen könnten sicherstellen, dass nur getestete und kompatible Versionen verwendet werden, wodurch die Zuverlässigkeit und Stabilität des Systems gewährleistet wird.

Zudem könnte bei großen Änderungen ein automatisiertes System eingeführt werden, das Änderungs- und Versionierungsprotokolle führt, um die gesamte Historie einer Verwaltungsschale oder eines Teilmodells zu dokumentieren. Dadurch könnte bei Bedarf auf ältere Versionen zurückgegriffen werden (Version Rollback), falls eine neue Version nicht wie erwartet funktioniert. Ein solches System würde die Flexibilität und Resilienz der Verwaltungsschale deutlich erhöhen und könnte als zusätzlicher Sicherheitsmechanismus im Falle unerwarteter Probleme mit neuen Versionen fungieren.

Idee: Automatische Validierung des Assets anhand gegebener Parameter (Wird u.a. im BaSys4Transfer-Projekt ebenfalls verfolgt.) Siehe auch [12].

### VWS-Aufbau für den Leitungssatz

Bei der Umsetzung der Versionierung von Leitungssatz-Spezifikationen ist es wichtig zu berücksichtigen, dass die Entwicklung und die Produktion zeitlich und organisatorisch entkoppelt sind. Änderungen entstehen in der Regel zuerst in der Entwicklung und fließen anschließend in die Produktion. Diese Übermittlung erfolgt üblicherweise in Form von halbjährlichen Releases. Ein zentraler Punkt dabei ist der definierte Freigabezustand zu einem bestimmten Zeitpunkt (z. B. zum Entwicklungsstart). Dieser Fahrzeugfreigabezustand (Fzg-Freigabezustand) bildet die Grundlage für die weitere Entwicklung und wird im Laufe der Zeit durch detaillierte Änderungen weiter verfeinert (siehe *Abbildung* 1230). .

Anstatt für jede kleine Änderung eine neue Version zu erzeugen, werden die Änderungen über einen definierten Zeitraum gesammelt und dann zu bestimmten Zeitpunkten als Sets freigegeben. Dadurch wird der Aufwand minimiert, indem nicht jede kleine Anpassung sofort zu einer neuen Version führt.

Es ist jedoch auch vorgesehen, dass dringende oder wichtige Änderungen, die nicht dem regulären Release-Zeitplan entsprechen, als Change Sets „out of order“ in die Produktion eingespielt werden können. Diese Änderungen müssen nicht zwingend in der Reihenfolge der Entwicklung umgesetzt werden, sondern können je nach Dringlichkeit priorisiert werden.

Die verschiedenen Änderungen sind dabei potenziell unabhängig voneinander und können sich in ihrer Komplexität stark unterscheiden, was zusätzliche Flexibilität erfordert, um sie effizient in die Produktion zu integrieren. Dieser Ansatz stellt sicher, dass die Produktion jederzeit mit den notwendigen Informationen versorgt ist, während gleichzeitig die Entwicklung weiterhin flexibel und detailliert am Produkt arbeiten kann.

-   **AEM** à Beschreibt eine definierte Änderung zu einem bestimmten Freigabezustand
-   **Change-Set** à Besteht aus mehreren AEMs und Bündelt diese zu einem Set

![image](https://github.com/user-attachments/assets/6f03b49f-979e-48d2-b50a-ce0be3745c64)   
Abbildung 12-30: Entwicklungsversionen und korrespondierende Change-Sets in der Produktion

Da die jeweils eingespielten Change Sets nicht direkt aufeinander aufbauen, ist die gängige semantische Versionierung mit aufsteigender Nummerierung (wie etwa 1.1.4  1.2.01.2.12.0.0) nicht anwendbar. In einem ersten Konzept sehen wir daher vor die „Versionsnummer“ als Textbaustein basierend auf den Change Sets der Releases zu gestalten, etwa durch Verkettung der Bezeichner/Versionsnummern der einzelnen im Release enthaltenen Änderungen. Diese Versionsnummer ist dann auch Teil der ID der entsprechenden Verwaltungsschale (siehe *Abbildung* 1231). *Abbildung* 1231 zeigt dabei beispielhaft drei Teilmodelle (CAD-Modell, Fähigkeiten, Prozesse). Vorteil dieses Aufbaus ist die menschenlesbare Dokumentation, die direkt von Experten der Branche verstanden werden kann.

### Versionierungskonzept der Verwaltungsschale

![image](https://github.com/user-attachments/assets/1e1d60a1-e76d-4c4b-b267-ab2d11e78e03)   
Abbildung 12-31: Vorgeschlagenes Versions-ID-Konzept

*Abbildung* 1231 zeigt auch, dass die Teilmodelle der Change Sets nicht direkt der zugehörigen VWS zugeordnet sind, sondern lediglich indirekt über Referenz-Teilmodelle. Dadurch können unveränderte Teilmodelle weiter referenziert werden in neuen Versionen des Teilmodells. Dies passt ebenfalls zur Struktur der Verwaltungsschale in Version 3, in der Teilmodelle als unabhängige Elemente eigenständig, etwa in einem Submodel Repository, existieren können. Somit ist es möglich ein Typ-Submodel, was in mehreren Verwaltungsschalen exakt gleich ist, zu referenzieren und bei Änderungen direkt alle Abhängigkeiten automatisch mitzupflegen.

Das orange markierte Prozesse-Teilmodell in der *Abbildung* stellt eine neue Version des alten Teilmodells (links) dar, auf das die zusätzliche Änderung 4 angewandt wurde, und dass eine Referenz auf die Vorgängerversion enthält. Auf diese Weise lassen sich alle übernommenen Änderungen bis zum ursprünglichen Referenz-Teilmodell zurückverfolgen.

Die Versionsnummer der Verwaltungsschalen und Teilmodelle sind dabei abhängig von den eingepflegten Änderungspaketen. Im Beispiel in *Abbildung* 1231 wurden durch die Änderungspakete 2 und 3 alle Teilmodelle angepasst, weshalb diese als „FZGQ2-23_AEM2+3“ versioniert sind. Durch Änderungspaket 4 wurde jedoch lediglich das Teilmodell Prozesse verändert, weshalb dazu eine neue Version erstellt, und die Versionsnummer verändert wird. Keine weiteren Teilmodelle werden in ihrer Version daher die Referenz zu Änderungspaket 4 erhalten. Änderungen für etwa Fähigkeiten müssten somit im nächsten Paket (Nummer 5) enthalten sein, sodass eine inkonsistente Versionsbezeichnung (etwa durch Doppelnutzung) nicht entstehen kann. *Abbildung* 1232 zeigt Beispiele für entsprechend versionierte Verwaltungsschalen.

Dateiname: [Versionierung_neu.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/General/Versionierung_neu.aasx)

![image](https://github.com/user-attachments/assets/6c452512-7e20-4ab7-9eae-2fc47212a4e0)   
Abbildung 12-32: Beispiel versionierter Verwaltungsschalen (Teilmodell

Für den standardisierten Zugriff sehen wir eine Erweiterung des Discovery/Registry Service vor, der als Default immer die aktuelle Version einer gegebenen Verwaltungsschale bereithält. Somit ist kein Bruch zur Konvention der Verwaltungsschalendefinition vorhanden. Dennoch könnte eine Erweiterung der API, um ebenfalls auf die älteren Versionen zugreifen zu können, in Betracht gezogen. Dazu wird im ersten Entwurf ein URL-Parameter erprobt, welcher optional ist und bei nicht-verwendung das standardmäßige Verhalten des entsprechenden Services laut VWS-Definition bereithält.

![image](https://github.com/user-attachments/assets/e0e5d114-c47d-4cde-8efa-788ed1ed77c6)   
Abbildung 12-33: "Latest" default

Technisch wird Git[^9] der auf einem davon abgeleiteten Mechanismus aufbauen, so dass Änderungen letzten Endes wie Patches behandelt werden und ein „Git-Branching resultieren.

[^9]: <https://git-scm.com/>

Bezüglich des konkreten Zugriffs auf eine versionierte VWS eines Leitungssatzes wurden drei mögliche Varianten identifiziert (das Asset ist hierbei jeweils der zu bauende Leitungssatz):

### Zugriff mit Registry und Discovery

Hier kennt die Anwendung die Asset-ID und fragt damit beim Discovery Service ab, welche VWS zu der Asset-ID assoziiert sind. Hierzu fragt die Discovery den Versionierungsservice an mittels eines *GET-Request* (*Abbildung* 1234), welcher die *VWS-ID* mit Versionsnummer zurückgibt, die dann an die Anwendung weitergeleitet wird. Anschließend fragt die Anwendung das *VWS-Registry* nach dem Endpunkt der VWS mit der entsprechenden *VWS-ID*. Die *VWS-Regist*ry gibt der Anwendung einen *VWS-Deskriptor* zurück. Danach holt die Anwendung mit diesem Deskriptor die VWS aus dem *VWS-Repository*.

Bei dieser Lösung muss ein Discovery- und ein Versionierungsservice entwickelt werden. Ein Discovery Service ist durch Version 3 der VWS allgemein vorgesehen und zuständig für das Auffinden von VWS zu einer Asset-ID bzw. das bidirektionale Mapping zwischen Asset und VWS.

![image](https://github.com/user-attachments/assets/7818a6d9-cd67-4a75-a1ef-23f018e09472)   
Abbildung 12-34: Zugriff mit Discovery und Registry

### Zugriff ohne Discovery

In diesem Fall sendet die Anwendung ein *GET-Request* zu der Registry mit der Asset-ID (*Abbildung* 1235). Die Registry leitet die Anfrage weiter an den Versionierungsservice und fragt nach der aktuellen Version des Leitungssatzes. Der Versionierungsservice gibt der Registry die VWS-ID mit Versionsnummer zurück. Die Registry macht einen *GET-Aufruf*, um den Endpunkt der VWS zu ermitteln. Danach gibt die Registry der Anwendung den VWS-Deskriptor zurück, welcher den VWS-Endpoint beinhaltet. Die Anwendung macht anschließend einen *GET-Aufruf* an das VWS-Repository, um das VWS-Objekt zu erhalten.

Bei dieser Lösung übernimmt die Registry die Discovery-Funktion, und hat direkte Interaktion mit dem Versionierungsservice. Für diese Variante muss eine VWS-Registry ebenfalls das Auflösen der Versionsnummer übernehmen und entsprechend erweitert werden.

![image](https://github.com/user-attachments/assets/cc05e52e-9210-4334-98f6-ed0b78720995)   
Abbildung 12-35: Zugriff ohne Discovery

### <a name="_5.5"></a>5.5 Zugriff ohne Registry

In dieser Variante fragt die Anwendung den Discovery Service mit der *Asset-ID* nach der *VWS-ID* (*Abbildung* 1236). Die Discovery gibt der Anwendung eine *Teil-VWS-ID* zurück. Mit der Teil-VWS-ID macht die Anwendung einen *GET-Aufruf* beim Versionierungsservice, um die aktuelle VWS-Version zu bekommen, und baut die vollständige spezifische *VWS-ID* mit der Versionsnummer zusammen, bevor die Anfrage an das VWS Repository gesendet wird, sodass eine VWS statt aller vernetzter Verwaltungsschalen gefunden werden kann. Das *VWS-Repository* gibt der Anwendung somit das spezifische VWS-Objekt zurück.

Bei dieser Lösung muss die Anwendung die Logik zu Auflösung der vollständigen ID kennen, um die relevante VWS zu finden. Dies hat den Nachteil, dass die Entwickler von Anwendungen Kenntnisse über diesen Mechanismus haben müssen, um die relevante VWS zu finden.

![image](https://github.com/user-attachments/assets/a798fec3-37b3-465d-b403-40056c8bc6e3)   
Abbildung 12-36: Zugriff ohne Registry

## <a name="_6"></a>6. Synchronisation

**Synchronisation zwischen Asset und seiner Verwaltungsschale**

Mit der Definition der Verwaltungsschale als Digitaler Zwilling kommt direkt die Anforderung an die Äquivalenz der Daten, die im bzw. zum Asset vorliegen, mit den Daten, die durch die Verwaltungsschale repräsentiert werden. Dabei ist es unerheblich, ob die Daten z.B. durch einen Sensor erfasst und in einer Speicherprogrammierbare Steuerung (SPS) des Assets vorliegen oder ob die Daten durch eine Person in einer Datenbank außerhalb der Systemgrenzen des Assets erfasst wurden. In beiden Fällen sollen die Daten widerspruchsfrei sein.

Man kann hier zwischen zwei Ansätzen unterscheiden. Zum einen können die Daten zusätzlich in den Teilmodellen der Verwaltungsschale abgelegt werden, die in einem Submodel Repository gehostet werden. Das Submodel Repository agiert in diesem Fall als Datenspeicher und bei einer Änderung ist auch das Datum im Repository zu aktualisieren. Man kann in diesem Fall von einem Push-Vorgang in Richtung Teilmodell der Verwaltungsschale sprechen. Im zweiten Fall wird bei dem Zugriff auf die Verwaltungsschale der aktuelle Wert aus der SPS oder dem Drittsystem geladen und weitergereicht. In diesem Fall agiert das Submodel Repository als Proxy und es handelt sich nicht um einen Synchronisationsvorgang im engen Sinn, da das Datum nur einmal gespeichert ist. Man kann von einem Pull-Vorgang durch die Implementierung der Verwaltungsschale sprechen.

Für beide Vorgehensweise gibt es bereits Konzepte und auch praktische Umsetzungen:

Als Beispiel für das Push-Prinzip sei die Data Bridge-Komponente des Eclipse BaSyxTM[^10] Framework genannt, welche die Verwaltungsschalenmiddleware in beide Richtungen mit weiteren Systemen verbinden kann.

[^10]: <https://github.com/eclipse-basyx/basyx-databridge>

Für die Umsetzung eines Pull-Prinzip existiert in Eclipse BaSyxTM das Property Delegation Feature.

Beide genannten Lösungen wurden im Projekt VWS4LS untersucht und werden als valide, funktionierende Lösung eingeschätzt. Die Synchronisation zwischen Asset und Verwaltungsschale wird damit als Stand der Technik betrachtet und der Schwerpunkt wurde im Projekt auf die Synchronisation zwischen Verwaltungsschalen gelegt.

**Synchronisation zwischen Verwaltungsschalen**

Die Ergebnisse aus TP 2 und der Architekturgruppe „Verlinkung“ zeigen, dass Verwaltungsschalen (im Folgenden als „abhängige VWS“) auf Basis anderer VWS (im Folgenden „übergeordnete VWS“) definiert werden. Dafür gibt es folgende Fallbetrachtungen:

Szenario 1: Unterschiedliche „Wahrheiten“ zum selben Asset

Zum selben Asset-Typ gibt es für die Rollen im Prozess jeweils eigene Typ-Verwaltungsschalen. Diese können einerseits unterschiedliche Detailstufen darstellen (vgl. Typ Leitungssatzkomponente OEM / Tier1), aber auch voneinander abweichende Angaben definieren (vgl. Freigabebereiche für Komponenten).

Szenario 2: Ableitungen:

Basierend auf einer VWS werden andere abgeleitete VWS erzeugt, z.B. Verwendung von Komponenten im Leitungssatz oder Ableitung von Halbfabrikaten aus der Leitungssatz-VWS. Bei beiden genannten Ableitungen handelt es sich eigentlich um die gleiche Beziehung in entgegengesetzter Richtung gedacht.

In beiden Fällen ergibt sich ein Synchronisationsbedarf zwischen den abhängigen VWS und der übergeordneten VWS im Falle von Änderungen an der übergeordneten VWS. Im Folgenden wird ein Konzept für die Synchronisation schrittweise beschrieben.

### <a name="_6.1"></a>6.1 Rahmenbedingungen für den gewählten Lösungsansatz

Bei den Überlegungen zum SPoT (siehe Kapitel 12.1.2) wurde aufgezeigt, dass eine Verteilung der Informationen über mehrere Repositories, jeweils betrieben durch verschiedene Partner der Wertschöpfungskette, angestrebt wird. Wenn man in der Praxis aber an Bibliotheken für Leitungssatzentwicklungswerkzeuge, mit mehreren tausend Komponenten von mehr als 100 verschiedenen Herstellern denkt, liegt es nahe, lokale Kopien der Verwaltungsschalen anzulegen, selbst wenn diese ein 1:1 Abbild der entfernten Verwaltungsschale sind. Dieses lokale “Caching” verringert die Antwortzeit der Systeme und erhöht die Ausfallsicherheit.

Der Bedarf nach zuverlässigen Synchronisationsmechanismen besteht beim lokalen Caching, um auch bei redundanter physikalischer Datenspeicherung nach wie vor einen logischen SPoT zu realisieren. Der Begriff der führenden Verwaltungsschale kann hier auf die ursprüngliche Verwaltungsschale angewendet werden, die den SPoT darstellt, wobei die abhängige Verwaltungsschale das “gecachte” Objekt ist, also die lokale Kopie.

Aus den Überlegungen zum SPoT geht hervor, dass es, bezogen auf ein bestimmtes Teilmodell, ein konkreter Datenbestand als SPoT definiert werden kann. Es wird angenommen, dass sämtliche Änderungen an diesem führenden Datenbestand vorgenommen werden und dass eine Synchronisation nur in eine Richtung, ausgehend vom führenden Datenbestand erfolgt. Eine Synchronisation in die umgekehrte Richtung kann zu Konfliktenten führen, wenn z.B. zeitgleich dasselbe Datenelement unterschiedlich geändert wird. Solche Konflikte sind nur schwierig aufzulösen und widersprechen der Idee des SPoT.

Es wird also vorausgesetzt, dass sämtliche Änderung in dem führenden Teilmodell vorgenommen werden und diese Änderungen anhand von Synchronisationsnachrichten an einen oder mehrere Empfänger verteilt wird. Bewusst offen bleibt jedoch, was mit den Synchronisationsnachrichten auf der Empfängerseite passiert. Bleibt es beim Anlegen einer exakten Kopie des ursprünglichen Teilmodells, wird es um zusätzliche Informationen ergänzt oder werden einzelne Werte mit eigenen "Wahrheiten” auf der Empfängerseite überschrieben?

All dies sind mögliche Anwendungsfälle. Es ist aber immer davon auszugehen, dass eine Änderung am führenden Teilmodell für den Empfänger von Interesse ist. Aber selbst wenn das nicht der Fall ist, kann die Synchronisationsnachricht der Ausgangspunkt sein für eine Überprüfung der eigenen Wahrheit auf der Empfängerseite.

Es wird angenommen, dass die Synchronisationsbeziehung im Einverständnis und mit Kenntnis aller beteiligten Parteien eingerichtet wird. Das Konzept geht davon aus, dass die Empfänger aus technischer Sicht und aus Sicht einer etwaigen Berechtigungssteuerung Zugriff haben auf das führende Teilmodell der Senderseite. Dieser Zugriff ist notwendig, damit initial der Empfänger seine lokale Kopie (abhängige VWS) anlegen kann. Diese abhängige VWS wird daraufhin durch die Synchronisationsnachrichten, welche die führende Verwaltungsschale bei Wertänderungen aktiv aussendet, aktuell gehalten. Fehler in der Übertragung können einen kompletten Abgleich des Teilmodells bzw. Eine Neu-Initialisierung erforderlich machen, sodass der direkte Zugriff auf das Teilmodell durch den Empfänger auch zu einem späteren Zeitpunkt noch notwendig und sinnvoll ist.

### <a name="_6.2"></a>6.2 Konfiguration der Synchronisationsbeziehung

Es wird davon ausgegangen, dass eine Synchronisationsbeziehung immer auf Ebene ganzer Teilmodelle eingerichtet wird. Eine feinere Steuerung erhöht den Konfigurations- und Verwaltungsaufwand. Eine Synchronisation aller Teilmodelle einer Verwaltungsschale ohne Möglichkeit zu Einschränkungen scheint aus fachlicher Sicht nicht sinnvoll; es sollen selten alle Informationen zu einem Asset mit allen Partnern der Wertschöpfungskette geteilt werden.

Zum Einrichten der Synchronisationsbeziehung registriert sich die Verwaltungsschale, die Änderungen bezüglich relevanter Teilmodelle empfangen möchte, bei der führenden Verwaltungsschale. Die Initiative, dass eine Synchronisationsbeziehung eingerichtet wird, geht also von der Empfängerseite aus. Die Synchronisationsnachrichten werden direkt an den jeweiligen Empfänger gesendet. So behält die sendende Verwaltungsschale die Kontrolle darüber, wer die Nachrichten empfängt und man kann die Mechanismen der Zugriffssteuerung auf Teilmodelle auch auf die Synchronisationsnachrichten anwenden. Würde man z.B. einen Message-Broker einbeziehen, der die Zustellung der Nachrichten an die einzelnen Empfänger übernimmt, müsste dieser auch die Zugriffssteuerung auf die Teilmodelle der Verwaltungsschale berücksichtigen und anwenden. Wir gehen im Konzept hier jedoch davon aus, dass eine Komponente innerhalb der Systemgrenzen der Verwaltungsschalenimplementierung das zustellen der Nachrichten übernimmt.

Folgende Informationen sind im Rahmen des Verhandlungsprozesses für die Synchronisationsbeziehung festzulegen:

1.  URL zur Registry, in der die empfangende Verwaltungsschale registriert ist
2.  VWS-Id der empfangenden Verwaltungsschale
3.  Liste der relevanten Teilmodelle, deren Änderungen gesendet werden sollen
4.  Zeitintervall, das mindestens zwischen zwei Änderungsnachrichten liegen soll
5.  Zeitintervall, nachdem mindestens eine Heartbeat-Nachricht gesendet werden soll, falls keine Änderung vorliegt
6.  Weitere Parameter für die Steuerung des Fehlerhandlings wie z.B. Mindestzeitintervall für die Pufferung bei fehlerhaften Zustellversuchen

![image](https://github.com/user-attachments/assets/b9dab30e-6765-4ec5-851b-860574c9bc44)   
Abbildung 12-37: VWS-Synchronisation: Teilmodell zur Konfiguration der Synchronisationsbeziehung

Der 4. Parameter kann bei sich häufig ändernden Werten sinnvoll sein, um das Nachrichtenaufkommen zu regulieren. So kann man die Häufigkeit an die Anforderungen der Empfängerseite und an die gegebenen technischen Rahmenbedingungen der Netzwerkkommunikation anpassen. Dieser Parameter ist optional zu sehen. Erfolgt eine Änderung am Teilmodell innerhalb des Zeitintervalls wird zunächst keine Synchronisationsnachricht gesendet. Erst nachdem das Zeitintervall verstrichen ist, wird wieder eine Synchronisationsnachricht gesendet, die in einer Nachricht alle geänderten Teilmodellelemente mit dem jeweils aktuellen Wert beinhaltet.

Ändert sich z.B. innerhalb des Zeitintervalls ein bestimmtes Teilmodellelement zehn Mal, so wird nur eine Nachricht gesendet, die den jüngsten Wert des Elements beinhaltet.

Ist das Zeitintervall nicht angegeben oder auf 0 gesetzt, wird jede Änderung unmittelbar als Synchronisationsnachricht gesendet.

Es sollen beim Senden der Synchronisationsnachrichten die gleiche Berechtigungssteuerung greifen wie beim direkten Zugriff auf das Teilmodell über die Verwaltungsschalen-API. Um dies realisieren zu können, muss sich der Empfänger beim Einrichten der Synchronisationsbeziehung gegenüber der führenden Verwaltungsschale authentifizieren und für den Teilmodell-Zugriff autorisieren. Die führende Verwaltungsschale sollte innerhalb der Konfiguration zur Synchronisationsbeziehung die Informationen ablegen die notwendig sind, um auch zu einem späteren Zeitpunkt prüfen zu können ob der jeweilige Empfänger immer noch berechtigt ist auf das Teilmodell zuzugreifen. Welche Information hier notwendig ist, hängt von der technischen Implementierung der Zugriffsteuerung ab und deshalb sollen an dieser Stelle keine konkreten Vorgaben gemacht werden. Hierfür kommen auf der Senderseite möglicherweise noch weitere Parameter hinzu, die in der Konfiguration abgespeichert werden müssen.

Es wird vorgeschlagen die Konfiguration der Synchronisationsbeziehung in einem eigenen Teilmodell zur führenden Verwaltungsschale zu hinterlegen, wobei das Teilmodell für die Empfänger der Synchronisationsnachrichten nicht zugreifbar sein darf. Die Initiative zur Konfiguration geht zwar vom Empfänger der Synchronisationsnachrichten aus, aber die Konfiguration kommt durch Interaktion, durch den Austausch von Nachrichten, zu Stande und nicht durch direktes Schreiben des Empfängers in das Konfigurations-Teilmodell.

Als Interaktionsprotokoll zur Konfiguration der Synchronisationsbeziehung bietet sich das in VDI/VDE 2193-2 [13] beschriebene Ausschreibungsverfahren an. In diesem Zusammenhang kann man das Senden der Synchronisationsnachrichten als Dienstleistung (Service) ansehen, welche von der führenden Verwaltungsschale angeboten wird. Man kann die sendende Verwaltungsschale als *Service Provider* ansehen. Die empfangende Verwaltungsschale gibt mit der Initiative zum Konfigurieren der Synchronisationsbeziehung den Auftrag zum Senden der Nachrichten und hat somit die Rolle des *Service Requesters* (Auftraggeber).

Das Interaktionsprotokoll Ausschreibungsverfahren startet mit der Ausschreibungsnachricht vom *Service Requester* zum *Service Provider*. Inhalt der Ausschreibungsnachricht sind die oben aufgezählten Punkte.

Kann der *Service Provider* die Parameter der Synchronisationsbeziehung akzeptieren, antwortet er mit einem Angebot, welches die Parameter der Ausschreibung bestätigt. Ist die Einrichtung der Synchronisation nicht möglich, weil der Empfänger z.B. nicht Zugriff auf alle relevanten Teilmodelle hat oder die Zeitintervalle außerhalb des zulässigen Bereichs liegen, lehnt der *Service Provider* die Ausschreibung ab oder antwortet mit einem Angebot, das aus Sicht des *Service Provider*s funktionierende Konfigurationsparameter enthält.

Der *Service Requester* wiederum hat die Möglichkeit das Angebot mit den ggf. geänderten Konfigurationsparametern mit einer entsprechenden Nachricht zu akzeptieren oder abzulehnen.

Der *Service Provider* bestätigt die Angebotsannahme mit einer Nachricht und ab diesem Zeitpunkt ist die Synchronisationsbeziehung konfiguriert und die Synchronisationsnachrichten werden an den neu hinzugefügten Empfänger (*Service Requester*) gesendet.

Die erste Nachricht beinhaltet das komplette Teilmodell, um den *Service Requester* mit einem initialen Datenstand zu versorgen. So ist ausgeschlossen, dass Änderungen zwischen dem Einrichten der Synchronisationsbeziehung und der ersten gesendeten Änderung für den *Service Requester* verloren gehen.

Die Besonderheit des Ausschreibungsverfahrens in diesem Kontext ist die Tatsache, dass nur ein *Service Provider* angefragt wird. Nur die Verwaltungsschale, die den SPoT darstellt, kann diesen Service erbringen.

![image](https://github.com/user-attachments/assets/f04d78c8-267a-4030-b978-c56ea63f2562)   
Abbildung 12-38: Interaktionsprotokoll zur VWS-Synchronisation

### <a name="_6.3"></a>6.3 Senden von I4.0-Nachrichten zur Synchronisation

Im TP 6 von VWS4LS wurde als Mechanismus zum Austausch von I4.0-Nachrichten das Konzept der “Operation” des Verwaltungsschalen-Metamodells vorgeschlagen [14]. Zur Implementierung eines solchen Nachrichtenaustausch wurde ein Teilmodell namens „*Message Participant*“ erarbeitet, welches eine entsprechende Operation “*newMessage*” definiert. Die Operation wird vom Sender der Nachricht aufgerufen, wobei die Operation im Teilmodell “*Message Participant*” der empfangenden Verwaltungsschale ausgeführt wird.

Dieses Teilmodell und die Vorgehensweise wurden zunächst für den Nachrichtenaustausch im Interaktionsprotokoll “Ausschreibungsverfahren” konzipiert. Da das Ausschreibungsverfahren zur Konfiguration der Synchronisationsbeziehung eingesetzt werden soll, kann vorausgesetzt werden, dass sowohl *Service Requester* als auch *Service Provider* das Teilmodell “*Message Participant*” implementieren. Somit ist es naheliegend dieses Teilmodell mit der entsprechenden Operation zum Austausch von I4.0-Nachrichten auch für die Synchronisationsnachrichten zu nutzen.

Ein erster Ansatz für ein Interaktionsprotokoll ist, dass bei einer Änderung in einem Teilmodell auf Seite des *Synchronisation Service Provider* überprüft wird, ob für das Teilmodell Synchronisationsbeziehungen konfiguriert sind. Falls ja, wird für jede konfigurierte Synchronisationsbeziehung eine Nachricht generiert.

Die Granularität bzw. der Umfang der Änderungen, die innerhalb einer Synchronisationsnachricht gesendet werden, orientiert sich an Vorgängen, die zu Wertänderungen führen. Werden bspw. mit einer PUT- oder PATCH-Operation mehrere Teilmodellelemente gleichzeitig geändert, sind alle Wertänderungen verpflichtend innerhalb einer Synchronisationsnachricht zu übermitteln, um auf Seite des *Service Requesters* die gleichen Bedingungen in Bezug auf Datenkonsistenz zu schaffen wie auf Seite des *Service Providers* gegeben. Um dies zu gewährleisten, muss auch die Nachricht als Ganzes auf die *Service Requester* VWS angewendet werden. Wird ein einzelnes Datenelement geändert, so wird im allgemeinen Fall direkt eine Nachricht generiert mit dieser einzelnen Wertänderung. Im besonderen Fall, bei eingestelltem Mindestintervall, wird diese Nachricht aber zunächst gepuffert und ggf. mit weiteren Nachrichten, die innerhalb dieses Intervalls erzeugt werden, zusammengefasst.

Einen Mechanismus zur Gewährleistung von Konsistenz und Transaktionssicherheit über mehrere Teilmodelle hinweg sieht das Interaktionsprotokoll nicht vor. Ein solcher Mechanismus ist auch bei der lokalen VWS über die API-Zugriffe nicht gegeben. Um einen solchen Mechanismus zu realisieren sind Maßnahmen außerhalb des Interaktionsprotokolls zu treffen. Vorstellbar ist z.B. ein Datenelement, das einen konsistenten bzw. inkonsistenten Zustand anzeigt. Will man mehrere Teilmodelle ändern, ist dieser Zustand auf “inkonsistent” zu setzen, die Änderungen auf die betreffenden Teilmodelle anzuwenden und erst dann wieder den Zustand auf “konsistent” zu setzen. Vor den Zugriffen auf die VWS ist immer der Zustand zu prüfen. Um den Mechanismus auch im Rahmen der Synchronisation anwendbar zu machen, sind die Nachrichten in exakt der Reihenfolge zu erstellen, in der die lokalen API-Aufrufe stattfinden und die Nachrichten sind auch unbedingt in der Reihenfolge ihrer Erstellung zuzustellen.

Die Nachricht wird wie beschrieben per Operationsaufruf zugestellt. Dafür führt der *Service Provider* für die in der Konfiguration hinterlegte VWS-Id einen Discovery-Prozess bei dem ebenfalls konfigurierten VWS-Repository durch und ermittelte das “*Message Participant*”-Teilmodell. Per Rückgabewert des Operationsaufrufs wird mitgeteilt, ob die Zustellung erfolgreich war. War die Zustellung der Nachricht nicht erfolgreich, z.B. wegen temporär unterbrochener Netzwerkverbindung, puffert der *Service Provider* die Nachricht und wiederholt den Zustellversuch zu einem späteren Zeitpunkt. Gegebenenfalls ist die Konfiguration der Synchronisationsbeziehung um eine max. Anzahl an gepufferten Nachrichten, eine Höchstdauer für die Pufferung, oder eine Zeitintervall für die Wiederholungsversuche zu erweitern.

### <a name="_6.4"></a>6.4 Inhalte der I4.0-Nachrichten zur Synchronisation

Der Aufbau der Synchronisationsnachricht folgt VDI/VDE 2193-1 [15] und teilt sich in Nachrichtenrahmen und Interaktionselementen mit den Nutzdaten zur Übermittlung der Wertänderungen.

Tabelle 122 Elemente des Nachrichtenrahmens

| **Nachrichtenelement** | **Beschreibung**                                                                                               | **Verwendung** |
|------------------------|----------------------------------------------------------------------------------------------------------------|----------------|
| Typ                    | Zweck der Nachricht: Synchronisation, Heartbeat                                                                | Verpflichtend  |
| Sender                 | Absender einer Nachricht (VWS-ID)                                                                              | Verpflichtend  |
| Empfänger              | Empfänger einer Nachricht (VWS-ID)                                                                             | Optional       |
| Konversations-ID       | ID der Synchronisationsbeziehung, festgelegt während der Konfiguration (Verhandlungsprozess)                   | Verpflichtend  |
| Nachrichten-ID         | ID einer Nachricht, um z.B. eine doppelte Verarbeitung auf Empfängerseite zu verhindern.                       | Verpflichtend  |
| Als-Antwort-Auf        | Ausdruck, der die Ursprungsnachricht referenziert, wird in diesem Interaktionsprotokoll bisher nicht benötigt. | Nicht genutzt  |
| Antworten-bis          | Zeitpunkt bis zu dem die Antwort vorliegen muss, wird in diesem Interaktionsprotokoll bisher nicht benötigt.   | Nicht genutzt  |
| Semantisches Protokoll | Identifikation des semantischen Protokolls auf das sich der Zweck bezieht, hier Synchronisation                | Verpflichtend  |
| Rolle                  | Aufgabe des Senders der Nachricht im semantischen Protokoll, hier Synchronisation Message Provider             | Optional       |

Im Bereich der Interaktionsmodelle wird zum einen die Teilmodellreferenz des geänderten Teilmodells angegeben und zum anderen als Datenelement eine Serialisierung der geänderten Teilmodellelemente. Optional kann in einem weiteren Datenelement eine Serialisierung der geänderten Teilmodellelemente mit ihren Werten vor der Änderung übertragen werden. Da es erforderlich sein kann, die vorherigen Werte je *Service Requester* zu speichern, z.B. in Verbindung mit Nutzung der minimalen Intervalle zwischen zwei Nachrichten, kann diese Speicherung zu Ressourcenproblemen beim *Service Provider* kommen. Beispiel sind begrenzte Hardwareressourcen oder eine hohe Anzahl an *Service Requester*n die mit Synchronisationsnachrichten zu versorgen sind. Aus diesem Grund wird das Datenelement mit den Vorgängerwerten als optional vorgeschlagen und wäre im Konfigurationsprozess zu vereinbaren.

### <a name="_6.5"></a>6.5 Verarbeiten von I4.0-Nachrichten zur Synchronisation

Die Zustellung der Synchronisationsnachricht erfolgt, wie oben beschrieben, über den Aufruf der entsprechenden Operation im Teilmodell „Message Participant” und nicht etwa, in dem das betroffene Element durch den *Synchronisation Message Provider* direkt im Zielteilmodell des *Synchronisation Message Requesters* geändert wird.

Mit der Implementierung dieser Operation besteht auf Seite des *Synchronisation Message Requesters* ein hoher Freiheitsgrad, wie mit der empfangenen Nachricht umgegangen wird. Wie eingangs beschrieben, werden verschiedene Einsatzgebiete des Interaktionsprotokolls Synchronisation gesehen. Im angesprochenen Anwendungsfall Caching, könnte die Funktion der Operation lediglich darin bestehen, in einem Cache mit 1:1 Kopien der SPoT-VWS den Cache ungültig zu setzen, damit beim nächsten Zugriff auf den Cache wieder ein Zugriff auf die SPoT-VWS erfolgt und ein aktualisiertes Cache-Objekt generiert wird. Der Algorithmus der Operation benötigt dazu lediglich die VWS-Identifikation aus dem Rahmen der I4.0-Nachricht und die Interaktionselemente der Nachricht würde der Algorithmus nicht auswerten. Mit der VWS-Identifikation, also der VWS-Id im Sender-Datenfeld des Nachrichtenrahmens, wird das Cache-Objekt, welches zu dieser VWS-ID gehört, gesucht und aus dem Cache entfernt.

Ein komplexerer Caching-Algorithmus könnte die serialisierten Teilmodellelemente, die in der Nachricht enthalten sind, dazu nutzen, um die Cache-Objekte direkt zu aktualisieren.

Das Anwendungsgebiet ist nicht auf Caching beschränkt. Die diskutierten Anwendungsfälle aus Sicht der fachlichen Domäne Leitungssatz zeigen u.a., dass es sinnvoll ist bei den abhängigen, abgeleiteten Verwaltungsschalen eine Normierung der Daten vorzunehmen. Beispielsweise die Umrechnung von Grad Fahrenheit in Grad Celsius oder AWG-Leitungsquerschnitte in das metrische System. Aber auch komplexere Geschäftslogiken mit Fallunterscheidungen bis hin zum Durchlauf langlaufender Workflows sind denkbar. Gerade bei den langlaufenden Algorithmen taucht wieder die Problematik der Datenkonsistenz auf und die Wichtigkeit der Verarbeitungsreihenfolge. Sollte in diesem Fall ein Puffern der eingehenden Synchronisationsnachrichten notwendig sein, so ist diese auf Seite des *Synchronisation Message Requesters* zu implementieren. Das Interaktionsprotokoll sieht vor, dass der Nachrichteneingang durch den Rückgabewert der Operation bestätigt wird. Diese Bestätigung ist aber rein auf die Datenübertagung zu beziehen und nicht auf die erfolgreiche Verarbeitung der empfangenen Nachricht. Es macht keinen Sinn, einen Fehlerstatus des Operationsaufrufs zurückzumelden, weil die Nachrichtenverarbeitung nicht abgeschlossen ist oder die Inhalte aus fachlicher Sicht, also aus Sicht der Geschäftslogik, nicht akzeptiert werden. An dieser Stelle sei auf das Änderungsmanagement (Kapitel 12.5) verwiesen, welches sich mit der fachlichen Abstimmung von Änderungen beschäftigt und auf der technischen Übertragung von Wertänderungen, wie sie hier beschrieben wurde, aufsetzt.

### <a name="_6.6"></a>6.6 Umgang mit Fehlerzuständen

Wie oben beschrieben stellt der Operationsaufruf die Schnittstelle zwischen *Synchronisation Message Provider* und *Synchronisation Message Requester* dar. Der *Synchronisation Message Provider* ist dafür verantwortlich, dass der Operationsaufruf zuverlässig und in der korrekten Reihenfolge ausgeführt wird. Erst wenn der Operationsaufruf der vorhergehenden Nachricht mit erfolgreichem Rückgabestatus abgeschlossen wurde, darf der *Synchronisation Message Provider* die Nachricht als zugestellt betrachten und den Operationsaufruf für die folgenden Nachricht ausführen. Wenn ein Operationsaufruf technisch im Augenblick scheitert oder der *Synchronisation Message Requester* den Operationsaufruf mit einem Fehlerstatus quittiert, ist diese Nachricht zwischenzuspeichern und der Operationsaufruf ist, nach einem vorab vereinbarten Zeitintervall, zu wiederholen. Die Anzahl der Wiederholungen des Zustellversuchs, das Zeitintervall zwischen den Zustellversuchen, und die Obergrenze für Zeitdauer und Nachrichtenanzahl für die Zwischenspeicherung auf Providerseite sind Bestandteil der Konfiguration der Synchronisationsbeziehung. Sollte einer der Parameter überschritten werden, so werden sowohl die Zustellversuche der betreffenden Nachricht als auch die weitere Synchronisationsbeziehung durch den *Synchronisation Message Provider* beendet. Der *Synchronisation Message Provider* informiert den *Synchronisation Message Requester* durch den einmaligen Zustellversuch einer Nachricht vom Typ “Canceled”. Bei diesem Nachrichtentyp ist die Angabe der Konversation-Id verpflichtend, damit der *Synchronisation Message Requester* erkennen kann, welche Synchronisationsbeziehung abgebrochen wurde, falls er mehrere Konfigurationen beim gleichen Provider eingerichtet hat.

Grundsätzlich ist nach einem erfolgreichen Operationsaufruf die Verantwortung für die weitere Verarbeitung der Nachricht auf den Requester übergegangen. Sollte eine Pufferung der Nachrichten für die folgende Verarbeitung notwendig sein, so ist diese auf Seite des Requesters zu implementieren.

Sollte innerhalb eines konfigurierten Zeitintervalls keine Nachricht vom Provider gesendet worden sein, so erzeugt der Provider eine Heartbeat-Nachricht mit dem entsprechenden Typ im Nachrichtenrahmen und der Konversations-Id, welche der Konfiguration der Synchronisationsbeziehung entspricht. Ziel dieser Nachrichten ist es, dem Requester eine Möglichkeit zu bieten, das Funktionieren der Synchronisationsbeziehung zu überwachen und eine Annahme über die Aktualität der Daten zu treffen, die ihm vorliegen.

Sollte innerhalb des konfigurierten Zeitintervalls weder eine Synchronisationsnachricht noch eine Heartbeat-Nachricht eingehen, muss der Requester davon ausgehen, dass die Synchronisationsbeziehung abgebrochen ist. Soll aus seiner Sicht die Synchronisation fortgesetzt werden, so ist - wie bei einem neuen Einrichten einer Synchronisationsbeziehung - der entsprechende Verhandlungsprozess durch eine Ausschreibungsnachricht zu starten. An dieser Stelle ist die bestehende Konversations-Id der abgebrochenen Synchronisationsbeziehung weiterzuverwenden.

Mit dem erfolgreichen Durchlaufen des Ausschreibungsverfahrens ist auch eine Re-Initialisierung des Datenbestandes durch komplettes Abrufen aller relevanten Teilmodelle durchzuführen. Dies ist im Verantwortungsbereich des Requesters.

Das gleiche Vorgehen, wie beim Ausbleiben der Heartbeat-Nachricht, wendet der Requester bei Eingang einer Nachricht vom Typ “Canceled” an.

Das beschriebene Vorgehen zum Umgang mit Fehlern ist bewusst einfach gehalten, in der Hoffnung, dass dadurch möglichst viele VWS-Implementierungen das Interaktionsprotokoll zur Synchronisation unterstützen. Im Ergebnis entspricht das im Wesentlichen dem Quality of Service Level 2 (“Exactly once”) des MQTT -Protokolls. Dies ist den Diskussionen der fachlichen Anforderung an Synchronisierung geschuldet. Sollte sich später zeigen, dass es andere Anforderungen gibt, sei an dieser Stelle empfohlen sich an Definitionen und Mechanismen zu orientieren, die im Bereich der Message Broker etabliert sind.

## <a name="_7"></a>7. Änderungsmanagement

Um flexibel und effizient auf sich ändernde Anforderungen reagieren zu können, ist ein gut durchdachter Änderungsprozess entscheidend. Hierbei werden eine Reihe von grundlegenden Änderungsbedarfen unterschieden:

-   **Technischer Änderungsbedarf**: Der technische Änderungsbedarf bezieht sich auf alle Änderungen an der Bezugskonfiguration, z.B. die Länge einer Leitung, der Austausch einer vollständigen Leitung oder die Integration einer neuen Fahrzeugfunktion.
-   **Produktänderung**: Produktänderungen entstehen, wenn neue Technologien oder Komponenten eingeführt werden, wie der Austausch eines Steckers gegen einen anderen.
-   **Kostenoptimierung**: Änderung wegen Kostenoptimierung zielen darauf ab, die wirtschaftliche Effizienz zu erhöhen und Kosten zu reduzieren.
-   **Prozessoptimierung**: Verbesserung von Fertigungsabläufen zur Steigerung der Produktivität, bspw. durch den Einsatz anderer Komponenten oder Verfahren, die den Prozess vereinfachen. Hierfür sind i.d.R. Änderungen am Produkt notwendig (z.B. zusätzliche Halter).
-   **Lieferengpässe**: wenn Materialien oder Komponenten nicht rechtzeitig verfügbar sind und alternative Lösungen oder Lieferanten gefunden werden müssen.
-   **Regularien**: Änderungsbedarf, für die Anpassung an aktuelle gesetzliche Vorgaben und Standards, erfordern.

Gemeinsam mit den Projektpartnern, die über das Domänenwissen des Leitungssatzes verfügen, sollte ein Ablauf für das Änderungsmanagement erstellt werden. Nach gemeinsamer Auffassung findet das Änderungsmanagement ausschließlich auf Typ-Ebene im Entwicklungsprozess statt. Aus dem Ablauf sollten wiederkehrende Interaktionen erkannt und generalisiert werden, sodass am Ende ein flexibler, aus Bausteinen zusammengesetzter Ablauf, entsteht.

Das Konzept soll die Abläufe durch proaktive Verwaltungsschalen realisieren. Dazu sind neben einer VWS für das Asset spezielle VWS für das Änderungsmanagement vorgesehen. Hierbei war zu entscheiden, ob es eine zentrale VWS zur Steuerung des Änderungsmanagement geben sollte, oder ob mehrere kleinere Workflows in verteilten VWS verankert werden sollten, die dann automatisiert bei Änderungen gestartet werden.

Die Definition des Ablaufs sollte Fragen klären, wie:

-   Wer initiiert eine Änderung?
-   Wer genehmigt eine Änderung?
-   Welche Rollen sind im Änderungsmanagementprozess beteiligt?

Durch zusätzliche Definitionen von Interaktionsabläufen im nicht genehmigten Fall oder im Fehlerfall sollen alle möglichen Fälle abgefangen werden.

Zudem sollten für das Änderungsmanagement aktuell bestehende Prozesse in der Domäne analysiert werden. Sofern bereits jetzt ein großer manueller Aufwand vorhanden ist, könnten Konzepte wie GIT/SVN zumindest einen zeitlichen Vorteil mit sich bringen. Automatisierte Änderungsverwaltung oder auch weitere Konzepte sollten entsprechend der Anforderungen aus der Domäne betrachtet und (auch in ökonomischer Hinsicht) evaluiert werden.

Ähnlich zur Versionierung in Kapitel 0 werden während des Änderungsprozesses manuelle Arbeitsschritte notwendig sein, wie z.B. das Anstoßen eines solchen Prozesses oder die Analyse der technischen Umsetzbarkeit der gewünschten Änderung.

### <a name="_7.1"></a>7.1 Ablauf

Die eingangs aufgeführten konkreten Änderungsbedarfe haben keinen Einfluss auf den grundsätzlichen Ablauf des Änderungsprozesses.

Der Änderungsprozess beginnt immer mit der Identifikation einer Änderung, gefolgt von einer Auswirkungsanalyse und einer Prüfung der technischen Machbarkeit. Anschließend erfolgt die Entscheidung, ob und wie die Änderung umgesetzt wird. Zuletzt wird die Änderung dokumentiert.

Je nachdem, ob der Änderungsbedarf durch den OEM oder von einem Tier festgestellt wurde, ergeben sich daraus unterschiedliche Ablaufszenarien. Diese werden nachfolgend näher erläutert und basieren auf einer Masterarbeit[^11], die im Zusammenhang mit dem Projekt VWS4LS durchgeführt wurde.

[^11]: Omar Abdelmageed, „*Konzept zur Umsetzung eines Konfigurationsmanagements mit Hilfe der Verwaltungsschale“*, Masterarbeit, Otto-von-Guericke-Universität Magdeburg, Fakultät für Elektrotechnik und Informationstechnik, November 2023.

#### <a name="_7.1.1"></a>7.1.1 Szenario 1: Änderungsbedarf seitens des OEM

In diesem Szenario stellt der OEM einen Änderungsbedarf fest und startet den Änderungsprozess. Dieser ist in 10 Einzelschritte aufgegliedert (*Abbildung* 1237):

![image](https://github.com/user-attachments/assets/fba29450-13f2-4de8-818a-e40aadb16617)   
Abbildung 12-39: Änderungsmanagement: Änderungsbedarf vom OEM.

1.  Änderungsidentifikation:
    -   Zunächst stellt der OEM einen Änderungsbedarf fest und löst damit den Änderungsprozess aus.
2.  Engineering Change Request (ECR) erstellen:
    -   Der OEM erstellt in der Rolle der „Requesters“ einen ECR.
    -   Der erste Schritt zur Erstellung erfolgt in der Regel in informellen Formaten, wie E-Mail, handschriftliche Notizen oder per mündlicher Überlieferung.
    -   Anschließend werden daraus alle notwendigen Informationen extrahiert und in das ECR-Teilmodell (Siehe 12.7.2.1) überführt.
    -   In die Erstellung des ECR werden Fachprojektleiter und Entwicklungsingenieure miteinbezogen.
3.  ECR teilen:
    -   Eine Kopie des ECR wird mit Tier X geteilt. (Die Bezeichnung „Tier X“ wird hier als Sammelbegriff für alle Zulieferstufen verwendet, also Tier 1-, Tier 2-, Tier n-Zulieferer und Konfektionäre).
    -   Wenn ein OEM mehrere Zulieferer für dieselben Teile beauftragt hat, erhält jeder betroffene Zulieferer eine Kopie des ECR.
4.  Auswirkungen prüfen:
    -   Tier X prüft die Auswirkungen der vorgeschlagenen Änderung. Dies kann bei einfachen Änderungen teilautomatisiert geschehen. Für komplexere Änderungsanfragen werden Mitarbeiter in den Prozess involviert, die die Auswirkungen der Änderungen analysieren.
    -   Für Komplexe Änderungsanfragen wird ein internes Change Control Board (CCB) wird auf Seiten des Zulieferers durchlaufen
    -   Betroffene Fachabteilungen werden identifiziert.
    -   Eingangsinformationen aus ECR werden in Tier X-spezifische Formate übersetzt (z.B. KBL).
    -   Kaufmännische Prozesse werden abgedeckt.
    -   Ausarbeitung wird in Zusammenarbeit der betroffenen Fachabteilungen erstellt.
5.  Engineering Change Proposal (ECP) erstellen:
    -   Basierend auf der Auswirkungsanalyse erstellt Tier X das Teilmodell Engineering Change Proposal (ECP) (Siehe 12.7.2.2)
    -   Dieser enthält das ein Angebot, zu welchen Konditionen der Zulieferer die Angefragte Änderung umsetzen kann.
6.  ECP teilen:
    -   Der ECP wird durch den Vertrieb des Zulieferers zur Bewertung mit dem OEM geteilt.
    -   Der ECP verweist auf den initialen ECR, damit dieser zugeordnet werden kann
7.  ECP bewerten:
    -   Einkauf, Fachabteilungen und Requester des OEM bewerten den ECP.
    -   Der Requester hat dabei die Rolle des Geldgebers und vertritt Interessen auf Gesamtfahrzeugebene
8.  Entscheidung treffen:
    -   Der OEM trifft eine Entscheidung, ob die Änderung angenommen oder abgelehnt wird.
    -   Wenn das ECP abgelehnt wird, endet der Prozess hier.
    -   Wenn das ECP angenommen wird, geht es weiter mit Schritt 9.
9.  Engineering Change Order (ECO) erstellen:
    -   Der das Entwicklungsteam des OEM erstellt eine Engineering Change Order (ECO) (Siehe 12.7.2.3).
    -   Dieser enthält die technische Beschreibung der Änderung, eine neue Bezugskonfiguration und den Einsatzzeitpunkt.
    -   Die ECO verweist auf den zugehörigen ECP, damit diese zugeordnet werden kann.
10. Bezugskonfiguration aktualisieren:
    -   Der OEM aktualisiert die Bezugskonfiguration basierend auf dem ECO.
11. ECO und neue Bezugskonfiguration freigeben:
    -   Der ECO und die neue Bezugskonfiguration werden durch den OEM freigegeben.
12. Änderung implementieren:
    -   Tier X implementiert die Änderung.

#### <a name="_7.1.2"></a>7.1.2 Szenario 2: Änderungsbedarf seitens des Tier X

In diesem Szenario stellt der Tier X einen Änderungsbedarf fest und löst den Änderungsprozess aus. Dieser ist in 9 Einzelschritte mit diversen Entscheidungswegen untergliedert (*Abbildung* 1238):

![image](https://github.com/user-attachments/assets/d49e0a84-50c1-41cb-81b5-1181b792956f)   
Abbildung 12-40: Änderungsmanagement: Änderungsbedarf vom Tier X

1.  Änderungsidentifikation:
    -   Der Prozess beginnt mit der Identifikation einer notwendigen Änderung durch Tier X.
2.  Optimization Request:
    -   Tier X erstellt einen Optimierungsantrag.
3.  Prüfung auf Plausibilität:
    -   Der OEM prüft, ob der Optimierungsantrag plausibel ist.
    -   Wenn der Antrag plausibel ist, wird er an ein Change Control Board, bestehend aus allen betroffenen Parteien, übergeben (3.1). Hier können sowohl Vertreter des OEM als auch des Konfektionärs beteiligt sein.

Wenn der Antrag nicht plausibel ist, wird er abgelehnt (3.2) und der Prozess endet hier.

1.  Auswirkungsanalyse:
    -   Wenn der Antrag plausibel ist, führt Tier X eine Auswirkungsanalyse durch, teilautomatisiert oder manuell, wie es im vorhergehenden Kapitel beschrieben wurde.
2.  Änderungsvorschlag erstellen:
    -   Tier X erstellt basierend auf der Analyse einen Änderungsvorschlag und übergibt ihn an das Change Control Board (CCB).
3.  Entscheidung:
    -   Das CCB trifft eine Entscheidung über den Änderungsvorschlag.
    -   Wenn die Entscheidung positiv ausfällt, führe die nächsten Schritte 7 und 8 parallel zu 9 aus.
    -   Wenn die Entscheidung negativ ausfällt, lehne den Antrag ab (3.2) und der Prozess endet hier.
4.  Bezugskonfiguration aktualisieren:
    -   Die Bezugskonfiguration wird in er VWS des Konfigurationsobjektes aktualisiert.
5.  Konfigurationsobjekt teilen:
    -   Die aktualisierte VWS des Konfigurationsobjektes wird mit allen relevanten Parteien geteilt.
6.  Umsetzung der Änderung:
    -   Bei Zustimmung wird der Prozess „OEM gibt Änderungen vor“ angestoßen, wie er im vorhergehenden Kapitel beschrieben ist. (Hier in *Abbildung* 1238 dargestellt, als stilisierte Version des Prozesses.)

### <a name="_7.2"></a>7.2 Änderungsmanagement in der Verwaltungsschale

Um das Änderungsmanagement in der Verwaltungsschale abzubilden, wird zunächst eine VWS für das Konfigurationsobjekt erzeugt (Siehe *Abbildung* 1239: ÄM_Konfigurationsobjekt

). Dieses dient als Ankerpunkt für die Teilmodelle E*ngineeringChangeRequests*, *EngineeringChangeProposals*, *EngineeringChangeOrders* und *Bezugskonfigurationen*.

Dateiname: [Änderungsmanagement.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/General/Aenderungsmanagement.aasx)[^12]

[^12]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/General/Aenderungsmanagement.aasx>

![image](https://github.com/user-attachments/assets/5c8093e0-2c83-4297-b492-c28c2720feed)   
Abbildung 12-41: ÄM_Konfigurationsobjekt

#### <a name="_7.2.1"></a>7.2.1 Teilmodell EngineeringChangeRequests

Das Teilmodell *EngineeringChangeRequests* (

*Abbildung* 1240) enthält eine oder mehrere *SubmodelElementCollection*, die jeweils eine Änderungsanfrage repräsentieren und eine Reihe von Eigenschaften enthält:

![image](https://github.com/user-attachments/assets/4838a297-1d51-4870-8cf4-2c568cc867e6)   
Abbildung 12-42: VWS-Änderungsmanagement: Teilmodell EngineeringChangeRequests

-   *Status_ECR*: beschreibt den aktuellen Bearbeitungsstatus des ECR. Initial wird der Status "in Bearbeitung" vergeben. Für den weiteren Verlauf stehen "angenommen" oder "abgelehnt" zur Verfügung.
-   *Name_Antragsteller_ECR*: ist die verantwortliche Person für den ECR.
-   *Zeitpunkt*: spiegelt den Eingangszeitpunkt des ECR wieder.
-   *Beschreibung_des_Änderungsbedarf:* formlose Beschreibung der Änderung.
-   *Derzeitige_Bezugskonfiguration:* verweis auf die Bezugskonfiguration, die abgeändert werden soll.
-   *File*: eine oder mehrere ergänzende Dateien. Beispiele: CAD-Datei der vorgesehenen Änderung, Änderungsanfrage als PDF.
-   *zugehöriger_ECP:* verweist auf den zugehörigen ECP, wenn der ECR angenommen wurde.
-   *Begründung_zur_Ablehnung:* enthält den Grund für die Ablehnung, wenn der ECR abgelehnt wurde.

#### <a name="_7.2.2"></a>7.2.2 Teilmodell EngineeringChangeProposals

Das Teilmodell *ECP* (*Abbildung* 1241) enthält eine oder mehrere SubmodelElementCollection(s), die jeweils einen Änderungsvorschlag repräsentieren und eine Reihe von Eigenschaften enthält:

![image](https://github.com/user-attachments/assets/70d16c8f-65a0-40bd-a22e-ec6dcc83fd22)   
Abbildung 12-43: VWS-Änderungsmanagement: Teilmodell EngineeringChangeProposals

-   *Status_ECP*: beschreibt den aktuellen Bearbeitungsstatus des ECP. Initial wird der Status "in Bearbeitung" vergeben. Für den weiteren Verlauf stehen "angenommen" oder "abgelehnt" zur Verfügung.
-   *zugehöriger_ECR*: verweist auf den zugehörigen Engineering Change Request (ECR), welcher diesen Vorschlag initiiert hat.
-   *Name_Antragsteller*: ist für den Initiator des ECP vorgesehen.
-   *Zeitpunkt*: spiegelt den Zeitpunkt der Erstellung des ECP wider.
-   *vorgeschlagene_Änderung*: beschreibt die vorgeschlagene Änderung.
-   *Auswirkungsanalyse*: enthält eine Analyse der Auswirkungen des Änderungsvorschlags, die in dem internen Change Control Board (CCB) der Entwicklungspartner durchgeführt wird.
-   *Liste_betroffene_Komponente*: listet die von der vorgeschlagenen Änderung betroffen Komponenten auf.
-   *Liste_Ressourcenbedarf*: spezifiziert den Ressourcenbedarf für die vorgeschlagene Änderung.
-   *Dokumente*: kann ergänzende Dateien enthalten, wie z.B. Pläne oder technische Spezifikationen.
-   *Begründung_zur_Ablehnung*: enthält den Ablehnungsgrund, falls der ECP abgelehnt wurde.

#### <a name="_7.2.3"></a>7.2.3 Teilmodell EngineeringChangeOrders

Das Teilmodell *ECO* (*Abbildung* 1242) enthält eine oder mehrere SubmodelElementCollection(s), die jeweils einen Änderungsauftrag repräsentieren und eine Reihe von Eigenschaften enthält:

![image](https://github.com/user-attachments/assets/004f80c3-b66a-4acc-9e33-0c7d7e0e1764)   
Abbildung 12-44: VWS-Änderungsmanagement: Teilmodell EngineeringChangeOrders

-   *Name_Auftragsteller*: gibt den Namen des Auftragstellers an.
-   *zugehöriger_ECP*: verweist auf den zugehörigen ECP, welcher diesen Auftrag initiiert hat.
-   *Erstellungszeitpunkt*: gibt den Zeitpunkt der Erstellung des Änderungsauftrags an.
-   *Beschreibung_der_Änderung*: beschreibt die durchzuführende Änderung.
-   *Schritte_zur_Änderungsimplementierung*: beschreibt mit einzelnen Properties die notwendigen Schritte zur Implementierung der Änderung durch einen Freitext.
-   *Implementierungsbericht*: enthält einen oder mehrere Berichte oder Dokumente zur Umsetzung der Änderung.
-   *neue_Bezugskonfiguration*: verweist auf die neue Konfiguration, die nach Umsetzung der Änderung gültig ist.

#### <a name="_7.2.4"></a>7.2.4 Teilmodell Bezugskonfigurationen

Das Teilmodell *Bezugskonfigurationen* (*Abbildung* 1243) enthält eine oder mehrere *SubmodelElementCollection*(s), die jeweils eine Bezugskonfiguration repräsentieren und eine Reihe von Eigenschaften enthält. Eine Bezugskonfiguration ist der Datenstamm (VEC, KBL, etc.), auf den eine Änderung angewendet wird.

![image](https://github.com/user-attachments/assets/35b03404-b063-4d73-b9b7-6dc41953087c)   
Abbildung 12-45: VWS-Änderungsmanagement: Teilmodell Bezugskonfiguration

-   *Datum_Freigabe*: enthält das Datum, ab wann die Bezugskonfiguration vom OEM freigegeben ist.
-   *Grund_für_die_Aktualisierung*: beschreibt den Grund für die Aktualisierung in menschenlesbarer Form.
-   *Dokumente*: enthält ein oder mehrere Dokumente, die den Datenstamm für die Bezugskonfiguration repräsentieren.

## <a name="_8"></a>8. Rückverfolgbarkeit

Das Thema Rückverfolgbarkeit fokussiert sich darauf, Informationen über die gesamte Wertschöpfungskette hinweg im VWS-Ökosystem auffindbar zu machen. Dazu wurden zwei Szenarien betrachtet:

### <a name="_8.1"></a>8.1 Szenario 1: Rückverfolgbarkeit über mehrere Tier-Stufen

Der OEM oder der Komponentenlieferant informiert den Kabelkonfektionär über eine fehlerhafte Charge. Der OEM verlangt eine Liste der betroffenen Leitungssätze, in denen Komponenten dieser Charge verbaut wurden.

#### <a name="_8.1.1"></a>8.1.1 Anforderungen

Unter Berücksichtigung einer modularen Verwaltungsschalen-Infrastruktur (vgl. Kapitel 12.2), ist eine eindeutige Identifizierung der am Herstellungsprozess beteiligten Assets über die gesamte Wertschöpfungskette unverzichtbar.

Schon bei der Bestellung des OEM beim Kabelkonfektionär muss eine eindeutige Identifizierung des Assets (Fahrzeug / Leitungssatz) erfolgen. Dieselbe Anforderung gilt bei der Beschaffung von Komponenten, die der Komponentenlieferant bereitstellt und beim Kabelkonfektionär verbaut werden (vgl. *Abbildung* 1244).

#### <a name="_8.1.2"></a>8.1.2 Lösungsweg

Für eine lückenlose Rückverfolgbarkeit müssen die Bestellinformationen eindeutig identifizierbar sein. Hierzu gehören unter anderem:

-   Fahrzeugidentifikationsnummer (FIN)
-   Artikelnummer oder Konfiguration des Leitungssatzes oder der Komponente
-   Auftragsnummer

Sobald das Produkt des Lieferanten an den Besteller übergeht, müssen die Lieferinformationen eindeutig identifizierbar sein. Hierzu gehören unter anderem:

-   FIN
-   Datum und Uhrzeit des Warenausgangs
-   Chargen- bzw. Seriennummer des Erzeugnisses

Diese Informationen müssen beim jeweiligen Lieferanten und Besteller in der zugehörigen Verwaltungsschale des Assets hinterlegt werden. Der Kabelkonfektionär muss für jeden Leitungssatz jede verbaute Komponente eindeutig identifizieren und in seiner Verwaltungsschale dokumentieren.

![image](https://github.com/user-attachments/assets/5de4fb70-303d-4c94-89db-b4edb7d1b33c)   
Abbildung 12-46: Rückverfolgbarkeit über mehrere Tier-Stufen

Mit diesem Ansatz wird das Szenario1 erfüllt:

Anhand der Chargennummer des Komponentenlieferanten kann der Kabelkonfektionär in seinen Verwaltungsschalen nachvollziehen, in welchen Leitungssätzen die Komponenten verbaut wurden, und übermittelt dem OEM die zugehörigen Bestell- bzw. Lieferinformationen (insbesondere die FIN).

### <a name="_8.2"></a>8.2 Szenario 2: Rückverfolgbarkeit beim Kabelkonfektionär

Der OEM reklamiert Leitungssätze, bei denen Schraubverbindungen Feldausfälle verursacht haben und fordert den Kabelkonfektionär dazu auf, den Schraubfall gemäß Spezifikation nachzuweisen.

#### <a name="_8.2.1"></a>8.2.1 Anforderungen

Ausgehend von der Bestellung des OEM bzw. eigenen Produktionserwartungen muss der Kabelkonfektionär eine lückenlose Rückverfolgbarkeit aller hergestellten Leitungssätze garantieren. Hierzu müssen die Chargennummern der Komponentenlieferanten sowie die Prozessdaten der Ressourcen dokumentiert und mit den Produktions-, Bestell- und Lieferdaten verknüpft werden.

#### <a name="_8.2.2"></a>8.2.2 Lösungsweg

Die folgende *Abbildung* illustriert den Zusammenhang ausgehend von der Bestellung, die in einen Produktionsauftrag überführt wird, bis zur Lieferung.

![image](https://github.com/user-attachments/assets/d6f77249-3d53-4d39-b3d9-98e5af38aef8)   
Abbildung 12-47: Rückverfolgbarkeit beim Kabelkonfektionär

Der Produktionsauftrag verweist auf eine oder mehrere Chargen, die wiederum auf ein oder mehrere Lose verweisen. Jedes Los verweist wiederum auf eine oder mehrere Produkt-Instanzen (z.B. Leitungssatz oder Komponente). Diese Aufgliederung entspricht den heutigen Produktionsbedingungen.

Die Produkt-Instanz beinhaltet Informationen über die durchgeführten Produktionsprozesse und wird von einem Produkt-Typ abgeleitet, der wiederum die geplanten Prozessschritte (BoP) sowie die dafür benötigten Komponenten und Halbfabrikate definiert (BoM).

In der BoP im Produkt-Typ werden die einzelnen Prozessschritte mit ihren jeweiligen Soll-Parametern definiert. In der Produkt-Instanz werden in der BoP die Prozessergebnisse dokumentiert und mit den Chargeninformationen der Komponenten und Halbfabrikate verknüpft.

Mit diesem Ansatz wird das Szenario 2 erfüllt:

Anhand der vom OEM bereitgestellten FIN kann der Kabelkonfektionär die zugehörigen Produktionsaufträge und somit die Produkt-Instanzen ermitteln. In den Produkt-Instanzen ermittelt der Kabelkonfektionär dann den geforderten Produktionsprozess für die Schraubverbindung und kann anhand der dokumentierten Prozessdaten den geforderten Nachweis erbringen.

### <a name="_8.3"></a>8.3 Datenvorhaltung

Um den Anforderungen für die Rückverfolgbarkeit und den damit einhergehenden Anforderungen über die Detailtiefe der Informationen gerecht zu werden, ist es notwendig viele Informationen über lange Zeiträume vorzuhalten. Die hierdurch entstehenden Datenmengen müssen begrenzt werden, um die Kosten für die Datenhaltung beherrschbar zu machen.

Neben den Kosten für die Datenhaltung müssen auch gesetzliche und vertragliche Anforderungen beachtet und der Nutzen der Daten bewertet werden.

Für diesen Zweck wurde ein eigenes Teilmodell für die Datenvorhaltung definiert (*Abbildung 12-48) und als „IDTA 02056: *Data Retention Policies*“ [16] standardisiert. Dieses Teilmodell beschreibt die Anforderungen an eine Datenvorhaltung und lässt sich stufenweise ergänzen. So ist es beispielsweise möglich, gesetzliche Anforderungen zentral, und vertragliche Anforderungen produktspezifisch zu definieren. Auf das jeweilige Produkt werden dann alle Anforderungen angewendet.

![image](https://github.com/user-attachments/assets/d6d04498-61b1-4981-ad13-baf24a0fe8e5)   
Abbildung 12-48: Teilmodell "Data Retention Policies"

Das Teilmodell wird auf Typ-Verwaltungsschalen definiert und verweist mittels semantischer IDs („SemanticIds“) auf die betroffenen Informationselemente. Anhand der „RetentionTime“ wird festgelegt, wie lange das Informationselement vorgehalten werden muss.

Die zusätzlichen Metadaten „Source“ und „Issuer“ verweisen auf die Quelle der Regel. Beispielsweise auf eine gesetzliche, vertragliche, oder interne Regel.

Ob und wann eine Regel angewendet wird, ist über die Parameter „EffectiveFrom“ und „EffectiveUntil“ festgelegt. Somit können Regeln ab einem bestimmten Zeitpunkt und für einen bestimmten Zeitraum angewendet werden.

Da Regeln mittels der „InheritedFrom“-Beziehung überschrieben werden können – beispielsweise wegen einer vertraglichen Regelung länger aufbewahrt werden sollen – besteht auch die Möglichkeit, eine Regel mit „Immutable“ als unveränderlich zu definieren. Als „Immutable“ deklarierte Regeln dürfen auf keinen Fall überschrieben werden. Dazu gehören beispielsweise gesetzliche Regelungen.

Weil Regeln sich ändern können, kann anhand der Autordaten „Creator“, „CreationTime“, sowie „AuditLog“ genau nachvollzogen werden, wer bzw. wann eine Regel hinzugefügt bzw. geändert hat bzw. wurde.

Die Regeln müssen durch ein automatisches System angewendet und ausgewertet werden. Im Entstehungszeitpunkt eines Informationselements muss dieses automatische System die anzuwendenden Regeln auswerten und das Informationselement annotieren. Hierbei werden zwei Informationen hinterlegt:

-   Die Quelle der Regel „PolicySource“.
-   Der frühestmögliche Zeitpunkt für eine Löschung „KeepUntil“.

Damit die Daten auch gelöscht werden, muss das automatische System die Verwaltungsschalen regelmäßig überprüfen und fällige Daten löschen. Hierbei sind hierarchische Strukturen zu beachten, wobei ein tieferliegendes Element später gelöscht werden sollte als ein höherliegendes Element. Beispielsweise soll ein Teilmodell nach einem Jahr, ein Element innerhalb des Teilmodells aber erst nach zwei Jahren gelöscht werden. In diesem Fall darf das Teilmodell ebenfalls erst nach zwei Jahren gelöscht werden.

## <a name="fazit"></a>Fazit

Die umfassende Betrachtung der zentralen Architekturthemen – **Modularisierung**, **Versionierung**, **Verlinkung**, **Synchronisation**, **Änderungsmanagement** und **Rückverfolgbarkeit** – im Kontext des Leitungssatzes zeigt, wie entscheidend eine durchdachte, integrierte Strategie für das Managen von Verwaltungsschalen über den gesamten Lebenszyklus hinweg ist. Die Ergebnisse sind im Fokus des Projektes VWS4LS entstanden, in dem die Wertschöpfung des Leitungssatzes im Vordergrund steht. Dennoch wurde versucht, einen generalistischen Ansatz zu finden und die Ergebnisse für jegliche Industrie anwendbar zu machen.

**Modularisierung** und **Verlinkung** bilden die technische Grundlage für die Umsetzung einer verteilten und kollaborativen VWS-Lösung. Die Modularisierung erlaubt es, verschiedene Sichtweisen, mit unterschiedlichem Informationsgehalt der in der Wertkette angesiedelten Stakeholder, zu ermöglichen. Der Komponentenhersteller hat in diesem Szenario bspw. eine detailliertere Sicht auf die in der VWS enthaltenen Informationen (bspw. Qualitäts- und Produktionsdaten), die nicht für den Konfektionär oder den OEM bestimmt sind. Die *specificAssetId* spielt hierbei eine zentrale Rolle, da sie für die Verlinkung zwischen den VWS verschiedener Stakeholder verwendet wird. Diese ID ermöglicht das Auffinden der VWS in den Registries der Wertschöpfungspartner. Allerdings ist die Änderung der *specificAssetId* nur mit erheblichem Aufwand möglich, da sie den Kern der Verlinkung darstellt. Die **dezentrale Architektur** ist besonders wichtig, um die Vertraulichkeit der Daten zu gewährleisten und Akzeptanzprobleme aufgrund eines zentralen Administrators zu vermeiden. Die Implementierung eines Discovery-Konzeptes für den Datenraum ist dabei erforderlich, um die verteilte Datenverwaltung zu optimieren und den sicheren Austausch der Daten zwischen den Beteiligten zu gewährleisten.

**Versionierung** und die Definition des SPoT sind ebenfalls grundlegende Konzepte für eine dezentrale VWS-Lösung. Die Versionierung stellt sicher, dass alle Änderungen nachvollzogen und korrekt implementiert werden. Der SPoT sorgt dafür, dass es eine eindeutige, zentrale Quelle für alle relevanten Daten gibt, auch wenn diese dezentral verwaltet werden. In der Versionierung werden Arbeitsstände der VWS-Struktur festgehalten, um auf einem konsistenten Datenstand der VWS gemeinsam mit allen in der Wertschöpfungskette beteiligten Partnern zu arbeiten. Eine Grundlage dazu bietet das Änderungsmanagement, welches als Ergebnis eines Änderungsprozesses eine neue Version hervorbringt.

**Änderungsmanagement** muss spezielle Herausforderungen adressieren, die sich aus der gleichzeitigen Bearbeitung von VWSen durch verschiedene Unternehmen ergeben. Merge-Konflikte sind potenzielle Probleme, die durch den Abgleich von VWSen unterschiedlicher Arbeitsstände entstehen können. Eine mögliche Lösung besteht darin, dass Änderungen, die nicht vom aktuellen Besitzer der VWS vorgenommen wurden, in einer „Erweiterungs-VWS“ münden, die die aktuelle Version referenziert und eine eigene Sicht für das Unternehmen darstellt. Der Einsatz von Mechanismen wie Merge- oder Pull-Requests, ähnlich denen bei GIT, kann dabei helfen, Konsens zwischen den Partnern zu finden und Datenkonflikte effizient zu lösen.

**Rückverfolgbarkeit** ist von zentraler Bedeutung für die Nachverfolgung von Komponenten und Prozessen über die gesamte Wertschöpfungskette hinweg. Zwei Szenarien verdeutlichen, wie Verwaltungsschalen zur lückenlosen Identifizierung von Komponenten und zur Dokumentation der Spezifikationskonformität beitragen können. Durch die Verwendung von VWSen wird die Rückverfolgbarkeit optimiert und die Qualitätssicherung entlang der Lieferkette unterstützt.

**Synchronisation** gemäß VDI/VDE 2193-1 [15] bietet ein strukturiertes Verfahren für die Verwaltung von Datenänderungen zwischen VWSen. Die Definition der Nachrichtenstruktur und der Fehlerbehandlung gewährleistet eine konsistente und zuverlässige Datenübertragung. So wird gewährleistet, dass alle Partner entlang der Wertkette auf die jeweils aktuellen Daten zugreifen können. Das Synchronisationsprotokoll ermöglicht verschiedene Verarbeitungsarten und bietet eine solide Grundlage für zukünftige Anpassungen.

Zusammenfassend lässt sich sagen, dass die Modularisierung und Verlinkung die technische Basis für die Verwaltung des Leitungssatzes legen, während Versionierung, Änderungsmanagement und Rückverfolgbarkeit wesentliche Komponenten für eine präzise, flexible und nachvollziehbare Prozesskontrolle darstellen. Die Integration dieser Konzepte in eine dezentrale Architektur ist entscheidend, um sowohl die Datenkonsistenz zu gewährleisten als auch die Akzeptanz bei den Stakeholdern zu sichern. Trotz der gut strukturierten Ansätze sind weitere Detailarbeiten und Feinabstimmungen über das Projekt VWS4LS hinaus erforderlich, um die Implementierung der VWS zu vervollständigen und zukünftige Anforderungen auch in anderen Domänen zu erfüllen.

# <a name="literaturverzeichnis"></a>Literaturverzeichnis

| [1]   | „Single Point of Truth,“ [Online]. Available: https://de.wikipedia.org/wiki/Single_Point_of_Truth.                                                                                                                                                                                                                                                  |
|-------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [2]   | Industrial Digital Twin Association e.V., „Decentralized Registries: Taxonomy of decentralized registries and an architectural overview,“ June 2023. [Online]. Available: https://industrialdigitaltwin.org/en/wp-content/uploads/sites/2/2023/06/Decentralized-Registries-Taxonomy-of-decentralized-registries-and-an-architectural-overview_.pdf. |
| [3]   | Industrial Digital Twin Association e.V., „IDTA 02006-2-0 Digital Nameplate for Industrial Equipment,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Digital%20nameplate/2/0.                                                                                                                       |
| [4]   | Industrial Digital Twin Association e.V., „IDTA 02003-1-2: Generic Frame for Technical Data for Industrial Equipment in Manufacturing,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Technical_Data/1/2.                                                                                           |
| [5]   | J. Pfrommer, M. Schleipen und J. Beyerer, „PPRS: Production skills and their relation to product, process, and resource,“ IEEE 18th Conference on Emerging Technologies & Factory Automation (ETFA 2013), 2013. [Online]. Available: https://doi.org/10.1109/ETFA.2013.6648114.                                                                     |
| [6]   | Industrial Digital Twin Association e.V., „Registrierte IDTA Submodelle,“ [Online]. Available: https://industrialdigitaltwin.org/en/content-hub/submodels.                                                                                                                                                                                          |
| [7]   | Industrial Digital Twin Association e.V., „IDTA 02004-1-2 Handover Documentation,“ March 2023. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Handover%20Documentation/1/2.                                                                                                                          |
| [8]   | Industrial Digital Twin Association e.V., „IDTA 02011-1-1 Hierarchical Structures enabling Bills of Material,“ 2024 June. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Hierarchical%20Structures%20enabling%20Bills%20of%20Material/1/1.                                                           |
| [9]   | Prostep ivip, „Harness Description List (KBL),“ prostep ivip, 26 Jun 2022. [Online]. Available: https://ecad-wiki.prostep.org/specifications/kbl/.                                                                                                                                                                                                  |
| [10]  | Prostep ivip, „Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.                                                                                                                                                                                            |
| [11]  | Industrial Digital Twin Association e.V., „IDTA 02031-1-0 Bill of Process (WiP),“ [Online]. Available: https://industrialdigitaltwin.org/content-hub/teilmodelle.                                                                                                                                                                                   |
| [12]  | A. Bröring, M. Ehrlich, L. Wisniewski, H. Trsek und S. Heiss, „An Asset Administration Shell Version Control to Enforce Integrity Protection,“ 2022. [Online]. Available: https:/doi.org/10.25644/a4ws-9a49.                                                                                                                                        |
| [13]  | VDI/VDE, VDI/VDE 2193 Blatt 2 - Sprache für I4.0-Komponenten - Interaktionsprotokoll für Ausschreibungsverfahren, Bd. VDI/VDE Richtlinien, 2020.                                                                                                                                                                                                    |
| [14]  | M. Stolze, „Entwurf komplexer Automatisierungssysteme: Konzepte zur Realisierung proaktiver Verwaltungsschalen und deren Kommunikation,“ in *EKA*, 2024.                                                                                                                                                                                            |
| [15]  | VDI/VDE, VDI/VDE 2193 Blatt 1 - Sprache für I4.0-Komponenten - Struktur von Nachrichten, Bd. VDI/VDE Richtlinien, V. M. u. Automatisierungstechnik, Hrsg., 2020, p. 36.                                                                                                                                                                             |
| [16]  | Industrial Digital Twin Association e.V., „IDTA 02056-1-0 Data Retention Policies,“ June 2024. [Online]. Available: https://industrialdigitaltwin.org/wp-content/uploads/2024/06/IDTA-02056-1-0_Submodel_Data-Retention-Policies.pdf.                                                                                                               |
| [17]  | OPC Foundation, „OPC 40570: OPC UA for the Wire Harness Manufacturing Industry,“ https://profiles.opcfoundation.org/workinggroup/88, WiP. [Online]. Available: https://profiles.opcfoundation.org/document/214.                                                                                                                                     |
| [18]  | „Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.                                                                                                                                                                                                          |
| [19]  | J. a. S. M. a. B. J. Pfrommer, „PPRS: Production skills and their relation to product, process, and resource,“ IEEE 18th Conference on Emerging Technologies & Factory Automation (ETFA 2013), 2013. [Online]. Available: https://doi.org/10.1109/ETFA.2013.6648114.                                                                                |
| [20]  | Industrial Digital Twin Aassociation e.V., „IDTA 02004-1-2 Handover Documentation,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Handover%20Documentation/1/2.                                                                                                                                     |
| [21]  | Industrial Digital Twin Association e.V., „IDTA 02008-1-1 Time Series Data,“ 2023. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Time%20Series%20Data/1/1.                                                                                                                                          |
| [22]  | Industrial Digital Twin Association e.V., „IDTA 02010-1-0 Service Request Notification,“ 2023. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Service%20Request%20Notification/1/0.                                                                                                                  |
| [23]  | Industrial Digital Twin Association e.V., „IDTA 02020-1-0 Capability Description,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/development/Capability/1/0.                                                                                                                                                  |
| [24]  | Industrial Digital Twin Association e.V., „IDTA 01005-3-0-1: Specification of the Asset Administration Shell Part 5: Package File Format (AASX),“ 2024. [Online]. Available: https://industrialdigitaltwin.org/content-hub/aasspecifications/idta-01005-3-0-1_package_file_format_aasx.                                                             |
| [25]  | Industrial Digital Twin Association e.V., „IDTA 01002-3-0-2: Specification of the Asset Administration Shell Part 2: Application Programming Interfaces,“ June 2024. [Online]. Available: https://industrialdigitaltwin.org/content-hub/aasspecifications/idta_01002-3-0-2_application_programming_interfaces.                                      |
| [26]  | VDI/VDE, „VDI/VDE 2193 Blatt 1 - Sprache für I4.0-Komponenten - Struktur von Nachrichten,“ 2020. [Online]. Available: https://www.vdi.de/richtlinien/details/vdivde-2193-blatt-1-sprache-fuer-i40-komponenten-struktur-von-nachrichten.                                                                                                             |
| [27]  | Industrial Digital Twin Association e.V., „IDTA 02005 Provision of Simulation Models,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Provision of Simulation Models/1/0.                                                                                                                            |
| [28]  | Industrial Digital Twin Association, „IDTA 02003-1-2: Generic Frame for Technical Data for Industrial Equipment in Manufacturing,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Technical_Data/1/2.                                                                                                |
