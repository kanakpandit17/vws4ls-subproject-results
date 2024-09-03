# TP8 - Data Storage Policy, Sicherheit, Anbindung an Catena-X
## Zielsetzung
Das Teilprojekt 8 "**Data Storage Policy, Sicherheit, Anbindung an Catena-X**" hatte starke inhaltliche Überschneidung mit dem Teilprojekt 7 ["**Data Business Policy, Data Governance, Monetarisierung**"](/TP07#tp-7--data-business-policy-data-governance-monetarisierung) und war in folgende Arbeitspakete gegliedert: 

## AP 8.1 Technische Anforderungsanalyse
Im AP 8.1 "**Technische Anforderungsanalyse**“ sollten, ausgehend von den aktuellen Datenhaltungssituationen der Partner, Anforderungen für eine Datenhaltung im Hinblick auf die gemeinsame Nutzung entlang der Wertkette „Leitungssatz“ erarbeitet werden.
Die Zielstellung des Arbeitspaketes umfasste die Definition der notwendigen Anforderungen in Bezug zu Data Governance, Data Business Policy sowie Data Storage Policy, um einen sicheren interoperablen Datenaustausch für alle Beteiligten der Wertschöpfungskette sicherstellen zu können.
Da eine starke inhaltliche Überschneidung gegeben war, wurde das AP 8.1 bereits im Zuge des [AP 7.1 "Anforderungserhebung"](/TP07#ap-71---anforderungserhebung) abgearbeitet und dir Ergebnisse dort detailliert dokumentiert.

## AP 8.2 Technische Umsetzungskonzeption und Zielarchitektur
Im AP 8.2 „**Technische Umsetzungskonzeption und Zielarchitektur**“ sollten Lösungsansätze erforscht werden für die interoperable Nutzung von Daten der unterschiedlichen Akteure der Wertkette „Leitungssatz“ und über unterschiedliche Ablagestrukturen hinweg (On-Premises, Edge, Cloud). Als Leitbild dieser Lösungsbeschreibung wurde die übergeordnete Vision der Verwaltungsschale als Paradigma der Interoperabilität zwischen Produkt, Komponenten, Prozess und Produktion zugrunde gelegt und eine technische Anbindung mit Catena-X angestrebt. Inhaltlich wurde das Thema bereits in [AP 7.2 "Fachliche Konzeption der Daten-Policy entlang der Wertkette"](/TP07#ap-72---fachliche-konzeption-der-daten-policy-entlang-der-wertkette) erarbeitet und ist dort detailiert dokumntiert.

## AP 8.3 Vorbereitung der Anbindung an Catena-X
Im AP 8.3 „**Vorbereitung der Anbindung an Catena-X**“ wurde die Architektur der Catena-X-Plattform untersucht in Bezug auf Interoperabilität mit der Verwaltungsschale und eine exemplarische Implementierung eines kollaborativen Datenaustauschs anhand des nachfolgend beschriebenen Use Case über Catena-X Komponenten umgesetzt, welche den bidirektionalen Datenaustausch zwischen den Akteuren anhand eines konkreten Szenarios prototypisch demonstriert. Mit diesen nachfolgend beschriebenen Aktivitäten in AP 8.3 wurde auch das [AP 7.3 "Pilotierung und Erprobung"](/TP07#ap-73---pilotierung-und-erprobung-erstellung-implementierungsguideline) inhaltlich abgearbeitet.

###	Der Leitungssatz und seine Komponenten
Für die Darstellung des Use Cases wurde das vereinfachte Beispiel eines Leitungssatzes verwendet, der aus Stecker, Terminals und Leitungen besteht. Zusätzlich kann zwischen zwei Varianten ausgewählt werden. Variante 1 enthält 2 Stecker, die Terminals und die beiden oberen Leitung in Abbildung 1, während Variante 2 die beiden Stecker, die Terminals und die beiden unteren Leitungen enthält. 

![image](https://github.com/user-attachments/assets/b05ac68d-f96c-4a5e-879a-bedafc687761)
 
Abbildung 1: Vereinfachte Darstellung des Leitungssatzes

### Use Case
Ein OEM sendet einen Entwicklungsauftrag für eine 150%-Leitungssatzvariante an den Tier-1. In dem Entwicklungsauftrag ist eine BOM-Struktur mit den jeweiligen Komponenten enthalten. Der Tier-1 hat anschließend die Aufgabe alle notwendigen Informationen zu den einzelnen Komponenten von den Product-Ownern (Tier-2) zu aggregieren. Hierfür müssen die richtigen Endpunkte der Tier-2 identifiziert werden. Dazu werden die im Entwicklungsauftrag seitens des OEM hinterlegten Informationen verwendet. Ziel ist es, einen vollständigen aggregierten Digitalen Zwilling beim Tier-1 zu erzeugen, der alle Produktinformationen enthält, die von den einzelnen Tier-2 für Ihr Komponenten zu Verfügung gestellt werden.

In diesem Szenario wird eine Wertschöpfungskette des Leitungssatzes über drei Stufen abgebildet. Insgesamt werden beispielhaft fünf Teilnehmer betrachtet:

1.	Ein OEM als Auftraggeber
3.	Ein Tier-1 als Konfektionär und Auftragsempfänger sowie Data Consumer der Tier-2	
5.	Drei Tier-2 als Lieferanten von Tier-1 und Data Provider
   
 ![image](https://github.com/user-attachments/assets/64e59452-5849-4839-a585-6a0061a5fab2)

Abbildung 2: Beispielhafte Darstellung der Wertschöpfungskette eines Leitungssatzes

####	Ablauf des Szenarios
Die Aktionen der Akteure lassen sich grundlegend in zwei Kategorien aufteilen:

1.	**Data Provisioning**
2.	**Data Consumption**
   
Der Use Case wird nachfolgend auf Business Ebene beschrieben: 

1. **OEM: Data Provisioning**: Trigger für den Use Case ist die Anforderung des OEMs für einen Leitungssatz. Für unser vereinfachtes Szenario gehen wir davon aus, dass der OEM definiert, von welchem Zulieferer die Komponenten kommen sollen. Diese Anforderungen legt er in Form eines Submodels an und registriert einen Digitalen Zwilling (AAS) in seiner DTR. Anschließend informiert er seinen Tier 1 (Konfektionär) über den Auftrag.

2.	**Tier 2: Data Provisioning**: Die Tier 2 stellen die Informationen zu ihren Produkten in Form von Digitalen Zwillingen (AAS) bereit. Dazu erstellen sie die notwendigen Submodels. Diese werden dann zunächst in der Asset-Administration-Shell-Environment (AAS-Environment) hochgeladen. Danach werden in Catena-X ent-sprechende Digitale Zwillinge erstellt und in der DTR registriert.

3.	**Tier 1: Data Consumption (vom OEM)**: Tier 1 greift auf die Submodelle des OEMs zu. In diesem Kontext wird davon ausgegangen, dass der Tier1 vom OEM eine Mitteilung erhält, dass ein Entwicklungsauftrag vorliegt. Er sichtet die Informationen innerhalb des Auftrags und kann anhand der enthaltenen Informationen (BPNs) die erforderlichen Endpunkte der EDCs von den entsprechenden Tier 2 herausfinden.

4.	**Tier 1: Data Consumption (von den Tier 2)**: Mit den vom OEM definierten Zulieferern kann der Tier 1 die entsprechenden Endpunkte der Tier 2 herausfinden und auf die Daten zugreifen. Diese kann er im Anschluss sichten und entsprechende Komponenten für die Aggregation aussuchen. 

5.	**Tier 1: Data Provisioning**: Mit den Informationen der Tier 2 (welche Komponenten sie anbieten) kann der Tier 1 nun einen Leitungssatz mit den entsprechenden Komponenten darstellen. Er legt hierfür entsprechende Submodelle an und stellt die Verbindungen zu den ausgewählten Komponenten her. Daraufhin registriert er einen Digitalen Zwilling in seiner DTR mit den entsprechenden Submodels (detaillierte Beschreibung in Abschnitt 3 & 4.5).
 
 ![image](https://github.com/user-attachments/assets/121c8101-0d3e-4825-b111-f0731cedc6b6)

Abbildung 3: Prozessdiagramm Use Case

Die detaillierten Aktionen auf technischer Ebene zur Realisierung des UseCase-Demonstrators mit Catena-X sind im Kapitel [„Umsetzung des Use Cases“](/TP08/README.md#umsetzung-des-use-cases) beschrieben.

### Umsetzung des Use Cases
#### [Catena-X Anforderungen](/TP08/CX-Anforderungen.md)
#### [Testdaten](/TP08/Testdaten#readme)
#### [Zugriffskontrolle](/TP08/Zugriffskontrolle.md)
#### [Datenzugriffsmechanismen](/TP08/CX-Datenzugriff.md)
#### [Sequentieller Ablauf](/TP08/UseCaseAblauf.md)
