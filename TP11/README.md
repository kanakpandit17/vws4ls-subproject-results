# **TP11 – Anbindung an Catena-X**

Die Digitalisierung industrieller Wertschöpfungsketten erfordert standardisierte Datenmodelle sowie vertrauenswürdige Mechanismen für den Datenaustausch. Die Lückenlose digitale Abbildung und Absicherung von Datenflüssen entlang der Wertschöpfungskette ist entscheidend, um Effizienz, Rückverfolgbarkeit und Qualität sicherzustellen.

Zwei technologische Bausteine Verwaltungsschale und Eclipse-Dataspace Connector - EDC) sollen dabei gemeinsam genutzt werden, um vor allem das Accessmanagement bis auf Attributebene zu ermöglichen.

-   Die VWS ermöglicht als standardisierter Digitaler Zwilling eines physischen oder virtuellen Assets eine strukturierte und semantisch beschreibbare Bereitstellung von Informationen entlang des Lebenszyklus. Über integrierte Mechanismen wie Role-Based-Access-Control (RBAC) oder Attribute-Based-Access-Control (ABAC) lassen sich differenzierte Zugriffskonzepte auf Submodelle und Datenpunkte realisieren.
-   Der EDC wiederum stellt eine interoperable Infrastruktur für den sicheren und souveränen Austausch von Daten auf unternehmensübergreifender-Ebene bereit. Über Policies und Contract Definitions lassen sich Nutzungsbedingungen und Zugriffskontrollen entlang von Datenflüssen definieren und automatisiert durchsetzen.

Gerade in der Leitungssatzwertkette – mit ihren hohen Anforderungen an Variantenvielfalt, Fertigungstiefe und Lieferanteneinbindung – eröffnet die Kombination beider Technologien erhebliches Potenzial. Die VWS sorgt für semantisch konsistente Datenstrukturen auf Asset-Ebene (Produktrepräsentanz), während der EDC die kontrollierte Verteilung dieser Informationen über Unternehmensgrenzen hinweg ermöglicht. Eine koordinierte Anwendung der jeweiligen Zugriffskontrollmechanismen – also VWS-internes RBAC/ABAC und EDC-Policies – schafft dabei die Grundlage für Datensouveränität, Compliance und Effizienz in einem digitalisierten Wertschöpfungsnetzwerk.

Aktuell fehlt es jedoch an einem ersten technischen Durchstich, wie beide Technologien mit deren jeweiligen Konzepten kombiniert angewendet werden können. Eine solche Verbindung ist essenziell, um Zugriffsrechte und Nutzungsregeln konsistent zu übertragen und in durchsetzbare Vertragsbedingungen zu überführen. Der Aufbau eines interoperablen, sicheren Datenraums entlang der Leitungssatzwertkette stellt somit nicht nur einen wichtigen Use Case dar, sondern auch ein Schlüsselszenario für die Zukunft industrieller Datenökosysteme.

## Zielsetzung

Die Aufgabenstellung wurde in mehrere Arbeitspakete unterteilt. Zuerst sollte ein detailliertes Konzept zur Entscheidungsfindung bezüglich der Systemarchitektur, insbesondere für den Datenaustausch auf Attribut-Ebene aus einer VWS erstellt werden.

Zu **AP1** (Arbeitspaket 1) gehört zunächst die Analyse der Schnittstellen zwischen VWS, Submodellen und einzelnen Attributen, da der normale Transferprozess des EDCs diesen spezifischen Schnitt nicht unterstützt. Der Fokus liegt darauf, klare Spezifikationen zu schaffen, die als Grundlage für die technischen Umsetzungen in den nachfolgenden Phasen dienen.

1.2 die IDTA entwickelt eine Spezifikation eines Security-Submodells bzw. Security-Konzepts, welches innerhalb von BaSyx umgesetzt werden soll. Dieses soll die Auswahl der Daten auf Attributebene ermöglichen. Dafür wurden Meetings für die Synchronisation zwischen Fraunhofer IESE, ARENA2036 und msg durchgeführt, um diese Konzepte mit der aktuellen Situation in Catena-X zusammenzubringen.

1.3 Es soll geprüft werden, ob die für den Datenaustausch mit dem EDC gesetzten Policies dynamisch generiert werden können. Hierbei wird festgelegt, ob diese Policies durch einen externen Service, durch Integration in den EDC oder durch Einbau in eine VWS Registry generiert werden können.

In **AP2** soll das Szenario implementiert und folgend die Services auf einer aktuellen Tractus-X Version (Virtuelle Maschine in der IT-Infrastruktur) deployt und erprobt werden. Dazu gehört ebenfalls die Implementierung der attribut-basierten Sicherung von Submodellen innerhalb von BaSyx.

In **AP3** werden die bisherigen Arbeitspakete hinsichtlich der Security-Aspekte zusammengefasst. Im Rahmen dessen soll ein Rollen- und Rechtekonzept beschrieben werden, welches Erkenntnisse aus AP1, in Verbindung mit der Implementierung aus AP2 verbindet. Zusätzlich werden Ausblicke zur weiteren Optimierung und zu möglichen Weiterentwicklungen gegeben.

## Ergebnis

Das Ziel ist es zum einen eine umfassende Architektur-Dokumentation, die neben präzisen Schnittstellenbeschreibungen und erforderlichen Anpassungen an bestehenden Komponenten auch konkrete Vorschläge für ein effektives Identity- und Access-Management enthält. Diese Dokumentation bildet die Grundlage für die nachfolgenden Implementierungsschritte und agile Entwicklungsprozesse.

Folgend soll als weiteres Ergebnis ein Deployment der EDCs sowie notwendiger föderierter Services aus dem Catena-X Datenökosystem stattfinden, welches die spezifizierten Anforderungen erfüllen kann. Außerdem soll das BaSyx-Deployment weiterentwickelt werden, sodass es in der Lage ist attribut-basiert Verwaltungsschalen zu sichern.

Das Ziel ist die Erarbeitung einer Dokumentation zu den Arbeitspakten, die die Herangehensweise und die finalen Ergebnisse beschreibt.

## Begrifflichkeiten

| Begriff                     | Englischer Begriff                    | Beschreibung                                                                                                                                                                                                                          |
|-----------------------------|---------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Authentifizierung           | Authentication                        | Der Prozess, bei dem die Identität eines Benutzers, Geräts oder Systems überprüft wird. Es geht darum, sicherzustellen, dass jemand oder etwas tatsächlich der ist, für den er sich ausgibt. Frage: „Wer bist du?“                    |
| Autorisierung               | Authorization                         | Der Prozess, der bestimmt, welche Rechte oder Zugriffsberechtigungen ein authentifizierter Benutzer, Gerät oder System hat. Es legt fest, was jemand tun darf, nachdem seine Identität bestätigt wurde. Frage: „Was darfst du tun?“   |
| EDC                         | EDC                                   | Der Eclipse Dataspace Connector ist eine zentrale Komponente zum sicheren, souveränen Datenaustausch, Zugriffskontrolle und Datenübertragung in föderierten Datenräumen.                                                              |
| EDC Management API          | EDC Management API                    | REST-API zur Verwaltung von Assets, Policies, Verträgen und ihrer Verhandlung                                                                                                                                                         |
| EDC-Protokoll               | EDC Protocol                          | Das EDC-Protokoll bezieht sich auf eine Implementierung des Dataspace Protokolls, welches durch die International Dataspaces Association (IDSA) definiert wurde                                                                       |
| Tractus-X                   | Tractus-X                             | Referenzimplementierung der Catena-X-Dateninfrastruktur; beinhaltet zentrale Dienste wie Registries, Broker, Identity Provider, der Portal.                                                                                           |
| Angebot                     | Offer                                 | Ein Angebot ist ein Eintrag innerhalb eines Katalogs. Er kann dazu verwendet werden, um eine Vereinbarung mit dem Austeller des Katalogs über den Zugriff auf eine Ressource zu treffen.                                              |
| Katalog                     | Catalog                               | Der Katalog wird bei Anfrage dem externen Benutzer zur Verfügung gestellt. Er enthält verschiedene Angebote für den Zugriff auf Ressourcen des Austeller des Katalogs.                                                                |
| Vertrag                     | Contract                              | Ein Vertrag ist die Vorstufe zu einem Angebot. Der Besitzer eine Ressource definiert im Normalfall mehrere Verträge und definiert dann Regeln, von wem und wann ein Vertrag abgerufen werden darf. Das Resultat ist dann ein Angebot. |
| Vereinbarung                | Agreement                             | Eine Vereinbarung ist dann getroffen, wenn der Besitzer einer Ressource ein übermitteltes Angebot angenommen hat.                                                                                                                     |
| Regel/Policy                | Policy                                | Der Zugriff auf Verträge wird über Regeln/Policies eingeschränkt.                                                                                                                                                                     |
| Security-Submodell          | Security-Submodel                     | Teilmodell einer VWS zur Definition von Zugriffs- und Filterregeln für Daten auf Attributebene.                                                                                                                                       |
| ABAC                        | ABAC (Attribute-Based Access Control) | Attribut-basierte Zugriffskontrollmethode, bei der Entscheidungen auf der Ebene von Attributen (z.B. Nutzerrolle, Kontext) getroffen werden.                                                                                          |
| RBAC                        | RBAC (Role-Based Access Control)      | Rollen-basierte Zugriffskontrolle basierend auf definierten Benutzerrollen.                                                                                                                                                           |
| Single-Sign-On              | Single-Sign-On                        | Authentifizierungsmechanismus, der den Zugriff auf mehrere Systeme mit einmaligem Login ermöglicht.                                                                                                                                   |
| BPN                         | BPN                                   | Business Partner Number: Die BPN wird im Allgemeinen bei einer globalen Registrierungsstelle hinterlegt. Von dort kann sie dann abgerufen oder auch validiert werden.                                                                 |
| Interner Identity Provider  | Internal Identity Provider            | Der interne Identity Provider wird vom Besitzer einer Ressource verwendet, um Access-Tokens zum Zugriff auf diese Ressource zu ermöglichen.                                                                                           |
| Externer Identity Provider  | External Identity Provider            | Der externe Identity Provider ist eine globale Stelle die Identitäten überprüft und Tokens aufstellen kann.                                                                                                                           |
| IDTA                        | IDTA                                  | Industrial Digital Twin Association e. V.: Verein zur Standardisierung von Digitalen Zwillingen und der VWS                                                                                                                           |
| IDTA Security Spezifikation | IDTA Security Specification           | Mit der IDTA Security Spezifikation können Regeln definiert werden. Der primäre Einsatzzweck ist die Filterung von Daten beim Zugriff auf eine Ressource.                                                                             |


