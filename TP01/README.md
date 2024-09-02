# TP 1 – „Konzept, Informationsmodelle und Produktbeschreibung“

# <a name="_toc174347896"></a><a name="_toc130858691"></a><a name="_toc172726606"></a>**Inhalt**

[1	Zielsetzung](#_toc174347897)

[2	AP 1.1 - Zielbeschreibung des Gesamtkonzepts](#_toc174347898)

[2.1	Anforderungserhebung](#_toc174347899)

[2.2	Klassen vom Materialen](#_toc174347900)

[2.3	Prozessübersicht](#_toc174347901)

[2.4	PPR-Modell](#_toc174347902)

[2.5	Fazit](#_toc174347903)

[3	AP 1.2 - Entwicklung von Informationsmodellen und Zuweisung der Daten](#_toc174347904)

[3.1	VEC und KBL](#_toc174347905)

[3.1.1	Ausdrucksfähigkeit der Modelle](#_toc174347906)

[3.1.2	Lebenszyklus und industrieller Einsatz](#_toc174347907)

[3.1.3	Abdeckung Anforderungen im Kontext VWS4LS](#_toc174347908)

[3.1.4	Bewertung](#_toc174347909)

[3.2	ECLASS](#_toc174347910)

[3.3	RAMI 4.0](#_toc174347911)

[3.4	OPC UA](#_toc174347912)

[3.5	Fazit](#_toc174347913)

[4	AP 1.3 - Erfassen der Geschäftsmodelle für das Informationsmodell](#_toc174347914)

[5	AP 1.4 - Beschreibung der Tiefe der Informationsmodelle](#_toc174347915)

[5.1	Grundlagen](#_toc174347916)

[5.2	Prozessliste und Parameter](#_toc174347917)

[5.3	Produktionsdatensatz](#_toc174347918)

[5.4	VEC als Produktdatenmodell](#_toc174347919)

[5.5	OPC UA Schnittstelle](#_toc174347920)

[5.5.1	Identifikation](#_toc174347921)

[5.5.2	Job Management](#_toc174347922)

[5.5.3	Material und Artikel Management](#_toc174347923)

[5.5.4	ResultManagement](#_toc174347924)

[5.6	Fazit](#_toc174347925)

[6	AP 1.5 - Validierung der Standards](#_toc174347926)

[7	AP 1.6 - Dokumentation der Ergebnisse](#_toc174347927)

[Literaturverzeichnis](#_toc174347928)

[Abbildungsverzeichnis](#_toc174347929)

[Abkürzungsverzeichnis](#_toc174347930)


# <a name="_toc174347897"></a><a name="_ref174348561"></a>**1. Zielsetzung**
Das Ziel des Teilprojekts 1 bestand darin, Konzepte rund um das Informationsmodell und die Produktbeschreibung der Leitungssatzherstellung für die Automobilindustrie mittels Verwaltungsschalen (VWS) zu beschreiben.

Die VWS ist ein Schlüsselkonzept der Industrie 4.0 und bietet eine standardisierte Struktur für die Beschreibung von Assets (z.B. Maschinen, Komponenten oder Software) in einer digitalen Umgebung. Damit wird ein effizienter Datenaustausch zwischen verschiedenen Systemen und Anbietern ermöglicht.

In diesem Teilprojekt wird basierend auf der VWS ein detailliertes und umfassendes Informationsmodell des Leitungssatzes beschrieben. Das Modell soll dabei sowohl in der Entwicklungs- als auch in der Fertigungsphase des Leitungssatzes eingesetzt werden.

Darüber hinaus wird auch die Produktmodellierung des Leitungssatzes spezifiziert. Dies beinhaltet die detaillierten Anforderungen, die der Leitungssatz erfüllen muss.

In der **Entwicklungsphase** soll das Modell eine hinreichend detaillierte Darstellung des Leitungssatzes ermöglichen, einschließlich aller Komponenten und Eigenschaften. Damit soll die Planung und Optimierung des Designs erleichtert und sichergestellt werden, dass der Leitungssatz alle erforderlichen Spezifikationen und Standards erfüllt.

In der **Fertigungsphase** soll das Modell eine effiziente Kommunikation und Koordination zwischen den an der Produktion des Leitungssatzes beteiligten Maschinen und Systemen ermöglichen. Dies soll dazu beitragen, Fehler zu minimieren, die Produktionszeit zu verkürzen und die Qualität des fertigen Produkts zu verbessern.

Durch die derartige Nutzung des Modells in Entwicklung und Fertigung soll ein hohes Maß an automatisierbarer Kontrolle und Flexibilität gewährleisten werden, um letztendlich einen hochwertigen und effizient produzierten Leitungssatz zu erzielen.

Das Teilprojekt wurde in sechs Arbeitspakete aufgeteilt, die in den folgenden Kapiteln näher erläutert werden:

- AP 1.1 – Zielbeschreibung des Gesamtkonzepts
- AP 1.2 – Entwicklung von Informationsmodellen und Zuweisung der Daten
- AP 1.3 – Erfassung der Geschäftsmodelle für das Informationsmodell
- AP 1.4 – Beschreibung der Tiefe der Informationsmodelle
- AP 1.5 – Validierung der Standards
- AP 1.6 – Dokumentation der Ergebnisse

# <a name="_toc171581631"></a><a name="_toc171666665"></a><a name="_toc172726607"></a><a name="_toc174347898"></a>**2. AP 1.1 Zielbeschreibung des Gesamtkonzepts**
Das Hauptziel des AP 1.1 "Zielbeschreibung des Gesamtkonzepts" war die einheitliche Beschreibung der Komponenten des Leitungssatzes. Dies beinhaltet die Definition und Standardisierung der Terminologie und der Spezifikationen, die für die Beschreibung der verschiedenen Komponenten des Leitungssatzes verwendet werden.

Dies soll dazu beitragen, Missverständnisse und Inkonsistenzen zu vermeiden und eine klare und konsistente Kommunikation zwischen den verschiedenen Teams und Stakeholdern zu ermöglichen, die an der Entwicklung und Produktion des Leitungssatzes beteiligt sind. 

Darüber hinaus soll dieses Arbeitspaket auch die Grundlage für die kollaborative Entwicklung legen, indem es klare Richtlinien und Prozesse für die Zusammenarbeit und den Informationsaustausch zwischen den verschiedenen Stakeholdern und Teams bereitstellt, um die Effizienz und Effektivität der kollaborativen Entwicklung zu verbessern und letztendlich zu einem hochwertigen und effizient produzierten Leitungssatz zu führen. Von der Vorgehensmethodik her wurde im AP 1.1 zuerst eine Anforderungserhebung durchgeführt, um die dort identifizierten Anwendungsfälle und Parameter als Basis für die Definition einer Prozess- und Ressourcenübersicht für das anschließende Mapping auf das PPR-Modell heranziehen zu können. 
## <a name="_toc172726608"></a><a name="_toc174347899"></a>2.1 Anforderungserhebung
Im ersten Schritt wurde eine Liste von Anwendungsfällen zusammen mit Teilnehmern des Teilprojekts TP3 gesammelt, um ein umfassendes Verständnis der verschiedenen Szenarien zu erlangen, in denen der Leitungssatz in der Automobilindustrie eingesetzt wird. Durch die Zusammenarbeit mit den TP3-Teilnehmern konnte eine breite Palette von Anwendungsfällen identifiziert und erfasst werden, die die Vielfalt und Komplexität der Herausforderungen widerspiegeln, welche bei der Entwicklung und Produktion von Leitungssätzen auftreten können. 

Diese Anwendungsfälle (Use Cases) bilden die Grundlage für die Definition und Priorisierung der Anforderungen und Ziele der weiteren Arbeiten im Projekt. Sie ermöglichen es uns auch, die Auswirkungen und den Nutzen unserer Arbeit in einem realen Kontext zu bewerten und zu demonstrieren.

Die Use Cases erfassen verschiedene Sichten auf die Produktion des Leitungssatzes. Als wesentliche Aspekte sind die Produktbeschreibung inklusive der Verarbeitungsspezifikationen für dier Komponenten und die Steuerung des Materialflusses durch die Fabrik zu nennen. Die Bedeutung von 3D-Daten (CAD-Daten) des Leitungssatzes und der Ressourcen ist ebenfalls erfasst worden, wie auch die standardisierte Kennzeichnung der physischen Assets, um den Bezug zur Verwaltungsschale herstellen zu können. So ist wurde auch erkannt, dass die Versionierung von Instanzdaten eine entscheidende Relevanz für die eindeutige Beschreibung und Identifikation eines Leitungssatzes und der Einzelkomponenten besitzt. 

Darüber hinaus wurden Themen wie bspw. Grenz- und Sollwerte im MES und die Möglichkeiten zur Anpassung von Prozessparametern erfasst.

Es wurde auch auf die Ausstattung und Konfiguration der Produktionsmaschinen eingegangen, d.h. Aspekte wie die Bereitstellung von Fähigkeiten der Maschinen und Maschinenkomponenten, Übertragung von Rezepten, die Abfrage von Werkzeug-Setups, die Überwachung des Produktionsfortschritts und des Status der Produktionsressourcen sowie die Überwachung des Materialverbrauchs. 

![image](https://github.com/user-attachments/assets/f51a5280-ce06-4187-8f34-2f52524fc3fd)

<a name="_ref172727240"></a><a name="_toc174347931"></a>*Abbildung 1: Arbeitsdokument Anforderungssammlung (Auszug)* 

Schließlich wurden auch Themen der Qualitätssicherung behandelt, wie die Validierung und Auswahl von Kontaktteilen, die Validierung der Leitungssatzentwicklung, die Abbildung von Varianten und die Rationalisierung der End-Of-Line (EOL) Prüfung. Es wurde auch auf die Bedeutung von Wartungs- und Kalibrierdaten, Wartungsprotokollen, der maximalen Ausstattung und Bestückungsvarianten eingegangen. 

Von den ursprünglich 90 gesammelten Anwendungsfällen ([Abbildung 1](#_ref172727240)) wurden 46 als Grundlage für die Arbeit am Teilprojekt 1 ausgewählt. Diese Relevant für die Auswahl war die basierte auf ihrer Beziehung zur Definition des Datenmodells und den verwendeten Standards. Jeder dieser Anwendungsfälle wurde sorgfältig analysiert und bewertet, um seine Relevanz und seinen Beitrag zur Erreichung der Projektziele zu bestimmen. Die ausgewählten Anwendungsfälle decken ein hinreichend breites Spektrum der Szenarien und Herausforderungen ab, die bei der Herstellung von Leitungssätzen für die Automobilindustrie auftreten könnenonnten. Diese Anwendungsfälle bildeten daher die Grundlage für die weiteren Arbeiten im Projekt und um die Anforderungen und Ziele des Projekts effektiv zu definieren und zu priorisieren.
## <a name="_toc174347900"></a><a name="_toc172726609"></a>2.2 Klassen vom Materialen
In der Herstellung von Leitungssätzen werden verschiedene Materialklassen verwendet, die für die Leistung und Haltbarkeit des Endprodukts entscheidend sind. 

\- **Wire**: Dies ist das Grundelement eines jeden Leitungssatzes und besteht in der Regel aus Kupfer oder Aluminium. Diese Metalle werden aufgrund ihrer hervorragenden elektrischen Leitfähigkeit und Flexibilität ausgewählt. Die Drähte sind üblicherweise mit Isolationsmaterialien wie PVC, Polyethylen oder Polypropylen ummantelt, um elektrische Störungen zu verhindern.

\- **Terminal**: Kontaktteile sind Metallteile, die verwendet werden, um zwei oder mehrere Drähte miteinander zu verbinden. Sie werden um den Draht gecrimpt, um eine starke, leitfähige Verbindung zu schaffen. Crimps müssen präzise ausgeführt werden, um eine zuverlässige Verbindung zu gewährleisten.

\- **Seal**: Dichtungen werden eingesetzt, um die Verbindungspunkte vor Feuchtigkeit, Staub und anderen Umwelteinflüssen zu schützen. Sie bestehen häufig aus Gummi oder Silikon und bieten eine zusätzliche Isolationsschicht, die die Langlebigkeit des Leitungssatzes verbessert.

\- **Sleeve**: Schutzhüllen dienen dazu, die Drähte vor physischen Schäden und Umwelteinflüssen wie Hitze oder Abrieb zu schützen. Materialien wie Nylon oder Polyester werden oft für diese Schutzhüllen verwendet, da sie eine hohe Widerstandsfähigkeit bieten.

\- **Housing**: Gehäuse sind die äußeren Komponenten, die die elektrischen Verbindungen eines Leitungssatzes umschließen. Sie sind in der Regel aus Kunststoff oder Metall gefertigt und dienen dazu, die inneren Komponenten zu schützen und zu organisieren.
## <a name="_toc174347901"></a>2.3 Prozessübersicht
Die Leitungssatzindustrie zeichnet sich durch eine Reihe von spezialisierten und komplexen Prozessen aus, die die Produktion von hochwertigen und funktionalen Leitungssätzen ermöglichen. Diese Prozesse sind integraler Bestandteil des Fertigungsablaufs und sind sorgfältig darauf ausgelegt, präzise Designanforderungen zu erfüllen.

In einem integrierten Produktionssystem existieren dabei mehrere Arten von Fertigungskompetenzen:

- **Drahtschneiden**: Hier werden die einzelnen Drahtstränge, die zur Bildung des Endprodukts verwendet werden, geschnitten, gecrimpt und versiegelt.
- **Montage**: Hier werden die Drahtstränge zusammen auf einer Montageplatte platziert, in die richtigen Gehäuse platziert sowie verklebt.
- **Qualitätsprüfung**: Hier wird der Leitungssatz auf elektrische, mechanische und andere Eigenschaften geprüft, bevor er an den OEM ausgeliefert wird.

Dabei werden die folgenden gängigen Arten von Produktionsmaschinen zur Herstellung von Leitungssätzen eingesetzt:

- **Schneidemaschinen**: Diese werden verwendet, um Drähte auf bestimmte Längen zu schneiden.
- **Abisoliermaschinen**: Diese Maschinen entfernen die Isolierung von den Enden der Drähte.
- **Crimpmaschinen**: Werden verwendet, um Anschlüsse oder Stecker an den Enden der Drähte anzubringen.
- **Löt-/Verzinnungsstationen:** Diese werden zum Löten oder Verzinnen von Drahtenden verwendet.
- **Drahtverdrillmaschinen**: Werden verwendet, um mehrere Drähte miteinander zu verdrillen.
- **Drahtmarkierungsmaschinen**: Sie markieren Drähte zu Identifikationszwecken.
- **Bündelmaschinen**: Damit werden Drähte zu einem Leitungssatz gebündelt.
- **Kabelbinder- und Schrumpfschlauchmaschinen:** Werden zum Anbringen von Kabelbindern und zum Schrumpfen von Schläuchen für zusätzlichen Drahtschutz verwendet.
- **Prüfmaschinen**: Zur Durchführung von elektrischen Sicherheitstests und zur Gewährleistung der Funktionalität.

Hierbei gibt es Maschinen, die mehrere dieser Fertigungsschritte kombinieren können, und es gibt einzelne Fertigungsschritte, die manuell durchgeführt werden.

## <a name="_toc174347902"></a>2.4 PPR-Modell
Ein etablierter methodischer Ansatz für die Fertigungsdatenmodellierung ist das "Produkt-Prozess-Ressourcen" (PPR) Modell [1] [2]. Es ermöglicht eine ganzheitliche Sicht auf ein Fertigungsprojekt aus unterschiedlichen Sichtweisen und einen Datenaustausch über Fachbereichsgrenzen hinweg. Dieser Ansatz erlaubt damit eine effiziente Gestaltung und Rekonfiguration von Fertigungsressourcen, um damit die Reduzierung der Entwicklungszeit und der Rüstkosten zu erreichen.

![image](https://github.com/user-attachments/assets/615a4abf-eb01-4cb4-97dc-96e3c36e21a2)

<a name="_ref174024057"></a><a name="_toc174347932"></a>*Abbildung 2: PPR-Modell*

Die PPR-Modellierung [3] teilt den Produktionsvorgang in folgende Aspekte auf ([Abbildung 2](#_ref174024057)):

- **Produkt**: Bezeichnet den End- oder Zwischenprodukttyp. Es besteht ein Unterschied zwischen einem Produkttyp und dem 'realisierten' Werkstück zur Laufzeit
- **Prozess**: Stellt Veränderungen an einem Produkt dar, die während der Produktion auftreten. Prozesse können aus verschiedenen Bereichen stammen, wie z.B. Fertigung, Transport, Montage, usw. 
- **Ressource**: Sind die Systemkomponenten (Hardware, Software) die zur Durchführung der Prozesse benötigt werden.

Eine Herausforderung besteht darin, häufige Produktänderungen innerhalb kurzer Zeiträume zu berücksichtigen. Dies ist aufgrund der Limitierungen aktueller Ansätze zum Entwurf, Aufbau und der Rekonfiguration von Automatisierungssystemen schwierig. Ebenso führen die steigende Menge und Vielfalt an Informationen aus der Produktion zu Engpässen, welche aber auf effiziente Art und Weise ausgetauscht und wiederverwendet werden sollen.

Ein effektiver Ansatz, um die Anforderungen der Produkte an die Montageautomatisierung zu erfüllen, ist die Integration von Datenmodellen zur Kopplung der PPR-Domänenmodelle. Damit können Daten aus verschiedenen Ingenieurdomänen und Ingenieurwerkzeugen effektiv verknüpft werden.

## <a name="_toc172726611"></a><a name="_toc174347903"></a>2.5 Fazit
Im Arbeitspaket 1.1 wurden die grundlegenden Anforderungen an die Leitungssatzproduktion erfasst und analysiert. Dies beinhaltete eine Zusammenstellung der typischen Materialklassen, Produktionsprozesse und Produktionsequipment in der Leitungssatzindustrie. Mit den gesammelten Informationen konnte ein umfassendes Verständnis der spezifischen Anforderungen und Herausforderungen dieser Branche erlangt werden. Anschliessend wurde das Produkt-Prozess-Ressourcen (PPR) Modell zur Erstellung von detaillierten Datenmodellen ausgewählt. So ist für eine hinreichend genaue Datenmodellierung der realen Produktionsprozesse in der Leitungssatzindustrie als Grundlage für die Umsetzung von Automatisierungslösungen in diesem Umfeld möglich.

# <a name="_toc172726612"></a><a name="_toc174347904"></a>**3. AP 1.2 Entwicklung von Informationsmodellen und Zuweisung der Daten**
Im AP 1.2 „Entwicklung von Informationsmodellen und Zuweisung der Daten“ wurde basierend auf den folgenden vorhandenen Standards die Datenmodellierung untersucht. 

**KBL (Kabelbaumliste**) [4] wurde als XML-basiertes Datenaustauschformat entwickelt, nachdem sich die bis dahin übliche Verwendung von Konstruktionszeichnungen als nicht mehr hinreichend erwiesen hatte. Die Zielsetzung der KBL ist die digitale Beschreibung der Produktspezifikation eines Kabelbaums als Grundlage für den Austausch zwischen OEM und Konfektionär. 

**VEC (Vehicle Electric Container)** [5] ist ebenfalls ein XML-basiertes Datenaustauschformat und als moderner Nachfolger der KBL zu sehen, entwickelt für den Austausch von Daten im Entwicklungsprozess des physikalischen Bordnetzes mit Übergang zur Produktion in der Automobilindustrie. Er bietet ein integriertes Modell mit umfassenden Möglichkeiten, unter anderem zur Beschreibung von Kabelbaumkomponenten, verschiedener verschiedenen elektrologischer elektrologischen Sichten, sowie der Produktspezifikation des Kabelbaums mit dessen geometrischer Form (3D) & 2D). 

**OPC UA (Open Platform Communications Unified Architecture**) [6] ist ein maschinenorientierter Kommunikationsstandard, der auch semantische Modellierung unterstützt und für die industrielle Automatisierung entwickelt wurde. Er ermöglicht eine sichere und zuverlässige Kommunikation zwischen verschiedenen Geräten und Softwareplattformen.

**ECLASS** [7] ist ein etabliertes System für die semantische Klassifizierung und Beschreibung von Produkten und Dienstleistungen, die im Kontext der Industrie 4.0 verwendet werden. Es soll festgestellt werden, ob ECLASS eine nützliche Ressource für die Klassifizierung von Stammdaten in Datenmodellen der Leitungssatzindustrie sein kann. 

**RAMI4.0** (Reference Architectural Model for Industry 4.0) [8] ist ein Referenzarchitekturmodell, und könnte als Rahmen für die Modellierung der Konzepte innerhalb des Projekts dienen, denn durch die Nutzung internationaler Standards ermöglicht RAMI 4.0 eine nahtlose Kommunikation und Zusammenarbeit zwischen unterschiedlichen Systemen und Akteuren.

Das Ergebnis der Analyse zielte darauf ab, die besten Ansätze für die Nutzung dieser Standards innerhalb des Projekts zu identifizieren.
## <a name="_toc172726613"></a><a name="_toc174347905"></a>3.1 VEC und KBL
Im nächsten Schritt des Projekts wurde eine Analyse der KBL- und VEC-Datenmodelle durchgeführt, um das optimale Modell für das Projekt auszuwählen. KBL und VEC sind standardisierte Datenformate, die entwickelt wurden, um den Austausch, die Zusammenarbeit und die Archivierung von Informationen über das physische Bordnetz im Automobilsektor zu erleichtern. Die Modelle wurden unter dem Dach der prostep ivip Association [9] in Kooperation mit dem Verband der Automobilindustrie (VDA) [10] entwickelt.

Als Basis für eine Bewertung ist ein grundlegendes Verständnis der Ausrichtung von KBL & VEC, sowie deren Historie und Zusammenhänge notwendig [11]. 

**KBL (Kabelbaumliste):** Die KBL entstand im Zeitraum 1999 – 2005 (erste Veröffentlichung als VDA Recommendation) mit verschiedenen Erweiterungen in den folgenden Jahren. Die Zielsetzung der KBL ist die digitale Beschreibung der Produktspezifikation eines Kabelbaums als Grundlage für den Austausch zwischen OEM und Konfektionär (vgl. [Abbildung 3](#mergeformat)).

**VEC (Vehicle Electric Container):** In der Anwendung der KBL zeigte sich aber auch, dass dieser spezifisches Anwendungsfall nur ein kleiner, wenngleich auch ein sehr wichtiger, Teil der in der Bordnetzentwicklung existierenden Schnittstellen und Datenaustauschszenarien ist. Da die Abgrenzung der einzelnen Schnittstellen zum Teil unternehmens- und prozess-spezifisch ist, aber die ausgetauschten Inhalte und Strukturen an vielen Stellen überlappen, wurde der VEC als einheitliche digitale Sprache in der Wertschöpfungskette „physisches Bordnetz“ entwickelt (vgl. dazu „erweiterter Scope“ in [Abbildung 3](#mergeformat)).

![image](https://github.com/user-attachments/assets/39dc8835-d5c1-4c90-98c9-991065332827)

<a name="_ref171590447"></a><a name="_toc174347933"></a>*Abbildung 3 Vergleich Scope VEC & KBL [11]**

### <a name="_toc172726615"></a><a name="_toc174347906"></a>3.1.1 Ausdrucksfähigkeit der Modelle
Unter dem Gesichtspunkt der Ausdrucksfähigkeit der beiden Modelle ist die KBL eine echte Untermenge des VEC, d.h. alle Sachverhalte, die sich in der KBL abbilden lassen, können auch im VEC ausgedrückt werden, umgekehrt ist dies nicht der Fall. Hinweis: Diese Aussage betrifft die Ausdrucksfähigkeit der beiden Modelle. Die dafür verwenden Modellierungskonzept und Struktur, also die Syntax, sind andere. Das heißt, eine KBL-XML-Dateien ist nicht gleichzeitig auch ein gültiges VEC-XML. Lediglich die Inhalte der Datei würden sich verlustfrei auch als VEC-XML ausdrücken lassen.

Dieser Unterschied ergibt sich im Wesentlichen durch zwei Dimensionen:

1. Der VEC hat einen deutlich größeren Scope. Insbesondere bietet der VEC die Möglichkeit, die Struktur eines Artikels zu definieren. Beispielsweise ist mit dem VEC eine detaillierte Abbildung von Komponentendaten möglich, zum Beispiel Aufbau und Eigenschaften von Leitungen, Informationen zu Kontakteilen, Ermittlung von, Kammerpositionen in Steckern usw. Die KBL beschränkt sich hier im Wesentlichen auf die Sachnummer der Komponente und ein paar einfache EigenschaftenEigenschaften, die auf einer klassischen Leitungssatzzeichnung zu erkennen sind, zum Beispiel Farbe und Querschnitt von Leitungen oder Farbe und Kodierung von Steckern. Insbesondere wurde beim Design des VECs Wert darauf gelegt immer eine Nachverfolgbarkeit zwischen den Informationen der verschiedenen Disziplinen der Bordnetzentwicklung (z.B. Geometrie, Elektrologik, E/E-Architektur) zu erreichen.
2. Die KBL wird konzeptionell nicht mehr weiterentwickelt. Auch im Kern des Scopes der KBL haben sich einerseits die Anforderungen an die Detailtiefe einer Leitungssatzbeschreibung geändert, andererseits sind aber auch neue Komponentenarten und Technologien hinzugekommen, bzw. haben Bedeutung gewonnen, zum Beispiel modulare Stecker, Stecker mit mehreren Bündelanschlusspunkten, Hochvolt-Anwendungen, komplexere Leitungen, mehrteiligen Kontaktierungssysteme. Diese Anforderungen sind bei der Entwicklung des VECs berücksichtigt worden, aber aus verschiedenen Gründen nicht mehr in die KBL eingeflossen (siehe Abschnitt [4.1.2](#mergeformat)).
   
### <a name="_ref171612214"></a><a name="_toc172726616"></a><a name="_toc174347907"></a>3.1.2 Lebenszyklus und industrieller Einsatz
Die KBL befindet sich derzeit im „Maintenance Modus“, d.h. Themen, die den derzeitigen industriellen Einsatz gefährden, werden behandelt, es findet allerdings keine aktive Umsetzung neuer Anforderungen und keine Erweiterungen des Scopes statt.

Der Grund hierfür ist, dass eine Erweiterung des Scopes der KBL bzw. auch die Umsetzung der neuen Anforderungen im Scope der KBL nicht möglich gewesen wäre, bzw. sehr starke Änderungen an verschiedensten Modellierungskonzepten erfordert hätte. Hierzu muss man sich auch vor Augen führen, dass der Kern der KBL-Modellierung inzwischen 25 Jahre alt ist und auf dem damaligen Wissen und den entsprechenden Anforderungen und Modellierungskonzepten basiert. Das Ergebnis dieses „Weiterentwicklungsprozesses“ wäre eine „neue“ KBL gewesen, die aus Gesichtspunkten der Rückwärtskompatibilität, Wiederverwendbarkeit von Schnittstellen-Implementierungen und Daten keinen Mehrwert gegenüber einem direkten Umstieg auf den VEC geboten hätte.

Aus diesem Grund haben die zuständigen Gremien entschieden, die verfügbaren Ressourcen auf eine Weiterentwicklung des VECs zu konzentrieren. Der VEC wird aktuell aktiv weiterentwickelt und neue Anforderungen umgesetzt.

Die KBL ist Stand heute das verwendete Standardformat an der Schnittstelle OEM / Konfektionär für die Spezifikation einzelner Leitungssätze. Zudem wird die KBL in verschiedenen Prozessen zum Austausch von Leitungssatz-Geometriendaten und in seltenen Fällen für Elektrologik verwendet. Bei diesen Anwendungen handelt es sich aber um Anwendungen, die nicht im Scope der KBL liegen und ein hohes Maß an proprietärer Interpretation erfordern.

Der VEC wird bei verschiedenen OEMs für die Bereitstellung von Kabelbaum-Komponentendaten verwendet. Außerdem gibt es im Einsatz befindliche Implementierungen für den Austausch von Geometrie und Systemschaltplandaten. Außerdem wird er von verschiedenen Unternehmen für die Bereitstellung eines „digitalen Zwillings“ des physischen Bordnetzes an Folgeprozess (z.B. Kundendienst) genutzt. Neue Umsetzungsprojekte kommen hinzu.

### <a name="_toc172726617"></a><a name="_toc174347908"></a>3.1.3 Abdeckung Anforderungen im Kontext VWS4LS
Im Kontext des Projekts VWS4LS gibt es verschiedene Anwendungsfälle bei denen VEC bzw. teilweise auch KBL in Frage kommen. Im Folgenden drei Beispiele:

- 1. Produktspezifikation Leitungssatz: Dieser Anwendungsfall ist grundsätzlich sowohl mit KBL als auch VEC abbildbar. Fraglich ist dabei aber, ob die KBL für Anwendungsszenarien die notwendige detailtiefe beinhaltet, zum Beispiel Kontaktierungssituationen an HV-Leitungen.
- 2. Bereitstellung von Komponentendaten: Zur Parametrisierung von Fertigungsprozessen sind detaillierte Informationen über Kabelbaumkomponenten notwendig, bspw. Terminalmaße oder Kammerkoordinaten in Steckern. Diese Information können nur mit dem VEC bereitgestellt werden.
- 3. Definition von Halbprodukten: Für eine Abbildung des Herstellungsprozesses ist die Definition von Halb-/Zwischenprodukten notwendig. , Bspw.beispielsweise eine geschnittene & abisolierte Leitung. Durch die flexiblere Modellierung können solche Produkte mit dem VEC abgebildet werden. Mit der KBL ist dies nicht immer möglich, oder nur durch sehr „individuelle“ Interpretation der Modellelemente.

### <a name="_toc172726618"></a><a name="_toc174347909"></a>3.1.4 Bewertung
Zusammenfassend lässt sich sagen, dass die KBL derzeit für die Beschreibung des Produkts „Leitungssatz“ aufgrund der längeren Historie und der Stabilität etablierter Prozesse die breitere Verwendung hat. Allerdings lassen sich gewisse Anwendungsfälle im Projektkontext mit der KBL gar nicht abbilden.

Der VEC hingegen ist aufgrund der Umsetzung neuer Anforderungen, sowohl fachlich wie auch technologisch (z.B. Unterstützung von Ontologien), der kontinuierlichen Weiterentwicklung und der zunehmenden Anzahl an Umsetzungen die Wahl der Zukunft.

Insgesamt bietet VEC eine fortschrittlichere Lösung für die Leitungssatzfertigung, während KBL aufgrund seiner weit verbreiteten Nutzung weiterhin relevant bleibt.

Beide Modelle haben ihre Vorzüge: KBL ist weit verbreitet und hat eine etablierte Position in der Branche, während VEC eine fortschrittlichere Architektur bietet. Nach eingehender Analyse im Projekt wurde daher entschieden, sowohl das KBL- als auch das VEC-Datenmodell zu unterstützen. 

## <a name="_toc172726619"></a><a name="_toc174347910"></a>3.2 ECLASS 
Zu Beginn des Projekts wurde festgehalten, dass der ECLASS-Standard auf seine Anwendbarkeit für das Projekt geprüft werden soll.  ECLASS [7] ist ein weit verbreitetes Klassifikationssystem für Produkte und Dienstleistungen, das in verschiedenen Branchen eingesetzt wird. Die Beschreibung von Leitungssätzen erfordert detaillierte Informationen über Steckverbinder, Leitungen, Verbindungen, Isolierungen und vieles mehr. ECLASS bietet zwar eine allgemeine Struktur und einige Definitionen mit Projektbezug (Auszüge siehe [Abbildung 4](#_ref174089187) und [Abbildung 5](#_ref174089392)), aber es fehlen spezifische Attribute und Klassen, die für die detaillierte Beschreibung von Leitungssätzen geeignet sind. 

![image](https://github.com/user-attachments/assets/e89dc987-a3f5-4d10-bd29-c0f0232240b1)

<a name="_ref174089187"></a><a name="_toc174347934"></a>*Abbildung 4: ECLASS-Klassifizierungen für KFZ-Bordnetze [7]** 

![image](https://github.com/user-attachments/assets/c607187a-c28b-4304-a719-63af08354e31)

<a name="_ref174089392"></a><a name="_toc174347935"></a>*Abbildung 5: ECLASS-Klassifizierungen für Produktionsmaschinen [7]**

Eine weitere Prüfung fand im TP6 “Automatisierte Verhandlungsprozesse“ statt. Dort wurde nach semantischen Referenzen für ein I4.0-Vokabular recherchiert, damit es sowohl von Menschen als auch Ressourcen interpretiert werden kann. Es wurde festgestellt, dass ECLASS derzeit keine ausreichende Überdeckung mit dem im Projekt benötigten Vokabular bietet. Um unternehmens- bzw. industrieübergreifende-Interoperabilität im Projektkontext zu erreichen, wurden daher die bereits vorhandenen semantischen Definitionen der anderen Standards als ausreichend betrachtet (OPC UA und VEC). 

Erwähnenswert in diesem Zusammenhang ist auch das „Common Data Dictionary“ der IEC [12], worin ebenfalls tendenziell für den Leitungssatz verwendbare Klassifizierungen definiert sind, z.B. „[0112/2///61360_4#AAA548 (car plug)](https://cdd.iec.ch/cdd/iec61360/iec61360.nsf/TU0/0112-2---61360_4%23AAA548)“ und [„0112/2///61360_4#AAA611 (connector tool)](https://cdd.iec.ch/cdd/iec61360/iec61360.nsf/TU0/0112-2---61360_4%23AAA611)“. 

## <a name="_toc174011907"></a><a name="_toc174011908"></a><a name="_toc172726620"></a><a name="_toc174347911"></a><a name="_ref175664225"></a><a name="_ref175664231"></a><a name="_ref175664280"></a>3.3 RAMI 4.0
Das Referenzarchitekturmodell Industrie 4.0 (kurz RAMI 4.0) ordnet verschiedene Aspekte der Produktion in einem einzigen Modell, bestehend aus einer mehrdimensionalen Struktur, die verschiedene Ebenen, Lebenszyklusphasen und Hierarchieebenen umfasst, um die Komplexität der Industrie 4.0 übersichtlich abzubilden. Es umfasst eine Kommunikationsebene, die Lebenszyklen von Anlagen und Produkten sowie Automatisierungs- und IT-Ebenen. RAMI 4.0 ist ein kubisches Schichtenmodell, das in der DIN SPEC 91345 [13] definiert ist. Die Dimensionen des Würfels beschreiben die Architektur von Assets, ihren Lebenszyklus und ihre Zuordnung zu Hierarchieebenen [8]. 

RAMI 4.0 ist gut geeignet als übergeordneter Referenzrahmen für die Klassifikation der zu erstellenden Lösungsbestandteile im VWS4LS-Projekt. Es wurde jedoch entschieden, es nicht im Projekt zu berücksichtigen, da damit personelle Ressourcen gebunden, aber kein direkter anwendungsbezogener Mehrwert entstehen würde. 

## <a name="_toc172726621"></a><a name="_toc174347912"></a>3.4 OPC UA
**OPC UA (Open Platform Communications Unified Architecture)** ist ein Standard für eine Kommunikationsarchitektur, die für den Datenaustausch als plattformunabhängige, service-orientierte Architektur (SOA) entwickelt wurde und nicht nur den Transport von Maschinendaten, wie Regelgrößen, Messwerte, Parameter etc. ermöglicht, sondern diese auch maschinenlesbar semantisch zu beschreiben. Dabei werden nicht nur Betriebsdaten berücksichtigt, sondern auch Spezifikationen und Fähigkeiten der beteiligten Maschinen. Das ermöglicht die Kommunikation zwischen Produktionssteuerungssystemen wie MES (Manufacturing Execution Systems) und den Produktionsanlagen [14].

Die OPC UA Technologie bietet grundlegende Bausteine, die eine einheitliche Basis für die Kommunikation und den Datenaustausch bereitstellen und eine einheitliche Beschreibung und Kommunikation zwischen verschiedenen Systemen ermöglicht. Einer dieser Bausteine ist bspw. das Typenschild (Machinery Nameplate) [15], um Informationen über die Maschine, ihre Funktionen und Eigenschaften bereitstellen zu können.

![image](https://github.com/user-attachments/assets/00511486-b155-45ed-83d9-43dba634e918)

<a name="_toc174347936"></a>*Abbildung 6: OPC UA Technologie (Quelle: VDMA)*

Im Bereich der Leitungssatzfertigung gab es bislang keine spezifische Standardisierung für OPC UA. Da die Anforderungen an die Beschreibung von Leitungssätzen komplex und spezifisch sind, würden die verfügbaren allgemeinen Companion Specifications [6] nur bedingt ausreichen. Deshalb wurde im Projekt die Entscheidung getroffen, eine Companion Specification speziell für die Leitungssatzfertigung zu entwickeln. 

Diese neue Companion Specification «OPC 40570: OPC UA for the Wire Harness Manufacturing Industry» [16] wird die spezifischen Anforderungen der Branche berücksichtigen und eine einheitliche Kommunikation zwischen den beteiligten Akteuren ermöglichen. 

Insgesamt ist OPC UA ein zentrales Element der Digitalisierung in der Fertigungsindustrie, und die Entwicklung einer spezifischen Companion-Spezifikation für die Leitungssatzfertigung wird die Interoperabilität und Effizienz weiter verbessern.

## <a name="_toc173858769"></a><a name="_toc172726624"></a><a name="_toc174347913"></a>3.5 Fazit
Im Projekt wurden wesentliche Schlüsselentscheidungen getroffen, um die Interoperabilität und Effizienz der innerhalb der Leitungssatzfertigung zu verbessern:

**Unterstützung von VEC und KBL**: VEC bietet im Vergleich zu KBL eine fortschrittlichere Architektur und ermöglicht eine umfassendere Produktbeschreibung, einschließlich Stücklisten und Verbindungsinformationen. Trotzdem wurde beschlossen, neben dem VEC- auch das KBL-Datenmodell zu unterstützen, da es bei mehreren OEMs etabliert ist und von bestehenden Systemen unterstützt wird.

**OPC UA als Kommunikationsstandard**: Während VEC und KBL als Modell für die statische Produktbeschreibung dient, soll OPC UA als Kommunikationsstandard die dynamische Interaktion der verschiedenen Systeme in der Leitungssatzfertigung ermöglichen, einschließlich <a name="_hlk173905965"></a>MES (Manufacturing Execution Systems) und Produktionsanlagen. Ausserdem soll OPC UA die Grundlage für die Prozess- und Ressourcendatenmodelle bilden. 

**Entwicklung einer Companion Specification**: Da es keine spezifische Standardisierung für die Leitungssatzfertigung in OPC UA gab, wurde beschlossen, eine Companion-Specification in Zusammenarbeit mit dem VDMA zu entwickeln. Diese Spezifikation wird die spezifischen Anforderungen der LS-Branche berücksichtigen und eine einheitliche Kommunikation ermöglichen.

**Fokus auf den Schneidraum**: Eine weitere Entscheidung bestand darin, den Fokus auf die Produktionsprozesse im Schneidraum zu legen. Hier werden die Kabelbäume zugeschnitten und vorbereitet, bevor sie in die Montage gehen.

**VWS-Datenmodell für den Leitungssatz**: VEC und KBL-Dateien sowie OPC UA Nodeset-Dateien sollen unverändert in die VWS eingehängt bzw. verlinkt werden.

Insgesamt zielen diese Entscheidungen darauf ab, die Leitungssatzfertigung effizienter und flexibler zu gestalten, um den Anforderungen der modernen Automobilindustrie gerecht zu werden. 

# <a name="_toc172726625"></a><a name="_toc174347914"></a>**4. AP 1.3 Erfassen der Geschäftsmodelle für das Informationsmodell**
Im Arbeitspaket 1.3 „Erfassen der Geschäftsmodelle für das Informationsmodell“ sollen die bestehenden Geschäftsmodelle und ihre wirtschaftlichen Auswirkungen untersucht werden, um festzustellen, wie sie effektiv in das Informationsmodell integriert werden können. Dabei werden sowohl kurzfristige als auch langfristige wirtschaftliche Aspekte berücksichtigt, um sicherzustellen, dass das Modell nachhaltig und zukunftsorientiert ist.

_**Es wurde die Entscheidung getroffen, AP 1.3 in das TP 7 zu überführen, um eine fokussierte und spezialisierte Behandlung des Themas Geschäftsmodelle zu gewährleisten, in enger Abstimmung mit den Anforderungen des Informationsmodells.**_

# <a name="_toc172726626"></a><a name="_toc174347915"></a>**AP 1.4 <a name="_hlk171932657"></a>5. Beschreibung der Tiefe der Informationsmodelle**
Das Arbeitspaket 1.4 „Beschreibung der Tiefe der Informationsmodelle“ beschäftigte sich mit der detaillierten Beschreibung von Informations- und Datenmodellen für die Leitungssatzfertigung. 

Ein modellbasiertes Engineering erfasst das Fachwissen durch Designregeln, um die Qualität des Produktes zu verbessern, die Effizienz der Produktion zu steigern, sowie den automatisierten Datenaustausch zu unterstützen. Das digitale Leitungssatz-Modell soll daher als Grundlage dienen, um automatisiert detaillierte Arbeitsanweisungen zu generieren und eine präzise und effiziente Produktion in der Leitungssatzfertigung zu ermöglichen.
## <a name="_toc172726627"></a><a name="_toc174347916"></a>5.1 Grundlagen
Die Entwicklung des Leitungssatzes erfolgt durch den OEM (Original Equipment Manufacturer), typischerweise unter Verwendung der etablierten Modellierungsstandards KBL (Kabelbaumliste) und VEC (Vehicle Electric Container).

![image](https://github.com/user-attachments/assets/e9a11a7a-63f4-48db-8800-611f5c372492)

<a name="_toc174347937"></a>*Abbildung 7: Leitungssatzarchitektur. (Quelle: Eigene Darstellung)*

Der vom OEM auf dieser Basis bereitgestellte sog. „150%-Leitungssatz“ umfasst alle möglichen Varianten für den Leitungssatz einzelner Fahrzeugmodelle. Berücksichtigt wird dabei nicht nur die Standardkonfiguration, sondern auch zusätzliche Optionen und Ausstattungsvarianten. Diese umfassen unterschiedliche Motorisierungen, Sonderausstattungen, Länderanforderungen und individuelle Kundenwünsche. Das Ergebnis ist ein umfassendes Modell, das mehr Variationen umfasst, als jemals in einem einzigen real gefertigten Leitungssatz (in Abgrenzung dazu auch als sog. „100% Leitungssatz“ bezeichnet) enthalten sein können.

Diese Vielfalt führt zu der Notwendigkeit, für reale Modellkonstellationen dedizierte Produktionsaufträge ausleiten zu können. Jedes Fahrzeugmodell erfordert spezifische Leitungssatzvarianten, die auf individuellen Konfigurationen basieren. Diese müssen präzise hergestellt werden, um sicherzustellen, dass alle Komponenten korrekt verdrahtet sind [7].

Der Produktionsprozess besteht aus folgenden wesentlichen Bestandteilen:

1. **Leitungssatzentwurf durch den OEM:**
- Der OEM erstellt das Leitungssatzdesign mithilfe von CAD-Systemen und CAE-Tools.
2. **Extraktion der Produktionsinformationen:**
- Der Leitungssatzhersteller extrahiert aus dem OEM-Design die Informationen, die für die Herstellung jedes Leitungssatzes erforderlich sind. Dies umfasst Details zu Steckern, Kabeln, Längen, Verbindungen und Positionen.
- Die Daten werden in einem strukturierten Format gespeichert, um die Produktion effizient zu steuern. 
3. **Verteilung der Produktionsaufträge:**
- Der Hersteller verteilt die Produktionsaufträge auf die jeweiligen Maschinen für die verschiedenen Fahrzeugmodelle.
- Jeder Leitungssatz wird gemäß den spezifischen Anforderungen für das jeweilige Fahrzeugmodell hergestellt.
4. **Senden eines Produktionsauftrags an eine Maschine:**
- Die Maschinen erhalten die erforderlichen Informationen, z. B. Kabeltyp, Länge, Verbindungen und Positionen.
- Zu Übermittlung der Produktionsaufträge an die Maschinen wird OPC UA verwendet.
5. **Datenerfassung über die produzierte Charge:**
- Während der Produktion werden Daten wie Produktionszeit, Materialverbrauch und Qualitätsprüfungen erfasst.
- Der digitale Zwilling des Produkts (VWS) wird mit diesen Daten angereichert, zentral abgelegt gespeichert und kann für Rückverfolgbarkeit und Qualitätskontrolle genutzt werden.
6. **Montage und Endprüfung des Leitungssatzes:**
- Nach der Produktion der Einzelkomponenten werden die Leitungssätze montiert und auf ihre korrekte Verdrahtung überprüft, um die Qualität sicherzustellen und mögliche Fehler zu identifizieren.
- Die Endprüfung umfasst elektrische Tests, Widerstandsmessungen und Funktionsüberprüfungen.
- Der digitale Zwilling des gefertigten Endprodukts wird um diese Qualitätssicherungsdaten angereichert.

## <a name="_toc172726628"></a><a name="_ref173142594"></a><a name="_ref173142598"></a><a name="_toc174347917"></a>5.2 Prozessliste und Parameter
Im TP 3 wurden verschiedene Analyseaktivitäten durchgeführt, um eine Liste der Produktionsprozesse und ihrer Parameter zu erstellen. Schließlich wurden spezifische Kategorien erstellt, um diese Parameter zu gruppieren und den Produktionsprozess effizient zu gestalten. Es wurde ein detailliertes Prozess- und Parametermodell definiert, um die verschiedenen Produktionsprozesse und Parameter effizient und einheitlich verwalten zu können. Hierfür wurde zunächst jedem identifizierten Produktionsprozess eine eindeutige Bezeichnung sowie eine Beschreibung hinterlegt. Anschließend wurde jedem Prozess ein verantwortlicher Konsortialpartner zugewiesen, dessen Aufgabe darin bestand, die relevanten Prozessparameter nach Folgendem Schema zu definieren:

- **Name**: Ein eindeutiger und leicht verständlicher Name für den Parameter.
- **Einheit**: Die Maßeinheit des Parameters (Meter, Kilogramm, Sekunden, etc.).
- **Anforderungsgrad**: Definiert, inwiefern ein Parameter für den jeweiligen Prozess erforderlich (mandatorisch) oder optional ist.
- **Datentyp**: Der Datentyp des Parameters (Zahl, Text, Boolean, etc.)
- **Beschreibung**: Eine kurze Beschreibung des Parameters, die dessen Bedeutung und Verwendungszweck im Kontext des Produktionsprozesses erklärt.

Die so angereicherten Parameterdefinitionen wurden in die Prozessparameterliste übertragen und von allen Konsortialpartnern überprüft und validiert, um sicherzustellen, dass alle Definitionen korrekt und konsistent sind.

Nach der Validierung und Finalisierung wurden alle erfassten Prozesse und Prozessparameter an die den VDMA XE "VDMA"  zur Integration in die Companion Specification «OPC UA for the Wire Harness Manufacturing Industry» (VDMA 40570) [16] weitergegeben.

## <a name="_toc174347918"></a>5.3 Produktionsdatensatz
Ein Datensatz für die Produktion besteht aus 5 Prozessdatenbausteinen (siehe [Abbildung 8](#_ref174346634)). Prozesse können von der Montage über das Crimpen bis hin zu Tests und Qualitätskontrollen reichen. Jeder dieser Prozesse muss klar definiert und dokumentiert sein, um eine effiziente und fehlerfreie Produktion zu gewährleisten. Nach Abschluss der Produktion wird für jeden Prozess ein Satz von Resultaten zurückgeliefert, welche die Qualität und Genauigkeit jedes einzelnen Schrittes im Produktionsprozess widerspiegeln.

![image](https://github.com/user-attachments/assets/c9697d3a-8066-495e-bc19-a473b99a8af2)

<a name="_ref174346634"></a><a name="_toc174347938"></a>*Abbildung 8: WireHarness Data Domains (Quelle: Eigene Darstellung)*

Um eine Arbeitsauftragsanforderung (Job Order Request) für einen Fertigungsauftrag zusammenzustellen ([Abbildung 9](#_ref174345828)), muss als Voraussetzung eine Artikelspezifikation gemäß dem VEC-Standard vorliegen, welcher eine einheitliche Beschreibung von Fahrzeugelektronikkomponenten erlaubt und somit die Kommunikation und den Datenaustausch zwischen verschiedenen Systemen und Partnern in der Automobilindustrie ermöglicht.

Zusätzlich zur Artikeldefinition muss die Spezifikation eine Liste von Teilen enthalten, die für die Produktion benötigt werden. Dazu gehören beispielsweise Anschlüsse, Kabel, Dichtungen und weitere relevante Komponenten. 

![image](https://github.com/user-attachments/assets/d30ef32d-56ab-401e-a6a9-dc9fadc417c4)

<a name="_ref174345828"></a><a name="_toc174347939"></a>*Abbildung 9: JobOrder Request [16]**

Neben der Teileliste ist auch eine Liste der durchzuführenden Prozesse erforderlich. Ein solcher Datensatz für die Produktion besteht aus 5 Prozessdatenbausteinen (siehe [Abbildung 8](#_ref174346634)). Die Prozesse können von der Montage über das Crimpen bis hin zu Tests und Qualitätskontrollen reichen. Jeder dieser Prozesse muss klar definiert und dokumentiert sein, um eine effiziente und fehlerfreie Produktion zu gewährleisten. Nach Abschluss der Produktion wird für jeden Prozess ein Satz von Resultaten zurückgeliefert. Diese Ergebnisse sind von entscheidender Bedeutung, da sie die Qualität und Genauigkeit jedes einzelnen Schrittes im Produktionsprozess widerspiegeln.

Schließlich wird eine Arbeitsantwort erstellt, die eine Zusammenfassung der Produktionsergebnisse enthält. Diese Zusammenfassung bietet einen Überblick über die durchgeführten Arbeiten und die erreichten Ergebnisse. Sie dient als Nachweis (sog. „Audit Trail“) für die Einhaltung der Spezifikationen und als Qualitätsdokumentation. Die Arbeitsantwort ist somit ein wesentlicher Bestandteil des gesamten Produktionsprozesses und ermöglicht eine kontinuierliche Verbesserung und Optimierung der Arbeitsabläufe.

<a name="_toc172726629"></a>
## <a name="_toc174347919"></a><a name="_ref174348506"></a><a name="_ref174348579"></a>5.4 VEC als Produktdatenmodell
[Abbildung 10](#_ref173157831) skizziert die Nutzung des VEC-Modells im Kontext des Projekts. Jede Komponente, Terminal, Wire, Connector usw. kann mit ihren technischen Attributen im VEC-Modell beschrieben werden. Unter Verwendung dieser Komponenten wird dann eine Artikelbeschreibung aufgebaut, wobei dabei jede einzelne Verwendung greifbar sein muss, da diese einerseits unterschiedliche Eigenschaften erhalten können, vergleiche bspw. die *StrippingLength* in der Grafik, oder die Länge der Leitungen. Anderseits unterscheiden die Verwendung sich im Beziehungsgeflecht, das diese mit anderen Komponenten eingehen. Vergleiche bspw. Terminal „X“ an roter bzw. grüner Leitung.

Diese Artikelbeschreibung stellt dann das Grundgerüste für weitere Informationsinhalte dar. Diese können die Elemente der Artikelbeschreibung aus als Bezugspunkte nutzen. Beispielsweise kann die Definition von Fertigungsprozessen darüber eindeutig definieren für welches Element ein bestimmter Prozess gilt, also welche Leitung geschnitten werden soll, oder welche Leitungsende in einem Schritt abisoliert werden muss.

![image](https://github.com/user-attachments/assets/6acdb21d-323c-4405-9bfe-c94ddaac0a07)

<a name="_ref173157831"></a><a name="_toc174347940"></a>*Abbildung 10: Nutzung des VEC-Modells (Quelle: Eigene Darstellung)*

Da der VEC den kompletten Entwicklungsprozess des physischen Bordnetzes unterstützt ist das Modell sehr umfangreich. Für die im Projekt relevanten Anwendungsfälle werden lediglich die Bereiche „Komponentenbeschreibung“ und „Leitungssatzdefinition“ benötigt.

Wie in den vorhergehenden Abschnitten beschrieben besteht ein Datensatz für die Produktion aus 5 Prozessdatenbausteinen (siehe [Abbildung 8](#_ref174346634)). Die Bausteine „Article“ und „Parts“ liegen dabei im Kern des Scopes des VEC (siehe [Abbildung 11](#_ref173873644) mit dem Beispiel eines Kontaktteils). 

![image](https://github.com/user-attachments/assets/804b5044-aa64-48af-adf7-da87a3eb0615)

<a name="_ref173873644"></a><a name="_toc174347941"></a>*Abbildung 11: Beispiel VEC Terminal Datamodell (Quelle: VEC Recommendation V2.1)*

Eine erste Bewertung der benötigten Parameter (siehe „[6.2](#_ref173142594) [Prozessliste und Parameter](#_ref173142598)“) ergab eine hohe Abdeckung der benötigten Informationen durch den VEC, und zwar sowohl für den Bereich „Parts“ als auch für den Bereich „Article“. 

Eine Artikeldefinition ist mit der KBL ebenfalls grundsätzlich möglich, aber es fehlen verschiedenste Attribute, die im Kontext der Fertigung relevant sind (z.B. Abisolierlängen an Leitungsenden). Da der VEC derartige Attribute bereits enthält, wurde im Weiteren der Fokus auf den VEC gelegt, insbesondere für die Demonstratoren und die OPC UA Integration.

Im Rahmen des Projekts wurden für Parameter, die im VEC-Modell als fehlend identifiziert wurden, eine Reihe von Feature-Requests) an den VEC gestellt (siehe [Abbildung 12](#_ref174022396) und dort zum heutigen Zeitpunkt auch bereits weitestgehend in der aktuellen Version 2.1.0 umgesetzt [17]:

- - Identifikation von Werkzeugen für Komponenten.
- - Attribute für Schläuche die in der Verwendung geschlitzt werden.
- - Verschiedenste Parameter für die Beurteilung von Crimps (z.B.: Crimp-Höhe & Breite am Kontaktteil parametrisiert, Abzugskräfte, Crimp-Höhe und Breite in einer konkrete Verwendung)
- - Parameter zur Behandlung von Leitungsenden.
- - Parameter zur automatischen Bestückung von Gehäusen (z.B. Kammerkoordinaten, Einstecktiefe & anwendbare Kräfte).

![image](https://github.com/user-attachments/assets/6ce1c567-d881-4a38-91d8-52ec76778da6)

<a name="_ref174022396"></a><a name="_toc174347942"></a>*Abbildung 12: Feature Requests an den VEC*

## <a name="_toc173858778"></a><a name="_toc173858779"></a><a name="_toc173858780"></a><a name="_toc173858781"></a><a name="_toc173858782"></a><a name="_toc172726631"></a><a name="_ref173161462"></a><a name="_toc174347920"></a>5.5 OPC UA Schnittstelle
OPC UA hat für die unterschiedlichsten Anwendungsfälle eine Reihe von sog. Companion Specifications veröffentlicht [6], von denen einige möglicherweise eine vielversprechende Basis für die im Leitungssatz-Kontext zu lösenden Herausforderungen darstellen ([Abbildung 13](#_ref174019934)). 

![image](https://github.com/user-attachments/assets/d580499a-d4cf-4863-934d-af255b9de39c)

<a name="_ref174019934"></a><a name="_toc174347943"></a>*Abbildung 13: Relevante OPC UA Spezifikationen (Quelle: Eigene Darstellung)*

Die folgenden OPC UA Companion Specifications wurden als geeignete Basis für die VWS4LS-Anwendungsfälle identifiziert:

«**OPC 40001-1 Machinery Basic Building Blocks**» [15]

«**OPC 40001-3: Machinery Job Mgmt**» [18]

«**OPC 40001-101: Machinery Result Transfer**» [19]

«**OPC 10031-4: ISA-95-4 Job Control**» [20]

Für die in [Abbildung 13](#_ref174019934) aufgeführten fiktiven **«OPC UA Article»** und **«OPC UA Material»** wurden in der Folge dedizierte Lösungen erarbeitet. 

Für eine effektive Kommunikation mit der Maschinerie über eine OPC UA-Schnittstelle müssen bestimmte Datencontainer spezifiziert werden:

**Identification**: Enthält Informationen zur Identifizierung der Leitungssatzmaschine.

**MachineryItemState**: Zeigt den aktuellen Zustand der Leitungssatzmaschine an.

**MachineryOperationMode**: Gibt die Art der von der Maschine durchgeführten Aufgaben an.

**JobManagement**: Beinhaltet Informationen und Methoden, die sich auf die Aufträge beziehen. Dies umfasst die Zustände der aktuellen Aufträge und Methoden zum Einfügen, Entfernen, Freigeben und Unterbrechen eines Auftrags.

**ResultManagement**: Ist der Einstiegspunkt für das Ergebnismanagement, d.h. die Behandlung der Arbeitsantworten (JobResults).

**MaterialManagement**: Enthält Informationen und Methoden, die sich auf das Material beziehen (z.B. materialbezogene Prozesswerte). Dies umfasst die Zustände des aktuellen Materials, das von der Maschine bekannt ist, und Methoden zum Einfügen und Entfernen von Material.

**ArticleManagement**: Beinhaltet Informationen und Methoden, die sich auf den Artikel beziehen (z.B. materialbezogene Prozesswerte). Dies umfasst die Zustände des aktuellen Materials, das von der Maschine bekannt ist, und Methoden zum Einfügen und Entfernen eines Artikels.

### <a name="_toc172726632"></a><a name="_toc174347921"></a>5.5.1 Identifikation
Die OPC UA Companion Specification «**OPC 40001-1 Machinery Basic Building Blocks**» [15] dient zur Kommunikation zwischen Maschinen (M2M) und mit übergeordneten Systemen der Industrie 4.0 (z.B. MES) und unterstützt die folgenden Anwendungsfälle:

**Maschinenidentifikation und Typenschild:** Jede Maschine hat eine eindeutige Identifikation und ein Typenschild, die in einem OPC UA Server repräsentiert werden. Diese Informationen enthalten wichtige Details wie den Maschinentyp, das Modell, den Hersteller, das Herstellungsdatum und andere spezifische Informationen, die eine genaue Identifizierung und Klassifizierung der Maschine ermöglichen.

![image](https://github.com/user-attachments/assets/823bd896-86e3-4c52-96d4-e44cca82819b)

<a name="_toc174347944"></a>*Abbildung 14: MachineIdentificationType. (Quelle: OPC UA for Machinery [15]*)*

**Finden aller Maschinen in einem Server:** OPC UA ermöglicht es, alle Maschinen in einem Server zu finden. Dies ist besonders nützlich in großen industriellen Umgebungen, wo Hunderte oder sogar Tausende von Maschinen vorhanden sein können. Durch die Verwendung von OPC UA können Benutzer schnell und effizient alle Maschinen in einem Server lokalisieren und identifizieren.

**Komponentenidentifikation und Typenschild:** Ähnlich wie bei der Maschinenidentifikation hat auch jede Komponente einer Maschine eine eindeutige Identifikation und ein Typenschild. Diese enthalten Informationen wie den Komponententyp, das Modell, den Hersteller und andere spezifische Details. Dies ermöglichen eine genaue Identifizierung und Klassifizierung der Komponenten.

**Finden aller Komponenten einer Maschine:** Mit OPC UA können Benutzer alle Komponenten einer bestimmten Maschine finden. Dies ist besonders nützlich für die Wartung und Fehlerbehebung, da es ermöglicht, schnell die spezifischen Komponenten zu identifizieren, die gewartet oder ersetzt werden müssen.

**Maschinenüberwachung:** Durch die kontinuierliche Überwachung der Maschinenleistung und des Betriebszustands mittels OPC UA können Benutzer potenzielle Probleme frühzeitig erkennen und proaktiv Massnahmen ergreifen, um Ausfallzeiten zu vermeiden und die Effizienz zu verbessern.

![image](https://github.com/user-attachments/assets/f105eb83-491e-4509-b956-ef0d9c641482)

<a name="_toc174347945"></a>*Abbildung 15: MachineryItemState. (Quelle: OPC UA for Machinery [15]*)*

### <a name="_toc172726633"></a><a name="_toc174347922"></a>5.5.2 Job Management
Die OPC UA Companion Specifications «**OPC 10031-4: ISA-95-4 Job Control**» [20] und «**OPC 40001-3: Machinery Job Mgmt**» [18] ermöglichen eine standardisierte Verwaltung von Arbeitsaufträgen innerhalb von Maschinen und Anlagen (vgl. [Abbildung 9](#_ref174345828)). Im Folgenden sind einige Kernelemente beschrieben.

#### 5.5.2.1 ISA95JobOrderReceiverObjectType
Als Kernelement enthält *ISA95JobOrderReceiverObjectTyp* die Methoden zur Entgegennahme von Arbeitsaufträgen und optionale Definitionen zulässiger Arbeitsauftragsinformationen.

Dieser Objekttyp definiert die Metadaten der Zustandsmaschine für die verwalteten Arbeitsaufträge. Arbeitsaufträge werden dem System hinzugefügt, indem die Methoden *Store* oder *StoreAndStart* aufgerufen werden, woraufhin der Arbeitsauftrag in den Zustand *NotAllowedToStart* oder *AllowedToStart* versetzt wird. In beiden Zuständen wird der Arbeitsauftrag noch nicht ausgeführt. Durch Aufrufen der *Update*-Methode kann der Arbeitsauftrag noch geändert werden. Der Start eines Arbeitsauftrags wird durch die *Start*-Methode ausgelöst, die den Zustand von *NotAllowedToStart* zu *AllowedToStart* wechselt.

1. #### 5.5.2.2 ISA95JobResponseProviderObjectType
Ein weiterer wichtiger Bestandteil ist der *ISA95JobResponseProviderObjectType*, welcher eine Methode zur Entgegennahme von unaufgeforderten Arbeitsantwortanfragen beinhaltet. Dies ermöglicht es, auf eine Arbeitsauftragsanfrage zu reagieren und eine entsprechende Antwort zu generieren. Die Kombination des *ISA95JobOrderReceiverObjectType* mit der *ReceiveJobOrder*-Methode und des *ISA95JobResponseProviderObjectType* mit der *RequestJobResponse*-Methode bildet eine Transaktion, die es ermöglicht, einen Arbeitsauftrag zu senden und nach einer Arbeitsantwort zu fragen.

Die Spezifikation definiert auch den *ISA95JobOrderStateMachineType*, der die Untertypen der Zustände *NotAllowedToStart*, *AllowedToStart*, *Ended* und *Interrupted* definiert. Diese Zustände und Übergänge sind entscheidend für das Verständnis, wie Arbeitsaufträge im System hinzugefügt, ausgeführt und entfernt werden. Die Zustandsmaschine bietet eine klare Struktur, die es ermöglicht, den Lebenszyklus eines Arbeitsauftrags von der Erstellung bis zur Fertigstellung zu verfolgen.

1. #### 5.5.2.3 JobOrderList
Die *JobOrderList* definiert eine schreibgeschützte Liste von Jobauftragsinformationen, die vom Server verfügbar sind. Die zurückgegebenen Informationen werden vom Server definiert und können eine vollständige Kopie eines empfangenen Jobauftrags sein oder lediglich die IDs und den Status der Jobaufträge enthalten. Sollten keine Jobaufträge vom Server verfügbar sein, kann dieser Wert auch null sein.

1. #### 5.5.2.4 WorkMaster
Der *WorkMaster* definiert einen schreibgeschützten Satz von *WorkMaster*-IDs, die in einem Jobauftrag angegeben werden können, sowie den schreibgeschützten Satz von Parametern, die für einen bestimmten *WorkMaster* festgelegt werden können. Falls es keine Einschränkungen gibt, welche *WorkMaster*-IDs mit einem Jobauftrag gesendet werden können, kann dieser Wert ebenfalls *NULL* sein.

Rezepte, die mit dem Jobauftrag verbunden sind, werden unter Verwendung der *WorkMasterID* identifiziert. Die ID im *ISA95WorkMasterDataType* ist eine Identifikation des Work Masters und kann interne Identifikationen, OPC UA Node-IDs, Web-Links oder ein zwischen Client und Server vereinbartes Format sein. Diese Strukturen ermöglichen eine flexible und effiziente Verwaltung von Arbeitsaufträgen und Ressourcen in industriellen Automatisierungssystemen und unterstützen die Integration von Produktionsprozessen mit der Unternehmens-IT.
### <a name="_toc172726634"></a><a name="_toc174347923"></a>5.5.3 Material und Artikel Management
Teile und Artikel innerhalb dieser Begleitspezifikation setzen sich aus Strukturen von zwei verschiedenen Quellen zusammen: dem ISA-95 Materialmodell, welches für die allgemeine Verwendung vorgesehen ist, und dem domänenspezifischen VEC (Vehicle Electric Container) Modell (vgl. [6.4](#_ref174348579)). Diese wurden in die Begleitspezifikation integriert. Folglich bestehen sowohl Teil als auch Artikel immer aus zwei Segmenten: der generischen Komponente, die vom ISA-95-Modell abgeleitet ist, und dem Leitungssatzspezifischen Element aus dem VEC-Modell.

Das ISA-95 Materialmodell bietet eine umfassende Struktur zur Darstellung von Materialien und deren Eigenschaften, die in verschiedenen Industrien und Anwendungen genutzt werden können. Es ermöglicht eine einheitliche Beschreibung von Materialien, unabhängig von der spezifischen Anwendung oder dem Sektor. Dieses Modell ist besonders nützlich, um die Kompatibilität und Interoperabilität zwischen verschiedenen Systemen und Organisationen zu gewährleisten.

Das VEC-Modell hingegen ist speziell auf die Anforderungen der Fahrzeugelektrik und des Leitungssatzes zugeschnitten. Es berücksichtigt die einzigartigen Eigenschaften und Anforderungen, die mit der elektrischen Verkabelung von Fahrzeugen verbunden sind. Durch die Integration dieses Modells in die Begleitspezifikation wird sichergestellt, dass die spezifischen Bedürfnisse dieses Bereichs angemessen adressiert werden.

Durch die Zweiteilung der Struktur in ein generisches und ein spezifisches Segment können Anwender der Begleitspezifikation die Vorteile beider Modelle nutzen. 

Um die Informationsbausteine „Parts“ und „Article“ aus dem VEC-Modell für die OPC UA Schnittstelle zu verwenden, muss keine neue Modellierung für diese Aspekte entwickelt, sondern kann die Modellierung des VECs wiederverwendet werden. Die OPC UA definiert allerdings eine eigene Beschreibungssprache für Daten, das sog. „OPC UA Nodeset“ [21]. Um hier eine gute Integration zu erreichen und Entwickler von OPC UA Schnittstellen davon zu entlasten zwei unterschiedliche Datenformate verstehen zu müssen, erfolgte die Integration des VEC-Models nicht mittels der veröffentlichten XML Schema Repräsentation. Stattdessen wurde eine Transformation in Form eines XSLT-Skripts entwickelt [22], die das als XMI vorliegende VEC-Model gemäß definierter Regeln in ein OPC UA Nodeset umwandelt. Gleichzeitig wird dabei das Modell auf die für den Scope der OPC UA Schnittstelle relevanten Klassen heruntergefiltert.
### <a name="_toc172726635"></a><a name="_toc174347924"></a>5.5.4 ResultManagement
Im speziellen Kontext von «OPC 10031-4: ISA-95-4 Job Control» [20] werden Ergebnisse von Produktionsprozessen erfasst, überwacht und analysiert. Dies umfasst Aspekte wie Qualitätsprüfungen, Materialdaten, Produktionsstatistiken und vieles mehr. Dazu gibt es zwei Arten von Prozessparametern 

\- Die sog. **Validierung** überprüft stichprobenhaft (z.B. einmal am Anfang einer zu fertigenden Charge), ob ein Produkt den Anforderungen entspricht, da manche Validierungsmethoden zerstörerisch sind, so dass die geprüften Teile nicht weiterverwendet werden können. Ein Beispiel hierfür ist die Crimpzugkraft, die sicherstellt, dass eine Verbindung dauerhaft hält.

\- Die sog. **Überwachung** hingegen ist eine fortlaufende Qualitätssicherung, die für jedes produzierte Exemplar sicherstellt, dass die Produktionsstandards eingehalten werden. Die Crimpkraftanalyse („Crimp Force Analysis“, CFA) ist ein Beispiel für die fortwährende Überwachung einer Prozesseigenschaft bei der Herstellung von Crimpverbindungen.

Beide Prozesse sind entscheidend, um die Sicherheit und Zuverlässigkeit der Produkte zu gewährleisten.

Ein typischer Variablenbedarf wird wie folgt exemplarisch ermittelt: Vor der Produktion einer Charge von Kabeln wird ein Validierungsprozess durchgeführt, um sicherzustellen, dass die Spezifikationen eingehalten werden. Dieser Prozess beinhaltet die Überprüfung der Crimphöhe gemäss den festgelegten Variablen in der Artikelbeschreibung

- In der Artikelspezifikation wird eine Variable *CheckCrimpHeight* festgelegt, die bestimmt, dass die Crimphöhe überprüft wird.

- Die Spezifikation der Teile enthält die Maße und Toleranzen für die Produktion, z.B. die *NominalCrimpHeight*.

- Eine dritte Variable mit dem Namen *ActualCrimpHeight* wird verwendet, um die an einem bestimmten Kontaktpunkt gemessenen Werte zurückzugeben.

Nach der Validierung werden die tatsächlichen Werte für die Crimphöhen durch die Variable *ActualCrimpHeight* erfasst und zur weiteren Analyse zurückgegeben.

«OPC 40001-101 Machinery Result Transfer» [19] befasst sich mit dieser Übertragung von Ergebnissen und bietet Mechanismen zur Verwaltung und Übertragung von Produktionsdaten.

## <a name="_toc172726636"></a><a name="_toc174347925"></a>5.6 Fazit
Im Rahmen von AP XE "AP"  1.4 erfolgte eine intensive Auseinandersetzung mit der Tiefe der Informationsmodelle, um sicherzustellen, dass alle relevanten Daten und Informationen erfasst und in der erforderlichen Detailtiefe definiert sind. Ein Hauptaugenmerk lag dabei auf den bestehenden Standards VEC XE "VEC"  und OPC UA XE "OPC UA"  und die Granularität ihrer jeweiligen Datenstrukturen.

Während dieser Analyse haben sich einige Anpassungen und Erweiterungen an den bestehenden Standards herauskristallisiert, um die spezifischen Anforderungen der Kabelbaumindustrie zu erfüllen.

Änderungsvorschläge am VEC, um die vorhandenen Strukturen zu optimieren und die Datenrepräsentation zu verfeinern, wurden beim zuständigen Gremium eingereicht und dort zum heutigen Zeitpunkt auch bereits zu großen Teilen umgesetzt [17].

Eine Reihe von existierenden OPC UA Companion Specifications wurde las als geeignete Basis für die Anforderungen der Leitungssatz-Industrie identifiziert, bspw. «OPC 40001-1 Machinery Basic Building Blocks» [15] für die Maschinenidentifikation und die “OPC 40001-3: Machinery Job Mgmt» [18], «OPC 10031-4: ISA-95-4 Job Control» [20] und «OPC 40001-101 Machinery Result Transfer» [16] als Grundlage für die Verwaltung von Arbeitsaufträgen in der Fertigungsindustrie. Deshalb wurde darauf aufbauend in Kooperation mit dem VDMA die OPC UA Companion Specification «OPC 40570: OPC UA for the Wire Harness Manufacturing Industry» [16] definiert. 

Das Ziel dieser Spezifikation ist es, alle relevanten Aspekte und Anforderungen der Kabelbaumindustrie abzudecken und somit eine Grundlage für die Implementierung und Nutzung von OPC UA zu schaffen. Sie dient zudem als Bindeglied für die Anwendung der Verwaltungsschale und dem interoperablen Datenverkehr zwischen Ressourcen und Steuerungssystemen. 

Durch die enge Zusammenarbeit mit der dem VDMA und die Integration der Erkenntnisse in die OPC UA Spezifikation wurde ein nachhaltiger Beitrag geleistet, die Industrie 4.0-Vision in der Kabelbaumindustrie voranzutreiben und eine effiziente, standardisierte Kommunikation und Datenverarbeitung in diesem Bereich zu ermöglichen.

# <a name="_toc172726637"></a><a name="_toc174347926"></a>**6. AP 1.5 - Validierung der Standards**
Arbeitspaket 1.5 „Validierung der Standards“ sollte sich mit der Analyse der Informationsmodelle der bestehenden Standards beschäftigen, um sicherzustellen, dass alle relevanten Daten und Informationen erfasst und in der erforderlichen Detailtiefe definiert sind.  Die detaillierten Ergebnisse der Analyse wurden zur besseren Verständlichkeit des Dokuments bereits im Kapitel 3 beschrieben, hier nochmals eine Zusammenfassung der Resultate. Ein Hauptaugenmerk lag auf KBL, VEC und OPC UA und die Granularität ihrer jeweiligen Datenstrukturen. Insbesondere wurden in diesem AP die folgenden Beiträge erarbeitet:

**KBL und VEC**: Die bestehenden Datenmodelle wurde analysiert und für den VEC entsprechende Anpassungen und Erweiterungen vorgenommen [17], um es besser auf die Bedürfnisse der Leitungssatzindustrie abzustimmen. Diese Anpassungen umfassen sowohl strukturelle als auch funktionale Verbesserungen, um die Genauigkeit der Datenmodellierung zu erhöhen ([Abbildung 12](#_ref174022396)). Dadurch ist das VEC-Datenmodell in der aktuellen Version 2.1.0 [23] noch leistungsfähiger und anwendungsfreundlicher geworden.** Ergänzend wurde beschlossen, neben dem VEC- auch das KBL-Datenmodell zu unterstützen, da es bei mehreren OEMs etabliert ist und von bestehenden Systemen unterstützt wird.

**OPC UA:** Bestehende Bausteine wie «OPC 10031-4: ISA-95-4 Job Control» [20], «OPC 40001-3 Machinery Job Mgmt» [18] und «OPC 40001-101 Machinery Result Transfer» [16] wurden analysiert und als solide Grundlage identifiziert für die Entwicklung der neuen Companion Specification «OPC 40570: OPC UA for Wire Harness Manufacturing» [16]. Der Standard «OPC 40001-1 Machinery Basic Building Blocks» [15] bietet grundlegende Bausteine für die Maschinenidentifikation, die Überwachung von Maschinenzuständen und die präventive Wartung. Diese Bausteine ermöglichen eine einheitliche und strukturierte Darstellung von Maschineninformationen, was die Interoperabilität und Integration verschiedener Maschinen und Systeme erleichtert. «OPC 40001-3 Machinery Job Mgmt» [18] definiert die Bausteine für die Ausführung und Steuerung von Arbeitsaufträgen. Es umfasst die Verwaltung von Jobaufträgen, die Definition von Jobparametern und die Rückmeldung von Jobergebnissen, was eine effiziente Planung und Durchführung von Produktionsprozessen ermöglicht. Der Standard «OPC 40001-101 Machinery Result Transfer» [19] befasst sich mit der Übertragung von Ergebnissen und bietet Mechanismen zur Verwaltung und Übertragung von Produktionsdaten. Gemeinsam mit dem VDMA wurde im TP1 neue Companion Specification «OPC 40570: OPC UA for the Wire Harness Manufacturing Industry» [16] erarbeitet, um einen einheitlichen Standard für die Kommunikation und Interaktion zwischen verschiedenen Systemen in der Leitungssatzindustrie zu etablieren, was wiederum zu einer Umsetzung von Industrie 4.0 in Richtung einer vernetzten und intelligenten Fertigung in diesem Bereich beiträgt.

**Weiterentwicklung der VWS:** Für die VWS wurde ein Konzept definiert, welches den Austausch von Informationen zwischen Produktionsunternehmen in der Leitungssatzindustrie ermöglicht. Die VWS nutzt dabei die in TP1 erarbeiteten und verbesserten Datenmodelle von VEC, OPC UA und ECLASS, um eine effiziente, modulare und standardisierte Kommunikation und Datenverarbeitung zu gewährleisten. Daraus wurden Initiativen für neue Submodelle abgeleitet und in den entsprechenden Teilprojekten erarbeitet: „IDTA 02056-1-0 Data Retention Policies“ [24] und „IDTA 02031-1-0 Bill of Process“ [25] im TP3. Im TP5 wurde der Anwendungsfall der virtuellen Inbetriebnahme (VIBN) unter Einsatz der VWS untersucht. Im TP6 wurden I4.0-Nachrichten definiert, um Synchronisation von Werten und Verhandlungsprozesse zwischen Leitungssatz-VWS zu ermöglichen.

**Verwendung von ECLASS**: Es wurden Definitionen und Klassifikationen recherchiert, die bereits in ECLASS vorhanden sind und potenziell für VWS4LS-Artefakte verwendet werden können. Die Beschreibung von Leitungssätzen erfordert detaillierte Informationen über Steckverbinder, Leitungen, Verbindungen, Isolierungen und vieles mehr. ECLASS bietet zwar eine allgemeine Struktur, aber es fehlen spezifische Attribute und Klassen, die für die genaue Beschreibung von Leitungssätzen geeignet sind. Deshalbwurden die bereits vorhandenen semantischen Definitionen der anderen Standards (VEC und OPC UA) als ausreichend für den Projektkontext betrachtet.

**RAMI 4.0** wurde, wie schon weiter oben unter [4.3](#_ref175664280) beschrieben, als gut geeigneter übergeordneter Referenzrahmen für die Klassifikation der zu erstellenden Lösungbestandteile im VWS4LS-Projekt identifiziert. Es wurde jedoch entschieden, im Projekt keine Aufwände in diese Richtung zu investieren, da einerseits personelle Ressourcen gebunden, jedoch kein direkter anwendungsbezogener Mehrwert entstehen würde.

# <a name="_toc174347927"></a>**7. AP 1.6 - Dokumentation der Ergebnisse**
Im Rahmen von VWS4LS wurden eine Vielzahl von Arbeitsdokumenten erzeugt, in denen die Bearbeitung und Ergebnisse der einzelnen Teilprojekte und Arbeitspakete detailliert dokumentiert wurde. Zu diesen Dokumenten gehören unter anderem auch die Anforderungserhebung, die Prozess- und Parameterliste über alle Produktionsprozesse der Leitungssatzindustrie, die Betrachtungen zur Systemarchitektur sowie der Interaktionen und Schnittstellen zwischen den verschiedenen Komponenten des Systems. Dabei entstand auch ein VWS4LS-Datenmodellkonzept ([Abbildung 16](#_ref174093885)).

![image](https://github.com/user-attachments/assets/b9557137-7aab-46ed-acf4-aa9a72e423db)

<a name="_ref174093885"></a><a name="_toc174347946"></a>*Abbildung 16: VWS4LS Datenmodell. (Quelle: Eigene Darstellung)*

Dieses Dokument beschreibt den Hergang der im Verlauf des Teilprojekt 1 getroffenen wesentlichen Grundsatzentscheidungen für das Gesamtprojekt VWS4LS sowie die Beiträge zur Verbesserung und Weiterentwicklung der Standards und Technologien für die Kabelbaumindustrie ([Abbildung 17](#_ref174093980)). Dazu gehören insbesondere:

- **Verbesserung des VEC-Datenmodells**: Das bestehende VEC-Datenmodell wurde analysiert und entsprechende Anpassungen und Erweiterungen vorgenommen, um es besser auf die Bedürfnisse der Leitungssatzindustrie abzustimmen. Durch diese Arbeit ist das VEC-Datenmodell in der aktuellen Version 2.1.0 [23] noch leistungsfähiger und anwendungsfreundlicher geworden, wodurch es sich besser für die Nutzung in den unterschiedlichen Anwendungsfällen eignet. 
- **Weiterentwicklung der VWS**: Die VWS vereinfacht den Austausch von Informationen zwischen Produktionsunternehmen in der Kabelbaumindustrie. Teilprojekt 1 hat mittels der erarbeiteten und verbesserten Datenmodelle von VEC [17] und OPC UA [16] sowie der neuen Submodelle „IDTA 02056-1-0 Data Retention Policies“ [24] und „IDTA 02031-1-0 Bill of Process“ [25] maßgeblich zur Weiterentwicklung der Verwaltungsschale (VWS) beigetragen. Dabei wurden nicht nur theoretische Grundlagen, sondern auch praktische Lösungen geschaffen [22], um die Implementierung und Akzeptanz der VWS in der Industrie zu fördern. So wurde bspw. eine Testimplementierung erstellt, die auf der Hannover Messe im April 2024 präsentiert wurde. Hervorzuheben ist, dass diese Demonstration vom VDMA als eine der ersten umfassenden Integrationen zwischen der VWS und OPC UA anerkannt wurde. Die Testimplementierung umfasste verschiedene Anwendungsfälle, die die Flexibilität und Vielseitigkeit der VWS verdeutlichten. Die Präsentation auf der Hannover Messe ermöglichte es, die Vorteile und Möglichkeiten der VWS einem breiten Publikum aus Industrie und Forschung vorzustellen und wertvolles Feedback zu sammeln. Die Anerkennung durch den VDMA unterstreicht die Bedeutung dieser Arbeit und zeigt, dass die Integration von VWS und OPC UA einen wichtigen Schritt in Richtung einer vernetzten und intelligenten Fertigung darstellt.
- **Entwicklung einer OPC UA Companion Specification**: In einer engen Zusammenarbeit mit dem VDMA wurde die Entwicklung der neuen Companion Specification «OPC 40570: OPC UA for Wire Harness Manufacturing» [16] umgesetzt. Dies trägt dazu bei, einen Standard für die Kommunikation und Interaktion zwischen verschiedenen Systemen in der Kabelbaumindustrie zu etablieren, was wiederum zu einer effizienteren und zukunftssicheren Umsetzung von Industrie 4.0 in diesem Bereich beiträgt.

Durch die Bemühungen in diesen Bereichen hat VWS4LS maßgeblich zur Weiterentwicklung und Standardisierung in der Kabelbaumindustrie beigetragen und damit die Grundlage für eine erfolgreichere und effizientere Implementierung von Industrie 4.0 in diesem Sektor geschaffen ([Abbildung 17](#_ref174093980)).

![image](https://github.com/user-attachments/assets/40392c55-3c73-4695-88a7-d4ca426d2f57)

<a name="_ref174093980"></a><a name="_toc174347947"></a>*Abbildung 17: Im Rahmen von VWS4LS erstellte neue Standards*

# <a name="_toc174347928"></a>**Literaturverzeichnis**
|||
| :- | :- |
|[1] |S. Biffl, D. Winkler, L. Kathrein, F. Rinker, R. Mordinyi und H. Steininger, „Prozessunterstützung für modellorientiertes Engineering von CPPS von der Konzeptphase bis zur virtuellen Inbetriebnahme,“ in *Handbuch Industrie 4.0: Produktion, Automatisierung und Logistik*, Bd. Springer Referenz Technik und Informatik, Berlin, Heidelberg, Springer Berlin, Heidelberg, 2020, p. 39.|
|[2] |B. A. B. V. D. L. A. H. R. &. M. L. J. Ramis Ferrer, „Product, process and resource model coupling for knowledge-driven assembly automation,“ 2016. |
|[3] |J. a. S. M. a. B. J. Pfrommer, „PPRS: Production skills and their relation to product, process, and resource,“ IEEE 18th Conference on Emerging Technologies & Factory Automation (ETFA 2013), 2013. [Online]. Available: https://doi.org/10.1109/ETFA.2013.6648114.|
|[4] |„Harness Description List (KBL),“ prostep ivip, 26 Jun 2022. [Online]. Available: https://ecad-wiki.prostep.org/specifications/kbl/.|
|[5] |„Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.|
|[6] |„OPC UA Online Reference - Released Specifications,“ 2024. [Online]. Available: https://reference.opcfoundation.org/.|
|[7] |„ECLASS,“ ECLASS e.V., [Online]. Available: https://eclass.eu/eclass-standard/content-suche/search.|
|[8] |Platform Industrie 4.0, „RAMI 4.0: Ein Referenzarchitekturmodell als Kommunikationsgrundlage in der Industrie 4.0,“ 11 04 2022. [Online]. Available: https://www.dke.de/de/arbeitsfelder/industry/rami40.|
|[9] |„prostep ivip,“ prostep ivip e.V., [Online]. Available: https://www.prostep.org/.|
|[10] |„Verband der Automobilindustrie (VDA),“ [Online]. Available: https://www.vda.de/de.|
|[11] |J. Becker, „Whitepaper KBL vs. VEC - Similarities and differences - briefy and concisely summarized,“ 16 December 2022. [Online]. Available: https://ecad-wiki.prostep.org/post/kbl-vs-vec/.|
|[12] |IEC, „IEC 61360-4 - IEC/SC 3D - Common Data Dictionary,“ [Online]. Available: https://cdd.iec.ch/cdd/iec61360/iec61360.nsf/TreeFrameset?OpenFrameSet.|
|[13] |„DIN SPEC 91345:2016-04 - Referenzarchitekturmodell Industrie 4.0 (RAMI4.0),“ 2016. [Online]. Available: https://dx.doi.org/10.31030/2436156.|
|[14] |KEBA, „OPC UA – der zentrale Standard für Industrie 4.0 im Überblick,“ [Online]. Available: https://www.keba.com/de/news/industrial-automation/ueberblick-opc-ua-zentraler-standard-industrie-4-0.|
|[15] |OPC Foundation, „OPC 40001-1: Machinery Basic Building Blocks,“ [Online]. Available: https://reference.opcfoundation.org/Machinery/v103/docs/.|
|[16] |OPC Foundation, „OPC 40570: OPC UA for the Wire Harness Manufacturing Industry,“ https://profiles.opcfoundation.org/workinggroup/88, WiP. [Online]. Available: https://profiles.opcfoundation.org/document/214.|
|[17] |„VEC Release Notes - Version 2.1.0,“ prostep ivip, 08 01 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/release-notes/.|
|[18] |OPC Foundation, „OPC 40001-3: Machinery Job Mgmt,“ OPC Foundation, [Online]. Available: https://reference.opcfoundation.org/Machinery/Jobs/v100/docs/.|
|[19] |OPC Foundation, „OPC 40001-101: Machinery Result Transfer,“ [Online]. Available: https://reference.opcfoundation.org/Machinery/Result/v100/docs/.|
|[20] |O. Foundation, „OPC 10031-4: ISA-95-4 Job Control,“ [Online]. Available: https://reference.opcfoundation.org/ISA95JOBCONTROL/v200/docs/.|
|[21] |OPC Foundation, „OPC UA Nodesets,“ [Online]. Available: https://github.com/OPCFoundation/UA-Nodeset.|
|[22] |„VWS4LS-Github,“ ARENA2036 e.V., [Online]. Available: https://github.com/VWS4LS.|
|[23] |„Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.|
|[24] |Industrial Digital Twin Association e.V. (IDTA), „IDTA 02056-1-0 Data Retention Policies,“ June 2024. [Online]. Available: https://industrialdigitaltwin.org/wp-content/uploads/2024/06/IDTA-02056-1-0_Submodel_Data-Retention-Policies.pdf.|
|[25] |Industrial Digital Twin Association e.V. (IDTA), „IDTA 02031-1-0 "Bill of Process“ (WiP),“ [Online]. Available: https://industrialdigitaltwin.org/content-hub/teilmodelle.|
|[26] |Plattform Industrie 4.0, „Interoperability at Runtime - Exchanging Information via Application Programming Interfaces,“ Plattform Industrie 4.0, Berlin, 2021.|
|[27] |Industrial Digital Twin Association e.V. (IDTA), Specification of the Asset Administration Shell Part 2: Application Programming Interfaces – IDTA Number: 01002-3-0, 2023, Frankfurt. |
|[28] |OPC Foundation, „OPC 30270: Industry 4.0 Asset Administration Shell,“ [Online]. Available: https://reference.opcfoundation.org/I4AAS/v100/docs/.|
|[29] |H. &. K. A. Walsh, „Product, Process, Resource – an Integrated Modeling Approach for Production Engineering and Industrialized Construction,“ Project Production Institute , 2023. [Online]. Available: https://www.researchgate.net/publication/379534390_Product_Process_Resource_-_an_Integrated_Modeling_Approach_for_Production_Engineering_and_Industrialized_Construction.|




# <a name="_toc137487465"></a><a name="_toc172726639"></a><a name="_toc174347929"></a>**Abbildungsverzeichnis**
[Abbildung 1: Arbeitsdokument Anforderungssammlung (Auszug)	5](#_toc174347931)

[Abbildung 2: PPR-Modell	7](#_toc174347932)

[Abbildung 3 Vergleich Scope VEC & KBL \[11\]	9](#_toc174347933)

[Abbildung 4: ECLASS-Klassifizierungen für KFZ-Bordnetze \[7\]	11](#_toc174347934)

[Abbildung 5: ECLASS-Klassifizierungen für Produktionsmaschinen \[7\]	11](#_toc174347935)

[Abbildung 6: OPC UA Technologie (Quelle: VDMA)	12](#_toc174347936)

[Abbildung 7: Leitungssatzarchitektur. (Quelle: Eigene Darstellung)	15](#_toc174347937)

[Abbildung 8: WireHarness Data Domains (Quelle: Eigene Darstellung)	17](#_toc174347938)

[Abbildung 9: JobOrder Request \[15\]	18](#_toc174347939)

[Abbildung 10: Nutzung des VEC-Modells (Quelle: Eigene Darstellung)	19](#_toc174347940)

[Abbildung 11: Beispiel VEC Terminal Datamodell (Quelle: VEC Recommendation V2.1)	20](#_toc174347941)

[Abbildung 12: Feature Requests an den VEC	21](#_toc174347942)

[Abbildung 13: Relevante OPC UA Spezifikationen (Quelle: Eigene Darstellung)	21](#_toc174347943)

[Abbildung 14: MachineIdentificationType. (Quelle: OPC UA for Machinery \[14\])	23](#_toc174347944)

[Abbildung 15: MachineryItemState. (Quelle: OPC UA for Machinery \[14\])	23](#_toc174347945)

[Abbildung 16: VWS4LS Datenmodell. (Quelle: Eigene Darstellung)	28](#_toc174347946)

[Abbildung 17: Im Rahmen von VWS4LS erstellte neue Standards	29](#_toc174347947)


# <a name="_toc172726640"></a><a name="_toc174347930"></a>**Abkürzungsverzeichnis**

|||
| :- | :- |
|AP|Arbeitspaket|
|ECLASS||
|KBL|Kabelbaumliste|
|OEM|Original Equipment Manufacturer|
|OPC UA|Open-Plattform-Communication Unified Architecture|
|Plattform I4.0|Plattform Industrie 4.0|
|PPR|Produkt-Prozess-Ressourcen|
|RAMI4.0||
|TP|Teilprojekt|
|VEC|Vehicle Electric Container|


