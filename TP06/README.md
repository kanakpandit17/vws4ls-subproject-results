# TP 6 - Automatisierte Verhandlungsprozesse

## Inhalt

[Zielsetzung](#zielsetzung)

[AP 6.1 - Konzeptentwicklung für die technische und automatisierte Verhandlung](#_6.1)
- [6.1.1 Definition von Anwendungsfällen](#_6.1.1)
  - [6.1.1.1 Szenario „Order Driven Production“](#_6.1.1.1)
  - [6.1.1.2 Szenario „Zukaufteil“](#_6.1.1.2)
  - [6.1.1.3 Szenario „Synchronisation von Werten“](#_6.1.1.3)
  - [6.1.1.4 Szenario „Änderungsmanagement“](#_6.1.1.4)
- [6.1.2 Technische Umsetzung der Verhandlungskonzepte](#_6.1.2)

[AP 6.2 - Verhandlungsszenarien und -strategien](#_6.2)

[AP 6.3 - Capabilities](#_6.3)

[AP 6.4 - ECLASS und Industrie 4.0-Sprache](#_6.4)

[Fazit](#fazit)

[Literaturverzeichnis](#literaturverzeichnis)

## <a name="zielsetzung"></a>Zielsetzung

Im TP 6 "**Automatisierte Verhandlungsprozesse“** wurde ein Konzept mit Randbedingungen für automatisierte Entscheidungen definiert und Wege für die Kommunikation und Interaktion zwischen autonomen I4.0-Komponenten (z.B. Maschine zu Maschine, Leitungssatz zu Maschine oder Leitstand (MES) zu Maschine) entwickelt. Die Verhandlung zwischen den Systemen soll autonom durch die sog. "I4.0-Komponenten" geführt werden, die anhand von Daten und Informationen Entscheidungen treffen.

Hierzu wurde als Mechanismus zum Austausch von I4.0-Nachrichten das Konzept der “Operation” des Verwaltungsschalen-Metamodells vorgeschlagen.

Das TP 6 ist wie folgt gegliedert:

-   [AP 6.1 - Konzeptentwicklung für die technische und automatisierte Verhandlung](#6.1)
-   [AP 6.2 - Verhandlungsszenarien und -strategien](#6.2)
-   [AP 6.3 - Capabilities](#6.3)
-   [AP 6.4 - ECLASS und Industrie 4.0-Sprache](#6.4)

## <a name="_6.1"></a>AP 6.1 - Konzeptentwicklung für die technische und automatisierte Verhandlung

Im AP 6.1 "**Konzeptentwicklung für die technische und automatisierte Verhandlung**“ wurde ein Konzept mit Randbedingungen für das eigenständige Entscheiden definiert und Wege für die Kommunikation und Interaktion zwischen autonomen I4.0-Komponenten aufgezeigt.

Als ein erster Ansatz der aktiven Verwaltungsschale wird die Verbindung mit dem sog. Komponentenmanager betrachtet. Der Komponentenmanager soll anhand von Algorithmen ein zielgerichtetes Verhalten einer I4.0-Komponente (VWS und dazugehörendes Asset) beschreiben. Es wird ein Vorschlag für die Umsetzung unter Verwendung von Low-Code-Plattformen skizziert.

### <a name="_6.1.1"></a> 6.1.1 Definition von Anwendungsfällen

Für die Arbeitspakete AP 6.1 bis AP 6.4 werden konkrete Anwendungsfälle (Szenarios) definiert, anhand derer die Verhandlungskonzepte entwickelt und soweit möglich auch mit Demonstratoren validiert werden. Die Anwendungsfälle des TP 6 weisen einen Bezug zu den Use Cases des Gesamtprojektes VWS4LS auf und greifen sowohl Anforderungen als auch Ergebnisse anderer Teilprojekte auf.

Im Folgenden werden die als Anwendungsfälle ausgewählten Verhandlungsszenarien beschrieben.

#### <a name="_6.1.1.1"></a>6.1.1.1 Szenario „Order Driven Production“

##### Kontext

Angenommen wird ein Produktionsauftrag für ein definiertes Halbfabrikat „verdrilltes Leitungspaar“, für dessen Herstellung verschiedene Maschinen zum Einsatz kommen können, darunter auch Maschinen verschiedenen Typs. Die Herstellung kann dabei vollständig automatisiert auf einer einzigen Maschine erfolgen, die mehrere Fähigkeiten anbietet, oder alternativ über verkette Arbeitsschritte an mehreren unterschiedlichen Maschinen, wobei auch manuelle Tätigkeiten enthalten sein können.

Im Sinne einer auftragsgetriebenen Produktion verhandelt die VWS des Produkts mit den in Frage kommenden Produktionsressourcen, welche konkreten Ressourcen zu seiner Herstellung eingesetzt werden. D.h., bei diesem Ansatz „sucht“ sich das Produkt seinen Weg durch die Fabrik. Inwieweit mit dieser Vorgehensweise Optimierungsziele auf Ebene einer Fertigungsinsel mit mehreren Maschinen oder einer ganzen Fabrik erreicht werden können, also den gesamten Auftragsbestand betreffend, wurde im Projektteam kritisch diskutiert. Es wurde entschieden, das Szenario dennoch zu betrachten. Zum einen kann das Verhandlungsfenster so eingeschränkt werden, dass die Entscheidung sich im Rahmen einer vorab festgelegten Grobplanung bewegt. Die Durchführung der automatisierten Verhandlungsprozesse hat dann zum Ziel eine Feinplanung zu realisieren, mit der auf a priori nicht bekannte Einflussfaktoren im kurzfristigen Bereich reagiert werden kann. Außerdem kann das Konzept auf einen automatisierten Verhandlungsprozess mit Beteiligung einer VWS, die einen Fabrikleitstand (MES) darstellt und die eine Sicht auf alle Produktionsressourcen und den gesamten Auftragsbestand hat, übertragen werden. Mit dieser Sicht kann im Verhandlungsprozess wieder ein “fabrikweites” Optimum erreicht werden.

##### Technische Rahmenbedingungen

Für die konkrete Instanz des herzustellenden Halbfabrikats existiert eine zugehörige VWS „Produkt“ ab dem Zeitpunkt der Erstellung des Produktionsauftrags, d.h. zeitlich bevor das Asset physisch existiert. Die VWS „Produkt“ ist als proaktive VWS (Typ 3) ausgeführt, die über die Fähigkeit verfügt, im Interaktionsprotokoll Ausschreibungsverfahren nach VDI/VDE 2193-2 [1] in der Rolle des Auftraggebers (*Service Requester*) teilzunehmen.

Die Produktionsressourcen zur Herstellung des Halbfabrikats sind ebenfalls durch proaktive VWS (Typ 3) repräsentiert. Diese VWS verfügen über die Fähigkeit, im Interaktionsprotokoll Ausschreibungsverfahren in der Rolle als Auftragnehmer (*Service Provider*) teilzunehmen. Es wird in Betracht gezogen, dass stellvertretend für eine oder mehrere Produktionsressourcen ein MES oder ähnliches System die Rolle als Auftragnehmer einnimmt. Dieses System verfügt dann über eine VWS-Schnittstelle.

Das Auffinden der Verwaltungsschalen der in Frage kommenden Service Provider erfolgt über die Abfrage von vorab definierten VWS-Registries. An dieser Stelle ist eine Abfrage- bzw. Suchfunktion in der VWS-Registry erforderlich. Die Suchfunktion soll eine Liste von Verwaltungsschalen zurückliefern, die als Typ 3 VWS das entsprechende semantische Interaktionsprotokoll implementiert haben.

Die von der gemeinnützigen [Object Management Group (OMG)](https://www.omg.org/spec/BPMN)[^1] verwaltete und in ISO/IEC 19510:2013 [2] standardisierte „[Business Process Model and Notation“](https://de.wikipedia.org/wiki/Business_Process_Model_and_Notation) (BPMN) soll für die Modellierung und Digitalisierung der Prozesse verwendet werden. Dieser Standard wird international in vielen Organisationen eingesetzt und ermöglicht durch die visuelle Natur von BPMN ein besseres Verständnis komplexer Abläufe.

[^1]: <https://www.omg.org/spec/BPMN>

##### Erwartete Ergebnisse

Mit einem ersten Demonstrator-Aufbau wird geklärt werden, ob das Konzept der Umsetzung des proaktiven Anteils der VWS mittels einer BPMN-Workflow Engine trägt, wie in AP 3.3 beschrieben.

Es ist geklärt, wie die Nachrichten zwischen Verwaltungsschalen technisch ausgetauscht werden und welche Voraussetzungen an Teilmodelle, Modellierung der Beziehungen zwischen Verwaltungsschalen und Anforderungen an die VWS-Infrastruktur (VWS-Registry, AAS-Server) sich daraus ergeben.

Es ist validiert, dass die in den einzelnen Teilprojekten erarbeiteten Teilmodelle zu Fähigkeiten dafür geeignet sind, eine Entscheidung zu treffen, ob das Beispielprodukt mit einer bestimmten Ressource gefertigt werden kann oder nicht.

Es ist validiert, dass die in TP 5 erarbeitete Funktion zum Fähigkeitenabgleich dafür geeignet ist, eine Entscheidung zu treffen, ob das Beispielprodukt mit einer bestimmten Ressource gefertigt werden kann oder nicht.

Es ist definiert, welche Inhalte die Nachricht zur Anfrage beinhalten muss, damit der Auftragnehmer die notwendigen Informationen zur Entscheidung über die Machbarkeit (Fähigkeitenabgleich) erhält oder weiß, wo er diese abrufen kann.

Es ist definiert, welche Inhalte die Nachricht zum Angebot beinhalten soll, damit der Auftraggeber die Angebotsauswahl treffen kann.

##### Ablauf der Verhandlung

1.  Ausschreibung

Die Initiative zur Verhandlung geht von der VWS des Produktes aus. Über die Abfrage von vorab definierten VWS-Registries werden die Verwaltungsschalen der Produktionsressourcen gefunden. Die VWS des Produkts sendet eine Ausschreibung an alle gefundenen Verwaltungsschalen der Produktionsressourcen. Neben der Beschreibung des Produktes beinhaltet die Ausschreibung die angefragte Gesamtmenge des Produkts, eine Bündelgröße sowie den gewünschten Fertigstellungstermin.

1.  Prüfung der Machbarkeit

Durch einen Abgleich der vom Produkt geforderten Fähigkeiten mit den in der Produktionsressource verfügbaren Fähigkeiten wird in der VWS der Produktionsressource eine Entscheidung zur Machbarkeit getroffen. Dabei ist explizit vorgesehen, dass nicht alle erforderlichen Produktionsschritte durch die Ressource ausgeführt werden können, sondern dass nur ein Teil der Produktionsschritte mit den verfügbaren Fähigkeiten machbar sind. Ein Angebot soll in diesem Fall trotzdem abgegeben werden. Die Angebotsnachricht enthält eine Kennzeichnung, welche mit der Ausschreibung angefragten Produktionsschritte Bestandteil des Angebots sind und welche Produktionsschritte (aufgrund des Fähigkeitenabgleichs) nicht Bestandteil des Angebots sind.

![image](https://github.com/user-attachments/assets/b3d11e3c-372a-4493-8a31-51320a11b647)   
*Abbildung 6-1: Verhandlungsszenario 1 „Order Driven Production“*

##### Bezug zu VWS4LS Use Cases

Das Verhandlungsszenario „*Order Driven Production*“ adressiert in erster Linie den Use Case 4 „Automatisierung von flexiblen modularen Produktionsabläufen“. Mit dem Verhandlungsprozess wird die Grundlage für die Flexibilität innerhalb der Produktionsabläufe ohne zentrale Steuerungsinstanz geschaffen. So könnte z.B. nach dem Hinzufügen von zusätzlichen Produktionsmitteln mit neuen Fähigkeiten eine Zusteuerung von Produktionsaufträgen auf diese Produktionsmittel erfolgen, ohne dass ein zentraler Eingriff notwendig ist. Die Verhandlungsabläufe zwischen Produkt und Maschine und Maschine zu Maschine ermöglichen die Flexibilität in der Produktion, da sie kurzfristige Anpassungen erlauben und die Notwendigkeit für vorab stattfindende Planungsprozesse reduzieren.

Die im Szenario zu entwickelnden Möglichkeiten zum automatisierten Fähigkeitenabgleich sind im Use Case 2 „Berücksichtigen der automatisierten Produktionsfähigkeiten im Engineering“ relevant. Durch einen Verhandlungsprozess zwischen einer Typ-VWS zum Leitungssatz während des Engineering-Prozesses mit VWS von möglichen Produktionsressourcen können direkt Erkenntnisse zur automatisierenten Produktionsfähigkeit gewonnen werden, indem man die Angebote der Produktionsressourcen aus dem Verhandlungsprozess entsprechend auswertet.

##### Bezug zu VWS4LS Teilprojekten

Die grundlegende Modellierung von geforderten und verfügbaren Fähigkeiten in der VWS sowie ein allgemeingültiger Algorithmus zum Fähigkeitenabgleich wurden in TP 5 entwickelt. Das Datenmodell zum Produkt Leitungssatz wurde in TP 2 definiert und die Grundlage zum Abbilden der Produktionsprozesse wurde in TP 3 erarbeitet. In der automatisierten Verhandlung wird auf Daten zu Produkt, Prozess und Ressource zugegriffen, damit Algorithmen Machbarkeit und Kosten bewerten und daraus Entscheidungen ableiten können.

#### <a name="_6.1.1.2"></a>6.1.1.2 Szenario „Zukaufteil“

##### Kontext

Angenommen wird ein Produktionsauftrag für das in Verhandlungsszenario “*Order Driven Production*” definiertes Halbfabrikat „verdrilltes Leitungspaar“. Dieses Halbfabrikat soll als Unterauftrag an ein weiteres Unternehmen vergeben werden. Gefordert ist die komplette Herstellung des Halbfabrikats, wobei Freiheitsgrade bezgl. der eingesetzten Produktionsressourcen und der einzelnen Produktionsschritte bestehen.

Die Verwaltungsschalen auf Seite der Auftragnehmer repräsentieren in diesem Kontext nicht einzelne Produktionsmaschinen, sondern sind hierarchisch höher auf Ebene Fabrik oder Unternehmen angesiedelt und agieren als Softwareagent, der die Gesamtheit der in der Organisationseinheit zur Verfügung stehenden Produktionsressourcen vertritt.

Welche Unternehmen als Auftragnehmer in Frage kommen, ist im Vorfeld geklärt worden. Die rechtlich notwendigen Voraussetzungen, wie z.B. Abschluss eines Rahmenvertrags, der den automatisierten Verhandlungsprozess mit Delegation von Entscheidungen an die Softwareagenten regelt, werden als gegeben betrachtet. Die technisch notwendigen Kommunikationswege wurden im Vorfeld eingerichtet.

Auf Seite des Auftragnehmers erfolgt jeweils eine Prüfung der technischen Machbarkeit zur Herstellung des ausgeschriebenen Produktes. Ist eine Machbarkeit nicht gegeben, wird die Ausschreibung abgelehnt und eine Absage gesendet. Ansonsten wird zur Angebotserstellung ein Preis und ein Liefertermin ermittelt. Zur Umsetzung verschiedener Auswahlstrategien auf der Auftraggeberseite könnten weitere Informationen im Angebot notwendig sein, z.B. PCF-Daten. Es ist zu prüfen, welche Lösungsvorschläge oder Spezifikationen für den Nachrichteninhalt “Angebot” bereits vorhanden sind und welche Ansätze es gibt, um geforderte Angebotsinhalte zu kommunizieren. Gegebenenfalls sind entsprechende Vorschläge in [AP 6.2](#6.2) zu erarbeiten.

In einer Erweiterung des Verhandlungsszenarios “Zukaufteil” sind zusätzlich für jedes Produktionslos bei Produktionsstart Schliffbilder der Crimpterminals mit Messung und Beurteilung bezüglich Einhaltung der OEM- und Herstellervorgaben gefordert. Die Übermittlung der Bilder und Messergebnisse wird innerhalb der Instanz-Verwaltungsschalen der gelieferten Produkte erwartet. Die Anforderung wird in Form einer “Required Capability” bzw. eines “Required Service” mit der Ausschreibung kommuniziert und ist bei der Überprüfung der Machbarkeit auf Auftragnehmerseite mit den eigenen Fähigkeiten abzugleichen.

Neben Anforderungen an das Produkt kann es auch grundlegende Anforderungen an das Unternehmen bzw. die Unternehmensprozesse des Auftraggebers geben. Als Beispiel dient die Anforderung, dass auf Auftragnehmerseite ein Informationssicherheitsmanagementsystem nach ISO 27001 etabliert ist. Zum Nachweis dient ein Security Certification Certificate (SCC), wie es im Diskussionspapier “[Vertrauensinfrastrukturen im Kontext von Industrie 4.0](https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/Vertrauensinfrastrukturen.pdf)” [47] der [Plattform Industrie 4.0](https://www.plattform-i40.de/IP/Navigation/DE/Home/home.html) beschrieben ist. Es soll überprüft werden, ob die zu erarbeitenden Mechanismen zum Fähigkeitenabgleich auch dazu geeignet sind, Anforderungen zu SCC zu überprüfen.

##### Technische Rahmenbedingungen

Im Lebenszyklus Planungsstadium fungiert auf Auftraggeberseite eine Instanz-VWS des Halbfabrikats als Softwareagent, welcher ein Ausschreibungsverfahren initiiert. Auf Auftraggeberseite gibt es eine Registry für Verwaltungsschalen von potenziellen Auftragnehmern oder eine Liste mit Verweisen auf entsprechende Registries als Verzeichnis von Verzeichnissen.

Das Befüllen der Registry passiert während vorher stattfindender “Onboarding”-Prozesse neuer potenzieller Zulieferer. Ein IDS wie [Catena-X](https://catena-x.net/de/) kann hier über ein Unternehmensverzeichnis oder eine zentrale “[Digital Twin Registry](https://catena-x.net/en/offers-standards/semantic-layer#:~:text=The%20Digital%20Twin%20Registry%20provides%20a)” die Lösung zum Auffinden der “Verhandlungspartner”-Verwaltungsschalen liefern (siehe dazu TP 8).

Zur Durchführung dieser Machbarkeitsprüfung kann die VWS auf Auftragnehmerseite wiederum ein weiteres Ausschreibungsverfahren an die internen Produktionsressourcen zur Herstellung des ausgeschriebenen Produktes starten, analog dem Ausschreibungsverfahren aus dem Verhandlungsszenario “*Order Driven Production*”.

Ist die Machbarkeit gegeben wird der Prozess der Angebotserstellung angestoßen. Es ist eine automatisierte Bewertung des angefragten Produktes nach Herstellkosten notwendig. Zusätzlich zu den Herstellkosten werden in der Regel verschiedene Gemeinkostenzuschläge berücksichtigt, z.B. für Entwicklung oder Verwaltung. Die zu berücksichtigende Marge kann von verschiedenen Faktoren abhängen, z.B. vom anfragenden Kunden, vom angefragten Volumen, von der aktuellen Auslastung der Produktionsressourcen, etc. Für die technische Umsetzung der Angebotserstellung sind zwei Strategien denkbar:

1.  Angebotserstellung komplett innerhalb der VWS-Infrastruktur mit einem Preisfindungsalgorithmus, der innerhalb der verhandelnden VWS implementiert ist und Daten verwendet, die ausschließlich über VWS von Produkt, verwendeten Komponenten und verwendeten Ressourcen bereitgestellt werden
2.  Angebotserstellung außerhalb der VWS-Infrastruktur, delegiert an ein System (z.B. ERP oder Vertriebssystem) dass definierte Daten über API-Aufruf erhält (Stückliste, Prozessliste) und als Rückgabewert den Angebotspreis und Liefertermin zurückgibt.

Auf Auftraggeberseite müssen mehrere eingegangene Angebote miteinander verglichen werden. Dazu ist zunächst einmal ein Speicher für die eingegangen Angebote erforderlich. Aus Gründen der Nachvollziehbarkeit ist eine Anforderung denkbar, die eingegangen Angebote auch nach der Entscheidung aufzubewahren. Es soll versucht werden, die Speicherung der Angebotsdaten über eine entsprechendes Teilmodell der VWS abzubilden.

##### Erwartete Ergebnisse

Im Verhandlungsszenario 2 werden die Nachrichten zwischen Typ-3 VWS über Unternehmensgrenzen hinweg ausgetauscht. Es ist zu prüfen, ob das Dataspace Konzept (Catena X / Tractus X) zu dem gewählten technischen Weg für den Nachrichtenaustausch kompatibel ist.

In diesem Zusammenhang sollen Anforderungen an die VWS-Infrastruktur in Bezug auf Sicherheit, Datenschutz sowie Benutzer- und Rechteverwaltung (als Input für TP 8) ermittelt werden.

Die für Verhandlungsszenario 1 definierten Interaktionsprotokolle und Spezifikationen zum Nachrichtenaufbau sollen für das unternehmensübergreifende Szenario erweitert werden.

Für die automatisierte Erstellung eines Angebots im kaufmännischen Sinne wird in der Praxis die Integration eines ERP-System notwendig sein, in dem z.B. Einkaufspreise für die verwendeten Rohmaterialen oder Kalkulationsschemata für die Ermittlung einer Preisuntergrenze abgebildet sind. Hierzu soll exemplarisch aufgezeigt werden, wie eine Integration von weiteren, nicht AAS-basierten Systemen darstellbar ist.

##### Bezug zu VWS4LS

Mit unternehmensübergreifenden automatisierten Verhandlungsprozessen wird insbesondere die Automatisierung des Änderungsmanagements entlang der gesamten Wertkette unterstützt, da die Entscheidungen über Machbarkeit und Preisfindung sowie die Prozesse zur Beauftragung automatisiert werden.

In [TP 8](https://github.com/VWS4LS/vws4ls-subproject-results/tree/main/TP08) werden die Grundlagen für einen sicheren Datenaustausch über Unternehmensgrenzen hinweg erarbeitet. Die dort erarbeiteten Grundlagen zur Nutzung von International Dataspaces (IDS) zum verteilten Zugriff auf Verwaltungsschalen werden als Voraussetzungen für den Zugriff auf Produktdaten und geforderte Fähigkeiten im Rahmen des Ausschreibungsverfahren angesehen. Konzepte wie Unternehmensverzeichnisse ermöglichen das Auffinden von möglichen Auftragnehmern.

#### <a name="_6.1.1.3"></a>6.1.1.3 Szenario „Synchronisation von Werten“

Im TP 2 wurde im Rahmen des Konzeptes “Single Point of Truth” eine Verlinkung von verschiedenen VWS zum selben Typ einer Leitungssatzkomponente definiert. Die verschiedenen VWS bilden die Sichten der verschiedenen Partner in der Wertschöpfungskette des Leitungssatzes auf dasselbe Asset, also dieselbe Komponente, ab. In dem Zusammenhang wurde auch eine technische Lösung zur Synchronisierung von Änderungen an den Teilmodellen und Teilmodellelementen zwischen den verlinkten Verwaltungsschalen gefordert.

Ziel ist es, für diesen Synchronisierungsvorgang ein semantisches Protokoll zwischen zwei Typ 3 VWS zu entwickeln, angelehnt an das Ausschreibungsverfahren. Dabei initiiert die VWS, in der die Wertänderung vorgenommen wurde, den Dialog zu den verlinkten VWS, indem eine Nachricht mit der Wertänderung gesendet wird. Zum Senden wird die in den vorhergehenden Szenarien eingeführte Operation für I4.0-Nachrichten verwendet.

![image](https://github.com/user-attachments/assets/4727111d-360e-4b94-90d6-8ea15d221ad0)   
*Abbildung 6-2: Nutzung der I4.0-Nachricht für Synchronisation von Änderungen an Teilmodellen*

Die empfangende VWS führt auf ihrer Seite eine Machbarkeits- oder Plausibilitätsprüfung bzgl. des neuen Zielwertes durch (siehe Komponente „Change Handler“ in *Abbildung 6-2*). Gegebenenfalls kann vor Übernahme der Wertänderung auf der Empfängerseite ein Freigabeprozess integriert werden. Erst nach erfolgreicher Machbarkeitsprüfung und ggf. erfolgter Freigabe wird die Wertänderung in der empfangenden VWS umgesetzt und es erfolgt eine Rückmeldung an die VWS, welche die Wertänderung propagiert hat. Auch im Falle, dass die Änderung in der empfangenden VWS nicht umgesetzt wird, erfolgt eine entsprechende Rückmeldung. So kann auch die aufrufende VWS eine Übersicht über den Synchronisierungszustand führen.

#### <a name="_6.1.1.4"></a>6.1.1.4 Szenario „Änderungsmanagement“

Die in den beiden Verhandlungsszenarien zum Ausschreibungsverfahren und zur Synchronisierung erarbeiteten Mechanismen sollen verwendet werden, um die Informationsverteilung und Abstimmungsprozesse in der Erarbeitung und in der Umsetzung einer technischen Änderung am Leitungssatz zu unterstützen. Gegebenenfalls werden die Spezifikationen zu den semantischen Protokollen und zu den Nachrichten anhand dieses Szenarios noch erweitert oder verfeinert.

### <a name="_6.1.2"></a> 6.1.2 Technische Umsetzung der Verhandlungskonzepte

Um die Interoperabilität von I4.0-Komponenten zu realisieren, ist auch die Technologie für die Kommunikation zwischen den VWS des Typs 3 zu spezifizieren.

Das Diskussionspapier der Plattform Industrie 4.0 “Verwaltungsschale in der Praxis” [4] benennt als mögliche Technologien für die Interaktion zwischen aktiven Verwaltungsschalen OPC UA sowie die Protokolle MQTT, AMQP und HTTP. Als einfachste Form der Interaktion wird der API-Zugriff einer proaktiven VWS (Typ 3) auf eine reaktive VWS (Typ 2) beschrieben.

Da für den Nachrichtenaustausch im Rahmen des semantischen Protokolls “Ausschreibungsverfahren” weder in OPC UA eine Spezifikation vorliegt noch eine auf den anderen genannten technischen Protokollen eine Spezifikation bekannt ist, wird vorgeschlagen, die [REST-API der VWS](https://github.com/admin-shell-io/aas-specs-api)[^2] auch für die horizontale Kommunikation zwischen zwei VWS vom Typ 3 zu nutzen (siehe *Abbildung 6-3*).

[^2]: <https://github.com/admin-shell-io/aas-specs-api>

![image](https://github.com/user-attachments/assets/51c35e92-589c-45a9-9d0a-5e8bb4526dce)   
*Abbildung 6-3: Horizontale Kommunikation zwischen zwei Verwaltungsschalen vom Typ 3*

“[IDTA 01002-3 Verwaltungsschale im Detail – Teil 2](https://industrialdigitaltwin.org/content-hub/aasspecifications/idta_01002-3-0-2_application_programming_interfaces)” [5] beschreibt das Konzept einer Operation, die über das Interface “Submodel” mit den Methoden “[*InvokeOperationSync*](https://app.swaggerhub.com/apis/Plattform_i40/Entire-API-Collection/V3.0.2#/Asset%20Administration%20Shell%20API/InvokeOperationSync_AAS)” oder “[*InvokeOperationAsync*](https://app.swaggerhub.com/apis/Plattform_i40/Entire-API-Collection/V3.0.2#/Asset%20Administration%20Shell%20API/InvokeOperationAsync_AAS)” aufgerufen werden kann [4].

In der REST-API wird für den Aufruf der “[*invoke*](https://app.swaggerhub.com/apis/Plattform_i40/Entire-API-Collection/V3.0.2#/Asset%20Administration%20Shell%20API/InvokeOperationSync_AAS)”-Endpunkt zur Verfügung gestellt und zum Abholen der Ergebnisse eines asynchronen Aufrufs der Endpunkt “[*operation-results*](https://app.swaggerhub.com/apis/Plattform_i40/Entire-API-Collection/V3.0.2#/Asset%20Administration%20Shell%20API/GetOperationAsyncStatus_AAS)”.

Das in AP 6.1 erarbeitete Konzept sieht vor, für die Fähigkeit zur Teilnahme am semantischen Protokoll “Ausschreibungsverfahren” in der Rolle “Auftraggeber” oder “Aufragnehmer” ein Teilmodell zu erstellen, welches eine Operation vorsieht, mit der die Nachrichten des Interaktionsprotokolls ausgetauscht werden können.

Die Operation erhält eine Implementierung in der VWS-Middleware, welche die Nachricht an eine interne Workflowengine weiterleitet, welche dann die Verarbeitung der Nachricht und daraus abgeleitete Reaktionen orchestriert.

![image](https://github.com/user-attachments/assets/b232f01c-b78e-45d3-835f-bdf6c63269e2)   
*Abbildung 6-4: Ausschreibungsverfahren zwischen Auftraggeber und Auftragnehmer*

Während der Verhandlung laufen sowohl auf Seite des Auftraggebers als auch auf Seite der Auftragnehmer Entscheidungsalgorithmen ab. So ist z.B. der Inhalt der Ausschreibung zu analysieren, eine technische Machbarkeit zur Umsetzung der Ausschreibung zu prüfen, ein Angebot zu erstellen, die eingegangenen Angebote zu analysieren und eine Entscheidung zur Angebotsannahme bzw.   
\-ablehnung zu treffen. Statt diese Algorithmen in Form von Programmcode in der VWS zu hinterlegen oder in einem VWS-Repository zu implementieren, wurde im [TP 6](https://github.com/VWS4LS/vws4ls-subproject-results/tree/main/TP06) entschieden, einen sog. “[Low-Code](https://de.wikipedia.org/wiki/Low-Code-Plattform)"-Ansatz umzusetzen. Dazu ist geplant in [AP 6.2](#6.2) einen Demonstrator aufzubauen, der ein VWS-Repository mit einer BPMN-Workflowengine kombiniert. Die Entscheidungsalgorithmen werden in BPMN modelliert und innerhalb der Workflowengine ausgeführt. In *Abbildung 6-5* ist eine Beispielimplementierung für einen Algorithmus auf der Auftragnehmerseite des Ausschreibungsverfahrens dargestellt. Aus dem Workflow heraus können Teilmodelle bzw. -elemente der VWS abgefragt werden. Operationen, die auf die VWS aufgerufen werden, sowie Wertänderungen in der VWS können Ereignisse in der Workflowengine auslösen.

![image](https://github.com/user-attachments/assets/74b7cd9c-fd1e-45d6-a705-3ef7fcc0fe86)   
*Abbildung 6-5: Beispielimplementierung für einen Algorithmus*

### Proof-of-Concept

Ein erster Proof-of-Concept wurde mit der Open Source Workflow-Engine “[Flowable](https://www.flowable.com/open-source/docs/)”[^3] unter Verwendung des [BaSyx-SDK](eclipse-basyx/basyx-java-server-sdk)[^4] umgesetzt. Die Verwendung von BPMN zur Implementierung der Typ 3 VWS sollte dabei transparent für die anderen Systeme sein, die mit der VWS interagieren. Dies wird dadurch erreicht, indem die Interaktion ausschließlich mit der API der VWS erfolgt und niemals direkt mit der API der Workflow Engine.

[^3]: <https://www.flowable.com/open-source/docs/>

[^4]: <https://github.com/eclipse-basyx/basyx-java-server-sdk>

Durch den Einsatz der Low-Code Technologie soll eine einfache Anpassbarkeit des Verhaltensmodells der Typ 3 VWS über den gesamten Lebenszyklus des Assets hinweg gewährleistet werden. Die BPMN mit ihrer graphischen Darstellung liefert den Mehrwert einer Übersicht des Verhaltensmodells und ist insbesondere auch geeignet den aktuellen Zustand eines laufenden Verhandlungsprozesses für den Menschen zu visualisieren. Dies hat Relevanz für die Untersuchungen in Rahmen des Forschungsprojektes und es wird erwartet, dass auch im praktischen Einsatz Monitoring- und Analyseaufgaben anfallen werden, bei denen die graphische Notation unterstützt.

## <a name="_6.2"></a>AP 6.2 - Verhandlungsszenarien und -strategien

Im AP 6.2 „**Verhandlungsszenarien und -strategien**“ wurde im Wesentlichen an der technischen Umsetzung der in AP 6.1 erarbeiteten Verhandlungskonzepte und deren Erprobung an Demonstratoren gearbeitet. Ziel des Arbeitspaktes war es ursprünglich Strategien und Regeln zu definieren, die zum einen automatisierten Verhandlungsprozess verschiedener VWS zulassen und zum anderen den Entscheidungsverlauf nachvollziehbar machen. Dies wurde im Arbeitspaket erreicht, indem die Abläufe in Form von BPMN-Modellen formalisiert und in einer BPMN-Engine ausführbar gemacht wurden. Die Bearbeitung der in AP 6.1 definierten Verhandlungsszenarien zu Synchronisation und Änderungsmanagement erfolgte hauptsächlich im Rahmen des Architekturteams und die Ergebnisse sind entsprechend auch im Kapitel “Architektur AAS” dargestellt.

### Start des Verhandlungsprozesses

Um den Ablauf eines Verhandlungsprozesses starten zu können, wurde in der VWS des *Service Requesters* eine Operation “*startBiddingProcess*” zur Verfügung gestellt. Diese Operation kann zum Testen und Simulieren manuell über die Weboberfläche aufgerufen werden. In der finalen Version des Demonstrators erfolgt der Aufruf jedoch automatisiert über entsprechende Geschäftslogik in der VWS-Middleware. Realisiert wurde im finalen Demonstrator das Verhandlungsgszenario “*Order Driven Production*”. Wenn der Produktionsauftrag (Service Requester) einen bestimmten Status erreicht, wird die Operation “*startBiddingProcess*” ausgelöst. Daraufhin schickt der *Service Requester* eine Ausschreibungsnachricht betreffenden der Herstellung des entsprechenden Leitungssatzes bzw. Halbfabrikats. Ziel dieser Ausschreibung ist es von allen Produktionsmaschinen, die das angefragte Produkt herstellen können, Angebote zu bekommen und nach vorgegebenem Optimierungskriterium die Zielmaschine auszuwählen. Beim manuellen Aufruf wird das Optimierungskriterium in der Weboberfläche übergeben.

![image](https://github.com/user-attachments/assets/3b29c077-756b-4a83-94ed-fd3206329b93)   
*Abbildung 6-6*: *Start des Verhandlungsprozesses über die AAS-Weboberfläche*

Für die Geschäftslogik der Ausschreibungserstellung, Senden der Ausschreibung sowie Entgegennehmen und Auswerten der eingegangenen Angebote wurde in Flowable ein Workflowmodell “*Call for proposal*” erstellt. Die grundlegende Abfolge der Aktionen und Entscheidungen wurde mit dem in der Flowable-Weboberfläche enthaltenen BPMN-Modellierungswerkzeug definiert. Komplexere Aufgaben wie das Erstellen der I4.0-Nachrichten oder der Zugriff auf VWS über die REST-API wurden in eigenen Java-Klassen implementiert. Die Java-Klassen müssen als JAR-Datei in einem der Installationsverzeichnisse des Flowable-Servers kopiert werden und beim Start des Flowable-Services zur Verfügung stehen. Das Flowable Framework stellt dazu ein Interface “JavaDelegate” zur Verfügung (siehe [https://www.flowable.com/open-source/docs/bpmn/ch07b-BPMN-Constructs\#java-service-task](https://www.flowable.com/open-source/docs/bpmn/ch07b-BPMN-Constructs#java-service-task)), von dem abgeleitet werden kann, um eigene Programmlogik zu implementieren. Im BPMN-Modellierungswerkzeug wird dann eine Aufgabe vom Typ “*JavaServiceTask”* eingefügt, bei der man den Namen der Klasse angeben kann, deren Programmlogik an dieser Stelle ausgeführt werden soll.

![image](https://github.com/user-attachments/assets/adb8cd34-3f48-4a0f-aeb7-e6dea0e92e99)   
*Abbildung 6-7: [Prozessmodelle](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP06/Beispieldaten/Call_for_proposal.bpmn20.xml) in der Flowable-Weboberfläche*

Für die Geschäftslogik der Ausschreibungserstellung, Senden der Ausschreibung sowie Entgegennehmen und Auswerten der eingegangenen Angebote wurde in Flowable ein Workflowmodell “*Call for proposal*” erstellt. Die grundlegende Abfolge der Aktionen und Entscheidungen wurde mit dem in der Flowable-Weboberfläche enthaltenen BPMN-Modellierungswerkzeug definiert. Komplexere Aufgaben, wie das Erstellen der I4.0-Nachrichten oder der Zugriff auf VWS über die [REST-API](https://github.com/admin-shell-io/aas-specs-api) wurden in eigenen Java-Klassen implementiert. Die Java-Klassen müssen als JAR-Datei in einem der Installationsverzeichnisse des Flowable-Servers kopiert werden und beim Start des Flowable-Services zur Verfügung stehen. Das Flowable Framework stellt dazu ein Interface “*JavaDelegate*” (siehe [https://www.flowable.com/open-source/docs/bpmn/ch07b-BPMN-Constructs\#java-service-task](https://www.flowable.com/open-source/docs/bpmn/ch07b-BPMN-Constructs#java-service-task)) zur Verfügung, von dem abgeleitet werden kann, um eigene Programmlogik zu implementieren. Im BPMN-Modellierungswerkzeug wird dann eine Aufgabe vom Typ “JavaServiceTask” eingefügt bei der man den Namen der Klasse angegeben, deren Programmlogik an dieser Stelle ausgeführt werden soll.

Aufgabe der VWS-Operation “*startBiddingProcess*” ist es nun, in Flowable eine Instanz von diesem Workflowmodell ”*Call for proposal*” zu starten. Flowable bietet hierzu eine REST-API an, um mit der Workflowengine zu interagieren.

Starten einer Workflowinstanz über die [Flowable REST-API](https://www.flowable.com/open-source/docs/bpmn/ch14-REST#:~:text=Flowable%20includes%20a%20REST%20API%20to%20the):

POST runtime/process-instances

Request body:
````
{
   "processDefinitionKey":"callForProposal",
   "returnVariables":false,
   "tenantId": "tenant1",
   "variables": [
      {
        "name":"proposalSelectionStrategy",
        "value":"time"
      },
      {
        "name":"reqAasId",
        "value":"https://www.arena2036.de/ids/aas/5214_6011_7042_0566"
      },

   ]
}
````
Im ersten Proof-of-Concept in AP 6.1 wurde das Feature “*Operation Delegation*” genutzt der BaSyx Version 1 Middleware genutzt, um die Operation zu implementieren. Dieses Feature erlaubt es, den Operationsaufruf an einen HTTP-Endpunkt weiterzuleiten. Für dieses Projekt wurde das Feature auch für die BaSyx Version 2 implementiert. Um die Weiterleitung in BaSyx zu konfigurieren, wird der Operation in der VWS ein Qualifier hinzugefügt mit dem Typ “*invocationDelegation*”. Der Wert des Qualifiers ist die URL, an die weitergeleitet werden soll.

Um den oben gezeigten Request-Body zum Erzeugen einer Workflowinstanz in Flowable zur erstellen, erfolgt die Weiterleitung aus BaSyx zunächst an einen HTTP-Endpunkt in NodeRed. Die Aufgabe dieses NodRed-Flows “*startBiddingProcess*” ist es in einer Javascript-Funktion den Request-Body für den Flowable-Endpunkt “runtime/process-instances” aufzubereiten und an diesen weiterzuleiten. Im Demonstrator hat der NodeRed-Flow darüber hinaus mit den zusätzlichen grün markierten Debug-Knoten die Aufgabe, den Ablauf durch zusätzliche Ausgaben nachvollziehbar zu machen.

![image](https://github.com/user-attachments/assets/6159b859-8c93-4ef6-8987-54cb7560a3ba)   
*Abbildung 6-8: NodeRed-Flow “[startBiddingProcess](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP06/Beispieldaten/nodered_determineFeasibleScope.json)”*

In dem Aufruf an Flowable werden die Strategie für die Auswahl des Angebots und die AAS-Id der Verwaltungsschale, die die Rolle des *Service Requester* einnimmt, übergeben. Prozessinstanzvariablen dienen der Steuerung der Logik innerhalb des Workflows und können auch von den Java Service Tasks gelesen und geschrieben werden. Die Übergabe der AAS-Id des *Service Requester* ist notwendig, da dieselben Instanzen von NodeRed und Flowable für verschiedene *Service Requester* eingesetzt werden. Somit ist eine Zuordnung der Workflowinstanz zur jeweiligen Verwaltungsschale möglich und die AAS-Id wird als Sender in den I4.0-Nachrichten benötigt.

Um die AAS-Id von der BaSyx aus an den NodeRed-Flow zu übermitteln, wird die als Query-Parameter in der URL der *OperationDelegation* hinterlegt.

![image](https://github.com/user-attachments/assets/a2002aad-c67d-43fb-8c8a-0b87336a937c)   
*Abbildung 6-9: Darstellung der Workflow-Instanz mit Variablen in Flowable*

Die Workflowengine von Flowable generiert für jede Workflow-Instanz eine eindeutige Nummer als “Processinstance-ID”. Diese Nummer wird im folgenden Verhandlungsprozess in allen I4.0-Nachrichten als Konversations-Id verwendet. Damit ist eine eindeutige Zuordnung der eingegangenen Nachricht zur richtig Workflowinstanz und damit auch zur richtigen VWS möglich.

### Ermittlung der möglichen Service Provider

Eine Fragestellung, die es grundsätzliche zu lösen gilt, ist welche Typ-3 VWS die Ausschreibungsnachricht erhalten sollen. Damit die VWS grundsätzlich an dem Verhandlungsprozess teilnehmen kann, muss das Teilmodell *MessageParticipant* mit der Operation *newMessage* implementieren.

Für den Demonstrator wird diese Fragestellung so beantwortet, dass alle in Frage kommenden VWS in einer zentralen AAS-Registry bzw. deren *MessageParticipant*-Teilmodelle in einer zentralen Submodel Registry registriert sind. Im Teilmodell *MessageParticipant* ist in einer Submodel Element List hinterlegt welche Interaktionsprotokolle und welche Rollen im Interaktionsprotokoll die jeweilige VWS unterstützt. Gesucht wird nach VWS die das Interaktionsprotokoll VDI/VDE 2193-2 [1] in der Rolle “*ServiceProvider*” unterstützen. Jede VWS auf die das zutrifft erhält die Ausschreibungsnachricht, d.h. der Workflow des *Service Requester* ruft auf jede dieser VWS die Operation “*newMessage*” mit einer Ausschreibungsnachricht auf. Eine Filterung auf die Fähigkeiten des *Service Provider* erfolgt an dieser Stelle bewusst nicht. Die Entscheidung, ob der *Service Provider* über notwendige Fähigkeiten verfügt, sollte auch auf der Seite des *Service Provider* getroffen werden. Kann der *Service Provider* das angefragte Produkt nicht herstellen bzw. keinen der angefragten Prozesse ausführen, so wird gem. Interaktionsprotokoll eine Ablehnung der Ausschreibung erwartet.

### Übergabe der I4.0-Nachrichten an BPMN-Workflows

Beim Durchlauf des Interaktionsprotokolls kommt es abwechselnd zu der Situation, dass einer der Verhandlungspartner auf die Antwortnachricht des anderen warten muss. Im Fall der TP6-Implementierung des Verhandlungsprozesses gibt es eine Workflowinstanz für den *Service Requester* und eine Workflowinstanz je *Service Provider*, in denen diese Wartezustände abgebildet werden müssen. In BPMN kann dieser Wartezustand über das Notationselement vom Typ Ereignis modelliert werden. Im Demonstrator kommen dabei die Arten Zeitereignis, Nachrichtenereignis und Signalereignis zum Einsatz. Mit Ereignis wird ermöglicht, dass nach Ablauf eines vordefinierten Zeitraums die Bearbeitung der eingegangenen Angebote erfolgt, auch wenn noch nicht alle Service Provider auf die Ausschreibung geantwortet haben. Sind jedoch alle Angebote eingegangen, so soll nicht auf den Ablauf des Zeitintervalls gewertet werden, sondern unmittelbar mit dem weiteren Ablauf fortgefahren werden. Dies wird durch zwei parallele Ereignisse erreicht, die durch ein XOR-Gateway zusammengeführt werden.

![image](https://github.com/user-attachments/assets/e9cf140c-d6e5-4b3b-8a85-864d2f93bee5)   
*Abbildung 6-10: Zeit- und Signalereignis im [Workflow des Service Requesters](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP06/Beispieldaten/Call_for_proposal.bpmn20.xml)*

Das Signal, dass alle erwarteten Antworten eingegangen sind, wird dabei aus einem Unterworkflow heraus ausgelöst wird, welcher für jedes eingegangene Angebot durchlaufen wird.

![image](https://github.com/user-attachments/assets/688a9ce8-4523-4778-9c2b-20a41c41e78f)   
*Abbildung 6-11: [Unter-Workflow](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP06/Beispieldaten/Calculate_proposal.bpmn20.xml) für eingehende Angebots-Nachricht*

Um von außen ein Ereignis in der Flowable Workflowengine zu generieren, gibt es einen Rest-Endpunkt, der für eine “Execution” aufgerufen werden kann. Eine “Execution” ist ein Bestandteil einer Workflowinstanz und bei parallelen Ausführungspfaden innerhalb einer Workflowinstanz werden ggf. mehrere “Executions” angelegt.

Erzeugen eines Nachrichtenereignisses in Flowable über die REST-API ([https://www.flowable.com/open-source/docs/bpmn/ch14-REST\#execute-an-action-on-an-execution](https://www.flowable.com/open-source/docs/bpmn/ch14-REST#execute-an-action-on-an-execution)):

PUT runtime/executions/{executionId}

Request body:
````
{
  "action":"messageEventReceived",
  "messageName":"proposalReceived",
  "variables": [...]
}
````
Der Rest-Endpunkt POST query/executions in Flowable ermöglicht die Ermittlung der korrekten Execution-Id. Als Query-Parameter dienen der Name des relevanten Prozessmodells, z.B. CallForProposal, und die Prozessinstanz-Id, die als Konversations-Id im Rahmen der I4.0-Nachrichten - wie oben beschrieben - mitgesendet wird.

Das Element messageName im Request Body identifiziert des jeweilige Nachrichtenereignis im BPMN-Modell, das angesprochen werden soll und wird aus dem Typ der I4.0-Nachricht abgeleitet. Im Element variables werden die Nachrichteninhalte transportiert.

Die Implementierung der Operation newMessage, welche die in I4.0-Nachricht in der VWS entgegennimmt wurde zunächst wieder durch eine Weiterleitung an einen NodeRed-Flow implementiert. In NodeRed erfolgt zunächst eine Anfrage an Flowable mit der Konversations-Id, um die korrespondierende Execution-Id zu ermitteln, und es wird das Nachrichtenereignis in Flowable generiert. Ein Sonderfall stellt der Eingang einer Ausschreibungsnachricht auf der Seite des Service Providers dar, denn in diesem Fall muss erst eine Workflowinstanz vom entsprechenden Workflow-Modell “Calculate Proposal” gestartet werden. In dem Workflowmodell “Calculate Proposal” erfolgt dann die Überprüfung der Machbarkeit, d.h. die Prüfung, ob der Service Provider über die geforderten Fähigkeiten verfügt, sowie die notwendige Bewertung des ausgeschriebenen Produktes. Die Details hierzu sind im folgenden AP 6.3 beschrieben.

![image](https://github.com/user-attachments/assets/9ccadb74-7532-4c30-9070-cb78caadb632)   
*Abbildung 6-12: Mapping von I4.0-Nachricht zu BPMN-Ereignissen in [NodeRed](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP06/Beispieldaten/nodered_newMessage.json)*

## <a name="_6.3"></a>AP 6.3 - Capabilities

### Anforderungen an den Fähigkeitenabgleich in automatisierten Verhandlungsprozessen

Das AP 6.3 „**Capabilities**“ wurde ursprünglich definiert, um die ein Konzept für einen automatisierten Abgleich der verfügbaren Ressourcen mit den geforderten Fähigkeiten im Rahmen des Verhandlungsprozesses zu entwickeln. Im Kontext TP 6 ist dies z.B. notwendig, um einen Produktionsauftrag auf die richtige Maschine zuzuweisen oder um im Rahmen eines Ausschreibungsverfahren zu entscheiden, ob für eine Ausschreibung ein Angebot abgegeben werden kann oder nicht.

In TP5 wurde ein generischer Fähigkeitenabgleich entwickelt, der es erlaubt, aus Sicht eines einzelnen Produktionsprozesses diesen Abgleich durchzuführen. Dabei werden in der VWS des Produktes modellierte, geforderte Fähigkeiten mit den in der VWS der Produktionsressource modellierenten verfügbaren Fähigkeiten abgeglichen. Der entwickelte Algorithmus liefert eine Aussage, ob für den angefragten Prozess alle Fähigkeiten abgedeckt sind und im Sonderfall des Crimpprozesses darüber hinaus eine zusätzliche Information, ob für das jeweilige zu crimpende Kontaktteil ein geeignetes Crimpwerkzeug verfügbar bzw. in der Maschine montiert ist. Das in AP 6.3 entwickelte Konzept basiert direkt auf diesem Algorithmus und den dazugehörenden Teilmodellen.

Zunächst wurde in AP 6.3 analysiert welche Anforderungen an einen Fähigkeitenabgleich, die sich aus den automatisierten Verhandlungsprozesses ergeben, durch den oben beschriebenen Algorithmus nicht abgedeckt sind. Die in [AP 6.1](#6.1) und [AP 6.2](#6.2) beschriebenen Verhandlungsszenarien umfassen nicht nur die Ausführung eines einzelnen Produktionsprozesses, sondern umfassen die Herstellung eines komplexen Halbfabrikats zu dessen Herstellung mehrere Produktionsprozesse nacheinander, in einer bestimmten Reihenfolge auszuführen sind. Es ist also notwendig, den Algorithmus aus TP5 für jeden einzelnen Produktionsprozess auszuführen und die Einzelergebnisse zu einem Gesamtergebnis zusammenzuführen.

Ein entworfenes Verhandlungsszenario sieht vor, dass von Auftraggeberseite das gesamte Produkt mit allen notwendigen Prozessen ausgeschrieben wird, aber von Auftragnehmerseite explizit Angebote erwartet werden, die nur einen Teilumfang der Prozesse beinhalten. Der Auftraggeber, kann dann Teilaufträge an verschiedene Auftragnehmer vergeben. Die Teilaufträge aneinandergekettet ergeben dann zusammen den kompletten Produktionsprozess. Aus Sicht des Fähigkeitenabgleichs bedeutet das, dass es nicht ausreichend ist, alle geforderten Produktionsprozesse zu prüfen und sobald ein Prozess nicht erfüllt werden kann, ein negatives Ergebnis zurückzumelden. Es ist vielmehr erforderlich, mögliche Teilumfänge aus der Gesamtprozesskette zu ermitteln, mit der Angabe eines Startprozesses, evtl. Zwischenschritten und einem Endprozess. Es wurde entscheiden, die Datenstruktur des Angebots so zu gestalten, dass ein Auftraggeber mehrere Teilumfänge in einer Angebotsnachricht anbieten kann.

Stehen diese Möglichkeiten zur Verfügung, kann auf Auftragnehmerseite entschieden werden, ob ein Angebot abgeben werden kann oder ob die Ausschreibung abzulehnen ist. Es kann auch der Umfang festgelegt werden, also welche Teilaufträge angeboten werden. Zur Erstellung des Angebotes fehlt jetzt noch die quantitative Bewertung der Teilaufträge. Je nach Kontext ist eine Ermittlung der notwendigen Fertigungszeit, der Herstellkosten, eines Angebotspreises oder der zu berücksichtigenden CO2-Emissionen notwendig.

Um im Verhandlungsprozess optimale Entscheidungen treffen zu können und wettbewerbsfähige Angebote erstellen zu können, ist es wichtig, dass diese Bewertungsfunktion Ergebnisse liefern kann, die möglichst nahe an der Realität liegen. Dabei sollen sowohl individuelle Eigenschaften des angefragten Produktes als auch die konkreten Gegebenheiten bzgl. der vom Auftragnehmer eingesetzten Ressourcen und der Produktionsumgebung berücksichtigt werden.

Die Berechnungsfunktion kann am besten vom Maschinenhersteller, der alle internen Details der Ressource kennt, erstellt werden. Dabei könnten durch die verwendete Berechnungsformeln oder einzelne Parameterwerte Rückschlüsse auf interne Details der Maschine möglich werden, die zum schützenswerten geistigen Eigentum des Maschinenherstellers zählen. Deshalb sollte es möglich sein, die Bewertungsfunktionen zur Verfügung zu stellen, ohne diese offen zu legen.

Auf der anderen Seite sollten die Bewertungsfunktionen vom Maschinenbetreiber angepasst oder übersteuert werden können. In Abhängigkeit von der individuellen Produktionsumgebung beim Maschinenbetreiber können sich Abweichungen ergeben, die aber im Verhandlungsprozess berücksichtigt werden sollen.

Bestimmte Parameter, die bei den Bewertungsfunktionen berücksichtigt werden müssen, wie z.B. Materialeinkaufpreise oder Maschinenstundensätze sind heute in klassischen ERP- oder MES-System abgelegt. Deshalb ist es sinnvoll, wenn diese Systeme direkt in die Bewertungsfunktion einbezogen werden können.

### Implementierung des erweiterten Fähigkeitenabgleichs

Der in [TP 5](https://github.com/VWS4LS/vws4ls-subproject-results/edit/main/TP06/) entwickelte Algorithmus arbeitet generisch aufgrund der Informationen, die in standardisierten Teilmodellen abgelegt sind. Der Vorteil ist, dass dieser Algorithmus direkt in Verwaltungsschalen-Middleware implementiert werden kann und dann für alle Verwaltungsschalen, die in der Middleware gehostet werden, zur Verfügung steht.

Die oben beschriebenen Anforderungen lassen sich jedoch mit diesem generischen Ansatz nicht oder nur schwer umsetzen. Deshalb wurde vorgeschlagen, den erweiterten Fähigkeitenabgleich individuell je Asset auf Instanzebene zu implementieren. Um Interoperabilität zu gewährleisten, wird der Fähigkeitenabgleich als Verwaltungsschalen-Operation zur Verfügung gestellt. Der Algorithmus, der in der Auftragnehmer-Verwaltungsschale die Angebotserstellung implementiert, ruft also wiederum eine Operation der eigenen Verwaltungsschale auf, um den erweiterten Fähigkeitenabgleich mit Bewertungsfunktion auszuführen.

![image](https://github.com/user-attachments/assets/e215b19f-e29c-4603-a37b-69bb1c810584)   
*Abbildung 6-13: Erweiterter Fähigkeitenabgleich*

Für die Entwicklung des Demonstrators wurde die Operation “*determineFeasibleScope*” in der Verwaltungsschale angelegt (siehe Abbildung ) und mit dem Feature der Basyx Middleware an einen HTTP-REST Endpunkt in NodeRED weitergeleitet.

Die Funktion wird im Verhandlungsprozess aus einem komplexeren Workflow zur Angebotserstellung heraus aufgerufen, der in der BPMN-Engine Flowable umgesetzt wurde. Da die Workflow-Engine ein Implementierungsdetail der Service Provider Verwaltungsschalen ist, genauso wie die Implementierung der Funktion *determineFeasibleScope*, wurde entschieden den Aufruf aus dem BPMN-Workflow heraus direkt als HTTP-Aufruf des NodeRed-Endpunktes umzusetzen. Die Nutzung der VWS-Operation als Schicht, die Interoperabilität gewährleistet, ist nicht notwendig, da der Bewegungsrahmen hier innerhalb der Systemgrenzen einer einzelnen VWS-Implementierung ist. Der direkte HTTP-Aufruf hat den Vorteil, dass das Ergebnis direkt als Antwort des HTTP-Aufrufs gesendet werden kann.

Die Rückgabe einer Nachricht im HTTP-Response ist im Basyx-Feature “*OperationDelegation*” derzeit nicht vorgesehen.

Im Demonstrator ist ein NodeRed-Endpunkt für alle "*Service Provider*”-Verwaltungsschalen zuständig. Deshalb wird als Übergabeparameter neben der AAS-Id der Produkttyp-VWS auch die AAS-Id der Maschinen-VWS übergeben.

Von der Produkttyp-VWS werden die beiden Teilmodelle *RequiredCapabilities* und *BillOfProcess* geladen. Dann wird die Liste der Prozesse im Teilmodell *BillOfProcess* der Reihenfolge nach abgearbeitet, in dem je Prozess die relevanten geforderten Fähigkeiten aus dem Teilmodell *RequiredCapabilities* ermittelt werden und für diese wird dann der in AP 5.5. entwickelte Algorithmus zum Fähigkeitenabgleich aufgerufen (siehe TP5).

Aufgabe der Funktion “*determineFeasibleScope*” ist es, eine Liste mit Angeboten zu erstellen, die mögliche, d.h. machbaren Teilumfänge der gesamten Prozessliste des *BillOfProcess*-Teilmodells beinhalten. Dabei können sich bei einer Maschine, die mehrere Prozesse ausführen kann, mehrere Teilumfänge ergeben. Je Teilumfang wird angegeben, welches der Start- und End-Prozess ist, sowie welche Prozesse dazwischen im jeweiligen Angebot beinhaltet sind. Bei der Implementierung der Funktion für die Schneid-Crimp-Vollautomaten wird berücksichtigt, dass nur Leitungen bearbeitet werden können, die als ungeschnittene Leitung von der Leitungsspule zugeführt werden. Die machbaren Teilumfänge in den Angeboten müssen dementsprechend immer mit einem Cut-Prozess beginnen.

Die gesamte Ergebnisnachricht des Funktionsaufrufs besteht aus einer Liste von Angeboten mit einem Angebot je ermitteltem, machbaren Teilumfang. Jedes Angebot beinhaltet einen ermittelten Preis, ermittelte Ausführungsdauer und einen Wert zum CO2-Fußabdruck (PCF, Carbon Footprint).

Im folgenden Kapitel wird die Ermittlung dieser Werte für das Angebot beschrieben.

### Bewertung der Herstellungsprozesse aus Sicht der Produktionsressource

Das Konzept zur Implementierung der Operation “*determineFeasibleScope*” sieht vor, mit den Informationen der Produkttyp-VWS eine Bewertung aus Sicht jeweiligen Produktionsressource in Hinblick auf notwendige Produktionszeit sowie Herstellkosten und CO2-Fußabdruck durchzuführen.

Die Ermittlung der Herstellkosten und des CO2-Fußabdrucks basiert auf der Produktionszeit und wird mit den zugehörigen Faktoren bewertet. Zur Ermittlung der Materialkosten wird die Stückliste (BOM) des Produktes mit den Preisen der einzelnen Materialen bewertet. Es ist davon auszugehen, dass die entsprechenden Werte, wie Maschinenstundensätze oder Einkaufspreise, heute in ERP- und MES-Systemen zu finden sind und diese Systeme über entsprechende Programmierschnittstellen verfügen, um diese Daten abzufragen. In der Umsetzung des VWS4LS-Demonstrators könnte solche eine Abfrage z.B. mittels HTTP-REST erfolgen.

Mit voranschreitender Standardisierung ist zu erwarten, dass auch entsprechende Teilmodelle veröffentlicht werden, welche diese Informationen dann direkt über die VWS von Produktionsressource bzw. Verbundkomponente “Produkt” zugänglich machen.

Um die Machbarkeit dieses Konzept zu überprüfen, wurden im AP 6.3 für alle notwendigen Produktionsprozesse Formeln erarbeitet, die eine realistische Ermittlung der notwendigen Laufzeit an der Maschine erlauben. Die Parameter, die sich auf die Produkteigenschaften beziehen, ließen sich dabei alle in dem von TP 3 erarbeitenden Teilmodell *BillOfProcess* finden. Die Parameter, die Eigenschaften der Ressource darstellen, sind Implementierungsdetails der Operation “*determineFeasibleScope*”.

Beim Aufstellen der Formeln wurden die in AP 6.1 beschriebenen Maschinen zu Grunde gelegt.  
Dabei ist davon auszugehen, dass eine Maschine über die Fähigkeit verfügt, mehrere Prozesse unmittelbar nacheinander auszuführen. Es wird deshalb im Rahmen des Verhandlungsprozesses ein Angebot erwartet, mit der Angabe auf welche Prozesse des Teilmodells *BillOfProcess* sich das Angebot bezieht, d.h. mit Angabe des Startprozesses, des Endprozesses und der dazwischen ausgeführten Prozesse. Dabei wird eine Gesamtbewertung aller angebotenen Prozesse erwartet, nicht aber wie sich die Gesamtzeit oder die Gesamtkosten auf die einzelnen Prozesse verteilen.

#### Zeitermittlung für den Prozess Cut

Bei der Ausführung des Prozesses Cut sind das Einziehen der Leitung von der Leitungsspule und die Bewegung des Messers zu bewerten. Diese beiden Schritte werden nacheinander ausgeführt. Beim Einziehen ist in der Realität mit einer Beschleunigung am Anfang und mit einem Abbremsen am Ende des Einzugsvorgang zu rechnen, aber für die Zwecke des Verhandlungsprozesses ist die Annäherung mir konstanter Einzugsgeschwindigkeit hinreichend genau.

**Formel für den Prozess Cut**:

**t**cut = Cut.NominalLength : **v**Feeding + **t**CutterMovement

Beschreibung der Werte:

Cut.NominalLength:   
VWS-Teilmodellelement NominalLength des Prozesses Cut in Teilmodell *BillOfProcess* des angefragten Produktes.

**v**Feeding:  
Einzugsgeschwindigkeit als Wert, der innerhalb der Implementierung der Operation *determineFeasability* festgelegt wird.

**t**CutterMovement:  
Zeitdauer für die Bewegung des Messers als Wert, der innerhalb der Implementierung der Operation *determineFeasability* festgelegt wird.

#### Zeitermittlung für den Prozess MarkWire

Es wurden zwei verschiedene Arten von Markierungen erörtert: Zum einen Markierungsverfahren bei denen die Markierung mit einer Art Stempel in einem Zug aufgebracht wird (z.B. Hotstamp-Verfahren) und Tintenstrahl- oder Laserbedruckungsverfahren, bei denen kontinuierlich einzelne Reihen von Bildpunkten aufgebracht wird. Beide Verfahren werden während des Leitungseinzug durchgeführt, was zu einer Unterbrechung oder Verlangsamung des Leitungseinzugs führt. Die betrachteten Maschinen können den Prozess Mark nur in Verbindung mit dem Prozess Cut ausgeführen, weshalb die Bewertung als Zuschlag zur in Cut Ermittelten Zeit angelegt wurden.

Welches Markierungsverfahren für das Produkt anzuwenden ist, geht aus dem Teilmodellelement MarkingType des Prozesses MarkWire im Teilmodell *BillOfProcess* hervor.

**Formel für das Hotstamp-Verfahren**:

**t**mark = MarkWire.NumberOfRepetitions \* **t**stamp

Beschreibung der Werte:

MarkWire.NumberOfRepetitions:  
VWS-Teilmodellelement NumberOfRepetitions des Prozesses MarkWire in TeilModell *BillOfProcess* des angefragten Produktes.

**t**stamp:  
Zusätzliche Zeitdauer je Markierungsvorgang durch das Abbremsen oder Anhalten des Leitungseinzugs zur Ausführung des Markierungsvorgangs als Wert, der innerhalb der Implementierung der Operation *determineFeasibleScope* festgelegt wird.

**Formel für das Tintenstrahl- und Laserdruckverfahren**:

**t**mark = MarkWire.NumberOfRepetitions \* **t**printWidthUnit \* *lengthOf*( MarkWire.Content )

Beschreibung der Werte und Funktionen:

MarkWire.NumberOfRepetitions:  
VWS-Teilmodellelement NumberOfRepetitions des Prozesses MarkWire in TeilModell *BillOfProcess* des angefragten Produktes.

**t**printWidthUnit:  
Zusätzliche Zeitdauer je Ausdruck einer Druckeinheit (Bildpunktzeile, Buchstabe, Millimeter) durch das Abbremsen des Leitungseinzugs zur Ausführung des Druckvorgangs als Wert, der innerhalb der Implementierung der Operation *determineFeasibleScope* festgelegt wird. Die verwendete Einheit für den Zeitwert ist dabei auf die Funktion *lengthOf* abgestimmt.

*lengthOf*:  
Die Funktion lengthOf ermittelt die Anzahl Druckeinheiten (bspw. in Bildpunktzeilen, Buchstaben, Millimetern) die zur Darstellung des als Inputparameter gegebenen Inhalts notwendig sind.

MarkWire.Content:  
VWS-Teilmodellelement Content des Prozesses MarkWire in Teilmodell *BillOfProcess* des angefragten Produktes.

#### Zeitermittlung für den Prozess Strip

Bei der Ausführung des Prozesses Strip ist die Bewegung des Leitungsende hin zur Werkzeugstation und die Zeitdauer für das Einschneiden und Abziehen zu berücksichtigen. Es wurde angenommen, dass bezogen auf einen Abisolationsvorgang der Zeitunterschied bei unterschiedlichen Abisolationslängen vernachlässigt werden kann. Es gibt allerdings eine Obergrenze der Abisolationslänge, die die Maschine in einem Abisolationsvorgang bearbeiten kann. Das bedeutet, wenn die gewünschte Abisolationslänge diese Obergrenze übersteigt, so wird die Maschine mehrere Abisolationvorgänge hintereinander ausführen.

**Formel für den Prozess Strip**:

**t**Strip = *ceil*( (Strip.StopPosition - Strip.StartPosition) / **l**max ) \* **t**StripStep

Beschreibung der Werte und Funktionen:

*ceil*  
Funktion, die eine übergebene Dezimalzahl auf den nächsthöheren Ganzzahlwert aufrundet.

Strip.StopPosition  
VWS-Teilmodellelement StopPosition des Prozesses Strip in Teilmodell *BillOfProcess* des angefragten Produktes gibt die Endposition des abzuisolierenden Bereichs in Bezug auf das Leitungsende an.

Strip.StartPosition  
VWS-Teilmodellelement StartPosition des Prozesses Strip in Teilmodell *BillOfProcess* des angefragten Produktes gibt die Startposition des abzuisolierenden Bereichs in Bezug auf das Leitungsende an

**L**max  
Maximal mögliche Länge in einem Abisolationsvorgang als Wert, der innerhalb der Implementierung der Operation *determineFeasibleScope* festgelegt wird.

**t**StripStep  
Zeitdauer für einen Abisolationsvorgang als Wert, der innerhalb der Implementierung der Operation *determineFeasibleScope* festgelegt wird.

#### Zeitermittlung für den Prozess Crimp

Bei der Ausführung des Prozesses Crimp ist die Bewegung des Leitungsende hin zur Werkzeugstation und die Zeitdauer für das Ausführen des Crimps, was im Wesentlichen aus einem Werkzeughub besteht, zu berücksichtigen. Die Geschwindigkeit für die Bewegung des Schwenkarms hin zur Werkzeugstation kann von Leitungstyp und Leitungsquerschnitt abhängig sein. Die Zeitdauer für den Werkzeughub kann von Leitungsquerschnitt und verwendetem Terminal abhängig sein.

Es wurde deshalb vorgeschlagen diese beiden einzelnen Zeitwerte über Funktionen zu ermitteln. Die Implementierung dieser Funktionen könnte zum Beispiel durch Auswerten einer Tabelle mit Vorgabewerten erfolgen.

Die beiden Funktionen benötigen als Eingabeparameter aus dem Teilmodell *BillOfProcess* das Teilmodelelement *Crimp.WireCrossSectionArea* und aus dem allgemeinen Bereich die Referenzen auf die verwendeten Materialien, die in MaterialOccurrence angegeben sind.

Für die Implementierung des Demonstrators wurde entschieden, einen fixen Zeitwert je Crimpvorgang in der maschinenabhängigen Implementierung zu hinterlegen.

#### Zeitermittlung für den Prozess Seal

Bei der Ausführung des Prozesses Seal ist die Bewegung des Leitungsende hin zur Werkzeugstation und die Zeitdauer für das Aufschieben der Einzelleiterabdichtung zu berücksichtigen. Die Geschwindigkeit für die Bewegung des Schwenkarms hin zur Werkzeugstation kann von Leitungstyp und Leitungsquerschnitt abhängig sein. Die Zeitdauer für das Aufschieben kann von Leitungsquerschnitt und verwendetem Dichtungselement abhängig sein.

Es wurde deshalb vorgeschlagen, diese beiden einzelnen Zeitwerte über Funktionen zu ermitteln. Die Implementierung dieser Funktionen könnte zum Beispiel durch Auswerten einer Tabelle mit Vorgabewerten erfolgen.

Die beiden Funktionen benötigen als Eingabeparameter aus dem Teilmodell *BillOfProcess* das Teilmodelelement *Crimp.WireCrossSectionArea* und aus dem allgemeinen Bereich die Referenzen auf die verwendeten Materialien, die in MaterialOccurrence angegeben sind.

Für die Implementierung des Demonstrators wurde entschieden, einen fixen Zeitwert je Vorgangsausführung in der maschinenabhängigen Implementierung zu hinterlegen.

#### Zeitermittlung für den Prozess Twist

Für die Bewertung des Prozesses Twist ist die Anzahl der Umdrehungen zu berücksichtigen, welche die Maschine mit einer bestimmten Drehzahl ausführen muss. Die Anzahl der Umdrehungen ergibt sich aus der verdrillten Länge und der Schlaglänge. Zusätzlich kann es einen längenunabhängigen Wert geben, der für das Herstellen einer Ausgangs- oder Endposition notwendig ist, wie z.B. für das Greifen der Leitungsenden.

**Formel für den Prozess Twist**:

**t**Twist = **t**Fix + (WireTwist.NominalWireEndLength - WireTwist.Side1.NominalOpenEnd - WireTwist.Side1.NominalOpenEnd) / WireTwist.NominalLayLength  / **v**Rotation

Beschreibung der Werte:

**t**Fix  
Fester Zeitwert für Herstellen der Eingangs- und Ausgangskonfiguration, z.B. Greifen der Leitungen, der innerhalb der Implementierung der Operation *determineFeasibleScope* festgelegt wird.

WireTwist.NominalWireEndLength  
VWS-Teilmodellelement NominalWireEndLength des Prozesses WireTwist in Teilmodell *BillOfProcess* des angefragten Produktes gibt die Soll-Leitungslänge im verdrillten Zustand einschließlich der unverdrillten Leitungsenden an.

WireTwist.SideX.NominalOpenEnd  
VWS-Teilmodellelement NominalOpenEnd des Prozesses WireTwist in Teilmodell *BillOfProcess* des angefragten Produktes gibt die offene, d.h. nicht verdrillte Länge am Leitungsende Side1 oder Side2 an.

WireTwist.NominalLayLength  
VWS-Teilmodellelement NominalOpenEnd des Prozesses WireTwist in Teilmodell *BillOfProcess* des angefragten Produktes gibt die Schlaglänge an.

**v**Rotation  
Anzahl Umdrehungen je Zeiteinheit bezogen auf die Leitungen, d.h. Umdrehung die genau einen Verdrillschlag bewirkt. Dieser Wert wird innerhalb der Implementierung der Operation *determineFeasibleScope* festgelegt oder ermittelt.

#### Zeitermittlung für den Prozess SpotTape

Bei der Ausführung des Prozesses SpotTape ist das Positionieren des Wickelkopfes und die Umdrehungen des Wickelkopfes zu bewerten. Für das Teilmodell *BillOfProcess* wurde in TP3 festgelegt, dass die Informationen im Prozess WireTwist bereitgestellt wird.

**Formel zur Zeitberechnung**:

**t**Twist = **t**Fix + WireTwist.NumberOfLayersSpotTape \* **v**Rotation

Beschreibung der Werte:

**t**Fix  
Fester Zeitwert für Herstellen der Eingangs- und Ausgangskonfiguration, z.B. Greifen der Leitungen, der innerhalb der Implementierung der Operation *determineFeasability* festgelegt wird.

WireTwist.NumberOfLayersSpotTape  
VWS-Teilmodellelement NumberOfLayersSpotTape des Prozesses WireTwist in Teilmodell *BillOfProcess* des angefragten Produktes gibt die Anzahl der notwendigen Lagen vor.

**v**Rotation  
Anzahl Umdrehungen des Wickelkopfes je Zeiteinheit. Dieser Wert wird innerhalb innerhalb der Implementierung der Operation *determineFeasibleScope* festgelegt oder ermittelt.

## <a name="_6.4"></a>AP 6.4 - ECLASS und Industrie 4.0-Sprache

Das AP 6.4 „**ECLASS und Industrie 4.0-Sprache**“ wurde ursprünglich definiert, um die vorhandenen Spezifikationen zu Vokabular, Struktur der Nachrichten und Interaktionsprotokollen auf Anwendbarkeit im Kontext des Projektes zu überprüfen und aufzuzeigen, welche Erweiterungen notwendig sind, um die Anwendungsfälle aus der Domäne Leitungssatz abbilden zu können.

Das in VDI/VDE 2193-2 [1] spezifizierte Interaktionsprotokoll zum Ausschreibungsverfahren konnte für die in [AP 6.1](#6.1) entwickelten Anwendungsfälle eingesetzt werden. Eine Anpassung oder Erweiterung des Interaktionsprotokolls war dafür nicht notwendig.

Der Aufbau der Synchronisationsnachrichten folgt VDI/VDE 2193-1 [5] und teilt sich in Nachrichtenrahmen und Interaktionselementen mit den Nutzdaten zur Übermittlung der Wertänderungen. Die Interaktionselemente des Nachrichtenrahmens wurden wie folgt festgelegt:

| **Nachrichtenelement** | **Beschreibung**                                                                                               | **Verwendung** |
|------------------------|----------------------------------------------------------------------------------------------------------------|----------------|
| Typ                    | Zweck der Nachricht: Synchronisation, Heartbeat, Canceled                                                      | Verpflichtend  |
| Sender                 | Absender einer Nachricht (VWS-ID)                                                                              | Verpflichtend  |
| Empfänger              | Empfänger einer Nachricht (VWS-ID)                                                                             | Optional       |
| Konversations-ID       | ID der Synchronisationsbeziehung, festgelegt während der Konfiguration (Verhandlungsprozess)                   | Verpflichtend  |
| Nachrichten-ID         | ID einer Nachricht, um z.B. eine doppelte Verarbeitung auf Empfängerseite zu verhindern.                       | Verpflichtend  |
| Als-Antwort-Auf        | Ausdruck, der die Ursprungsnachricht referenziert, wird in diesem Interaktionsprotokoll bisher nicht benötigt. | Nicht genutzt  |
| Antworten-bis          | Zeitpunkt bis zu dem die Antwort vorliegen muss, wird in diesem Interaktionsprotokoll bisher nicht benötigt.   | Nicht genutzt  |
| Semantisches Protokoll | Identifikation des semantischen Protokolls auf das sich der Zweck bezieht, hier Synchronisation                | Verpflichtend  |
| Rolle                  | Aufgabe des Senders der Nachricht im semantischen Protokoll, hier Synchronisation Message Provider             | Optional       |

*Tabelle 6-1: Aufbau der Synchronisationsnachrichten*

Da zur technischen Umsetzung des Nachrichtenaustauschs die VWS-Operation gewählt wurde, wurde ein Mapping der I-4.0-Nachrichtenelemente auf Aufrufparameter der VWS-Operation erarbeitet. Die Operation “*newMessage*” ist generell dafür vorgesehen I4.0-Nachrichten auszutauschen, unabhängig vom Interaktionsprotokoll. Für diese Operation wurde ein Aufrufparameter mit idShort “*frame*” für die Attribute des Nachrichtenrahmens vorgesehen und ein zweiter Aufrufparameter mit idShort “*interactionElements*” für die anwendungsfallspezifischen Erweiterungen. Diese Operation ist über ein Teilmodell “*MessageParticipant*” definiert. Die Operation “*NewMessage*” ist im Interaktionsprotokoll Ausschreibungsverfahren sowohl vom *Service Requester* als auch vom *Service Provider* verpflichtend zu implementieren. Für *Service Requester* ist darüber hinaus eine Operation *startBiddingProcess* vorgesehen, mit der ein Durchlauf des Ausschreibungsverfahrens gestartet werden kann.

Damit man erkennen kann, welche VWS welches Interaktionsprotokoll implementiert, ist im Teilmodell “*MessageParticipant*” eine Liste “*semanticProtocols*” enthalten, in der angegeben wird, welches Interaktionsprotokoll implementiert ist und in welchen Rollen die VWS in diesem Interaktionsprotokoll einnehmen kann.

![image](https://github.com/user-attachments/assets/76692769-c08a-46a4-a59d-c7a274d4eabb)   
*Abbildung 6-14: VWS-Teilmodelle für [Service-Requester](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP06/Beispieldaten/ServiceRequester.aasx) und [Service-Provider](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP06/Beispieldaten/ServiceProvider.aasx)*

Als dritte Ebene neben Interaktionsprotokoll und Nachrichtenstruktur wurde in AP 6.4 das Vokabular der I4.0-Sprache betrachtet. Ein Abgleich von geforderten und in der Ressource verfügbaren Fähigkeiten konnte so generisch implementiert werden, dass auch ohne zusätzliche Semantik eine automatisierte Entscheidung möglich ist. Wie in [AP 6.3](#6.3) gezeigt ist aber eine gesamte Bewertung des Produktes bis hin zu einem Angebot in dieser generischen Form nicht mehr möglich. An dieser Stelle ist eine standardisierte Produktbeschreibung wichtig. Die semantisch eindeutig beschriebenen Teilmodellelemente sind durch das in [TP 3](https://github.com/VWS4LS/vws4ls-subproject-results/edit/main/TP03/) entwickelte Teilmodell “Bill Of Process” [7] gegeben. Allen Arbeiten an Informationsmodellen mit Bezug zum Produkt Leitungssatz lag das Modell des VEC zugrunde, das als umfassendes Datenmodell in der Branche immer noch weiterentwickelt wird. Was die Beschreibung der technischen Merkmale des Produktes Leitungssatz angeht, wurde keine Notwendigkeit erkannt, zusätzliche Semantik zu definieren.

Im Kontext des unternehmensübergreifenden Verhandlungsprozesses sind jedoch zusätzliche, nicht technische Merkmale für Ausschreibung und Angebot notwendig. Hier wurde so vorgegangen, dass zunächst eine Sammlung dieser Merkmale erfolgt ist und im Anschluss im ECLASS-Katalog entsprechende Merkmale und deren eindeutige IRDI gesucht wurden. Das Ergebnis ist in nachfolgender Tabelle dargestellt.

| **Nachrichtentyp** | **Datum**                            | **Abbildung in I4.0-Nachricht** | **Semantik**                        | **IRDI**                                        |
|--------------------|--------------------------------------|---------------------------------|-------------------------------------|-------------------------------------------------|
| Ausschreibung      | Zieltermin                           | Interaktions-Element            | ECLASS                              | 0173-1\#02-ABH165\#002                          |
| Ausschreibung      | Mengeneinheit                        | Interaktions-Element            | ECLASS                              | 0173-1\#02-ABC475\#003                          |
| Ausschreibung      | Menge                                | Interaktions-Element            | ECLASS                              | 0173-1\#02-AAR706\#002                          |
| Ausschreibung      | Lieferbedingung (Ausführung)         | Interaktions-Element            | ECLASS                              | 0173-1\#02-BAE397\#006                          |
| Ausschreibung      | Lieferbedingung (Gütegrad)           | Interaktions-Element            | ECLASS                              | 0173-1\#02-BAE398\#006                          |
| Ausschreibung      | Lieferbedingung/ Lieferzustand       | Interaktions-Element            | ECLASS                              | 0173-1\#02-BAE399\#006                          |
| Ausschreibung      | Lieferbedingung (Prüfumfang)         | Interaktions-Element            | ECLASS                              | 0173-1\#02-BAE400\#006                          |
| Ausschreibung      | Lieferbedingung                      | Interaktions-Element            | ECLASS                              | 0173-1\#02-BAE401\#004                          |
| Ausschreibung      | Norm Technische Lieferbedingungen    | Interaktions-Element            | ECLASS                              | 0173-1\#02-ABL353\#001                          |
| Ausschreibung      | Erwartete Verpackung                 | Interaktions-Element            | ECLASS                              | 0173-1\#02-AAK660\#006                          |
| Ausschreibung      | Menge je Verpackungseinheit          | Interaktions-Element            | ECLASS                              | 0173-1\#02-BAA306\#005                          |
| Ausschreibung      | Mengeneinheit je Verpackungseinheit  | Interaktions-Element            | ECLASS                              | 0173-1\#02-ABC475\#003                          |
| Ausschreibung      | Ersteller der Anfrage                | Nachrichten-Rahmen              |  Sender                             | n.a.                                            |
| Ausschreibung      | Anfragenummer                        | Nachrichten-Rahmen              | Konversations-Id                    | n.a.                                            |
| Ausschreibung      | Zeitpunkt Rückmeldung                | Nachrichten-Rahmen              | Antworten bis                       | n.a.                                            |
| Ausschreibung      | Verweis auf Anforderungsdokumente    | Interaktions-Element            | ECLASS / Aspekt Zusatzdokumentation | 0173-1\#01-ADN464\#011                          |
| Angebot            | Zugesicherter spätester Liefertermin | Interaktions-Element            | ECLASS                              | 0173-1\#02-ABH165\#002                          |
| Angebot            | Angebotspreis Brutto                 | Interaktions-Element            | ECLASS                              | 0173-1\#02-AAQ214\#002                          |
| Angebot            | Angebotspreis Netto                  | Interaktions-Element            | ECLASS                              | 0173-1\#02-BAF749\#003 / 0173-1\#02-AAO822\#002 |
| Angebot            | Angebotswährung                      | Interaktions-Element            | ECLASS                              | 0173-1\#02-AAO288\#006                          |
| Angebot            | Lieferkondition                      | Interaktions-Element            | ECLASS                              | 0173-1\#02-AAX092\#003                          |

*Tabelle 6-2: Zusätzliche Merkmale für VWS4LS-I4.0-Nachrichten zu Ausschreibung und Angebot*

## Fazit

Im Rahmen von TP 6 wurden zunächst die Vorarbeiten zur I4.0-Sprache analysiert. Obwohl die I4.0-Sprache im Hinblick auf die aktive VWS entwickelt wurde, gibt es bisher nur wenige Umsetzungen, die diese direkt in die VWS integrieren. Bisher wurden häufig agentenbasierte Ansätze gewählt, bei denen Software außerhalb der Systemgrenzen der Verwaltungsschale die Kommunikation übernimmt und Entscheidungen automatisiert. Als Kommunikationskanal kommen dabei häufig Nachrichtenprotokolle wie MQTT zum Einsatz, deren Anwendung im Zusammenhang mit der VWS derzeit nicht standardisiert ist.

In TP 6 wurde zum Nachrichtenaustausch bewusst die VWS-Operation gewählt, weil diese vollständig in “Specification of the Asset Administration Shell Part 2” [5] spezifiziert ist und somit die Interoperabilität im Hinblick auf die technische Übertragung von Nachrichten zwischen verschiedenen VWS-Implementierungen gewährleistet werden kann. Der mit VDI/VDE 2193-1 [6] standardisierte Nachrichtenaufbau konnte auch in den Aufrufparametern der VWS-Operation implementiert werden.

Die Nutzung der standardisierten VWS-API für den Nachrichtenaustausch bringt insbesondere im unternehmensübergreifenden Wertschöpfungsnetzwerk Vorteile. Dort, wo die Anbindung zum Lesen und Schreiben von Teilmodellen erfolgreich über Unternehmensgrenzen umgesetzt wird, können damit auch I4.0-Nachrichten ausgetauscht werden ohne zusätzliche Kommunikationskanäle einrichten und absichern zu müssen.

Durch die in VWS4LS entwickelten Teilmodelle steht das notwendige Vokabular für die automatisierten Verhandlungen im Kontext der Leitungssatzproduktion zur Verfügung.

Mit dem Einsatz der “Low Code”-Systeme NodeRed und Flowable sowie deren Erweiterung mit JavaScript-Modulen und Java Spring Beans wurde aufgezeigt, wie die Implementierung einer VWS über den Lebenszyklus des Assets hinweg anpassbar und flexibel gelöst werden kann. Mit der Implementierung (<https://github.com/VWS4LS/vws4ls-bidding-process>) wurden die Konzepte Komponentenmanager und Interaktionsmanager “nahe” an der Verwaltungsschale umgesetzt und eine Blaupause für die Umsetzung in VWS-Middleware geschaffen, siehe Abbildung 6-15.

![image](https://github.com/user-attachments/assets/7b683743-dfa5-49f5-a939-f29c3be969f0)   
*Abbildung 6-15: [Architektur](https://github.com/VWS4LS/vws4ls-bidding-process) für die VWS Typ 3 (“Proaktive VWS”)*

## <a name="literaturverzeichnis"></a>Literaturverzeichnis
|||
| :- | :- |
| [1]  | VDI/VDE, „VDI/VDE 2193 Blatt 2 - Sprache für I4.0-Komponenten - Interaktionsprotokoll für Ausschreibungsverfahren,“ 2020. [Online]. Available: https://www.vdi.de/richtlinien/details/vdivde-2193-blatt-2-sprache-fuer-i40-komponenten-interaktionsprotokoll-fuer-ausschreibungsverfahren. |
| [2]  | ISO/IEC, „ISO/IEC 19510:2013: Business Process Model and Notation (BPMN),“ [Online]. Available: https://www.iso.org/standard/62652.html.   |
| [3]  | Plattform Industrie 4.0, „Vertrauensinfrastrukturen,“ 03 2021. [Online]. Available: https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/Vertrauensinfrastrukturen.pdf.     |
| [4]  | Plattform Industrie 4.0, „Verwaltungsschale in der Praxis,“ 2021. [Online]. Available: https://industrialdigitaltwin.org/wp-content/uploads/2021/09/08_verwaltungsschale_in_der_praxis_de_2020.pdf.       |
| [5]  | Industrial Digital Twin Association e.V., „IDTA 01002-3-0-2: Specification of the Asset Administration Shell Part 2: Application Programming Interfaces,“ June 2024. [Online]. Available: https://admin-shell-io.github.io/aas-specs-antora/IDTA-01002/v3.0.2/index.html.      |
| [6]  | VDI/VDE, „VDI/VDE 2193 Blatt 1 - Sprache für I4.0-Komponenten - Struktur von Nachrichten,“ 2020. [Online]. Available: https://www.vdi.de/richtlinien/details/vdivde-2193-blatt-1-sprache-fuer-i40-komponenten-struktur-von-nachrichten.     |
| [7]  | Industrial Digital Twin Association e.V., „IDTA 02031-1-0 Bill of Process (WiP),“ [Online]. Available: https://industrialdigitaltwin.org/content-hub/teilmodelle.       |