2.4	AP 11.1 – Erarbeitung eines Konzepts zur Entscheidungsfindung
Das erste Arbeitspaket umfasst die Erarbeitung eines detaillierten Konzepts zur Entscheidungs-findung bezüglich der Systemarchitektur und Kommunikationsmethodik. Ziel ist es, klare Spezifika-tionen zu schaffen, auf deren Basis die technischen Umsetzungen in den nachfolgenden Phasen durchgeführt werden können. Zusätzlich sollen mögliche Konflikte erkannt und diese in Zusam-menarbeit von Fraunhofer IESE, ARENA2036, msg und Catena-X geklärt sowie mögliche Resolu-tionen erarbeitet werden. 
Das Ergebnis dieses Arbeitspakets ist eine vollständige Architektur-Dokumentation, die neben einer präzisen Beschreibung der Schnittstellen, der erforderlichen Anpassungen an bestehenden Komponenten und der definierten Policies auch konkrete Vorschläge für ein effektives Identity- und Access-Management beinhaltet.
2.4.1	Vorgehensweise und Inhalte
Zu Beginn erfolgt eine umfassende Analyse des Ist-Zustands durch einen semantischen und technischen Abgleich der vorhandenen VWS- und Aspektmodelle, um Überschneidungen, Konflik-te und Lücken zu identifizieren. Anschließend wird eine detaillierte Systemarchitektur entwickelt, die insbesondere die Anbindung der VWS an den EDC über eine erweiterte Distributed Digital Twin Registry (dDTR) spezifiziert. Dabei sind Transformationsregeln und Application Programming Interfaces (API) zu definieren, um Metadaten und Zugriffsrechte konsistent zwischen den Syste-men zu synchronisieren.
Ein weiterer zentraler Bestandteil ist die Konzeption eines Single-Sign-On Mechanismus, der si-cherstellt, dass Nutzer nahtlos und sicher auf verschiedene Services zugreifen können. Abschlie-ßend erfolgt die Erstellung einer Entscheidungsvorlage in Form eines Summary-Whitepapers, das die Grundlage für die nachfolgenden Implementierungsschritte darstellt. Diese Unterlagen dienen außerdem als Grundlage für agile Entwicklungsprozesse, inklusive Aufwandsschätzungen und Planungen der nächsten Projektschritte.
2.4.2	Discovery Workflow
Der Discovery Workflow ist statisch definiert und wird sich im Rahmen des Projekts nicht ändern. Zum besseren Verständnis wurde er initial dokumentiert:
 
Abbildung 2 1: Sequenzdiagramm für den Discovery-Workflow
2.4.3	Dataspace Workflow
Um ein Verständnis für AP 2 zu gewinnen, wurde der vollständige Dataspace-Workflow in mehre-ren Fassungen zwischen den Projektpartnern diskutiert und weiterentwickelt.
2.4.3.1	Dataspace Workflow - Initiale Fassung
Zunächst wird die initiale Fassung der Gespräche dargestellt. Bei dieser bleiben noch Fragen of-fen, welche im Folgenden behandelt werden, siehe Abbildung 2 2.
 
Abbildung 2 2: Initialer Catena-X EDC Transfer-Prozess
Die initiale Fassung beschreibt den vollständigen Catena-X-EDC Transfer-Prozess. Dieser beinhal-tet:
•	Anlegen von Asset, Policy und Contract für die Authentifizierung auf die Provider Digital Twin Registry für das Auffinden von Submodellen, die von Interesse sind
•	In die Digital Twin Registry werden alle Metadaten der angebotenen Submodelle abge-legt, um eine Discovery zu ermöglichen
•	Die Erstellung von Asset, Policy und Contract wird ebenfalls für die einzelnen Submodelle erstellt, um diese transferieren zu können
•	Über einen noch zu definierenden Mechanismus sollen die logischen Regeln aus dem Security-Submodell extrahiert werden. Für die Anwendung dieser Regeln stehen zu die-sem Zeitpunkt mehrere Möglichkeiten zur Verfügung:
o	Die Regeln werden über eine Erweiterung in der Digital Twin Registry umgesetzt. Dafür gibt es ungenutzte Security-Properties als Teil der Shell-Descriptor API, sie-he sldt-digital-twin-registry/docs/architecture/2-architecture-constraints.md 
o	Die Regeln werden als Teil der EDC-Policies umgesetzt. Dabei sind mehrere Fra-gestellungen hinsichtlich Umsetzbarkeit offen (siehe unten).
o	Die Regeln werden auf Seite des Submodel-Repositories bzw. auf BaSyx-Seite beim Provider umgesetzt.
Alle drei Optionen erfordern eine entsprechende Implementierung und sind von der Umsetzung sehr komplex, da sie mehrere Systeme beeinflussen.
Zudem müssen folgende Rahmenbedingungen beachtet werden:
•	Potenzielle Code-Änderungen an EDCs, der Digital Twin Registry oder anderen Kompo-nenten sollen nur beim Provider liegen.
•	Die Implementierung soll mit anderen Catena-X Participants kompatibel bleiben. Dies ist ggf. umsetzbar, solange die Änderung ausschließlich beim Provider stattfindet und bspw. Consumer-EDCs nicht aktiv an dem Security-Mechanismus beteiligt sind.
Offene Fragen: Security Submodell
Die folgenden Fragen haben sich zum Security-Submodell ergeben:
•	Ist das Security-Submodell zum übertragenen Submodel eine 1:n oder eine 1:1 Bezie-hung?
•	Wie definiert ein Security-Submodell eine Selektion für die zu übertragenden Submodels?
•	Ist die Selektion binär (Attribut anzeigen/nicht anzeigen) oder komplexer?
•	Ist die Selektion Consumer-abhängig?
•	Ist die Selektion allgemeingültig auf dem Submodell, unabhängig vom Consumer?
•	Wo ist die Überschneidung zu ABAC / RBAC?
Annahmen zu Policies
Eine Policy hat (zum jetzigen Zeitpunkt) folgende Limitationen:
•	Die Evaluation der Policies ergibt eine binäre Antwort (Policy erfüllt / Policy nicht erfüllt) zum Sichten des Angebots durch den Consumer.
•	Die Evaluation der Policies ergibt eine binäre Antwort (Policy erfüllt / Policy nicht erfüllt) zum Transfer des Angebots durch den Consumer.
•	Es findet keine Transformation der Daten (z.B. "Schwärzung von Daten" / Filterung der Daten) statt, sondern nur ein Abgleich von Fakten zu Policies, der in der binären Antwort resultiert.

Anforderungen an Security-Submodel
Was für die Umsetzung des Security-Submodell benötigt wird:
•	Definition von Regeln und Umsetzung der Regeln zum Erhalt eines selektiven Submodells
•	Eine Runtime, in der die Translation zu Regeln durchgeführt wird
•	Eine Runtime, in der die Selektion des Submodells durchgeführt wird
2.4.4	Zweite Fassung
Für die zweite Fassung, siehe Abbildung 2 3 wurden folgende Änderungen am Konzept durchge-führt:
•	Abwendung von Security-Submodels, da ein neues Security-Konzept durch die IDTA standardisiert wird.
•	Die Security-Regeln sowie Format, Scope, Rahmenbedingungen und Funktionalität wer-den durch die IDTA Security Spezifikation definiert .
Basierend darauf wurden folgende Entscheidungen getroffen:
•	Policies werden zur Authentifizierung eines Participants für den Zugriff auf ein Token ge-nutzt, welches auf das BaSyx-Backend autorisiert ist
o	Offene Punkt: Policies, die mit Catena-X kompatibel sind, könnten auch autogene-riert sein, aber eine Runtime dafür würde fehlen.
•	Sowohl Tractus-X (Datenökosystem-Infrastruktur) als auch BaSyx (VWS-Backend) nutzen für Demonstrationszwecke dieselbe Keycloak-Instanz
o	Die Regeln werden dateibasiert und zentral an einer Stelle verwaltet.
o	Für eine hohe Anpassbarkeit, werden für alle BaSyx Repositories, Registries und die Discovery explizite Regeln definiert
o	Zunächst liegt der Fokus auf die Umsetzung RBAC Regeln, da diese den Anwen-dungsfall ausreichend abdecken und die Komplexität damit gering gehalten wird
o	Im Ausblick ist die Erweiterung auf weitere Quellen für Regeln möglich 
 
 
Abbildung 2 3: Zweite Fassung des Catena-X EDC Transfer-Prozess
 
