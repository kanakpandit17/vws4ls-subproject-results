# TP11: Fortsetzung der Tätigkeiten „Anbindung an Catena-X:

## Arbeitspaket 1 - Erarbeitung eines Konzepts zur Entscheidungsfindung

1.  **Analyse des Ist-Zustands**
    1.  Abgleich der AAS- und Aspekt-Modelle, d.h. Identifizierung von Überschneidungen, Konflikten und Lücken.
2.  **Entwicklung der Systemarchitektur** für den modifizierten Data Provider (mit dem EDC und einer „extended dDTR“, die den Zugriff auf das Security-Teilmodell ermöglicht.). Dabei sind mindestens die folgenden Aspekte zu berücksichtigen;
    1.  Anbindung der AAS in den EDC über die modifizierte dDTR (z.B. direkt als Asset, um eine AAS mit all ihren Submodellen direkt über den EDC ansprechen zu können.) Beinhaltet ein Re-Design hinsichtlich der notwendigen Erweiterungen der dDTR auf der Provider Seite sowie die möglichst geringe Anpassung der Policies-Engine im Control Plane des EDC.
    2.  Beschreibung des Kommunikation-Schemas
    3.  Spezifikation von Transformationsregeln und APIs, um die Metadaten (insbesondere Zugriffsrechte und Rollen in Policies) und Daten zwischen den Systemen/Modellen konvertieren bzw. synchronisieren zu können.
    4.  Identitäten, in UUIDs mit dem Ziel des Single Sign On
    5.  Ausformulierung Entscheidungsvorlage mit Summary-Whitepaper zum Ansatz (5 bis 10 Seiten.
3.  **DOD**: **Architektur-Dokumentation** liegt vor in Form von:
    1.  Funktionsblockschaubild
    2.  Kommunikationsablauf und Schaubild mit Beschreibung der Schnittstellen und Formate
    3.  Transformationsregeln und APIs
    4.  Beschreibung der notwendigen Anpassungen in den verschiedenen Komponenten der Verwaltungsschale, ggf. Definition weiterer Properties für die AAS-Submodelle, um Versionierung, Zugriffsrechte und Workflow-Status analog zum EDC-Modell abbilden zu können
    5.  Beschreibung der notwendigen Anpassungen in EDC, dDTR, , ggf. weiterer Komponenten
    6.  Beschreibung des Ansatzes eines SSO
    7.  Entscheidungsvorlage und Beschreibung der Features inkl. Abschätzung des Aufwands
4.  **Beschreibung von Features** im Sinne einer agilen Umsetzungsvorgehensweise (Scrum) als Grundlage für die Abschätzung des Aufwands und der späteren Abarbeitung
5.  **Meilenstein-Entscheidung:** **Technische Umsetzbarkeit**
    1.  Gemeinsam wird der Scope des Prototyps (PoC) im Sinne eines MVP definiert.
    2.  Und dessen Umsetzbarkeit im vorgeben Rahmen geprüft
    3.  No-Go-/Go-Entscheidung für die softwaretechnische Implementation

## Arbeitspaket 2 - Technische Umsetzung der Systemarchitektur für die direkte Anbindung der Verwaltungsschale inkl. der Submodelle an den EDC

In diesem Arbeitspaket geht es um die Programmierung der notwendigen Modifikationen in der dDTR, der Control und ggfls. Data Plane des EDC, sowie evtl. weiterer Services, die entsprechend der Architektur und dem Ansatz des MVPs benötigt werden, sowie das Testen der Funktionalität. Abschließend sollen die standardisierungsfähigen Schnittstellen und Funktionalitäten identifiziert und beschrieben werden. Die Einzelnen Schritte sind wie folgt:

1.  **Technische Umsetzung** des Proof-of-Concepts im Demonstrator von VWS4LS):
    1.  Implementierung des im Meilenstein definierten PoCs basierend auf den aktuellen Releases von Tractus-X und BaSyx.
    2.  Abarbeitung der Features gemäß der Definition aus AP 1 inkl. Sicherstellung der grundlegenden Funktionsfähigkeit (Debugging)
    3.  Regelmäßige Abstimmung mit dem AG
2.  **Testen der Funktionalität** des Konzepts von AP 1
    1.  Die in der Verwaltungsschale gespeicherten Zugriffsregeln werden beim Datenaustausch umgesetzt.
    2.  Die ausgewählten Daten werden an einen Consumer-EDC ohne Modifikation übertragen.
    3.  SSO von Tractus-X zu BaSyx funktioniert.
3.  Ergänzend: **Impulse zur Standardisierung** bei CATENA-X und IDTA zusammenstellen, z.B.:
    1.  Vorschläge zur Interaktion von Verwaltungsschale mit einem EDC als Standard. Erstellt werden soll ein Dokument mit der technischen Beschreibung der standardisierungsfähigen Funktionen und Schnittstellen, das als Basis für die Einreichung für Standardisierungsvorschläge in den verschiedenen Working Groups des Catena-X Network Vereins, der Eclipse Data Space Group, den EDC Upstream oder auch der ITDA dienen kann.
    2.  Optional – Konzept und Architekturentwurf für ein KIT „AAS as a Services“
