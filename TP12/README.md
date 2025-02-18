# TP 12 - Produktkatalog
Im Teilprojekt 12 „Produktkatalog“ wurden auf Basis der in [TP1 „Konzept, Informationsmodelle und Produktbeschreibung„](https://github.com/VWS4LS/vws4ls-subproject-results/tree/main/TP01) erarbeiteten Konzepte rund um das Informationsmodell und die Produktbeschreibung der Leitungssatzherstellung für die Automobilindustrie mittels Verwaltungsschalen (VWS), klare anwendungsorientierte Regeln für das Erzeugen und Verwalten von Typ-Verwaltungsschalen erarbeitet.

Die VWS nach IEC 63278-1 bietet als Schlüsselkonzept der Industrie 4.0 eine standardisierte Struktur für die Beschreibung von Assets (z.B. Maschinen, Komponenten oder Software) in einer digitalen Umgebung. Damit wird ein effizienter Datenaustausch zwischen verschiedenen Systemen und Anbietern ermöglicht.

![image](https://github.com/user-attachments/assets/5de698ad-23e7-487f-b36c-bd9f6b960524)

Abbildung 1-1: VWS in der Leitungssatz-Wertkette

In TP1 Es wurde daher basierend auf der VWS ein detailliertes und umfassendes Informationsmodell des Leitungssatzes spezifiziert, welches auch die Produktmodellierung des Leitungssatzes umfasst. Dies beinhaltet die detaillierten Anforderungen, die der Leitungssatz erfüllen muss.

Unverzichtbarer Startpunkt für das Arbeiten mit Verwaltungsschalen ist jedoch die Bereitstellung von Typ-Verwaltungsschalen für die im Leitungssatzkontext verwendeten Komponenten (siehe Spalte „Tier X“ in Abbildung 1-1). Im bisherigen Projektverlauf wurde dieses Thema nicht ausreichend detailliert behandelt und um die Einführungshürden für die betroffenen Unternehmen zu senken, widmete sich TP12 diesem Thema.

Das Teilprojekt wurde in Arbeitspakete aufgeteilt, die in den folgenden Kapiteln näher erläutert werden.

## AP 1 - Anforderungsanalyse (12/2024)

Im AP1.1 „Anforderungsanalyse“ wurden Grundlagen definiert sowie Zielsetzung und Use Cases für das Teilprojekt geklärt. Zusammenfassend geht es darum, eine minimal notwendige Produktdatenqualität für die Datenmodellierung und ein Konzept zur Generierung eines Produktkatalog aus Produktdatenbanken zu definieren und möglichst bei den Projektpartnern umzusetzen.

### Typen von Digitalen Zwillingen

Digitale Zwillinge werden üblicherweise in Untertypen unterteilt, zu denen der digitale Zwillingsprototyp (DTP), die digitale Zwillingsinstanz (DTI) und das digitale Zwillingsaggregat (DTA) gehören. Der DTP besteht aus den Entwürfen, Analysen und Prozessen, d.h. Modellen, die ein physisches Produkt realisieren. Der DTP existiert, bevor es ein physisches Produkt gibt. Der DTI ist der digitale Zwilling jeder einzelnen Instanz des Produkts, sobald es hergestellt ist. Der DTI ist mit seinem physischen Gegenstück für die restliche Lebensdauer des physischen Gegenstücks verbunden. Der DTA ist die Zusammenfassung von DTIs, deren Daten und Informationen für Abfragen über das physische Produkt, Prognosen und Lernen verwendet werden können. Die spezifischen Informationen, die in den digitalen Zwillingen enthalten sind, werden durch Anwendungsfälle bestimmt. Der digitale Zwilling ist ein logisches Konstrukt, was bedeutet, dass die tatsächlichen Daten und Informationen in anderen Anwendungen enthalten sein können [1].

Das Konzept des DTP wird im Folgenden durch die Typ-VWS umgesetzt werden. Der DTI beschreibt das Konzept der Instanz-VWS. Der DTA ist nicht im Scope dieses Teilprojekts.

### Anwendungsfälle

Es wurde eine Liste von Anwendungsfällen gesammelt, um ein umfassendes Verständnis der verschiedenen Szenarien zu erlangen, in denen Typ-VWS für den Leitungssatz in der Automobilindustrie eingesetzt werden.

Diese Anwendungsfälle (Use Cases) bilden die Grundlage für die Definition und Priorisierung der Anforderungen und Ziele der weiteren Arbeiten im Teilprojekt.

Die Use Cases erfassen verschiedene Sichten auf die Produktion des Leitungssatzes. Als wesentliche Aspekte sind die Produktbeschreibung inklusive der Verarbeitungsspezifikationen für die Komponenten und die Steuerung des Materialflusses durch die Fabrik zu nennen.


## AP 2 - Datenmodellierung (01/2025)

-   **Typ-Verwaltungsschalen**-Datenmodell für den VWS4LS-Kontext definieren (**ID-Bildung, Versionierung**, semantische Referenzierung, generische Minimal-Inhalte, DPP, PCF, Technical Data, …) und in einem Leitfaden beschreiben.
    -   Begleitend einige (max. 10) einfache Komponenten-VWSen für die beteiligten Projektpartner manuell erzeugen, validieren und als qualitativ hochwertige Referenzen bereitstellen.
    -   Zur Verprobung sollen die erzeugten Referenz-VWSen auf diversen Servern (BaSyx, Meta-Level-Marketplace) gehostet und über diverse AAS-Viewer verprobt werden.

## AP 3 - Extraktionslogik (ETL) entwickeln (ab 02/2025)

-   Unternehmensinterne Datenquellen auf VWS-Struktur mappen.
    -   Datenquellen analysieren und auf Standards abstimmen.
    -   Schnittstellen zu Datenquellen implementieren.
    -   ETL-Prozesse zur Extraktion, Transformation und Integration erstellen.

## AP 4 - Verwaltungsschalengenerierung

-   Exportfunktion für Verwaltungsschale (z. B. in JSON/XML/AASX).
    -   Datenversionierung und Validierung definieren und einrichten.

## AP 5 - Integration und Bereitstellung

-   Deployment und Monitoring in die IT-Infrastruktur integrieren.

## AP 6 - Testen und Qualitätssicherung

-   Testen von Extraktions- und Exportprozessen.

## AP 7 - Dokumentation und Schulung

-   Technische Dokumentation und Nutzerhandbücher bereitstellen.