2.4.4.1	Finale Fassung
In der finalen Fassung, siehe Abbildung 2 4 wurden folgenden Entscheidungen getroffen:
•	Entscheidung mit Fraunhofer IESE zum Switch von der Tractus-X Registry auf die BaSyx Registry
o	Der Prozess wird dadurch signifikant simplifiziert, da nur noch eine Freigabe auf die BaSyx Infrastruktur stattfinden muss, statt einzelne Services freigeben zu müs-sen.
o	Dies Ermöglicht volle Kontrolle über den Autorisierungs- & Authentifizierungspro-zess durch den Provider.
Folgende Entscheidungen wurden final bestätigt:
•	Initial wird dieselbe Identity-Provider-Instanz für die Tractus-X und die BaSyx Infrastruktur genutzt.
•	Die Security-Regeln sowie Scope, Rahmenbedingungen und Funktionalität werden durch die IDTA Security Spec. Definiert.
 
Abbildung 2 4: Finaler Catena-X EDC Transfer-Prozess
 
2.5	AP 11.2 – Technische Umsetzung der Systemarchitektur
Im zweiten Arbeitspaket liegt der Schwerpunkt auf der technischen Umsetzung des zuvor entwi-ckelten Konzepts. Ziel ist die Implementierung eines funktionsfähigen Proof-of-Concepts (PoC), der den Transfer auf Attribut- bzw. Rollen-Ebene mit dem EDC, sowie BaSyx-Komponenten   er-möglicht.
2.5.1	Vorgehensweise und Inhalte
Die initiale Fassung der föderierten Services (Industry Core ) wird von dem Projekt der ARE-NA2036-X bereitgestellt und an den entsprechenden Stellen angepasst.
Zusätzlich werden dedizierte EDCs spezifisch für diesen Use-Case deployt mit denen das Szena-rio durchgespielt werden kann. Zudem wird eine aktualisierte Version von BaSyx auf der virtuellen Maschine Tractus-X 07 VM von Fraunhofer implementiert und deployt, auf welche der Datentrans-fer basieren soll. 
2.5.2	Variationen
Im Rahmen dieses Projekts wurden verschiedene Variationen spezifiziert, um den Einsatz von Identity-Providern und Token-Konfigurationen zu optimieren. Diese Variationen zielen darauf ab, unterschiedliche Szenarien zu unterstützen und die Flexibilität sowie Sicherheit der Systemarchi-tektur zu erhöhen. 
Die folgenden Abschnitte erläutern die einzelnen Varianten im Detail und bieten eine umfassende Übersicht über ihre Zielsetzung und Begründung sowie die Konfiguration von Keycloak.
Für die Umsetzung des Szenarios wird zunächst die Basisvariante umgesetzt und getestet, um einen PoC im Rahmen der noch verfügbaren Projektlaufzeit zu finalisieren. Diese Variante wird ausführlich in Kapitel 2.5.2.1 beschrieben. Weitere Varianten mit zwei Identity Providern und zwei Token werden in den Kapiteln 2.5.2.2 (Zwei Identity Providern) und 2.5.2.3 (Zwei Token Variante) beschrieben. 
2.5.2.1	Shared Identity-Provider / Basisvariante
Ein Keycloak-Server wird verwendet, um die Authentifizierung zu zentralisieren und den Zugriff auf geschützte Ressourcen zu steuern. Für die Kommunikation zwischen den Teilnehmern wird ein Tunnel zwischen dem Consumer und dem Provider über die EDCs der beiden Teilnehmer aufge-baut. Diese Kommunikation erfolgt durch eine Vertragsverhandlung über die EDC Control Plane.
Die Architektur des beschriebenen Systems umfasst mehrere wichtige Komponenten und Schritte:
•	Ein einzelner Keycloak-Server: Dieser Server übernimmt die zentrale Verwaltung und Au-thentifizierung der Benutzer und Clients. Durch die Implementierung von RBAC/ABAC-Regeln auf dem BaSyx-Server gewährleistet der Keycloak-Server im Zusammenspiel mit dem BaSyx Authorization Feature eine präzise und flexible Steuerung des Zugriffs auf verschiedene Ressourcen.
o	Wegen der deutlichen höheren Komplexität bei der Implementierung von ABAC-Regeln in BaSyx, wird das Konzept vorerst mit RBAC-Regeln getestet
•	EDC als Proxy und Kontrolleinheit: Der EDC dient als Proxy und ermöglicht die sichere Kommunikation zwischen Consumern und Providern. Er übernimmt die Rolle einer Kontroll- und Vermittlungseinheit, die den Zugriff auf den BaSyx-Server über die EDC Data Plane regelt.
•	Aufbau des Tunnels: Die Verbindung zwischen den Teilnehmern erfolgt über die EDCs beider Parteien. Diese Konnektoren ermöglichen eine Vertragsverhandlung über die EDC Control Plane
Ein wichtiger Aspekt der Authentifizierung ist die Generierung von Tokens. Diese Tokens werden aus der Kombination von Client-ID, Token-URL und Client-Secret erzeugt, welche vom Provider im Asset definiert werden. Durch diese Methode wird sichergestellt, dass nur autorisierte Benutzer auf die Ressourcen zugreifen können.
Ein zentraler Bestandteil des Systems ist der Einsatz von Keycloak für die Authentifizierung und Autorisierungsregeln. Die Nutzung von Keycloak-Clients ermöglicht die Definition von RBAC und ABAC-Rollen und -Attributen. Der Provider hat die vollständige Kontrolle über die Client-Konfiguration, insbesondere hinsichtlich der Rechte auf den BaSyx Server. Dieser Client wird ef-fektiv über den EDC angeboten.
Die Implementierung des beschriebenen Szenarios erfordert mehrere sorgfältig geplante Schritte:
•	Bereitstellung und Konfiguration des Keycloak-Servers: Die Einrichtung und Konfiguration des Keycloak-Servers ist der erste Schritt. Hierbei werden die verschiedenen Benutzer, Clients und deren Rollen bzw. Attribute definiert.
•	Deployment der EDC-Komponenten: Als nächster Schritt erfolgt die Bereitstellung der EDCs, welche die Verbindung zwischen den Konsumenten und Providern herstellen.
•	Aufbau des Tunnels: Nachdem die EDCs bereitgestellt wurden, wird der Tunnel zwischen den Teilnehmern aufgebaut. Dieser Tunnel ermöglicht eine sichere und zuverlässige Kommunikation.
•	Erstellung der Authorisierungsregeln in BaSyx: Für alle Ressourcen in der BaSyx Dis-covery, den Repositories und den Registries werden Zugriffsregeln in den JSON-Dateien definiert.
•	Erstellung und Konfiguration der Keycloak-Clients: Die Keycloak-Clients werden erstellt und konfiguriert, um die notwendigen Rollen oder Attribute zu definieren. Diese Informati-onen werden mit den in BaSyx definierten RBAC/ABAC-Regeln abgeglichen, um den Zu-griff auf den BaSyx Server zu steuern.
•	Generierung und Verwaltung von Tokens: Schließlich erfolgt die Generierung und Verwal-tung der Authentifizierungstokens, die für den Zugriff auf die Ressourcen benötigt werden.
Dieses Dokument hat die wesentlichen Aspekte der technischen Umsetzung eines Systems be-schrieben, das auf einer einzigen Keycloak Instanz basiert. Durch die detaillierte Beschreibung der Komponenten und Implementierungsschritte wird ein umfassender Überblick über die erwarte-ten Ergebnisse und die Vorteile dieser Architektur geboten, siehe Abbildung 2 5.
 
Abbildung 2 5: Architekturübersicht
2.5.2.2	Zwei Identity-Provider Variation
Für die Variante der Nutzung von zwei Identity-Providern wird ein Keycloak für die föderierten Tractus-X Services verwendet, während ein weiterer Keycloak vom Provider selbst eingesetzt wird. Diese Konfiguration bietet mehrere Implementierungsoptionen, welche den Grad der Kontrolle und Flexibilität des Providers erhöhen. Eine Übersicht des entwickelten Vorgehens ist in Abbil-dung 2 6 dargestellt. 
Eine Möglichkeit besteht darin, die Provider-Clients und Keycloak-Clients über die Policy- und As-set-Definition zuzuordnen. In der Asset-Definition wird der passende Client beziehungsweise Bu-siness Partner zu der Business Partner Number (BPN) in der Policy-Definition angegeben. Dadurch können die Zuordnung und Verwaltung der Rechte und Rollen auf feingranulare Weise erfolgen, was den Bedürfnissen des Providers gerecht wird.
Eine alternative Implementierungsmethode ist die Föderierung der Keycloaks. Durch das Teilen der Clients in der föderierten Struktur können die Vorteile der Basisvariante genutzt werden. Dabei bleibt der Provider in der Lage, das Rollen- und Rechtemanagement effektiv zu steuern. Dies er-möglicht eine zentrale Verwaltung der Authentifizierungs- und Autorisierungsrichtlinien, während gleichzeitig eine flexible Handhabung der Clients und ihrer Ressourcen gewährleistet wird.
Die beschriebenen Ansätze bieten dem Provider die Möglichkeit, das Zugangskontrollsystem an die spezifischen Anforderungen und Geschäftsprozesse anzupassen. Diese Flexibilität ist beson-ders wichtig, um verschiedenen Sicherheitsanforderungen gerecht zu werden und die Benutzer-freundlichkeit für die Endbenutzer zu maximieren. Durch die detaillierte Planung und Implementie-rung der beschriebenen Szenarien kann ein robustes und anpassungsfähiges System zur Verwal-tung von Identitäten und Zugriffsrechten geschaffen werden.
 