4.  **DoD**:
    1.  Die Anbindung der Verwaltungsschale in den EDC wurde als PoC mit dem gemeinsam definierten Produktionsumfang programmiert, getestet und ist als Projektdemonstrator vorführbar.
    2.  Folgende Funktionalitäten wurden in Tests nachgewiesen:
        1.  Die in der Verwaltungsschale gespeicherten Zugriffsregeln wurden beim Datenaustausch umgesetzt.
        2.  Die ausgewählten Daten wurden an einen Consumer-EDC ohne Modifikation übertragen (Eine Rückwärtskompatibilität muss gewährleistet sein)
        3.  SSO von Tractus-X zu BaSyx funktioniert.
    3.  Die während des AP erstellten Artefakte (Dokumentation und Sourcecode) wurden im [VWS4LS-Github-Repo](https://github.com/orgs/VWS4LS/repositories) hinterlegt.
    4.  Der Code wurde in Tractus-X als Fork hinterlegt.



## Arbeitspaket 3 - Access-Management (IAM) VWS4LS

Anforderungsanalyse: Unter der Annahme, dass der PoC aus AP 1 und 2 erfolgreich die Integration der Kernfunktionalität für die Integration der vollständigen Verwaltungsschale mit Umsetzung der in dem Security-Teilmodell gespeicherten Zugriffs- und Rollen-Regelungen gezeigt hat, geht es in diesem Arbeitspaket um die Ausarbeitung des zu Rechte-, und Rollen-Managements einschließlich des zu verwendenden Regelwerks. Abschließend ist ein Test mit dem im PoC entwickelten System vorgesehen. Die einzelnen Schritte sind:

1.  Evaluierungen zur Vorbereitung
    1.  Evaluierung der Anforderungen an das Access-Management basierend auf den spezifischen Bedürfnissen der Projektteilnehmer über entsprechende Abfrage, den technischen Randbedingungen der Verwaltungsschale, des EDCs und PoCs sowie auf Basis externer „Good Practices“.
    2.  Definition eines Rechte-/Rollenkonzepts für VWS4LS-Anwendungsfälle unter Verwendung vorhandenen bzw. bereits im Projekt vorgesehenen Zugriffs-Methodiken (RBAC/ABAC) der Verwaltungsschale z.B. Standard zur Security bei der IDTA, sowie der EDC-Policies.
2.  Erstellung eines funktionalen Konzeptes
    1.  Abbildung des Rechte-/Rollenkonzepts als Datenverwendungsrichtlinien, um den sicheren Datenaustausch und die Einhaltung von Nutzungsbeschränkungen gewährleisten.
    2.  Untersetzung mit einer Management-Governance zur langfristigen Verwaltung und Steuerung des Access-Managements basierend auf dem Authentifizierungs- und Autorisierungsmechanismus von Catena-X mit den BPNs.
    3.  Abbildung des Konzeptes auf die im Arbeitspaket 1 entwickelte Architektur
    4.  Abbildung des Rechte-/Rollenkonzepts auf die Architektur, die die Integration von Verwaltungsschale und EDC ermöglicht, inklusive der Definition von organisatorischen Schnittstellen.
    5.  Ableitung der entsprechenden notwendigen Semantiken, Attribute und Rückmeldungen („access failed because…“).
3.  Technische Umsetzung des Proof-of-Concepts im Demonstrator von VWS4LS
    1.  Integration des erarbeiteten Konzepts mit dem EDC, um den sicheren Datenaustausch und die Durchsetzung von Zugriffsrechten in dem Projektdemonstrator zu demonstrieren.
    2.  Dazu Erstellung von einigen Beispiel-LS-VWSen, die zugriffsbeschränkte Submodelle enthalten.
    3.  Testen der Ausführbarkeit der in den Beispiel-S_VWSen konfigurierten Zugriffsrechten basierend auf dem PoC mit externen Identitätsprovidern zur Authentifizierung der Teilnehmer im Datenraum.
    4.  Validieren der Sichtbarkeiten und Zugriffsrechte von Tractus-X zu den in BaSyx gehosteten VWS, bzw. deren Submodelle oder auch einzelne Attribute.
4.  Input sammeln für die Weiterentwicklung von BaSyx und Tractus-X, z.B.
    1.  z.B. Darstellung der Rechte/Rollenattribute in den LS-VWS-Submodellen.
    2.  z.B. Identifikation von Lücken in den Bestands-UIs von Tractus-X und BaSyx
5.  DoD:
    1.  Datenverwendungsrichtlinie und Governance als Dokument
    2.  Beispielhafte AAS-Teilmodelle mit Zugriffsbeschränkungen können nur über eine entsprechende Authentifizierung mit den passenden Rollenrechten eingesehen oder verändert werden.
    3.  Die während des AP erstellten Artefakte (Dokumentation und Sourcecode) wurden im VWS4LS-Github-Repo hinterlegt.
