# Ausblick

Die Ergebnisse von VWS4LS betten sich in ein Umfeld von Forschungs-, Standardisierungs- und Umsetzungsaktivitäten ein. Im nachfolgend dargestellten Strategiehaus lassen sich die inhaltlichen und organisatorischen Bezüge darstellen, siehe Abbildung 61. Insbesondere wird erkennbar, wo noch Bedarfe (Baustellen) zur weiteren Forschungs- und Entwicklungsarbeit bestehen.

![image](https://github.com/user-attachments/assets/fd2b2990-4942-43dc-a2d3-3b37dd83962d)

Abbildung 61: ARENA2036 AAS-Strategiehaus

## Offene Themenfelder und Ansätze zu weiterführenden Arbeiten

Im weiteren Verlauf des Kapitels, wird auf einige Bedarfe, die in Abbildung 61 dargestellt sind, detaillierter eingegangen. Wichtig zu erwähnen ist, dass diese Bedarfe aus dem Projektkontext heraus definiert wurden, und somit bestimmte Teilbereiche abdecken und keinen Anspruch auf Vollständigkeit besitzen.

### DataSpecification – Templates

Für *ConceptDescriptions* ist derzeit nur das Template „*DataSpecificationIec61360*“ definiert und es existiert eine Guideline, wie ECLASS-Referenzen darauf gemappt werden können [16]. Der Modellierungsansatz bspw. von vielen VEC-Strukturen wird durch dieses IEC61360-Template allerdings nicht optimal unterstützt. Die Definition und Standardisierung weiterer DataSpecification-Templates und zugehöriger Guidelines für die bessere Unterstützung anderer Modellierungsstandards wie VEC wäre daher wünschenswert. Ebenso die Bereitstellung von standardisierten *Concept Descriptions* als Bibliotheken in global verfügbaren Repositories.

### Events

„Events“ als wichtige Datenraum-Technologie sind auf Basis der VWS noch nicht industrietauglich standardisiert. Es existieren vielmehr unterschiedliche Lösungsansätze, die in Forschungsprojekten untersucht und verifiziert werden. Als wesentlicher Beitrag aus dem Projekt VWS4LS wurde im TP 14 „Demonstrator“ wurde dazu ein mögliches Konzept entwickelt und prototypisch implementiert. Dieser Ansatz kann nun zur weiteren Standardisierung eingebracht werden.

### Software als Produkt

Bisher fokussierte die Modellierung von Produkten mit der VWS auf typischen Hardwareprodukten. Für die Modellierung von softwarebasierten Produkten wären noch geeignete Konzepte zu definieren.

### Services als Produkt

Bisher fokussierte die Modellierung von Produkten mit der VWS auf typischen Hardwareprodukten. Für die Modellierung von Dienstleistungsangeboten (Services) wären noch geeignete Konzepte zu definieren.

### VWS-Generierung mit KI

Die inhaltliche Ausgestaltung von Verwaltungsschalen ist meist eine aufwendige Recherchearbeit zur Ermittlung der relevanten technischen Merkmale. Der hohe Aufwand resultiert daraus, dass existierende Produkte in verschiedenen Dateien unterschiedlicher Formate beschrieben sind (z. B. .pdf, .xls, …). Die korrekte Serialisierung in der Verwaltungsschale ist fehleranfällig, und bei einer großen Anzahl von Komponenten ist eine automatisierte Generierung unerlässlich. Erste Ansätze zur KI-gestützten Erzeugung und Prüfung von Verwaltungsschalen sind vielversprechend und könnten hier ansetzen. Ein Beispiel für eine solche Initiative ist der IOSB FA³ST CreAItor[^1]. Auch die Anwendung herkömmlicher KI-Chatbots mit geeigneten Large Language Models (LLMs) ist denkbar.

[^1]: <https://www.iosb.fraunhofer.de/de/projekte-produkte/faaast-ecosystem-digitale-zwillinge-aas.html>

### Produktkonfigurator

Ein relevanter Sonderfall in Abgrenzung zu seriengefertigten und lagerhaltigen Produktvarianten ist die Konfiguration, Bestellung und Fertigungsbeauftragung von variantenreichen Produkten (z.B. Leitungen mit frei wählbarer Länge, Farbe und Endbestückungen), ggf. auch in Losgröße 1. Für derartige Fälle wäre eine generische Modellierungsmethodik und Konfigurationsoberfläche sinnvoll, welche eine VWS mit den Bestell- und Produktionsdaten erzeugt.

### VWS-Qualitätssicherung und Validierung (regelbasiert und mit KI)

Erstellte Verwaltungsschalen müssen toolgestützt auf formelle und inhaltliche Korrektheit geprüft werden. Für die inhaltliche Validierung von Verwaltungsschalen könnte eine KI-Unterstützung für eine wesentliche Effizienzsteigerung und höhere Fehlerfindungswahrscheinlichkeit sorgen.

### Produktsuche mit KI

Im TP 12 wurde exemplarisch umgesetzt, wie ein herstellerübergreifender Produktkatalog aussehen kann (siehe Kapitel 3.5). Für einen Anwender wäre es eine wesentliche Verbesserung, wenn er KI-unterstützt die Produktauswahl durchführen könnte. Die klar strukturierten und klassifizierten Daten der Verwaltungsschalen, die über einheitliche Schnittstellen abrufbar sind, erlaubt es KI-Algorithmen wesentlich effektiver zu arbeiten. Für die Optimierung der Produktsuche wären geeignete LLMs sowie UI/UX-Konzepte für die Anwendung auf Produktkatalogen zu definieren.

### VWS für e-Commerce

Ein naheliegender nächster Schritt ist die Anbindung des VWS-basierten Produktkatalogs an e-Commerce-Infrastrukturen (e-Shops). Hierzu wurde ein Beitrag „[*Utilization of Asset Adminstration Shells for e-Commerce Applications*](https://github.com/VWS4LS/vws4ls-subproject-results/upload/main/TP12)“[^2] bei der „*30th IEEE International Conference on Emerging Technologies and Factory Automation (ETFA)“* eingereicht.

[^2]: <https://github.com/VWS4LS/vws4ls-subproject-results/upload/main/TP12>

#### Bereitstellung kommerzieller Daten

Die bislang nicht adressierte Bereitstellung von kommerziellen Datensätzen (d.h. Preise, Verfügbarkeiten, Lieferzeiten) zu den technischen Datensätzen der Produktmodelle über VWS-Technologie muss noch vollständig gelöst werden. Eine erster Vorschlag wurde im oben angeführten ETFA-Beitrag aufbereitet und eine erste prototypische Implementierung erfolgte im Zuge des TP12 mit dem VWS4LS-Marketplace.

#### Abwicklung Bestell- und Lieferprozesse über VWS

Die im neuen Submodell *IDTA 02050-1-0 Purchase Order* vorgeschlagene Abwicklung von Bestell- und Lieferprozessen muss noch finalisiert und umgesetzt werden. Dahingehende Vorschläge wurden im oben angeführten ETFA-Beitrag aufbereitet.

#### Anbindung an e-Shop

Die bislang nicht adressierte Anbindung eines AAS-basierten Produktkatalogs an ein e-Commerce-Backend muss noch vollständig gelöst und standardisiert werden. Eine erster Vorschlag wurde im oben angeführten ETFA-Beitrag aufbereitet.

## Business-Sicht

Die Einführung der Verwaltungsschale (Asset Administration Shell, AAS) als Standardisierungsinitiative im industriellen Umfeld adressiert zentrale Herausforderungen der digitalen Transformation. Ihr Einsatz ermöglicht eine durchgängige, digitale und interoperable Datenhaltung über den gesamten Lebenszyklus industrieller Assets hinweg. Aus Businesssicht ergeben sich daraus folgende wesentliche Vorteile:

**Effizienzsteigerung durch Standardisierung**

Die AAS schafft eine einheitliche Datenstruktur und ein maschinenlesbares Datenformat. Dadurch werden bisherige Unzulänglichkeiten, wie die Pflege von Daten in unterschiedlichen Tabellen, Datenbanken oder inkompatiblen Systemen, überwunden. Daten werden nach klar definierten Standards aufbereitet und klassifiziert, was die Komplexität reduziert und Medienbrüche vermeidet.

**Automatisierung und Fehlerreduktion**

Durch die Standardisierung können zahlreiche Routinetätigkeiten automatisiert werden. Prozesse wie das Suchen, Erfassen und Übertragen von Daten erfolgen künftig digital und ohne manuellen Aufwand. Das minimiert Fehlerquellen und beschleunigt Abläufe signifikant. Die Integration von KI und Automatisierungslösungen wird erleichtert.

**Digitale Transparenz und Nachvollziehbarkeit**

Mit der AAS werden alle relevanten Daten zentral und nachvollziehbar bereitgestellt. Referenzdokumente wie CAD-Dateien oder Wartungsprotokolle sind eindeutig referenzierbar und jederzeit abrufbar. Das verbessert die Datenqualität, ermöglicht eine lückenlose Dokumentation und erleichtert Audits sowie Compliance-Prüfungen.

**Verbesserte Datenanalyse und Innovationsförderung**

Die durchgängige Verfügbarkeit und Vergleichbarkeit von Daten erlaubt umfassende Analysen und Auswertungen. Unternehmen können ihre Prozesse gezielt überwachen, Optimierungspotenziale identifizieren und Innovationen schneller umsetzen. Die kontinuierliche Verbesserung wird so systematisch unterstützt.

**Neue Formen der Zusammenarbeit**

Die AAS fördert die digitale Kollaboration innerhalb von Unternehmen und über Unternehmensgrenzen hinweg. Informationen können effizient, sicher und ortsunabhängig ausgetauscht werden. Das stärkt die Zusammenarbeit in Wertschöpfungsnetzwerken, erleichtert die Integration von Partnern und ermöglicht neue Geschäftsmodelle.

**Ökonomische Vorteile**

Die Standardisierung durch die Verwaltungsschale führt zu einer signifikanten Reduktion von Prozesskosten. Zeitaufwändige, manuelle Tätigkeiten entfallen, Schnittstellen werden vereinfacht und die IT-Landschaft wird harmonisiert. Unternehmen profitieren von höherer Produktivität, geringeren Fehlerquoten und einer gesteigerten Wettbewerbsfähigkeit