Abbildung 2 6: Architekturübersicht mit zwei Identity Providern
2.5.2.3	Zwei Token Variation
Die entscheidende Differenz bei dieser Variante besteht darin, dass nach der Weiterleitung des Requests über den EDC-Tunnel ein weiterer Token vom EDC generiert und intern für den Proxy genutzt wird. Eine Übersicht des entwickelten Vorgehens ist in Abbildung 2 7dargestellt. 
Dies bietet erweiterte Sicherheit, da der Zugang zu den Ressourcen noch stärker kontrolliert wer-den kann. Allerdings führt dies auch zu einem höheren Implementierungsaufwand beim EDC, weil zusätzliche Schritte zur Token-Generierung und Verwaltung erforderlich sind. 
Diese zusätzliche Sicherheitsebene garantiert, dass nur autorisierte Anfragen den Proxy erreichen und bearbeitet werden, wodurch die Integrität und Vertraulichkeit der Daten gewahrt werden.
 
Abbildung 2 7: Architekturübersicht mit zwei Token Variation
2.5.3	Deployment
Zur Nutzung der bereitgestellten föderierten Services, werden erweiterte Umbrella-Charts von Trac-tus-X genutzt. In diesem Szenario wird ein Provider- und ein Consumer-EDC inkl. peripherer Ser-vice deployt, siehe Abbildung 2 8.
Die konkrete Definition der values.yaml kann in dem entsprechenden Repository überprüft wer-den. Die folgenden Schritte zeigen den genauen Ablauf dieses Prozesses:
1.	Wechseln auf das Verzeichnis der Umbrella Charts:
o	cd .\charts\umbrella\
2.	Erstellen der Abhängigkeiten der Helm Charts:
o	helm repo add tractusx-dev https://eclipse-tractusx.github.io/charts/dev/ 
o	helm repo add runix https://helm.runix.net
o	helm dependency build
3.	Installieren der Charts mit dem folgenden Befehl auf der entsprechenden Kubernetes Umgebung:
o	helm install --create-namespace -n vws4ls -f values-vws4ls.yaml vws4ls .
4.	Setze Secret für Keycloak Token Request in dem EDC-Vault-Pod per Shell:
o	vault kv put secret/{{PROVIDER_CLIENT_SECRET_KEY}} con-tent={{PROVIDER_CLIENT_SECRET}}
 
Abbildung 2 8: Deployment-Diagramm
2.5.4	Durchführung Szenario
Zu Beginn muss der EDC im Portal (siehe Abbildung 2 9) für den eigenen Nutzer registriert wer-den. Dies kann man unter dem Punkt „Connector Management“ durchführen:
 
Abbildung 2 9: Connector Management (links) und -Registration (rechts)
Konkret sind die durchzuführenden Konfigurationen (siehe Abbildung 2 10) unter dem hell-blauen Panel ersichtlich:
 
Abbildung 2 10: Connector Configuration
Diese User-spezifischen Werte müssen in den entsprechenden Umbrella-Charts hinterlegt werden. Für das vorliegende Szenario werden einfachheitshalber automatisch generierte EDCs der Umbrella-Charts genutzt, die mit den korrekten Daten vorbefüllt sind.
Zuletzt werden die deployten EDCs mit ihren konkreten Endpoints registriert, siehe Abbildung 2 11. Ein Beispiel für Endpoints ist folgende Adresse:
https://dataprovider-vws4ls.e34eabb8a136438fafe9.germanywestcentral.aksapp.io/api/v1/dsp 
 
