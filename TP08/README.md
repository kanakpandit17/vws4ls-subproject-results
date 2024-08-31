## Zielsetzung
Im Teilprojekt 8 "**Data Storage Policy, Sicherheit, Anbindung an Catena-X**" war das Thema „Anbindung an Catena-X“ wesentlicher Inhalt, basierend auf den konzeptionellen Erkenntnissen von TP 7. 

Dabei wurde auch das AP 7.3 "Pilotierung und Erprobung" mit den Aktivitäten in TP 8 inhaltlich abgearbeitet. Dazu wurde eine exemplarische Implementierung eines kollaborativen Datenaustauschs anhand des nachfolgend beschriebenen Use Case über Catena-X Komponenten umgesetzt, welches den bidirektionalen Datenaustausch zwischen den Akteuren anhand eines konkreten Szenarios prototypisch demonstriert.

## Use Case
Ein OEM sendet einen Entwicklungsauftrag für eine 150%-Leitungssatzvariante an den Tier-1. In dem Entwicklungsauftrag ist eine BOM-Struktur mit den jeweiligen Komponenten enthalten. Der Tier-1 hat anschließend die Aufgabe alle notwendigen Informationen zu den einzelnen Komponenten von den Pro-duct-Ownern (Tier-2) zu aggregieren. Hierfür müssen die richtigen Endpunkte der Tier-2 identifiziert werden. Dazu werden die im Entwicklungsauftrag seitens des OEM hinterlegten Informationen verwen-det. Ziel ist es, einen vollständigen aggregierten Digitalen Zwilling beim Tier-1 zu erzeugen, der alle Pro-duktinformationen enthält, die von den einzelnen Tier-2 für Ihr Komponenten zu Verfügung gestellt werden.

In diesem Szenario wird eine Wertschöpfungskette des Leitungssatzes über drei Stufen abgebildet. Insgesamt werden beispielhaft fünf Teilnehmer betrachtet:

1.	Ein OEM als Auftraggeber
3.	Ein Tier 1 als Konfektionär und Auftragsempfänger und Data Consumer von Tier 2	
5.	Drei Tier 2 als Lieferanten von Tier 1 und Data Provider
   
 ![image](https://github.com/user-attachments/assets/64e59452-5849-4839-a585-6a0061a5fab2)

Abbildung 1: Beispielhafte Darstellung der Wertschöpfungskette eines Leitungssatzes

##	Der Leitungssatz und seine Komponenten
Für die Darstellung des Use Cases wird das vereinfachte Beispiel eines Leitungssatzes verwendet. Dieser besteht aus Stecker, Terminals und Leitungen. Zusätzlich soll die Möglichkeit gegeben sein, eine Auswahl zwischen zwei Varianten auszuwählen. Hierfür ist Variante 1, 2 Stecker, die Terminals und die beiden oberen Leitung in Abbildung 2, und Variante 2 enthält die beiden Stecker, die Terminals und die beiden unteren Leitungen. 
![image](https://github.com/user-attachments/assets/b05ac68d-f96c-4a5e-879a-bedafc687761)
 
Abbildung 2: Vereinfachte Darstellung des Leitungssatzes

## Umsetzung des Use Cases
### [Catena-X Anforderungen](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP08/CX-Anforderungen.md)
### [Testdaten](https://github.com/VWS4LS/vws4ls-subproject-results/tree/main/TP08/Testdaten#readme)
### Zugriffskontrolle
### Datenzugriffsmechanismen
### Sequentieller Ablauf
