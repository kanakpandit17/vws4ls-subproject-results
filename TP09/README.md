# TP 9 - Pilotierung, Erprobung, Demonstrator

## Inhalt

[Zielsetzung](#zielsetzung)

[AP 9.1: Konzeption und Bauplan des Demonstrators](#_9.1)

[AP 9.2 - Umsetzung des physischen Demonstrators](#_9.2)
- [9.2.1 Demonstrator Ausbaustufe 1 (2022) – HMI 2022](#_9.2.1)
- [9.2.2 Demonstrator Ausbaustufe 2 (2023) - HMI 2023](#_9.2.2)

[AP 9.3 - Umsetzung des digitalen Demonstrators](#_9.3)
- [9.3.1 Demonstrator Ausbaustufe 3 (2024) – HMI 2024](#_9.3.1)
- [9.3.2 Demonstrator Ausbaustufe 4 (2024) - Ergebnistagung](#_9.3.2)

[AP 9.4 - Demonstration der Anwendungsfälle](#_9.4)

## Zielsetzung

Im TP9 „**Pilotierung, Erprobung, Demonstrator**“ fand die partnerübergreifende Pilotierung und Erprobung für die Lösungskonzepte zur Umsetzung der Verwaltungsschale statt. Dazu wurden über die Projektlaufzeit mehrere Demonstratoren aufgebaut, welche die erarbeiteten Ergebnisse und Konzepte aus den verschiedenen TPs integrieren und vor allem die Mehrwerte der VWS darstellen sollen.

Das TP9 war in folgende Arbeitspakete gegliedert:

## <a name="_9.1"></a>AP 9.1: Konzeption und Bauplan des Demonstrators

Im AP 9.1 „**Konzeption und Bauplan des Demonstrators**“ wurde die Ausgestaltung des Demonstrators erarbeitet. Insbesondere wurden hier die zeitlichen Ausbaustufen geplant (*Abbildung* 9-1). Wie in der *Abbildung* dargestellt, wurden an vielen Ecken und Enden die bisherige Planung an das Projektgeschehen angepasst. Die verschiedenen Demonstrator-Stufen werden in den beiden nachfolgenden Kapiteln dargestellt.

![image](https://github.com/user-attachments/assets/622f0224-df58-43af-9de5-8db2a5884273)    
*Abbildung 9-1: Zeitplan TP9*

Die Konzeption der Demonstratoren wurde bereits kurz nach Projektbeginn im Dezember 2021 gestartet und über die gesamte Projektlaufzeit fortgesetzt. Insgesamt wurden 4 Demonstratoren entwickelt und aufgebaut, welche im Folgenden beschriebenen werden. Der physische Aufbau des Demonstrators hat sich nach der Fertigstellung von Stufe 2 kaum mehr verändert. Der Hauptteil der Veränderung erfolgte anschließend vor allem softwareseitig. Daher werden die Stufen 1 und 2 des Demonstrators in dem *Kapitel 9.2* dargestellt wo es um die physische Demonstration geht und die Demonstrator-Stufen 3 und 4 in dem *Kapitel 9.3* dargestellt.

## <a name="_9.2"></a>AP 9.2 - Umsetzung des physischen Demonstrators

Im AP 9.2 „**Umsetzung des physischen Demonstrators**“ wurde die Umsetzung der physischen Elemente (Sachmittel) des Demonstrators definiert. Dies umfasste geeignete Beispiele für Komponenten des Leitungssatzes, ganze Teilleitungssätze und Produktionsmittel zur Bearbeitung und Montage des Leitungssatzes. Für alle diese Komponenten haben die Partner des Konsortiums Beiträge geleistet.

Die Konzeption der Demonstratoren, fing bereits kurz nach dem Start des Projektes im Dezember 2021 an und wurde über die gesamte Projektlaufzeit fortgesetzt. Insgesamt wurden 4 verschiedenen Demonstratoren entwickelt und aufgebaut, welche im Folgenden kurz beschrieben und im weiteren Verlauf des Kapitels öfter referenziert werden.

### <a name="_9.2.1"></a> Demonstrator Ausbaustufe 1 (2022) – HMI 2022

Ziel des ersten Demonstrators war es, auf die Komplexität des Leitungssatzes aufmerksam zu machen, und erste statische Produktverwaltungsschalen selbst mittels des AASX-Package-Explorers aufzubauen.

Hierzu wurde ein Leitungssatz einer bereits auf dem Markt befindlichen Mercedes C-Klasse (2016) von dem Projektpartner Dräxlmaier zur Verfügung gestellt. Eine Konstruktion aus Monopanplatten, Klavierscharnieren und Abschlussleisten aus Edelstahl wurde zurechtgeschnitten und montiert, damit der Leitungssatz darauf befestigt und auf Messen präsentiert werden kann (siehe *Abbildung* 9-12).

![image](https://github.com/user-attachments/assets/c417b8bd-55bf-45be-8306-0b26e4011f6b)   
*Abbildung 9-2: Physikalische Leitungssatzpräsentation inkl. Verwaltungsschalen (Bildschirme)*

Zur Präsentation erster Produktverwaltungsschalen wurden 4 ausgewählte Leitungssatzkomponenten (Clip, Terminal, Tape und Leitung) als VWS mit dem AASX-Package-Explorer erstellt. Hierfür wurden die bereits vorhandenen Teilmodelle der IDTA verwendet (d.h. *DigitalNameplate*, *ContactInformation*, *TechnicaData* und *HandoverDocumentation).*

![image](https://github.com/user-attachments/assets/103720c6-9ecb-4f25-84ec-aa31ce85e053)   
*Abbildung 9-3: Beispiel VWS-Terminal*

### <a name="_9.2.2"></a> Demonstrator Ausbaustufe 2 (2023) - HMI 2023

![image](https://github.com/user-attachments/assets/0363f5b3-a495-41cd-8e79-c894489f36e3)   
*Abbildung 9-4: Projektdemonstrator mit Fokus auf der Implementierung der VWS im Produktionsprozess*

Ziel des zweiten Demonstrators war es, die dynamische Einbindung der VWS in einen Leitungssatzproduktionsprozess umzusetzen und vor allem die Mehrwerte der VWS und deren Möglichkeiten in Bezug zur durchgängigen Digitalisierung durch einen Standard in den Vordergrund stellen. Der grundsätzliche Aufbau des Demonstrators besteht aus sechs Hauptkomponenten, die im Folgenden kurz erläutert werden:

-   **MES-Applikation**  
    Die Manufacturing Execution System (MES)-Applikation dient dazu, den Produktionsauftrag zu initiieren und die verschiedenen Informationsquellen sowie -ströme zu koordinieren.
-   **Einzelkomponente Leitung**  
    Die Leitung besitzt eine eigene Verwaltungsschale, in der wesentliche Informationen wie *WireNumber* und *WireBatch* hinterlegt sind. Diese Daten werden durch das Scannen eines QR-Codes in den Produktionsprozess integriert.
-   **Einzelkomponente Terminal**  
    Auch das Terminal verfügt über eine eigene Verwaltungsschale. Deren Informationen, wie *TerminalNumber* und *TerminalBatch*, werden ebenfalls über das Scannen eines QR-Codes in den Prozess eingebracht.
-   **Crimp-Maschine**  
    Die Aufgabe der Crimp-Maschine ([Wezag_UP150](https://www.wezag.de/maschine/crimpmaschine-wdt-up150/)) ist die Durchführung des Crimp-Prozesses. Die im Auftrag enthaltenen Informationen werden in den Produktionsprozess der Maschine eingespeist, während gleichzeitig Produktionsdaten an die MES-Applikation zurückübermittelt werden.
-   **Shopfloor-Monitoring**  
    Das Monitoring-System erfasst verschiedene Informationen von der Maschine sowie den Typ- und Instanz-Verwaltungsschalen des jeweiligen Auftrags, wie etwa den Verlauf der Crimpkraft.
-   **BaSyx-Middleware**  
    In der BaSyx-Middleware sind die Verwaltungsschalen der Maschine und der jeweiligen Jobs hinterlegt, auf die während des Produktionsprozesses zugegriffen wird.

![image](https://github.com/user-attachments/assets/278e0513-b170-4218-bd7c-a3edcfacf2df)    
*Abbildung 9-5: Bestandteile Demonstrator und Informationsfluss*

Die Initialisierung eines Produktionsauftrags erfolgt durch das Scannen eines QR-Codes. Dieser enthält grundlegende Informationen zum Auftrag, wie die Job- und Produktnummer sowie eine ID für die zu verwendende Maschine. Im nächsten Schritt wird der Auftrag um weitere Informationen ergänzt, indem QR-Codes der Einzelkomponenten (Verwaltungsschalen von Leitung und Terminal) gescannt werden. Diese Informationen werden im Auftrag hinterlegt und vervollständigen die Auftragsbeschreibung.

Die MES-Applikation übermittelt anschließend den Auftrag mit der entsprechenden Produktionsfreigabe an die Maschine, woraufhin der Crimp-Prozess gestartet wird. Während der Produktion erzeugt die Maschine verschiedene Daten, wie den Verlauf der Crimpkraft oder die Produktionsendzeit. Diese Informationen werden nach Abschluss des Prozesses an die MES-Applikation zurückgesendet und in der entsprechenden Job-Verwaltungsschale gespeichert. Dieser Schritt veranschaulicht sowohl das Push- als auch das Pull-Prinzip, indem die Verwaltungsschale in der Lage ist, Informationen zu liefern und diese an vorgesehenen Speicherorten abzulegen.

## <a name="_9.3"></a>AP 9.3 - Umsetzung des digitalen Demonstrators

Im Arbeitspaket 9.3 „Umsetzung des digitalen Demonstrators“ wurde eine mehrstufige Demonstration der Entstehung und der Anreicherung der Verwaltungsschale entlang der Leitungssatz-Wertschöpfungskette erarbeitet. In der ersten Stufe wurde nach jedem Prozessschritt entlang des gesamten Entstehungsprozesses das Entwicklungsstadium des Assets „Leitungssatz“ (oder der Sub-Komponenten) und die dazugehörige Verwaltungsschale dargestellt

### <a name="_9.3.1"></a> **Demonstrator Ausbaustufe 3 (2024) – HMI 2024**

Ziel der Ausbaustufe 3 war die dynamische Einbindung der Verwaltungsschalen (VWS) in einen Leitungssatzproduktionsprozess mit mehreren Produktionsressourcen. Der physische Aufbau des Demonstrators hatte sich im Vergleich zu *Kapitel 9.2* lediglich dahingehend lediglich dahingehend verändert, das eine weitere Produktionsressource nahezu nicht verändert, dass eine weitere Produktionsressource ([Komax Alpha](https://www.komaxgroup.com/de/products/crimp-to-crimp/alpha-565)) mit eingebunden wurde (siehe *Abbildung* 9-6). Der Produktionsressource ist aufgrund der Größe und Transportabilität als Simulation verfügbar und steht physisch nicht zur Verfügung. Darüber hinaus besteht der Demonstrator weiterhin aus den Grundkomponenten – MES-Applikation, Produktionsmaschine, BaSyx und den Verwaltungsschalen der Einzelkomponenten (Leitungen und Terminals).

![image](https://github.com/user-attachments/assets/705ba228-eef7-4676-9b89-1336607569b4)    
*Abbildung 9-6: Aufbau des Demonstrators*

Der Fokus der Veränderung lag in der Nutzung von lokalen Rechnern und dezentralen Servern in der ARENA2036[^1]. Lokal laufen die MES-Applikation und die gesamte Shopfloor-Anbindung, während die Daten dezentral auf den Servern der ARENA2036 gesammelt werden. Darüber hinaus wurde die Anzahl der Produktionsressourcen erweitert, indem eine physische Maschine ([Wezag UP150](https://www.wezag.de/maschine/crimpmaschine-wdt-up150/)) und eine simulierte Maschine ([Komax Alpha](https://www.komaxgroup.com/de/products/crimp-to-crimp/alpha-565)) eingebunden wurden. Zusätzlich werden verschiedene Anbindungsprotokolle (OPC-UA Companion Specification und eine proprietäre Schnittstelle) unterstützt. Im Folgenden wird der Ablauf des Demonstrators beschrieben, bei dem aus verschiedenen Produktvarianten eine Auswahl getroffen und der Crimp-Prozess zur Herstellung einer gecrimpten Leitung durchgeführt wird. Die einzelnen Prozessschritte finden sowohl vor Ort auf dem Shopfloor als auch auf dezentralen Servern statt.

[^1]: <https://tractus-x-07.arena2036.de/>

**Abschnitt 1: Auf dem Shopfloor – Produktauswahl und Auftragserstellung**

Der Prozess startet mit der Produktauswahl. Es stehen drei verschiedene Leitungsvarianten zur Verfügung, die sich jeweils durch unterschiedliche Querschnitte unterscheiden. Zu jeder Leitung muss das passende Terminal ausgewählt werden. Das Ziel ist es, eine gecrimpte Leitung auf einer geeigneten Maschine herzustellen.

Sobald die Produktauswahl getroffen wurde, erstellt die MES-Applikation automatisch den Produktionsauftrag. Dazu fordert das MES zunächst die erforderlichen Produkt- und Prozessdaten an und legt fest, welche Ressource – also welche Maschine – für die Durchführung des Crimp-Prozesses genutzt wird. Sobald alle Informationen erfasst sind, ist der Auftrag vollständig beschrieben und wird zur weiteren Bearbeitung an die BaSyx-Middleware übertragen.

**Abschnitt 2: Zentral auf einem Server in der ARENA2036 – Erstellung der Verbundkomponente Verwaltungsschale**

m nächsten Schritt wird auf den Servern die Job-Verwaltungsschale des ausgewählten Produkts erstellt. Diese Verwaltungsschale enthält alle für die Produktion relevanten Informationen, einschließlich der spezifischen Daten der gewählten Leitung und des Terminals. Nachdem der Auftrag und alle damit verbundenen Informationen digital erfasst sind, werden die Auftragsdetails an die ausgewählte Maschine übermittelt, die den Crimp-Prozess durchführen soll.

**Abschnitt 3: Zurück auf dem Shopfloor – Prozessausführung**

Die ausgewählte Maschine auf dem Shopfloor übernimmt die Ausführung des Crimp-Prozesses. Hierbei kommen verschiedene Kommunikationsprotokolle wie die OPC-UA Companion Specification zum Einsatz, um eine reibungslose Steuerung und Datenübertragung sicherzustellen. Während des Produktionsprozesses werden sämtliche Prozessdaten – wie der Verlauf der Crimpkraft und die Endzeiten der Produktionsschritte – in die zuvor erstellte Verwaltungsschale zurückgespielt. Dieser Vorgang ermöglicht eine vollständige digitale *Abbildung* und Rückverfolgbarkeit des Produktionsprozesses.

Am Ende des Prozesses entsteht eine gecrimpte Leitung, die das Zielprodukt des Demonstrators darstellt. Dieser Ablauf verdeutlicht die enge Verzahnung von lokaler Produktion und digitaler Beschreibung sowie das Zusammenspiel zwischen physischen Produkten und ihren digitalen Abbildern.

### <a name="_9.3.2"></a> Demonstrator Ausbaustufe 4 (2024) - Ergebnistagung

Ziel dieser Ausbaustufe war, den statischen Teil des Demonstrators weiter zu reduzieren und somit ein weiterer Schritt in Richtung dynamischer VWS-Nutzung einer realistischen industriellen Anwendung zu tätigen. Hierfür wurden die im Projekt entwickelten Funktionen des *Capabilitychecks (TP5)*, dem *Automatisiertenverhandlungsprozess* (TP6), *Tool-Wear Funktion* (Ansatz zur Predictiv Maintanance à hochzählen der Produktionszyklen) und die Submodellstruktur von *ProductionOrder/Batch/Lot* (TP3) implementiert. Somit hat sich der physische Aufbau des Demonstrators, im Vergleich zum *Kapitel 9.3.1* nicht verändert, sondern die Veränderungen finden softwareseitig statt.

![image](https://github.com/user-attachments/assets/2c4a9fc3-a611-493f-8f49-86cf7bf56691)    
*Abbildung 9-7: Schematischer Prozessablauf*

In *Abbildung* 9-7 ist der Prozessablauf des finalen Demonstrators zusehen, auf den im weiteren Verlauf des Kapitels eingegangen wird. Die farblichen Markierungen der Aktivitäten, bedeutet eine Unterscheidung der Hauptkomponenten des Demonstrators.

-   Blau: Eine Aufgabe, die durch die BaSyx-Middleware umgesetzt werden muss
-   Grün: Eine Aufgabe, die durch die MES-Applikation umgesetzt werden muss
-   Rot: Eine Aufgabe die durch den Verhandlungsprozess umgesetzt werden muss
-   Gelb: Eine Aufgabe, die durch den Werker umgesetzt werden muss

Zu Beginn wird eine Produktauswahl durch den Werker in der MES-Applikation getroffen. Hierfür stehen wieder die verschiedenen Kombinationen aus Leitung und Terminal in unterschiedlichen Querschnitten zur Auswahl, die für die Produktion unterschiedliche Capabilities benötigen. Nach der Auswahl des Produktes, wird automatisiert in der *BaSyx-Middleware* eine VWS-Kombination für die Produktinstanz aus den *ProductionOrder*, *Batch* und *Lot* erzeuget, welche im folgenden Prozessablauf mit weiteren Prozessinformationen gefüllt werden. Anschließend wird der Werker durch das MES aufgefordert, die entsprechenden Produktinformationen, die für die spätere Ausführung des Prozesses notwendige sind, hinzuzufügen – dieser Schritt wird durch das Scannen der QR-Codes stellvertretend für den Verweis auf Einzelkomponenten umgesetzt. Da jedes Produkt unterschiedliche *Capabilties* benötigt, müssen nun im nächsten Schritt die potenzielle möglichen Produktionsressourcen ausfindig gemacht werden. Hierfür wurde der in *Kapitel 7.2* bereits beschriebene Verhandlungsprozess implementiert, der genau Ablauf ist in *Abbildung* 9-8 nochmal dargestellt. Ziel hierbei ist es, eine Produktionsstrategie zu definieren, in Abhängigkeit der notwendigen *Required Capabilties* auf Produktseite, mit dem Ziel „Best-Time“ (schnellstmögliche Produktion).

![image](https://github.com/user-attachments/assets/e63215ca-f11d-4256-a6cb-29dd545347eb)    
*Abbildung 9-8: Verhandlungsprozess zwischen Service Requester und Provider*

Als Ergebnis des Verhandlungsprozesses werden alle potenziellen Produktionsressourcen ausgegeben, die den *Capabilities* entsprechen würden. Die Informationen werden anschließend an das MES weitergeben und für den Werker zur in der MES-Applikation visuell zur Verfügung gestellt. Der Werker wählt nun eine der möglichen Ressourcen und muss der MES-Applikation die aktuelle Ressourcen Konfiguration (Werkzeugkonfiguration) mitteilen. Dieser Vorgang wird durch Abscannen der entsprechenden QR-Codes durchgeführt, die repräsentativ für die einzelnen Tools stehen. Sollte nun eine nicht passende Ressourcenkonfiguration aktuell auf der Ressource sein, wird der Werker aufgefordert die passenden Topols zum einen zu scannen und anschließend die Ressource neu zu Rüsten. Die neue Ressourcenkonfiguration wird anschließend in die Instanz VWS der *ProductionOrder* eingefügt und der Auftrag wird nun an die ausgewählte Ressource weitergeleitet. Die Ressource wird nun vom System freigeschaltet und kann den vorgesehenen Prozess durchlaufen. Nach Abschluss des Produktionsprozesses werden die während des Prozesses erzeugten Prozessdaten direkt in das Entsprechende *Batch* bzw. *Lot* eingefügt. Weiter wird die Information des „Prozessabschlusses“ an das MES weitergeben und der *Count* für die vom Werkzeug durchlaufenen Produktionszyklen (Ansatz *Predictiv Maintanance*) um 1 erhöht. Das MES setzt in diesem Fall den Status auf IDLE und ist nun bereit für einen neuen Auftrag.

## <a name="_9.4"></a>AP 9.4 - Demonstration der Anwendungsfälle

Im AP 9.4 „**Demonstration der Anwendungsfälle**“ wurden dedizierte Szenarien für die jeweiligen Zusammenhänge der fünf Hauptanwendungsfälle gezeigt:

1.  Kollaborative Entwicklung (im Engineering entstehen Typ-Daten, diese werden beim Tier 1 und 2 ergänzt),
    -   Durch die Umsetzung bzw. die Anbindung der VWS an das Catena-X Ökosystem unter Verwendung der Tractus-X Komponenten, wurde ein solches Szenario in *Kapitel 8.3* durchgespielt und detailliert beschrieben. Aufgrund technischer Differenzen (siehe *Kapitel 8.3.6*) und einiger fundamentaler Fragestellungen konnte eine Kombination aus den Demonstratoren aus *Kapitel 8.3* und *9.3.2* nicht umgesetzt werden.
2.  Fähigkeiten und Randbedingungen der Produktion im Engineering berücksichtigen (Varianten-Konfiguration)
    -   Durch die Beschreibung von "offered" und "required Fähigkeiten" wird dieser Anwendungsfall konzeptionell und demonstrativ abgedeckt. Die generische Beschreibung eines Produkttyps – dies kann sowohl ein einzelnes Produkt als auch eine Ressource sein – ermöglicht es, für die jeweilige Produktinstanz die notwendigen Fähigkeiten, die für die Produktion erforderlich sind, abzuleiten. Anschließend werden die Fähigkeiten der Produktinstanz mit den "offered Capabilities" der Produktionsressourcen verglichen. In Abhängigkeit der Kriterien (bspw. Best-Cost, Best-Time oder ähnliches) wird eine geeignete Strategie für die Wertschöpfung definiert. Diese Aspekte sind durch die generische Beschreibung der Capabilities, den Verhandlungsprozess und dem Capability-Check ebenfalls im Demonstrator abgedeckt, welcher in *Kapitel 9.3.2* beschrieben ist.
3.  Daten- und Informationsbereitstellung für die Rüstung und Parametrisierung der Produktionsmittel je Instanz (Anpassung der Komponenten, Werkzeuge, Bahnen etc.),
    -   Durch die im TP3 beschriebene Prozessliste (*Kapitel 3.3.2*) wurden alle notwendigen Parameter, die für die Prozessausführung erforderlich sind, im Detail beschrieben. Für den Crimpprozess wurde der dort erläuterte Zusammenhang zwischen ProductionOrder, Batch und Lot genutzt, um eine exemplarische Umsetzung innerhalb des Demonstrators zu ermöglichen. Die Prozessliste diente dazu, die erforderlichen Prozessparameter sowie die notwendigen Informationen für die Ressourcen bereitzustellen und zu aggregieren.
4.  Automatisiertes Änderungsmanagement entlang der Wertkette (Änderungen im Engineering führen zu automatisierten Anpassungen der Komponenten und der Prozesse),
    -   Dieser Anwendungsfall wird sowohl konzeptionell als auch demonstrativ in den Demonstratoren präsentiert. Die Untergruppe „Änderungsmanagement“ aus dem Architekturteam (*Kapitel 12.7*) beschreibt einen konzeptionellen Prozess, wie eine Änderung beschrieben sein muss, und welche Stakeholder in dem Prozess involviert sind. Hingegen die Untergruppe „Synchronisation“ ebenfalls aus dem Architekturteam (*Kapitel 12.5*) eine technische Änderung zweier VWS beschriebt und wie diese umgesetzt werden können. Teile aus den Ergebnissen der Synchronisationsgruppe sind bereits in dem Demonstrator im *Kapitel 9.3.2* verwertet worden, da der Mechanismus, für eine Verhandlung nahezu identisch mit der Synchronisation ist.
5.  Prozess- und Qualitätsdaten erfassen, dokumentieren und rückverfolgbar machen.
    -   Dieser Anwendungsfall ist sowohl konzeptionell als auch demonstrativ im Demonstrator, welcher im *Kapitel 9.3.2* beschrieben wurde, abgedeckt. In der VWS, werden nach der Prozessausführung alle Qualitätsdaten, wie bspw. die Crimpkraftkurve und weitere Prozessdaten aggregiert.

Für die Anwendungsfälle wurden typische Bearbeitungsvorgänge dargestellt, bspw. eine Platzierung von Steckern auf dem Kabelformbrett mittels Roboter, das Crimpen eines Leiters, das Bestücken des Steckers sowie das Zusammenstecken eines Steckers mit einem anderen oder einem Steuergerät.