Abbildung 2 11: Abschluss Connector Registration
2.5.4.1	Data Provisioning
Folgend wird der Data-Provisioning-Teil beschrieben, bestehend aus der Population des BaSyx-Backends, sowie der Anlegung der Assets, Policies und Contracts im EDC.
Für die Durchführung des Szenarios wird eine Postman Collection beigelegt, welche alle Schritte von Provisioning bis Consumption definiert. Zusätzlich werden diese hier nochmal separat be-schrieben.
Die folgenden Schritte müssen an den entsprechenden Endpoints der Provider EDC Management API und des BaSyx-Environments durchgeführt werden, um die Submodelle bereitzustellen, eine Contract Negotiation und den dazugehörigen Transfer des Keycloak-Tokens durchzuführen und schlussendlich den Zugriff auf die Submodelle zu ermöglichen.
2.5.4.1.1	BaSyx-Backend
Im Rahmen des Berichtzeitraums wurde das Eclipse BaSyx Sicherheitsfeature eingesetzt und weiterentwickelt, um eine regelbasierte Zugriffssteuerung zu ermöglichen. BaSyx gliedert sich in mehrere Komponenten: das AAS-Repository, Submodel-Repository und ConceptDescription-Repository sowie die AAS-Registry, Submodel Registry und den AAS-Discovery Service. Die ers-ten drei Repository-Komponenten werden häufig als "AAS-Environment" zusammengefasst.
Das Sicherheitsfeature implementiert zunächst eine RBAC in Verbindung mit Keycloak, das als Identity Provider fungiert. Nutzer und deren Rollen werden in Keycloak gespeichert, während die Zugriffsregeln in BaSyx hinterlegt sind, um den Zugriff auf Ressourcen im Backend zu steuern. Diese Regeln werden in einer oder mehreren JSON-Dateien als Array abgelegt und folgen dem JSON-Schema in Fehler! Verweisquelle konnte nicht gefunden werden., das die Definition von Rollen, erlaubten Aktionen und Zielinformationen, bzw. die betroffenen Ressourcen umfasst.
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "title": "RBAC Rules",
  "description": "A list of RBAC rules for roles and target components.",
  "type": "array",
  "items": {
    "type": "object",
    "required": ["role", "action", "targetInformation"],
    "properties": {
      "role": {
        "type": "string"
      },
      "action": {
        "oneOf": [
          {
            "type": "string",
            "enum": ["CREATE", "READ", "UPDATE", "DELETE", "EXECUTE"]
          },
          {
            "type": "array",
            "items": {
              "type": "string",
              "enum": ["CREATE", "READ", "UPDATE", "DELETE", "EXECUTE"]
            },
            "minItems": 1
          }
        ]
      },
      "targetInformation": {
        "type": "object",
        "required": ["@type"],
        "properties": {
          "@type": {
            "type": "string",
            "enum": [
              "aas",
              "submodel",
              "concept-description",
              "aas-environment",
              "aas-registry",
              "submodel-registry",
              "aas-discovery-service"
            ]
          },
          "aasIds": {
            "oneOf": [
              { "type": "string" },
              {
                "type": "array",
                "items": { "type": "string" }
              },
              { "type": "null" }
            ]
          },
          "submodelIds": {
            "oneOf": [
              { "type": "string" },
              {
                "type": "array",
                "items": { "type": "string" }
              }
            ]
          },
          "submodelElementIdShortPaths": {
            "oneOf": [
              { "type": "string" },
              {
                "type": "array",
                "items": { "type": "string" }
              }
            ]
          },
          "conceptDescriptionIds": {
            "oneOf": [
              { "type": "string" },
              {
                "type": "array",
                "items": { "type": "string" }
              }
            ]
          },
          "assetIds": {
            "type": "array",
            "items": {
              "type": "object",
              "required": ["name", "value"],
              "properties": {
                "name": { "type": "string" },
                "value": { "type": "string" }
              }
            }
          }
        },
        "additionalProperties": false
      }
    },
    "additionalProperties": false
  }
}
Listing 2 1: RBAC Rules JSON Schema
Die als JSON-Objekte definierten Regeln bestehen aus mehreren Schlüssel-Properties. Die "role" beschreibt den Namen der Rolle, während "action" die erlaubten Aktionen wie "CREATE", "READ", "UPDATE", "DELETE" und "EXECUTE" umfasst. Die "targetInformation" gibt die Res-source an, auf welche die Regel angewendet wird. Hierbei ist "@type" entscheidend, da es den Typ der Ressource festlegt, wobei die Optionen "aas", "submodel", "concept-description", "aas-environment", "aas-registry", "submodel-registry" und "aas-discovery-service" zur Verfügung ste-hen. Zusätzlich können für die spezifischen Ressourcen, je nach Typ ("@type"), weitere Properties definiert werden, die die Identifizierung von AAS-, Submodel- oder Concept-Description-Repository, sowie den Registries und dem Discovery Service ermöglichen. Die Typen "aas", "sub-model" und "concept-description" können auch hier wieder als "aas-environment" zusammenge-fasst werden
Für "@type": "aas" lautet die nachfolgende Property "aasIds", welche als Wert entweder einen String oder einen Array von Strings mit den AASIdentifiern, für die diese Regel gilt, hat. 
Beispiel
{
  "role": "basyx-reader",
  "action": "READ",
  "targetInformation": {
    "@type": "aas",
    "aasIds": "*"
  }
}
Listing 2 2: Beispiel einer AAS Repository Rolle
Für "@type": "submodel" lauten die nachfolgenden Properties "submodelIds" und optional "sub-modelElementIdShortPaths", welche als Wert entweder einen String oder einen Array von Strings mit dem SubmodelIdentifiern bzw. SubmodelElementIdShortPaths für die diese Regel gilt, haben. Werden die SubmodelElementsIdShortPaths nicht explizit angegeben, sind implizit alle Submo-delElemente des betroffenen Submodels für die definierten Aktionen zugänglich. 
Beispiel
{
  "role": "basyx-reader",
  "action": "READ",
  "targetInformation": {
    "@type": "submodel",
    "submodelIds": "*",
    "submodelElementIdShortPaths": "*"
  }
}
Listing 2 3: Beispiel einer Submodel Repository Rolle
Für "@type": "concept-description" lautet die nachfolgende Property "conceptDescriptionIds", welche als Wert entweder einen String oder einen Array von Strings mit dem ConceptDescriptio-nIdentifiern, für welche diese Regel gilt, hat.
Beispiel:
{
  "role": "basyx-reader",
  "action": "READ",
  "targetInformation": {
    "@type": "concept-description",
    "conceptDescriptionIds": "*"
  }
}
Listing 2 4: Beispiel einer Concept Description Repository Rolle
Für "@type": "aas-environment" können dieselben Properties der Typen "aas", "submodel" und "concept-description" folgen.
Beispiel
{
  "role": "admin",
  "action": ["CREATE", "READ", "UPDATE", "DELETE"],
  "targetInformation": {
    "@type": "aas-environment",
    "aasIds": "*",
    "submodelIds": "*"
  }
}
Listing 2 5: Beispiel einer AAS Environment Rolle
Für "@type": "aas-registry" lautet die nachfolgende Property, wie bei "aas", ebenfalls "aasIds" welche als Wert entweder einen String oder einen Array von Strings mit dem AASIdentifiern, für welche diese Regel gilt, hat.
Beispiel
{
  "role": "basyx-reader",
  "action": "READ",
  "targetInformation": {
    "@type": "aas-registry",
    "aasIds": "*"
  }
}
Listing 2 6: Beispiel einer AAS Registry Rolle
Für "@type": "submodel-registry" lautet die nachfolgende Property, wie bei "submodel", ebenfalls "submodelIds", welche als Wert entweder einen String oder einen Array von Strings mit dem Sub-modelIdentifiern, für welche diese Regel gilt, hat.
Beispiel
{
  "role": "basyx-reader",
  "action": "READ",
  "targetInformation": {
    "@type": "submodel-registry",
    "submodelIds": "*"
  }
}
Listing 2 7: Beispiel einer Submodel Registry Rolle
Für "@type": "aas-discovery-service" lautet die nachfolgende Property, wie bei "aas" und "aas-registry", ebenfalls "aasIds", welche als Wert entweder einen String oder einen Array von Strings mit dem AASIdentifiern, für welche diese Regel gilt, hat, gefolgt von der Property "assetIds", durch welche die erlaubten AssetIds bestimmt werden. Hier gilt die Besonderheit, dass eine AssetId selbst aus zwei Werten bestimmt wird, daher als Objekt, bestehend aus den Properties "name" und "value" angegeben wird. wenn keine AssetIds erlaubt sein sollen, muss diese Property als leeres Array angegeben werden. andernfalls als Array von Objekten mit den genannten Proper-ties.
Beispiel
{
  "role": "basyx-aas-discoverer",
  "action": "READ",
  "targetInformation": {
    "@type": "aas-discovery-service",
    "aasIds": null,
    "assetIds": [
      {
        "name": "*",
        "value": "*"
      }
    ]
  }
}
Listing 2 8: Beispiel AAS Discovery Service Rolle
Für Alle Properties nach @type kann auch das Wildcard Symbol "*" angegeben werden, um alle Ressourcen der betroffenen Komponente zu erlauben (Wie in den Beispielen bereits exzessiv genutzt). Es existiert keine Ausschluss-Syntax, um auszudrücken, dass "alle außer ..." erlaubt sind. Daher müssen alle zulässigen Ressourcen stets explizit angegeben werden, sofern nicht alle Ressourcen erlaubt sind.
Für die Anbindung an Catena-X wurde eine klare Zuordnung zwischen Rolle und BPN geschaf-fen, indem die BPN selbst direkt als Rolle verwendet wurde. Eine Beispielregel könnte damit fol-gendermaßen aussehen:
{
  "role": "BPNL000000OEM1AT",
  "action": "READ",
  "targetInformation": {
    "@type": "aas-environment",
    "aasIds": "https://example.com/ids/sm/1203_7012_1142_1277_OEM1",
    "submodelIds": [
      "https://admin-shell.io/idta/SubmodelTemplate/DigitalNameplate/2/0_OEM1",
      "https://admin-shell.io/idta/SubmodelTemplate/HandoverDocumentation/1/0_OEM1",
      "https://admin-shell.io/idta-02023-1-0_OEM1",
      "https://admin-shell.io/ZVEI/TechnicalData/Submodel/1/2_OEM1",
      "https://admin-shell.io/IDTA-CATENAx/BatteryData/Submodel/1/0_OEM1",
      "https://example.com/ids/sm/8471_7012_1142_8921_OEM1",
      "https://example.com/ids/sm/1203_7012_1142_2277_OEM1"]
  }
}
Listing 2 9: CATENA-X Regel mit BPN als Rolle
Diese Regeln werden in einer oder mehreren JSON-Dateien in einem bestimmten Verzeichnis ge-pflegt.  Da die BaSyx Komponenten jeweils in einem eigenen Docker Container liegen, wird dieses Verzeichnis entsprechend für jeden Container explizit gemountet, also in den jeweiligen Container gespiegelt. 
Um den Authentifizierungsworkflow abzuschließen, ist es notwendig, die entsprechenden Nutzer und Rollen in Keycloak anzulegen.
2.5.4.1.2	Konnektoren
2.5.4.1.2.1	Asset
POST {{PROVIDER_MANAGEMENT_URL}}/v3/assets
{
  "@context": {
    "edc": "https://w3id.org/edc/v0.0.1/ns/",
    "cx-common": "https://w3id.org/catenax/ontology/common#",
    "cx-taxo": "https://w3id.org/catenax/taxonomy#",
    "dct": "http://purl.org/dc/terms/"
  },
  "@id": "{{ASSET_ID}}",
  "properties": {
    "cx-common:version": "3.0"
  },
  "privateProperties": {
  },
  "dataAddress": {
    "@type": "DataAddress",
    "type": "HttpData",
    "baseUrl": "{{PROVIDER_VWS_ENVIRONMENT}}",
    "proxyQueryParams": "true",
    "proxyPath": "true",
    "proxyMethod": "false",
    "oauth2:tokenUrl": "{{CATENAX_CENTRALIDENTITY PROVIDER_TOKEN_URL}}",
    "oauth2:clientId": "{{PROVIDER_CLIENT_ID}}",
    "oauth2:clientSecretKey": "{{PROVIDER_CLIENT_SECRET_KEY}}"
  }
}
Listing 2 10: Asset
2.5.4.1.2.2	Policy
POST {{PROVIDER_MANAGEMENT_URL}}/v3/policydefinitions
{
  "@context": {
    "odrl": "http://www.w3.org/ns/odrl/2/"
  },
  "@type": "PolicyDefinitionRequestDto",
  "@id": "{{ASSET_ID}}-policy",
  "policy": {
    "@type": "odrl:Set",
    "odrl:permission": [
      {
        "odrl:action": "USE",
        "odrl:constraint": {
          "@type": "LogicalConstraint",
          "odrl:or": [
            {
              "@type": "Constraint",
              "odrl:leftOperand": {
             "@id": "BusinessPartnerNumber"
              },
              "odrl:operator": {
                "@id": "odrl:eq"
              },
              "odrl:rightOperand": "{{CONSUMER_BPN}}"
            }
          ]
        }
      }
    ]
  }
}
Listing 2 11: Policy
2.5.4.1.2.3	Contract
POST {{PROVIDER_MANAGEMENT_URL}}/v3/contractdefinitions
{
    "@context": {},
    "@id": "{{ASSET_ID}}-contract",
    "@type": "ContractDefinition",
    "accessPolicyId": "{{ASSET_ID}}-policy",
    "contractPolicyId": "{{ASSET_ID}}-policy",
    "assetsSelector": {
        "@type": "CriterionDto",
        "operandLeft": "https://w3id.org/edc/v0.0.1/ns/id",
        "operator": "=",
        "operandRight": "{{ASSET_ID}}"
    }
}
Listing 2 12: Contract
2.5.4.2	Data Consumption
Zuerst muss der Katalog angefragt werden, um eine Offer-ID zu erhalten. Dies geschieht durch eine Anfrage an den Katalog via POST zu der URL {{CONSU-MER_MANAGEMENT_URL}}/v3/catalog/request. Dabei müssen die relevanten Parameter wie counterPartyAddress und counterPartyId angegeben werden.
Mit der erhaltenen Offer-ID wird als nächstes die Contract Negotiation durchgeführt. Dieser Schritt umfasst die Verhandlung der Vertragsbedingungen und die Festlegung der Vereinbarungen zwi-schen den beteiligten Parteien.
Nachdem die Contract Negotiation abgeschlossen ist, wird das daraus resultierende Contract Ag-reement abgefragt, um die ID des Vertrags zu erhalten. Diese ID ist für die weiteren Schritte not-wendig, um den Datentransferprozess unter dem Provider und Consumer zu identifizieren.
Zuletzt wird der Transferprozess durchgeführt, wobei ein Token generiert wird, der zum Zugriff auf BaSyx genutzt werden kann. Dieser Token ermöglicht den sicheren und autorisierten Zugriff auf die Daten und Ressourcen, die im BaSyx-System gespeichert sind.





2.5.4.2.1	Datentransfer über Konnektoren
Catalog Request
POST {{CONSUMER_MANAGEMENT_URL}}/v3/catalog/request
{
    "@context": {
        "@vocab": "https://w3id.org/edc/v0.0.1/ns/"
    },
    "@type": "CatalogRequest",
    "counterPartyAddress": "{{PROVIDER_PROTOCOL_URL}}",
    "counterPartyId": "{{PROVIDER_BPN}}",
    "protocol": "dataspace-protocol-http",
    "querySpec": {
        "offset": 0,
        "limit": 50
    }
}
Listing 2 13: Catalog Request
Contract Negotiation
POST {{CONSUMER_MANAGEMENT_URL}}/v3/contractnegotiations
{
    "@context": {
        "@vocab": "https://w3id.org/edc/v0.0.1/ns/"
    },
    "@type": "NegotiationInitiateRequestDto",
    "counterPartyAddress": "{{PROVIDER_PROTOCOL_URL}}",
    "protocol": "dataspace-protocol-http",
    "policy": {
        "@context": "http://www.w3.org/ns/odrl.jsonld",
        "@type": "odrl:Offer",
        "@id": "{{OFFER_ID}}",
        "target": "{{ASSET_ID}}",
        "assigner": "{{PROVIDER_BPN}}",
        "odrl:permission": {
            "odrl:target": "{{ASSET_ID}}",
            "odrl:action": {
                "odrl:type": "USE"
            },
            "odrl:constraint": {
                "odrl:or": {
                    "odrl:leftOperand": "BusinessPartnerNumber",
                    "odrl:operator": {
                        "@id": "odrl:eq"
                    },
                    "odrl:rightOperand": "{{CONSUMER_BPN}}"
                }
            }
        },
        "odrl:prohibition": [],
        "odrl:obligation": []
    }
}
Listing 2 14: Contract Negotiation
Transfer Process
GET {{CONSUMER_MANAGEMENT_URL}}/v3/contractnegotiations/{{NEGOTIATION_ID}}
POST {{CONSUMER_MANAGEMENT_URL}}/v3/transferprocesses
{
    "@context": {
        "@vocab": "https://w3id.org/edc/v0.0.1/ns/"
    },
    "@type": "TransferRequest",
    "protocol": "dataspace-protocol-http",
    "counterPartyAddress": "{{PROVIDER_PROTOCOL_URL}}",
    "contractId": "{{CONTRACT_AGREEMENT_ID}}",
    "transferType": "HttpData-PULL",
    "dataDestination": {
        "type": "HttpProxy"
    },
    "connectorId": "{{CONSUMER_BPN}}",
    "privateProperties": {},
    "callbackAddresses": []
}
Listing 2 15: Transfer Process
Zugriff auf das Token 
Der Datentransfer, der im vorherigen Kapitel durchgeführt wurde, ermöglicht die Generierung ei-nes Access-Tokens für einen Client aus dem Keycloak Identity-Provider, welcher eine Berechti-gung auf das BaSyx-Backend besitzt.
{
  "@context": "https://w3id.org/dspace/2024/1/context.json",
  "@type": "dspace:TransferStartMessage",
  "dspace:providerPid": "urn:uuid:a343fcbf-99fc-4ce8-8e9b-148c97605aab",
  "dspace:consumerPid": "urn:uuid:32541fe6-c580-409e-85a8-8a9a32fbe833",
  "dspace:dataAddress": {
    "dspace:endpointType": "https://w3id.org/idsa/v4.1/HTTP",
    "dspace:endpoint": "BASYX BACKEND API ENDPOINT",
    "dspace:endpointProperties": [
      {
        "dspace:name": "https://w3id.org/edc/v0.0.1/ns/authorization",
        "dspace:value": "AUTH TOKEN"
      },
      {
        "dspace:name": "https://w3id.org/edc/v0.0.1/ns/authType",
        "dspace:value": "bearer"
      },
      {
        "dspace:name": "https://w3id.org/tractusx/auth/refreshToken",
        "dspace:value": "REFRESH TOKEN"
      },
      {
        "dspace:name": "https://w3id.org/tractusx/auth/expiresIn",
        "dspace:value": "300"
      },
      {
        "dspace:name": "https://w3id.org/tractusx/auth/refreshEndpoint",
        "dspace:value": "REFRESH ENDPOINT"
      }
    ]
  }
}
Listing 2 16: Zugriff auf das Token
Zugriff auf das BaSyx-Backend
Der Zugriff auf das BaSyx Backend ist durch OAuth 2.0 mit Json-Web-Tokens (JWT) gesichert und erfolgt in zwei Schritten (Siehe Kapitel 2.6.4.1.2). Dabei müssen sich die Benutzer gegenüber Keycloak mit Basic Auth authentifizieren. Dadurch erhalten sie ein JWT-Token, mit dem sie sich im Anschluss gegen das Backend authentifizieren können.  Dies Authentifizierung gegen Keycloak erfolgt über die Access Token URL, die bei der verwendeten Version 25.0.6 stets dem Schema https://<KEYCLOAK-HOST>/realms/<REALM-NAME>/protocol/openid-connect/token folgt. Für die initiale Authentifizierung gibt es zwei Möglichkeiten:
(1) Nur mit Client Credentials im HTTP-Header oder
(2) durch die zusätzliche Übermittlung von Benutzeranmeldedaten im Body.
Im zweiten Fall (2) enthält das erhaltene Token Informationen über die Rolle des Nutzers, welche für die RBAC Authorisierung benötigt werden. In beiden Fällen (1 und 2) werden immer die Client Credentials als Basic Auth im Header übermittelt. Sie bestehen aus Client ID und Client Secret. Diese Informationen werden in dem Format <Client ID>:<Client Secret> in Base64 kodiert. Dann wird das Header-Feld "Authorization" erstellt und als Wert "Basic ", (gefolgt von einem Leerzei-chen) und den kodierten Anmeldedaten übergeben. Die Client Credentials können in Keycloak in der Clients Sektion gefunden werden. 
 
Abbildung 2 12: Keycloak Admin Console – Client ID + Client Secret
Dafür meldet man sich in der Keycloak Admin Console an, wechselt zu dem gewünschten Realm und wählt im Linken Menü Clients aus. Daraufhin wird eine Liste von Clients angezeigt, aus der man den betroffenen Client auswählt. Unter dem Reiter Settings findet man die Client ID und un-ter Credentials das Client Secret.
Um zusätzlich einen Nutzer zu Authentifizieren (2), werden die User Credentials im Body der Au-thentifizierungs Anfrage in dem Folgenden Format mitgegeben:
grant_type=password
username=<username>
password=<password>scope=openid
Listing 2 17: User Credentials im Body einer Authentifizierungsanfrage
Da die User Credentials im Body im Klartext übertragen werden und auch die Client Credentials im Header ohne weiteres in ein lesbares Format gebracht werden können, ist an dieser Stelle unbe-dingt die Verwendung von https zu empfehlen. 
Nach erfolgreicher Authentifizierung stellt Keycloak ein JWT-Token aus. Dieses Token dient zur Authentifizierung des Benutzers gegenüber dem BaSyx Backend und enthält die Rollen und Be-rechtigungen, die für den Zugriff auf die Ressourcen erforderlich sind. Die definierten RBAC-Regeln steuern den Zugriff auf verschiedene Endpunkte der Repositories, Registries und des Discovery Services.
Der weitere Authentifizierungsfluss mit dem Token erfolgt so, dass das JWT-Token in den HTTP-Header jeder nachfolgenden Anfrage an das Backend eingefügt wird. Dies geschieht im Header-Feld "Authorization" mit dem Präfix "Bearer ". Das Token wird bei jeder Anfrage an das BaSyx Backend überprüft, um sicherzustellen, dass er gültig ist und die erforderlichen Berechtigungen für den angeforderten Zugriff vorhanden sind. Keycloak selbst wird nicht für jede Anfrage direkt an-gesprochen; stattdessen erfolgt die Validierung des Tokens durch die Backend-Anwendung, die sicherstellt, dass der Token nicht abgelaufen ist und die richtigen Rollen und Berechtigungen ent-hält.
2.5.5	Ergebnis
Als Ergebnis steht am Ende dieses Arbeitspakets ein voll funktionsfähiger Projektdemonstrator zur Verfügung, der nicht nur die technische Machbarkeit des PoCs beweist, sondern auch konkrete Vorschläge und technische Spezifikationen liefert. Diese können die Grundlage für zukünftige Standardisierungsprozesse innerhalb relevanter Organisationen wie Catena-X und der IDTA bil-den.
 
2.6	AP 11.3 – Identity & Access Management (IAM)
2.6.1	Zielsetzung
In diesem Abschnitt werden die in den vorherigen Arbeitspaketen gewonnenen Erkenntnisse im Hinblick auf Security-Aspekte zusammengefasst. Zudem werden relevante Begriffe erläutert und ein Ausblick darauf gegeben, wie die erarbeiteten Lösungen in der Zukunft noch optimiert und weitergeführt werden können.
2.6.2	Vorgehensweise und Inhalte
Grundsätzlich lassen sich zwei Ebenen bei der Betrachtung von Security-Aspekten unterscheiden. Die erste Ebene bezieht sich auf die Authentifizierung und Autorisierung von Benutzern oder Sys-temen. Hier stellt sich die Frage, wer sich wie authentifizieren kann und welche zusätzlichen Infor-mationen zur Autorisierung bereitgestellt werden müssen.
Die zweite Ebene bezieht sich auf die verwendete Infrastruktur. Dabei geht es darum, wie die Au-thentifizierung geregelt wird (zentral oder dezentral) und welche Kombinationen möglich sind.
Im ersten Abschnitt werden wir uns mit der Idee hinter der IDTA Security Spezifikation beschäfti-gen, die sich hauptsächlich auf RBAC und ABAC stützt. Dabei spielt auch die Verwendung von Identity Providern eine wichtige Rolle und wie diese in verschiedenen Szenarien eingesetzt wer-den können. Es werden verschiedene Szenarien durchgespielt, um zu verdeutlichen, wie Identity Provider in der Praxis eingesetzt werden können. Dabei wird auch auf die Vor- und Nachteile ver-schiedener Implementierungen eingehen.
Nach Aufbau der Verbindung schlägt die IDTA-Sicherheitsspezifikation die Verwendung eines JSON-Web-Tokens (JWT-Tokens) zur Absicherung des Kommunikationskanals vor. JWT-Tokens sind in der aktuellen Kommunikation mit REST nicht mehr wegzudenken und hinlänglich bekannt. In einem der nachfolgenden Kapitel wird deshalb nur kurz auf JWT-Tokens und weitere Möglich-keiten eingegangen.
Um einen sicheren Kommunikationskanal einzurichten, ist es in der Regel erforderlich, sicherzu-stellen, dass der Kommunikationspartner ein berechtigtes Interesse an den zu übermittelnden Daten hat. In der Umgebung von Catena-X wird dazu eine Business Partner Number (BPN) ver-wendet, die entsprechend abzusichern ist. Die BPN kann durch eine Signatur des zentralen An-bieters geschützt oder alternativ eine Dezentrale ID (DID) verwendet werden.
2.6.3	Authentifizierung
2.6.3.1	Der allgemeine Ablauf
Die Authentifizierung bei einem Data Provider erfolgt derzeit über die BPN, siehe Abbildung 2 13. Mit der BPN kann man bei einem Data Provider einen Katalog anfordern, welcher Informationen über den möglichen Zugriff enthält. Ohne die BPN stellt der Data Provider entweder keine oder nur allgemeine Daten zur Verfügung. 
Eingeschränkt wird diese Liste vom Data Provider, durch die Angabe von Regeln (Policies). D.h. der Data Provider definiert Regeln, welche sich für eine Business Partner auf die Auswahl der Einträge im Katalog (catalog) auswirkt. 
 
Abbildung 2 13: Authentifizierungs-Workflow
Aus dem Katalog (catalog) wird ein passendes Angebot (offer) ausgewählt. Der Data Provider bestätigt das Angebot anschließend in Form einer Vereinbarung (agreement). Damit kommt ein Vertrag (contract) zwischen dem Data Consumer und Data Provider zustande. Auf Basis der aus-getauschten Daten wird dann der Zugriff auf bestimmte Bereiche des Data Providers freigegeben.
2.6.3.1.1	Policies
Der Katalog mit den Angeboten wird für einen Interessenten dynamisch erstellt. Um die Auswahl der relevanten Angebote für den Interessenten im Katalog einzuschränken, sind Auswahlregeln notwendig. Hierfür werden in diesem Fall Policies verwendet. Policies sind "Wenn-Dann"-Regeln – wenn die Bedingung erfüllt ist, wird das Angebot in den Katalog aufgenommen.
2.6.3.1.2	IDTA Security Spezifikation
Diese Spezifikation zielt darauf ab Einschränkungen der zu übermittelten Daten (und nicht des Angebots) vorzunehmen. Grundsätzlich spricht nichts dagegen die Regeln der IDTA Security Spezifikation auch auf die Angebote des Katalogs anzuwenden. Im Moment findet die Auswahl des Angebots auf Basis der Policies statt. Um die IDTA Security Spezifikation auch auf die Filte-rung des Angebotskatalogs anzuwenden, müssen die bisherigen Implementierungen auf Basis der Policies angepasst oder ersetzt werden.
2.6.3.2	Konsequenzen aus dem allgemeinen Ablauf
Wie aus den Ausführungen hervorgeht, gibt es auf Data Provider Seite keine speziellen Zugriffe für ausgewählte Personen, Personengruppen oder Subjekte (z.B. eine Maschine). Mit der BPN identifiziert man sich als interessierter Business Partner.
Die tatsächliche Auswahl geht vom Data Consumer aus, indem er aus dem Katalog ein Angebot auswählt. Beispielsweise gibt es auf Seiten des Consumers zwei verschiedene Gruppen. Beide benötigen verschiedene Informationen über die Produkte des Data Providers. Der Data Provider stellt also zwei unterschiedliche Angebote (im Katalog) für die beiden Gruppen zur Verfügung. Der Data Consumer wählt dann anhand der Zugehörigkeit der Person zu einer Gruppe das passende Angebot aus.
Exkurs: Durch die Einführung einer individuellen Anmeldung eines Users kann der Data Provider die Kontrolle über den Zugriff auf seine Daten verbessern. Erreichen könnte man dies, indem man einen speziellen Eintrag im Katalog anbietet, der eine individuelle Anmeldung eines Users erfor-derlich macht. Hierfür ist eine Erweiterung (Extension) des EDC auf Seiten des Data Providers notwendig. Zusätzlich muss der Data Provider eine Erfassung der angemeldeten User ermögli-chen, indem er eine Identity Provider Funktionalität bereitstellt. Durch die individuelle Anmeldung eines Users kann der Data Provider sicherstellen, dass nur autorisierte Benutzer Zugriff auf seine Daten erhalten. Hierbei kann er auch die Rollen und Berechtigungen der Benutzer berücksichti-gen und so ein höheres Maß an Sicherheit gewährleisten.
2.6.3.3	BPN Security
Aktuell sind zwei Verfahren spezifiziert, welche die Absicherung der BPN gewährleisten. 
Bei dem vermutlich bekannteren Verfahren registriert man eine BPN bei einer zentralen Stelle. Nach der Registrierung kann eine signierte BPN angefordert werden, die dann an den Data Pro-vider zur Authentifizierung des Business Partners weitergereicht werden kann. Dieses Verfahren ähnelt stark dem Austausch von Zertifikaten.
Eine weitere Möglichkeit ist die Verwendung einer DID. Dieses Verfahren ist ähnlich zum vorheri-gen, mit dem Unterschied, dass eine DID vom Besitzer angepasst werden kann. Der Aussteller bestätigt die DID und übermittelt sie an das Subject (z.B. die Person), welches sie beantragt hat. Die DID ist dann im Besitz des Antragsstellers. Anschließend kann der Inhalt an die jeweilige Auf-gabe angepasst und in Form eines Verifiable Credential (VC) an den Data Provider übergeben werden. Für die Bestätigung der Gültigkeit der ursprünglich übermittelten Daten ist dann erneut die Bestätigung des Ausstellers (insbesondere der DID) erforderlich.
Exkurs: Da der Besitzer einer DID diese anpassen kann, könnte man sich beispielsweise vorstel-len, dass der Consumer seine DID bzw. die VC so erweitert, dass der Data Provider zusätzliche Informationen erhält (z.B. eine Rolle), die es ermöglichen, den Katalog gezielter anzupassen. Im Gegensatz zur ursprünglichen Variante kann der Data Provider nun genauer entscheiden, welche Angebote er welchem Anfragenden anbietet.
2.6.4	Autorisierung
Die Autorisierung erfolgt in zwei verschieden Abschnitten. Zunächst findet beim Data Provider eine Filterung der möglichen Angebote anhand der BPN statt. Hat der Data Consumer dann einen Vertrag mit dem Data Provider geschlossen, bekommt der Data Consumer ein Access-Token, wel-cher weitere Informationen (Claims) enthält. Diese Informationen machen bei Zugriffen auf die Daten des Data Provider anschließend eine weitere Filterung der Daten möglich.
Die Prüfungen, welche bei Zugriff erfolgen, sind in der IDTA Security Spezifikation beschrieben. Grundlage zur Autorisierung ist ein JWT-Token.
2.6.4.1	Token
Tokens sind die etablierte Methode Security-Informationen über eine REST-Schnittstelle auszu-tauschen. Grundsätzlich sind zwei verschieden Arten von Tokens üblich. Das Opaque-Token wird in dieser Konstellation nicht verwendet und wird hier nur der Vollständigkeit halber ebenfalls be-schrieben.
2.6.4.1.1	Opaque-Token
Dieses Token ist ein einfacher String. Der Identity Provider des Data Provider muss immer bei dem ausstellenden Identity Provider die Gültigkeit des Tokens bestätigen lassen. Es enthält keine zu-sätzlichen Informationen über den Aufrufer. Der Vorteil ist, dass das Token jederzeit vom ausstel-lenden Identity Provider widerrufen werden kann.
2.6.4.1.2	JWT (Json-Web-Token)
JWT-Tokens sollten aus der allgemeinen Literatur bereits bekannt sein. Ein kurzer Überblick über das Verfahren:
Ein JWT-Token besteht aus drei Teilen, die durch Punkte getrennt sind, und wird in der Regel über HTTPS übertragen. Der erste Teil enthält die sogenannten Header, also Metadaten über den Token. Der zweite Teil enthält die Nutzlast, also die eigentlichen Daten. Der dritte Teil ist die Signatur, die sich aus dem Hash des ersten und zweiten Teils sowie einem geheimen Schlüssel zusammensetzt. JWT-Tokens bieten eine sichere Möglichkeit, Ansprüche zwischen zwei Parteien auszutauschen, ohne dass eine zentrale Authentifizierungsinstanz erforderlich ist. Zur Validierung der Signatur wird der öffentliche Schlüssel des Austellers (Identity Provider) benötigt.
2.6.4.1.3	Access-Token
Das Access-Token ist der generelle Schlüssel für die die Autorisierung innerhalb einer Anwen-dung. Die Nutzlast kann Daten (Claims) wie beispielsweise Rollen enthalten, die bei der Überprü-fung von Zugriffsberechtigungen verwendet werden. Das Token kann nicht widerrufen werden, sondern enthält lediglich ein Ablaufdatum.
Da das Access-Token sehr viele Fragen bzgl. des Inhaltes offen lässt, wurde zusätzlich das ID-Token (Connect ID) spezifiziert welches die Inhalte genauer festlegt. Für die Sicherstellung, dass der Zugriff erlaubt ist, ist aber allein das Access-Token relevant.
2.6.4.2	Claims, Scopes, Rollen
Ein JWT-Token kann neben der grundlegenden Authentifizierung auch zusätzliche Informationen in Form von Claims enthalten. Die folgenden Informationen dienen einer Erläuterung der Begriffe Claims, Scopes und Rollen.
2.6.4.2.1	Claims
In einem JWT ist ein ‚Claim-Assertion‘ eine Information in Form eines Key-Value Paares. Der Wert kann ein einzelner Wert oder auch ein Array von Werten sein. Durch einen Claim-Assertion bestä-tigt der ausstellende Identity Provider die Gültigkeit eines bestimmten Attributes mit einem spezifi-schen Wert. Beispiele für Claims sind z.B. ‚sub‘ (Subject) für den Benutzernamen, ‚scope‘ für Be-rechtigungen oder ‚role‘ für Rollen.
2.6.4.2.2	Scope
Ein Scope ist normalerweise ein festgelegter Begriff, der sowohl in Anfragen als auch in Antworten verwendet wird. Ein Scope definiert einen bestimmten Umfang an Claims, also die Informationen, die in einem Token enthalten sein sollen.  Darüber hinaus kann ein Scope festlegen, welche Akti-onen oder Ressourcen einem Benutzer erlaubt sind.
Wenn ein Scope in einer Anfrage angegeben ist, muss das zurückgegebene Token die entspre-chenden Claims enthalten. Identity Provider können Scopes auch als optional definieren. Optio-nale Scopes werden vom Identity Provider standardmäßig bereitgestellt, falls sie nicht explizit in der Anfrage angegeben wurden.
Bei fehlenden, nicht als optional markierten Scopes, kann dies zu unterschiedlichen Folgen füh-ren. Manche Identity Provider zeigen eine Fehlermeldung an, andere erzeugen ein Token ohne die notwendigen Berechtigungen.
2.6.4.2.3	Rollen
Während standardisierte Claims wie ‚sub‘ oder ‚scope‘ feste Bedeutungen haben, sind Rollen nicht standardisiert. Sie können aber zusätzlich im JWT-Token angegeben werden, um dem Be-nutzer spezifische Rechte oder Verantwortlichkeiten zuzuordnen.
2.6.5	Regeln – IDTA Security Spezifikation
Die Regeln zur Authentifizierung und Autorisierung sind in der IDTA Security Spezifikation be-schrieben und haben folgendes Prinzip: Zum Vergleich werden die Attribute der Modelle und Submodelle herangezogen. Als Ziel der Regeln können einzelne Attribute, ganze Modelle oder Submodelle dienen.
Zum Vergleich stehen dann verschieden Optionen offen.
•	Vergleiche mit anderen Attributen
•	Festgelegte Werte (z.B. ein Datum ‚freigegeben ab‘)
•	Claims aus den Access-Tokens (z.B. eine bestimmte Rolle)
2.6.6	Identity Provider
Ein Identity Provider stellt das Access-Token zum Zugriff auf eine Ressource (Modelle und Sub-modelle) aus. Diese können in unterschiedlichen Varianten zentraler und dezentraler Identity Pro-viders ausfallen.
Die grundlegende Herausforderung besteht darin, dass der Data Provider dem Identity Provider vertrauen muss. Vertrauen bedeutet in diesem Kontext, dass der Identity Provider die Access-Tokens signiert und der Data Provider anhand dieser Signatur die Gültigkeit des Tokens überprü-fen kann. Wie bereits erwähnt, benötigt man einen zentralen Identity Provider, um eine überprüf-bare BPN (Business Partner Number) zu gewährleisten. Zusätzlich werden oft weitere Claims be-nötigt, um die Sicht auf die BPN einzuschränken. Um solche Claims zu definieren, benötigt der Data Provider Zugriff auf den zentralen Identity Provider.
Ein Identity Provider stellt Access-Tokens zur Verfügung, um den Zugriff auf Ressourcen wie Mo-delle und Submodelle zu ermöglichen. Dabei gibt es verschiedene Varianten von Identity Provi-ders – zentrale und dezentrale Identity Providers. Im Folgenden werden die unterschiedlichen Möglichkeiten betrachtet
2.6.6.1	Keine Authentifizierung/Autorisierung
Liegt keine Authentifizierung in Form einer BPN vor, können trotzdem die vom Data Provider als öffentlich gekennzeichneten Daten abgerufen werden, siehe Abbildung 2 14.
 
Abbildung 2 14: Unauthenticated Access
2.6.6.2	Interne Authentifizierung/Autorisierung
In diesem Fall ist der Identity Provider auf die Ressourcen des Data Providers abgestimmt. Aller-dings muss der Data Provider in diesem Fall auch extern gepflegte Informationen, wie zum Bei-spiel die BPN, zusätzlich in seinem System hinterlegen. Dies kann zu Problemen führen, wenn diese externen Daten synchron gehalten werden müssen, siehe Abbildung 2 15.
 
Abbildung 2 15: Internal Authentication
2.6.6.3	External und internal Identity Providers
In diesem Aufbau ist der externe Identity Provider für die Authentifizierung verantwortlich, siehe Abbildung 2 16. Dabei werden die folgenden Schritte durchlaufen:
1.	Der externe Benutzer besorgt sich ein Token beim externen Identity Provider.
2.	Mit dem Token vom externen Identity Provider weißt sich der externe Benutzer beim inter-nen Identity Provider des Data Providers aus.
3.	Der interne Identity Provider des Data Providers überprüft das Token vom externen Identi-ty Provider und stellt das interne Access-Token aus.
4.	Mit dem internen Access-Token weißt sich der externe Benutzer dann gegenüber dem Da-ta Provider aus.
 
Abbildung 2 16: External Authentication
Ein Nachteil ist, dass externe Benutzer für jeden Data Provider einen separaten Token benötigen und sich bei jedem Data Provider erneut anmelden müssen. Durch die Möglichkeit das vom exter-nen Identity Provider erhaltenen Token weiter zu verwenden, entfällt allerdings die erneute Au-thentifizierung.
Exkurs: Verschiedene Identity Providers (z. B. Keycloak) können so konfiguriert werden, dass die Authentifizierung über einen externen Identity Provider erfolgt. Das Access-Token wird weiterhin vom internen Identity Provider ausgestellt. Dadurch verändert sich das Szenario, da die zusätzli-che Kommunikation mit dem externen- vom internen Identity Provider übernommen wird. Allerdings bedeutet dies, dass das Token vom externen Identity Provider nicht zur Verfügung steht. Die Au-thentifizierung muss dann bei jedem Data Provider neu vorgenommen werden.
2.6.6.4	Gateway
Um der Flut von möglichen Access-Tokens entgegenzuwirken, kann die Verwendung eines Gate-ways von Nutzen sein. Der externe Anwender benötigt weiterhin das Token des externen Identity Providers. Damit meldet er sich beim Gateway des Data Provider an. Das Gateway kontaktiert den internen Identity Provider und übergibt ihm das externe Token. Konnte das externe Token vali-diert werden, generiert der interne Identity Provider ein internes Token, das für den Zugriff auf die Ressourcen des Data Provider verwendet wird, siehe Abbildung 2 17.
Bei jedem weiteren Zugriff wird geprüft, ob zum externen Token bereits ein interner Token exis-tiert. In diesem Fall ist die erneuet Generierung eines Tokens über den internen Identity Provider nicht mehr notwendig.
 
Abbildung 2 17: Token Exchange via Gateway
Der Vorteil dieses Ansatzes ist es, dass der externe Anwender nur noch den Token kennen muss, welcher er bei der Authentifizierung beim externen Identity Provider bekommen hat.
2.6.7	Ergebnis
Die beschriebenen Methoden zum Identity- und Accessmanagement gewährleisten einen siche-ren und kontrollierten Datenaustausch und schaffen Grundlagen für zukünftige Weiterentwicklun-gen und Standardisierungen. Es wird eine solide Basis gebildet für die Integration weiterer Si-cherheitsmechanismen und die langfristige Vision einer einheitlichen und sicheren Datenarchitek-tur unterstützt.

