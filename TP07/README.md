# TP 7 – Data Business Policy, Data Governance, Monetarisierung

## Inhalt

[Zielsetzung](#zielsetzung)

[AP 7.1 - Anforderungserhebung](#_7.1)
- [7.1.1 Datenrichtlinien (Data Business Policy)](#_7.1.1)
- [7.1.2 Zugriffskontrolle](#_7.1.2)
- [7.1.3 Rollen und Rechtekonzept](#_7.1.3)
- [7.1.4 Datensicherheit beim Datenaustausch](#_7.1.4)
- [7.1.5 Datensouveränität](#_7.1.5)
- [7.1.6 Datenhaltung (Data Storage Policy) im Hinblick auf die gemeinsame Nutzung](#_7.1.6)
- [7.1.7 Datenhaltungsformate und -infrastrukturen](#_7.1.7)
- [7.1.8 Anbindung an Catena-X](#_7.1.8)
- [7.1.9 Daten-Monetarisierung](#_7.1.9)

[AP 7.2 - Fachliche Konzeption der Daten-Policy entlang der Wertkette](#_7.2)
- [7.2.1 Integration von Data-Governance-Aspekten in das Metamodell der VWS](#_7.2.1)
- [7.2.2 IDS-Architektur](#_7.2.2)
- [7.2.3 Voraussetzungen für den International Data Space (IDS)](#_7.2.3)
- [7.2.4 Datenmonetarisierung](#_7.2.4)

[AP 7.3 - Pilotierung und Erprobung: Erstellung Implementierungsguideline](#_7.3)

[7.4 Fazit](#_7.4)

[Literaturverzeichnis](#literaturverzeichnis)

## Zielsetzung

Das TP 7 "**Data Business Policy, Data Governance, Monetarisierung**" fokussierte auf die effiziente Nutzung von Daten in der Wertschöpfungskette, der Gewährleistung der Datensicherheit und der Schaffung von Mehrwert für Unternehmen, d.h. damit Unternehmen, die innovative Geschäftsmodelle entwickeln auch neue Einkommensquellen generieren können, basierend auf dem Zugang zu Informationen und Diensten über die VWS.

Die drei Arbeitspakete konzentrierten sich auf die Anforderungen und Rahmenbedingungen auf organisatorischer Ebene für den herstellerübergreifenden Datenaustausch und den Umgang mit Daten mithilfe der VWS. Im ersten Schritt wurden Anforderungen gesammelt und analysiert, danach wurde ein Konzept entwickelt, wie eine Data Governance aussehen soll. Im nächsten Schritt wurde ein repräsentativer Anwendungsfall im Bereich der Leitungssatzherstellung definiert, der den Austausch von Informationen zwischen Teilnehmern der Wertschöpfungskette darstellt. Dieser Anwendungsfall wurde unter der Perspektive der Verwendung eines Internationalen Datenraums (IDS) beschrieben, um auf die Analyse der Informationsübertragung zu fokussieren. Zuletzt wurden in einem Piloten die Ansätze geprüft.

## <a name="_7.1"></a> AP 7.1 - Anforderungserhebung

Im AP 7.1 "**Anforderungserhebung**“ wurden, ausgehend von den aktuellen Datenhaltungssituationen der Partner, Anforderungen für eine Datenhaltung im Hinblick auf die gemeinsame Nutzung entlang der Wertkette „Leitungssatz“ erarbeitet. Dabei wurde für jede Anforderungskategorie die zu betrachtenden Aspekte, sowie die zu bedienenden potenziellen Schnittstellen aufgelistet.

#### <a name="_7.1.1"></a> Datenrichtlinien (Data Business Policy)

Eine Datenrichtlinie dient als Leitfaden und Orientierung für die Verwendung und den Umgang mit vertraulichen Daten. Sie ist eng mit der Data Governance (DG) verknüpft und bildet einen Teilbereich davon [50] [51]. Eine Datenrichtlinie setzt sich aus einer formellen Sammlung von Regeln, Prinzipien und Verfahren zusammen, die einen kontinuierlichen und korrekten Umgang mit Daten sicherstellen sollen. Ein grundlegendes legislatives Regelwerk hierzu ist die [Datenschutz-Grundverordnung (DSGVO](https://dsgvo-gesetz.de/))[^1]. Zudem behandelt eine Datenrichtlinie verschiedene Aspekte, wie bspw. Anforderungen an die Datenqualität (DQ), den Datenzugriff, die Datensicherheit sowie die Verwendung und Nutzung der Daten [50] [51]. Auf diese Weise soll eine Datenrichtlinie bedeutenden Teil der organisatorischen Anforderungen an den herstellerübergreifenden Datenaustausch abdecken. Im Folgenden werden stark angelehnt an [52] und [53] die Aspekte hergeleitet und beschrieben, die die Einhaltung einer Datenrichtlinie betreffen.

[^1]: <https://dsgvo-gesetz.de/>

#### Datensicherheit

Der Datenaustausch zwischen den Herstellern muss gemäß den von beiden Parteien vereinbarten und/oder gesetzlich vorgeschriebenen Datenrichtlinien erfolgen. Dazu gehören die Gewährleistung des gegenseitigen Vertrauens und/oder der Authentifizierung der beteiligten Parteien, ein sicheres Informationsmanagement und die Datenintegrität, wie z. B. die Datenverschlüsselung [50] [54]. Zu diesem Zweck wurde bereits die Norm ISO 27001 [55] definiert und diverse [BSI-Standards](https://www.bsi.bund.de/dok/6604686)[^2] veröffentlicht. Diese Norm zielt darauf ab, ein Grundvertrauen auf der Basis eines Zertifikats zu ermöglichen, das von einer Zertifizierungsstelle nach erfolgreicher Authentifizierung ausgestellt wird. ISO 27001 vergibt dieses Zertifikat an Organisationen, die ein sicheres Informationsmanagementsystem gewährleisten können. Damit können kooperierende Organisationen, die Daten austauschen wollen, sicher sein, dass die Daten in der anderen Organisation mit der notwendigen und erforderlichen Sicherheit behandelt werden. Für den herstellerübergreifenden Datenaustausch von personenbezogenen Daten besteht die zusätzliche Anforderung der [Datenschutz-Grundverordnung (DSGVO)](https://dsgvo-gesetz.de/), deren strikte Einhaltung zwingend erforderlich ist. Aufgrund der zahlreichen Voraussetzungen, Regelungen und strengen Kontrollen wird im Kontext der VWS die Annahme getroffen, dass personenbezogene Daten sich nicht für den automatisierten Datenaustausch über die VWS eignen und daher nicht für diesen Zweck freigegeben werden. Folglich unterliegt der herstellerübergreifende Datenaustausch von personenbezogenen Daten weiterhin einer manuellen Prüfung und Freigabe. Um dies zu gewährleisten, werden die Daten zunächst klassifiziert. Diese Klassifikation der Daten wird in der Spezifikation des Teilaspekts Rollen- und Rechtemanagement erläutert.

[^2]: <https://www.bsi.bund.de/dok/6604686>

**Definition of Done:** Die Anforderung gilt als erfüllt, wenn der Datenaustausch zwischen den Herstellern nach vereinbarten Datenrichtlinien erfolgt, bei denen die Anforderungen an die Datensicherheit, einschließlich Authentifizierung und Autorisierung, erfüllt sind. Darüber hinaus müssen die Bestimmungen der Allgemeinen Datenschutzverordnung strikt eingehalten werden, und personenbezogene Daten können nicht automatisch ausgetauscht werden. Die manuelle Überprüfung und Freigabe personenbezogener Daten muss nach festgelegten Rollen- und Rechteverwaltungsverfahren erfolgen und umgesetzt werden.

#### Interoperabilität

Die Interoperabilität der VWS bezieht sich auf die Fähigkeit, Daten zwischen verschiedenen Systemen und Organisationen zu übertragen. Dies bedeutet, dass Organisationen mit unterschiedlichen Organisationsstrukturen oder Organisationssystemen dennoch Daten miteinander austauschen können [56]. Um Interoperabilität zu gewährleisten, sind einheitliche Datenformate, Strukturen und Kommunikationsprotokolle erforderlich [56] [57] [58]. Hierzu wurden im Rahmen der VWS standardisierte Datenaustauschformate wie XML, JSON und AASX definiert [55] [59] [56]. Einen weiteren wichtigen Aspekt stellt die semantische Interoperabilität dar. Diese bezieht sich auf die Fähigkeit, eine gemeinsame und eindeutige Bedeutung von Daten sicherzustellen. Das bedeutet, dass Daten in Form von Properties in der Struktur der VWS mit global standardisierten Lexika und den darin enthaltenen IDs, Nomenklaturen, Konzeptbeschreibungen oder Metadaten versehen werden.

**Definition of Done:** Die Anforderung gilt als erfüllt, wenn die VWS die Übertragung von Daten zwischen verschiedenen Systemen und Organisationen ermöglicht und dabei standardisierte Datenformate, Strukturen und/oder Kommunikationsprotokolle verwendet. Zudem muss sichergestellt werden, dass Daten in der VWS eine gemeinsame und eindeutige Bedeutung haben und von allen beteiligten Akteuren interpretiert werden können.

#### Datenintegrität

[Datenintegrität](https://de.wikipedia.org/wiki/Integrit%C3%A4t_(Informationssicherheit)) bezeichnet die DQ über den gesamten Datenlebenszyklus hinweg [50] [56]. Im Rahmen des herstellerübergreifenden Datenaustauschs, sowohl während der Übertragung als auch der Speicherung, wird die Vollständigkeit, Richtigkeit, Unveränderlichkeit, Verfügbarkeit und Aktualität dieser Daten gewährleistet [56][55].

**Definition of Done:** Diese Anforderung gilt als erfüllt, wenn die Daten in der VWS während des gesamten Lebenszyklus, einschließlich Übertragung und Speicherung, die genannten Kriterien hinsichtlich Vollständigkeit, Richtigkeit, Unveränderlichkeit, Verfügbarkeit und Aktualität erfüllen. Hierfür können Authentifizierungsmethoden und/oder Rollen- sowie Rechtemodelle in der Konzeption berücksichtigt und umgesetzt werden.

#### Datensouveränität

[Datensouveränität](https://de.wikipedia.org/wiki/Datenbank#Datensouver%C3%A4nit%C3%A4t) [60] bezeichnet im Kontext der VWS die Sicherstellung, dass die jeweiligen Organisationen die Kontrolle, Datenhoheit und das Recht über ihre Daten während des herstellerübergreifenden Datenaustauschs beibehalten [56]. Das soll unabhängig von der Anzahl teilnehmender Akteure oder Systeme sichergestellt werden. Demnach sollen Organisationen im Zuge der Datensouveränität eigenständig entscheiden können, welche Daten, in welchem Umfang und mit wem geteilt werden.

**Definition of Done:** Die Anforderung gilt als erfüllt, wenn die Datensouveränität basierend auf den Datenrichtlinien berücksichtigt und gewährleistet ist. Somit müssen die Datenrichtlinien vor dem Datenaustausch von dem Datenbenutzer akzeptiert werden.

### <a name="_7.1.2"></a> Zugriffskontrolle

Eine [Zugriffskontrolle](https://de.wikipedia.org/wiki/Zugriffskontrolle) umfasst die Sicherstellung der Authentifizierung, Autorisierung und Vertrauenswürdigkeit aller beteiligten Akteure, welche Datenzugriff auf die VWS erhalten möchten. Die Zugriffskontrolle stellt somit eine fundamentale Grundlage für die Einhaltung der Datensicherheit, Vertraulichkeit und Datenintegrität dar. Die Authentifizierung soll die Identität und Echtheit des Benutzers sicherstellen, bspw. Soll mittels Zertifikate, Passwörter oder Benutzernamen überprüft werden, ob es sich bei dem zugreifenden Benutzer tatsächlich um diesen handelt [56]. Die Autorisierung legt nach erfolgreicher Authentifizierung fest, welcher Benutzer auf welche Daten und Inhalte zugreifen darf [56]. Für die Festlegung der Granularität des Datenzugriffs können bspw. Rollen und Rechte den entsprechenden Benutzern zugewiesen werden. Die Zugriffsrechte regeln und beschränken die Aktionen, welche die Rollen und Benutzer ausführen können.

**Definition of Done:** Die Anforderung gilt als erfüllt, wenn der Zugriff auf die Daten der VWS durch eine Zugriffskontrolle beschränkt wird. Durch die Authentifizierung muss erfolgreich die Identität der Benutzer überprüft werden. Durch die Autorisierung müssen erfolgreich die Zugriffsrollen und Zugriffsrechte festgelegt werden, die die Aktionen der Benutzer regulieren und beschränken.

### <a name="_7.1.3"></a> Rollen und Rechtekonzept

Die geteilte Nutzung der Daten einer VWS durch andere Akteure der Wertkette setzt Lösungen für das Rollen- und Rechtemanagement voraus, um Zugriffe zu verwalten und die Granularität für den Datenzugriff durch verschiedene Benutzer, Rollen und/oder Attribute sicherzustellen. Dazu müssen die jeweiligen verwendeten Rollen, Rechte sowie Attribute zwischen den beiden Akteuren in der Datenrichtlinie definiert werden. Ebenso sollte den Rollen ein Zugriffszeitraum zugewiesen werden, welcher regelt, wie lange der Datenzugriff auf die entsprechende VWS gewährt wird. Nach dem Ablauf des Zugriffszeitraums soll der Prozess der Zugriffskontrolle erneut durchgeführt werden [56]. Für die Zugriffskontrolle haben sich bisher zwei Konzepte etabliert: die rollenbasierte Zugriffskontrolle (RBAC = *role-based access control*) und die attributbasierte Zugriffskontrolle (ABAC = *attribute-based access control*). Für RBAC müssen Rollen definiert werden, die sowohl eine unterschiedliche Tiefe des Zugriffs, also wie weitgreifend der Zugriff auf die Daten sein darf, als auch welche operativen Rechte die jeweiligen Rollen erhalten, also ob Daten lediglich gelesen oder auch verändert oder kopiert werden dürfen. Diese Rollen müssen für beide Parteien gültig sein. Dieselben Unterscheidungen gelten auch für das ABAC, hierbei müssen jedoch Attribute definiert werde, anhand derer die Zugriffsrechte unterschieden werden können. Diese Attribute können unterschiedlicher Art sein, wie die Position innerhalb eines Unternehmens oder der Nachweis einer bestimmten Fähigkeit. Dieser Katalog an Attributen muss bei beiden Parteien, also dem Datenurheber und der Partei, die Zugriff auf die Daten erhalten möchte, gültig sein. Der Vorteil von ABAC gegenüber RBAC ist, dass jeder Person individuell anhand eigens definierter Attribute ein präzises Zugriffsprofil erstellt werden kann. Bei RBAC können den verschiedenen Personen lediglich voreingestellte, statische Rollen zugewiesen werden. Das ABAC-Modell erfordert jedoch weit größere Verwaltungsaufwände als das RBAC-Modell.

**Definition of Done:**

-   Die Anforderung gilt als erfüllt, wenn das Rollen- und Rechtemanagement die Granularität für den Datenzugriff sicherstellt, Rollen, Rechte und Attribute in der Datenrichtlinie definiert und festhält
-   Beschreibung des Konzepts zu Rollen und Rechtenmanagement von VWS liegt vor. Der Schwerpunkt liegt hier auf der Konzeption einer Lösung, die sich gut in die Struktur der VWS integriert
-   Definition der möglichen Rollen und Rechte für einen bestimmten Use Case
-   Erprobung des Konzeptes. BaSyx bietet bereits einige Möglichkeiten, Rollen und Rechte zu definieren

### <a name="_7.1.4"></a> Datensicherheit beim Datenaustausch

Beim Austausch von Daten zwischen Unternehmen muss die Vertraulichkeit, Integrität und Verfügbarkeit der Informationen gewährleistet werden. In diesem Zusammenhang zielt die Datensicherheit darauf ab, die Informationen vor unbefugtem Zugriff durch Benutzer zu schützen. Zu diesem Zweck können Technologien zur Datenverschlüsselung sowohl während der Übertragung als auch bei der Speicherung eingesetzt werden. Ein exemplarisches Beispiel hierfür ist die Anwendung bereits bekannter Konzepte wie dem Transport Layer Security (TLS) für die Datenübertragung und der Datenverschlüsselung. Zusätzlich ermöglicht die Aufzeichnung der Prozesse durch Traceability-Tools die Analyse von Anomalien im Verhalten der Daten. In diesem Kontext spielen die Speicherung der Daten und deren Sicherungskopien eine sehr wichtige Rolle. Im Folgenden werden die grundlegenden Aspekte im Zusammenhang mit dem Thema Datensicherheit und ihre jeweiligen Anforderungen vorgestellt:

#### Vertraulichkeit:

Vertraulichkeit bezieht sich nach ISO/IEC 27002 [12] auf den Aspekt, nach dem ausschließlich autorisierte Benutzer Zugriff auf relevante Informationen haben. Zur Gewährleistung der Vertraulichkeit von Informationen in der VWS-Umgebung können verschiedene Techniken und Konzepte in Betracht gezogen werden.

**Aspekte:**

-   Einschränkung des Zugriffs durch Benutzerklassifizierung: Begrenzung des Zugriffs von Benutzern auf Repositories und Datensätze von Unternehmen, die am Datenaustausch beteiligt sind, durch die Erstellung eines Modells zur Klassifizierung potenzieller Benutzer mit Interesse an den in der VWS vorhandenen Informationen und Diensten
-   Konzeption eines Verschlüsselungsmodells: Verschlüsselung von Informationen in der VWS, um die Daten vor nicht autorisiertem Zugriff zu schützen
-   Klassifizierung vor der Übertragung: Klassifizierung von Informationen nach ihrer Sensibilität vor der Übertragung in die VWS-Repositories. Hierzu wird die Umsetzung eines Konzepts zur Klassifizierung von Daten anhand verschiedener Kategorien unter Verwendung der etablierten Struktur der VWS vorgeschlagen
-   Verwendung von Geheimhaltungsvereinbarungen (NDA): Geheimhaltungsvereinbarungen (NDA) stellen ein rechtliches Instrument dar, um die Vertraulichkeit zu gewährleisten

**Schnittstellen:**

-   Rollen- und Rechte-Management
-   Authentifizierung
-   Autorisierung
-   Aspekte des Architekturteams, wie bereits umgesetzte Konzepte zu Modularisierung, Versionierung und Verlinkung

#### Integrität

Der Begriff "Integrität" in diesem Kontext bezieht sich auf die Originalität der Daten, d.h. dass die betreffenden Daten vollständig und unverändert bleiben. Geeignete Integrations- und Schutzmaßnahmen sollen verhindern, dass die Daten beschädigt oder unerwartet verändert werden. Dabei spielt auch der Speicherort der Daten eine entscheidende Rolle. Daher ist ein Konzept unerlässlich, das die Integrität der Daten innerhalb einer VWS oder einer untergeordneten Informationsstruktur, wie einem Teilmodell, einer Sammlung von Teilmodellen oder einer Eigenschaft, gewährleisten kann. In diesem Zusammenhang sollte es jederzeit möglich sein festzustellen, ob die Daten in ihrem Originalzustand verfügbar sind, also frei von unbefugten Änderungen.

**Aspekte**

-   Konzept zur Datenintegrität muss vorhanden sein
-   Die entwickelte Lösung muss sich nahtlos in die Struktur der VWS integrieren lassen

**Schnittstellen:**

-   Rollen und Rechtekonzepte
-   Verschlüsselungstechnologien
-   Digitale Signatur
-   Aspekte des Architekturteams, wie bereits umgesetzte Konzepte zu Rückverfolgbarkeit und Verlinkung

#### Verfügbarkeit

Verfügbarkeit in diesem Kontext beschreibt die Fähigkeit auf Daten zuzugreifen, wann immer sie benötigt werden. Eine hohe Datenverfügbarkeit bedeutet, dass Daten zuverlässig und ohne Unterbrechung zugänglich sind. Dies erfordert oft redundante Systeme, Datensicherung und Notfallwiederherstellungspläne, um sicherzustellen, dass Daten auch bei Hardwarefehlern, Naturkatastrophen oder anderen unerwarteten Ereignissen verfügbar bleiben. Die Wahl der Mittel folgt dem Status Quo der geeigneten Technologien.

**Aspekte:**

-   Funktionalität: Die VWS kann ihre Aufgaben erfüllen ohne unerwartete Ausfälle und Probleme zu haben
-   Erreichbarkeit: Bewertung erfolgt durch Netzwerkverfügbarkeit und Konnektivität.
-   Das Konzept kann durch beteiligte Systeme unterstützt/umgesetzt werden (BaSyx, Catena-X, EDC etc.)

**Schnittstellen**

-   Cloud und Synchronisierungsdienste
-   Datensicherheit
-   Datenintegrität
-   Aspekte des Architekturteams, wie bereits umgesetzte Konzepte zu Modularisierung, Versionierung

### <a name="_7.1.5"></a> Datensouveränität

Datensouveränität beschreibt die rechtlichen Rahmenbedingungen, die den Umgang mit Daten betreffen. In diesem Zusammenhang spielt der Datenschutz eine unverzichtbare Rolle. Die sogenannten Schutzziele sind die Eckpfeiler der Informationsschutzes. Die drei wichtigsten sind auch als CIA-Dreiklang bekannt: Vertraulichkeit (Confidentiality), Integrität (Integrity) und Verfügbarkeit (Availability).

Darüber hinaus impliziert Datensouveränität den selbstbestimmten Umgang mit den eigenen Daten und damit die volle Kontrolle über die Erhebung, Speicherung, Nutzung und Verarbeitung dieser Daten. Souveränität bezieht sich auf die Definition, wem die Daten gehören, wo die Daten gespeichert werden, wie sie genutzt werden und welche Regeln für den Missbrauch oder die Manipulation von Daten gelten. Maßgebliche Regelungen im Bereich der Datensouveränität sind dabei nationale und internationale Datenschutzbestimmungen wie die Datenschutz-Grundverordnung (DSGVO) und das Datenschutzgesetz.

**Aspekte**

-   Konzeption eines Modells für die Speicherung von Daten auf der Grundlage des Zustands der Daten, wobei zwischen gespeicherten und verwendeten Daten unterschieden wird. In der VWS-Umgebung ist es wichtig zu definieren, wo sich das Repository des VWS befinden wird
-   Definition von Regeln, d. h. vertragliche Regelung des Umgangs mit Daten, die gemeinsam genutzt oder gespeichert werden
-   Konzeption eines Modells zur Pseudonymisierung und Verschlüsselung der Daten, das die Sicherheit der Daten gewährleistet

**Schnittstellen**

-   Datensicherheit
-   Dezentral Repository
-   Aspekte des Architekturteams, wie bereits umgesetzte Konzepte zu Versionierung und Rückverfolgbarkeit

### <a name="_7.1.6"></a> Datenhaltung (Data Storage Policy) im Hinblick auf die gemeinsame Nutzung

Die Datenhaltung in der VWS ist ein zentraler Aspekt der Industrie 4.0 und bezieht sich auf die systematische Erfassung, Speicherung und Verwaltung von Daten. Sie ermöglicht die Integration von Daten aus verschiedenen Quellen, gewährleistet deren Konsistenz und stellt sicher, dass sie für die relevanten Akteure zugänglich sind.

In der VWS dient die Datenhaltung als Brücke zwischen der physischen und der digitalen Welt. Sie ermöglicht die digitale Repräsentation von physischen Objekten und Systemen, was für die Interoperabilität und Zusammenarbeit von Systemen entscheidend ist. Die umfangreichen Möglichkeiten der Datenhaltung in der VWS führen zu einer Reihe von technischen und technologischen Anforderungen.

Das Ziel der Datenspeicherung ist die Speicherung, der Abruf und die Nutzung von Informationen in einer sicheren Art und Weise entsprechend dem Bedarf des Nutzers. In diesem Zusammenhang ist es notwendig, die Speicherung von VWS-Informationen vor Ort oder in der Cloud zu vergleichen.

Zum einen erfordert die effektive Speicherung und Verwaltung von Daten robuste Datenbanktechnologien und -infrastrukturen. Diese müssen in der Lage sein, große Mengen an Daten zu verarbeiten und gleichzeitig hohe Leistung, Sicherheit und Zuverlässigkeit zu gewährleisten. Gleichzeitig stellen Richtlinien zur Datenspeicherung einen wichtigen Bestandteil der Data Governance dar.

Zum anderen erfordert die Integration von Daten aus verschiedenen Quellen und deren Bereitstellung für verschiedene Akteure fortschrittliche Technologien zur Datenintegration und -transformation. Hier kommen beispielsweise Technologien wie APIs, Microservices und Middleware zum Einsatz.

**Aspekte:**

-   **Datenbanktechnologien und -infrastrukturen**: Die effektive Speicherung und Verwaltung von Daten erfordert robuste Datenbanktechnologien und -infrastrukturen. Diese Systeme müssen in der Lage sein, große Mengen an Daten zu verarbeiten und gleichzeitig hohe Leistung, Sicherheit und Zuverlässigkeit zu gewährleisten. Darüber hinaus müssen sie skalierbar sein, um mit dem Wachstum der Datenmengen Schritt zu halten, und sie müssen flexible Datenmodelle unterstützen, um eine Vielzahl von Datentypen und -strukturen zu verarbeiten
-   **Datenintegrations- und Transformationstechnologien**: Die Integration von Daten aus verschiedenen Quellen und deren Bereitstellung für verschiedene Akteure erfordert fortschrittliche Technologien zur Datenintegration und -transformation. Diese Technologien müssen in der Lage sein, Daten aus verschiedenen Formaten und Strukturen zu extrahieren, zu transformieren und zu laden (ETL-Prozesse), um eine einheitliche und konsistente Sicht auf die Daten zu gewährleisten. Beispiele für solche Technologien sind APIs, Microservices und Middleware
-   **Datenstrukturierung und -standardisierung**: Die Daten in der VWS sollten in einer strukturierten und standardisierten Form vorliegen. Dies bedeutet, dass die Daten in einer Weise organisiert sein sollten, die eine konsistente Interpretation und Nutzung über verschiedene Systeme und Plattformen hinweg ermöglicht. Die Verwendung internationaler Standards wie OPC UA kann dabei helfen, ein hohes Maß an Interoperabilität zu gewährleisten
-   **Datenqualität**: Die Daten müssen genau, aktuell und relevant sein. Unvollständige oder veraltete Daten können zu falschen Entscheidungen führen und die Effizienz der Prozesse beeinträchtigen. Daher sollte ein effektives Datenqualitätsmanagement implementiert werden, das die Genauigkeit, Vollständigkeit und Aktualität der Daten sicherstellt
-   **Datensicherheit**: Die Sicherheit der Daten ist ein wichtiger Aspekt. Die Daten in der Verwaltungsschale sollten vor unbefugtem Zugriff geschützt sein. Dies kann durch verschiedene Mechanismen wie Verschlüsselung, Zugriffskontrollen und sichere Übertragungsprotokolle erreicht werden. Darüber hinaus sollte die Verwaltungsschale in der Lage sein, auf Sicherheitsvorfälle zu reagieren und geeignete Maßnahmen zur Behebung von Sicherheitslücken zu ergreifen. Die Daten in der VWS sollten sicher gespeichert und übertragen werden. Dies umfasst sowohl physische Sicherheitsmaßnahmen (z.B. sichere Server) als auch digitale Sicherheitsmaßnahmen (z.B. Verschlüsselung)
-   **Datenschutz**: Im Einklang mit den Datenschutzgesetzen und -richtlinien müssen personenbezogene Daten geschützt und vertraulich behandelt werden. Die VWS sollte Mechanismen zur Einhaltung dieser Anforderungen implementieren, einschließlich der Gewährleistung der Einwilligung der betroffenen Personen, der Begrenzung der Datennutzung auf den angegebenen Zweck und der Gewährleistung des Rechts auf Zugang, Berichtigung und Löschung. Datenschutz und Compliance: Die Dateninfrastruktur sollte die Einhaltung von Datenschutzgesetzen und -richtlinien gewährleisten. Dies umfasst Aspekte wie die sichere Speicherung und Übertragung von Daten, die Einhaltung von Zugriffskontrollen und die Implementierung von Datenschutzmaßnahmen wie Datenverschlüsselung und Anonymisierung. Standards und Frameworks wie ISO 27001 und GDPR bieten Richtlinien und Best Practices für den Datenschutz und die Compliance
-   **Datenlebenszyklusmanagement**: Die Verwaltungsschale sollte in der Lage sein, den gesamten Lebenszyklus der Daten zu verwalten, von der Erstellung und Nutzung bis zur Archivierung oder Löschung. Dies beinhaltet auch die Nachverfolgbarkeit und Historisierung der Daten, um Änderungen im Laufe der Zeit nachvollziehen zu können und die Einhaltung von Vorschriften zu gewährleisten
-   **Datenzugänglichkeit und -nutzbarkeit**: Die Daten in der Verwaltungsschale sollten leicht zugänglich und nutzbar sein. Dies bedeutet, dass die Daten in einer für Menschen lesbaren und verständlichen Form präsentiert werden sollten. Gleichzeitig sollte die Verwaltungsschale APIs oder andere Schnittstellen bereitstellen, um den maschinellen Zugriff auf die Daten zu ermöglichen. Darüber hinaus sollte die Verwaltungsschale in der Lage sein, die Daten in einer Weise zu präsentieren, die die Entscheidungsfindung unterstützt, beispielsweise durch Visualisierungen oder aggregierte Berichte
-   **Interoperabilität**: Die Dateninfrastruktur sollte den Austausch von Daten mit anderen Unternehmen ermöglichen. Hierfür könnten Technologien wie APIs, Web-Services und standardisierte Datenformate wie JSON oder XML verwendet werden. Darüber hinaus sollte die Dateninfrastruktur den Standard OPC UA [62] [18] unterstützen, der eine sichere und zuverlässige Kommunikation zwischen verschiedenen industriellen Geräten ermöglicht.
-   **Data Governance**: Unter dem Aspekt einer Data Governance sind folgende Aspekte zu berücksichtigen und zu definieren:
    -   Speicherort der Daten (ist vorgegeben beim jeweiligen Asset-Hersteller)
    -   Dauer der Speicherung
    -   Mechanismen zur Identifizierung der Versionen der Daten
    -   Wann wird die Datenspeicherung in eine Datenarchivierung umgewandelt.

**Definition of Done:**

-   Konzept unter Berücksichtigung der Data Storage Policy Anforderungen wurde erstellt
-   Definition einer anwendbaren Dateninfrastruktur die Datenintegration und -transformation unterstützt

**Schnittstellen:**

-   Architektur Team
-   Single point of truth (SPoT)
-   Integration von Daten mit VWS

### <a name="_7.1.7"></a> Datenhaltungsformate und -infrastrukturen

Datenhaltungsformate und -infrastrukturen in der VWS beziehen sich auf die Art und Weise, wie Daten strukturiert, gespeichert und verwaltet werden. Sie sind entscheidend für die Effizienz und Effektivität der Datenverarbeitung. Datenhaltungsformate bestimmen, wie Daten repräsentiert und interpretiert werden. Sie können von einfachen Textdateien bis hin zu komplexen relationalen oder nicht-relationalen Datenbankstrukturen reichen. Datenformate wie KBL [5] und VEC [6] werden in der Leitungssatz-Branche verwendet. Im Kontext VWS4LS wurde das AASX-Format [63] eingeführt. Bei allen diesen Dateitypen handelt es sich um strukturierte XML-Formate. Im IDS-Kontext werden vor allem JSON-basierte Datenobjekte verwendet. Datenhaltungsinfrastrukturen beziehen sich auf die physischen und logischen Ressourcen, die zur Speicherung und Verwaltung von Daten verwendet werden. Sie umfassen Hardware-Ressourcen wie Server und Speichersysteme sowie Software-Ressourcen wie Datenbankmanagementsysteme und Datenverarbeitungstools. So ist z.B. die Auswahl der geeigneten Datenbanktechnologie entscheidend für eine effiziente Speicherung der gemeinsam ausgetauschten Daten. Hier kommen sowohl [relationale Datenbanken](https://de.wikipedia.org/wiki/Relationale_Datenbank) (z.B. MySQL, PostgreSQL) als auch [NoSQL-Datenbanken](https://de.wikipedia.org/wiki/NoSQL) (z.B. MongoDB, Cassandra) in Frage, je nach den spezifischen Anforderungen an die Datenstruktur und -abfrage. Beispielsweise eignen sich relationale Datenbanken für eine strukturierte, tabellenbasierte Datenhaltung, während für unstrukturierte oder semi-strukturierte Daten NoSQL-Datenbanken besser geeignet sind [64]. Zur Datenverarbeitung von Echtzeitdaten oder großen Datenmengen können Technologien wie [Apache Kafka](https://de.wikipedia.org/wiki/Apache_Kafka) oder [Apache Hadoop](https://de.wikipedia.org/wiki/Apache_Hadoop) zum Einsatz kommen. Im Folgenden werden die relevanten Aspekte der Datenspeicherformate und -infrastrukturen erläutert:

-   **Skalierbarkeit**: Die Dateninfrastruktur muss skalierbar sein, um den Anforderungen des Datenwachstums und der Nutzung gerecht zu werden. Skalierbare Cluster- oder Cloud-Datenbanken, wie z.B. [Amazon DynamoDB](https://de.wikipedia.org/wiki/Amazon_Dynamo) oder [Google Cloud Spanner](https://de.wikipedia.org/wiki/Spanner_(Datenbank)), bieten hier Lösungen, da sie eine nahezu unbegrenzte Skalierbarkeit und hohe Leistung bieten
-   **Hochverfügbarkeit**: Die Dateninfrastruktur sollte hochverfügbar und ausfallsicher sein, um einen kontinuierlichen Betrieb zu gewährleisten. Technologien wie Redundanz, Replikation und automatisches Failover können hier eingesetzt werden, um die Verfügbarkeit und Zuverlässigkeit der Dateninfrastruktur zu erhöhen
-   **Datensicherung und Wiederherstellung**: Es ist wichtig, regelmäßige Datensicherungen durchzuführen und Mechanismen für die schnelle Wiederherstellung von Daten im Falle eines Datenverlusts zu implementieren. Technologien wie Snapshots, Point-in-Time-Recovery und Backup-Lösungen können hier eingesetzt werden
-   **Datenschutz und Compliance**: Die Dateninfrastruktur sollte die Einhaltung von Datenschutzgesetzen und -richtlinien gewährleisten. Dies umfasst Aspekte wie die sichere Speicherung und Übertragung von Daten, die Einhaltung von Zugriffskontrollen und die Implementierung von Datenschutzmaßnahmen wie Datenverschlüsselung und Anonymisierung

Diese Aspekte sind entscheidend für die effektive Implementierung einer Datenhaltungsinfrastruktur im Kontext der VWS. Es ist wichtig, dass diese Anforderungen bei der Auswahl und Implementierung der Dateninfrastruktur berücksichtigt werden. Es ist auch wichtig zu beachten, dass die spezifischen Anforderungen je nach Anwendungsfeld und spezifischen Bedürfnissen des Unternehmens variieren können.

**Aspekte:**

-   Definition der Haltung von Daten im Unternehmen
-   Erweiterung der Datenformate
-   Definition der optimalen Infrastrukturlösungen für die Datenhaltung

**Schnittstellen:**

-   Architekturteam, Modularisierung

### <a name="_7.1.8"></a>  Anbindung an Catena-X

[Catena-X](https://catena-x.net/de/) als führender IDS im Automotive-Bereich soll für VWS4LS nutzbar gemacht werden. Daher muss ein systemübergreifende Gesamtkonzept definiert werden und die entsprechenden System-Schnittstellen bedient werden können.

**Aspekte**:

-   Definition der Vorteile und Herausforderungen der von Catena-X angebotenen Schnittstellen für Ihren VW-Datenanschluss
-   Kompatibilität der im Projekt verwendeten semantischen Modelle und der von Catena verwendeten Konzepte
-   Definition der notwendigen Infrastruktur zur Bereitstellung der erforderlichen Dienste im Rahmen des Datenaustausches auf der Ebene der Wertschöpfungskette

**Schnittstellen:**

-   AAS-Discovery
-   DT-Registry

### <a name="_7.1.9"></a> Daten-Monetarisierung

Ziel ist die Entwicklung eines umfassenden Rahmens zur Konzeptualisierung, Implementierung und Validierung eines Modells zur Monetarisierung von Daten im Kontext der Struktur der VWS und seiner Anwendung in der Fertigungsindustrie. Das umfasst einen klaren und strukturierten Ansatz für die digitale Darstellung von Produkten, Prozessen und Ressourcen, den bidirektionalen Austausch von Daten sowie die damit verbundenen Herausforderungen im Bereich Datenmanagement und -sicherheit. Bestehende Monetarisierungsmodelle in anderen Bereichen sollen auf Ihre Anwendbarkeit auf das Konzept des AAS untersucht werden, bspw. Pay-per-Use oder datengestützte Dienstleistungen. Ein weiterer Schwerpunkt liegt auf der Identifizierung der Wertschöpfungskategorien, die durch die Monetarisierung von Daten erreicht werden können, wobei zwischen internem (innerhalb des Unternehmens) und externem (kundenorientierten) Mehrwert unterschieden wird. Dazu müssen klare und messbare wirtschaftliche Indikatoren festgelegt werden, um die direkten wirtschaftlichen Vorteile zu bewerten, wie bspw. Kostenreduzierung oder Produktivitätssteigerung. Ein System zur Festlegung von Zugriffsrechten bei gleiochzeitiger Gewährleistung der Souveränität des Datenbesitzers muss definiert werden. Im Rahmen der Implementierungsstrategien sind konkrete Strategien zur Validierung des Monetarisierungsmodell auf Basis eines spezifischen Anwendungsfalls notwendig, um sicherzustellen, dass die Bedingungen des industriellen Umfelds repräsentativ sind. Dazu sollte in einem Pilotprojekt die Sammlung von Daten und die Analyse der Leistung des Modells unter realen Bedingungen stattfinden. Abschließend sollte eine umfassende Analyse der während des Piloten erzielten Ergebnisse durchgeführt werden, indem die erreichten wirtschaftlichen Vorteile mit den während der Konzeptionsphase festgelegten Indikatoren verglichen werden. Das Modell sollte basierend auf den in der Bewertung gewonnenen Erkenntnissen angepasst werden, um seine Robustheit und Anpassungsfähigkeit an verschiedene Kontexte innerhalb der Fertigungsindustrie sicherzustellen.

Diese Anforderung zielt darauf ab, einen systematischen Ansatz zur Konzeptualisierung, Entwicklung und Validierung eines Monetarisierungsmodells für Daten auf der Grundlage des AAS zu etablieren, das nicht nur direkte wirtschaftliche Vorteile bietet, sondern auch die digitale Transformation der Fertigungsindustrie fördert und Innovation sowie Wettbewerbsfähigkeit unterstützt.

**Aspekte**

-   Adaption bereits etablierter Geschäftsmodellkonzepte im Rahmen der VWS
-   Berücksichtigung von Datenzugriffskonzepten und deren Granularität im Rahmen der Monetarisierung von Informationen und Diensten

**Schnittstellen**

-   Aspekte der Daten-Governance
-   Datensicherheit

## <a name="_7.2"></a> AP 7.2 - Fachliche Konzeption der Daten-Policy entlang der Wertkette

Im Rahmen des Arbeitspakets 7.2 wurden die relevanten Aspekte der DG, die für das VWS-Ökosystem benötigt werden, durch eine Literaturanalyse ermittelt. Ausgehend von diesen identifizierten Aspekten werden Zugangskontrolle, Rollen- und Rechtemanagement und Richtlinien für die Datenverwaltung im Detail behandelt. Darüber hinaus werden Lösungen für die Integration dieser konzeptionellen Ansätze in das aktuelle VWS-Metamodell diskutiert. Dieser Ansatz schafft die Grundlage für die Einführung von VWS in der Industrie und fördert standardisierte Praktiken für die gemeinsame Nutzung von Daten durch die Akteure der Industrie. Dieses Konzept wurde in zwei wissenschaftlichen Veröffentlichungen vorgestellt [52] [53].

Nachdem die Aspekte, die intern in den Unternehmen zu berücksichtigen sind, bestimmt und definiert wurden, wird zusätzlich eine Architektur für den externen Austausch von Informationen und Diensten rund um die Wertschöpfungskette auf der Grundlage des International Data Space (IDS) Ökosystems vorgestellt. Für den Automobilsektor wird [Catena-X](https://catena-x.net/de/) als IDS für den sicheren Austausch von Informationen und Diensten betrachtet und deshalb in diesem Arbeitspaket als Lösungsansatz genannt. Ergänzend wird eine Unterscheidung zwischen operativen und nicht-operativen Daten vorgeschlagen, um zum einen die Sicherheit besser zu gewährleisten und zum anderen eine bessere architektonische Trennung der beteiligten Systeme (VWS und IDS) zu realisieren.

### <a name="_7.2.1"></a> Integration von Data-Governance-Aspekten in das Metamodell der VWS

#### Relevante Aspekte

Um die relevanten Aspekte der Daten-Governance für den Datenaustausch zwischen Herstellern im VWS-Ökosystem zu ermitteln, wurden eine Literaturrecherche unter Verwendung etablierter Datenbanken wie [Web of Science](https://www.webofscience.com/), [IEEE Explore](https://ieeexplore.ieee.org/), [ACM Digital Library](https://dl.acm.org/) und [Semantic Scholar](https://www.semanticscholar.org/) sowie der [Plattform Industrie 4.0](https://www.plattform-i40.de/) durchgeführt. Zur Sicherstellung der Reproduzierbarkeit und Eingrenzung des Umfangs wurde eine Reihe mithilfe boolescher Operatoren verknüpfter Schlüsselwörter festgelegt:

„*asset administration shell*" UND („*data governance*" ODER „*data policy*" ODER „*data exchange*" ODER „*access control*" ODER „*access permission*" ODER „*authorization*" ODER „*authentication*" ODER „*security*")

Da die frühesten Publikationen im AAS-Bereich mit diesen Schlüsselwörtern aus dem Jahr 2017 stammen, konzentriert sich diese Arbeit auf Veröffentlichungen aus diesem Zeitraum bis zum aktuellen Jahr 2023, in dem diese Untersuchung durchgeführt wird. Die systematische Überprüfung umfasste Schritte wie die Datenbanksuche, die Entfernung irrelevanter Veröffentlichungen und die Überprüfung der verbleibenden Arbeiten. Von den ursprünglich 50 identifizierten relevanten Publikationen wurden nach Verfeinerung und Vorauswahl 29 beibehalten. Nach einer detaillierten Analyse wurden weitere 17 Arbeiten ausgeschlossen, da sie das Thema der Daten-Governance nur oberflächlich behandelten.

![image](https://github.com/user-attachments/assets/4a11c4f9-b46e-423d-8fa7-05c47e46a333)   
*Abbildung 7-1: Überblick über den systematischen Prozess der Literaturrecherche*

Abschließend wurden unter Anwendung der [Snowballing-Methode](https://dl.acm.org/doi/10.1145/2601248.2601268) sechs zusätzliche Publikationen identifiziert, was zu einem finalen Satz von 18 relevanten Arbeiten führte, die eingehend untersucht wurden, um Einblicke in die Behandlung der Daten-Governance-Aspekte im AAS-Ökosystem zu gewinnen. *Abbildung* 7-1 illustriert die angewandte Methodik ab, die Zahlen in Klammern repräsentieren die Anzahl der aufgefundenen Publikationen.

Die so identifizierten Publikationen wurden anschließend anhand von zwei Kategorien analysiert:

-   Die erste Kategorie klassifiziert die Publikationen nach ihrem Ziel: Stand der Technik, Konzeption und Vorschlag. Die Publikationen zum Stand der Technik untersuchen theoretische Fortschritte in VWS und Daten-Governance (DG). Die Konzeptionen präsentieren konzeptionelle Rahmenwerke, während die Vorschläge praktische Lösungen auf der Grundlage der Literatur bieten.
-   Die zweite Kategorie hebt die Aspekte der DG hervor, die in den Publikationen behandelt werden, wie Datensicherheit (15), Authentifizierung (15), Autorisierung (10), Vertraulichkeit (8), Rollen- und Rechteverwaltung (10), Datensouveränität (5) und Datenintegrität (9). Diese Publikationen vertiefen die Themen Sicherheit beim Datenaustausch zwischen Herstellern, Authentifizierung, Zugriffskontrolle und Vertraulichkeit, unter anderem. Es werden verschiedene Methoden der Authentifizierung und Autorisierung, wie X.509 und OAuth2.0, diskutiert. Die Rollen- und Rechteverwaltung stellt sicher, dass Benutzer nur auf die relevanten Informationen zugreifen, während die Datensouveränität gewährleistet, dass die Teilnehmer die Kontrolle über ihre Daten behalten. Die Datenintegrität ist entscheidend, um die Qualität und Sicherheit der Daten während ihres gesamten Lebenszyklus zu gewährleisten. Für weitere Details wird auf die genannten Publikationen verwiesen [52] [53].

Die Analyse der Literatur zeigte eine erhebliche Lücke bei der mit DG verbundenen Aspekte im VWS-Ökosystem. Obwohl einige spezifische Aspekte der DG diskutiert wurden, oft auf theoretische Weise, fehlt es deutlich an konkreten Implementierungen. Daher wird auf Basis grundlegender Prinzipien vorgeschlagen, das DG-Konzept durch drei zentrale Aspekte für den Informationsaustausch in der Wertschöpfungskette zu behandeln:

Im Hinblick auf die **Datenrichtlinien** wird die Bedeutung der Wahrung von Vertraulichkeit, Datensouveränität, Sicherheit und Integrität betont. Derzeit gibt es jedoch kein spezifisches Konzept, das beschreibt, wie diese Prinzipien im bestehenden VWS-Metamodell strukturiert werden sollten. Daher wird vorgeschlagen, dass die Datenrichtlinien Anforderungen wie Datensicherheit, Interoperabilität, Datenintegrität, Datensouveränität, Zugangskontrolle und Rollen- und Rechteverwaltung umfassen. Die **Zugangskontrolle** wurde in den analysierten Publikationen ebenfalls nicht ausreichend behandelt. Um die Authentizität des Benutzers oder Systems, das Zugriff auf die VWS anfordert, sicherzustellen, wird empfohlen, die Datenrichtlinien durch Zugangskontrolle zu ergänzen und diese mit den Aspekten Authentifizierung und Autorisierung zu verbinden. Schließlich wird das **Rollen- und Rechtemanagement** als ein entscheidender Aspekt diskutiert, der den Zugriff auf die VWS-Informationen gemäß den definierten Rollen und Rechten garantiert und autorisiert.

#### Data-Governance-Aspekte im Metamodell der VWS

Um die identifizierten Aspekte einer Daten-Governance (DG), d.h. **Datenrichtlinien, Zugangskontrolle** sowie **Rollen- und Rechtemanagement** in das Ökosystem der VWS zu integrieren, werden zwei Optionen betrachtet.

Die erste Option integriert die DG-Aspekte in Form eines SM, basierend auf einem SM-Template der IDTA. Dies erfordert, solch ein DG-SM zu jeder Instanz des Daten-SM einzufügen, bevor mit dem Datenaustausch fortgefahren wird. Da DG ein Konzept ist, das alle SM umfasst, ist diese Idee anfällig für Fehler und unnötige Komplexität, da die DG-Aspekte, wie das Rollen- und Rechtemanagement, manuell auf jedes SM referenziert werden müsste.

Die zweite Option integriert die DG-Aspekte direkt in die Struktur der VWS, d.h. das Metamodell der VWS wird erweitert. Auf diese Weise würde die AAS die identifizierten DG-Aspekte inhärent enthalten und die Notwendigkeit einer zusätzlichen Integration beseitigen. Daher schlagen wir vor, das Metamodell der VWS mit den identifizierten DG-Aspekten zu erweitern. Dieser Ansatz bietet eine kohärentere und effizientere Lösung, welche Redundanzen vermeidet und den Integrationsprozess der DG-Aspekte in die VWS-Umgebung vereinfacht. Für die Integration wird das vorhandene Metamodell der VWS (DIN EN IEC 63278-1, Version 3) erweitert um die vorgeschlagenen Aspekte der DG.

Um ein Verständnis für die Erweiterung des bestehenden Metamodells im Hinblick auf die neuen Klassen und Attribute zu schaffen, werden zunächst die integrierten Superklassen (SC) **UserInformation** und **Authorizable** erläutert.

![image](https://github.com/user-attachments/assets/b2144730-80da-4fad-a9d4-c8c7019444bb)    
*Abbildung 7-2: Überblick über die Superklasse „UserInformation“*

Die SC *UserInformation* (*Abbildung 7-2*) kann verwendet werden, um auf die Benutzerinformationen in einem Element des Metamodells der VWS zu verweisen, sodass sie Informationen über den Benutzer enthalten kann, wie Identifikation, Rollen oder Rechte, wenn dies für den weiteren Prozess erforderlich ist. Die SC *UserInformation* erbt alle Attribute der Klassen *Referable, HasSemantics* und *Qualifiable* für eine konkrete Spezifikation, Referenz und weitere Informationen über den Ersteller des Benutzers. Die Informationen über den Benutzer setzen sich aus den Attributen *userId, userRole, userRights, userType, accessTime* und *userPublicKey* zusammen. Die *userId* enthält eine lokal eindeutige ID des Benutzers in Form einer Zeichenkette (*string)*, so dass der Benutzer eindeutig identifiziert und im jeweiligen System referenziert werden kann. Das Attribut *userRole* referenziert die Rolle des Benutzers aus der Menge der definierten Rollen der Klasse *UserRole*, welche eine Aufzählung der definierten Benutzerrollen enthält. Damit kann der Benutzer als *StandardUser, TechnicalUser, ExecutiveUser, Administrator* oder *AASResponsible* ausgewiesen werden. Um die Kohärenz des Konzepts zu wahren, wird jedem Benutzer eine Rolle gemäß den Spezifikationen zugewiesen, da andernfalls die Zuordnung der mit der jeweiligen Rolle verbundenen Rechte zu Inkonsistenzen und Mehrdeutigkeiten führen kann. Analog repräsentiert das Attribut *userRights* die Rechte des Benutzers aus den definierten Rechten. *UserRights* enthält eine Aufzählung der definierten Benutzerrechte, die in Benutzerrollen verankert sind. Damit wird spezifiziert, ob der Benutzer *Lese-, Schreib- oder vollen Zugriff* auf das SM hat. Diese Rechte sind inkrementell strukturiert und bauen aufeinander auf, was die Rollen abgrenzt und sicherstellt, dass die Rechte mit der dem Benutzer zugewiesenen Rolle übereinstimmen. Das Attribut *userType* assoziiert jeden Benutzer mit einem Benutzertyp aus den vordefinierten Benutzertypen der Klasse *UserType*, die angibt, ob der Benutzer *intern, extern* oder sowohl *intern als auch extern* ist. Das Attribut *accessTime* enthält einen Zeitstempel mit dem Zeitpunkt des Zugriffs des Benutzers auf die Informationen oder Dienste des jeweiligen SM. Diese Zugriffszeit wird gespeichert und jedes Mal überschrieben, wenn der Benutzer authentifiziert wird und soll dazu dienen, den Zugriffszeitraum in einer spezifischen Implementierung zu verwalten und einzuschränken. Das letzte Attribut *userPublicKey* enthält den öffentlichen Schlüssel des Benutzers in Form eines *string*, der zur Authentifizierung mit einem Zertifikat verglichen wird.

![image](https://github.com/user-attachments/assets/6d4c0c8f-0007-4874-a9e5-036c525990b4)   
*Abbildung 7-3: Überblick über die Superklasse „Authorizable“*

Die *Abbildung 7-3* zeigt einen Überblick über die erweiterte Superklasse *Authorizable*, welche von den SC *HasSemantics, Referable* und *Qualifiable* erbt. Insbesondere repräsentiert die Klasse *Authorization* die Autorisierung des Benutzers mit den Attributen *authenticationCheckPoint*, *authorizeUser* und *submodelAccessRestriction*. Das Attribut *authenticationCheckPoint* vom Typ *Boolean* repräsentiert, ob der Benutzer erfolgreich authentifiziert wurde. Ähnlich repräsentiert das Attribut *authorizeUser* ob die Eigenschaften des Benutzer mit den Autorisierungsbeschränkungen übereinstimmen. Die Klasse *Authorization* enthält das Attribut *submodelAccessRestriction*, um mögliche Beschränkungen der Autorisierung für den Datenzugriff zu definieren. Die Klasse *SubmodelAccessRestriction* definiert die Beschränkungen für die Autorisierung des Benutzers. Zu diesem Zweck enthält die Klasse die Attribute *typeRestriction* und *rolesRestriction*. Die Rechte sind, wie bereits erwähnt, mit der jeweiligen Rolle des Benutzers verbunden. Das Attribut *typeRestriction* vom Typ *string* repräsentiert Sichtbarkeit für das SM, die zugewiesenen Benutzertypen aus der zulässigen Menge von Benutzertypen sind in dieser *string* definiert. Analog zur Sichtbarkeit werden die zulässigen Rollen für den Datenzugriff über das Attribut *rolesRestriction* definiert.

![image](https://github.com/user-attachments/assets/50d6165e-3c06-445c-8af5-95f5817aeb6e)   
*Abbildung 7-4: Übersicht über die Integration der identifizierten Data-Governance-Aspekte in das bestehende Metamodell der Verwaltungsschale (Erweiterungen fettgedruckt)*

Die *Abbildung 7-4* veranschaulicht die Integration einer DG in die VWS-Struktur. Das erweiterte Metamodell umfasst das Attribut *accessControl*, das Sicherheitsaspekte wie Authentifizierung und Datenrichtlinien für die VWS-Zugangskontrolle anspricht. Das Attribut *accessControl* gehört zur Klasse *AccessControl*, die *Authentifizierung*smethoden und *Datenrichtlinien* verwaltet. Die Klasse *AccessControl* erbt von der SC *UserInformation*, die Informationen für die Benutzerauthentifizierung und die Authentifizierung von Kontrollpunkten bereitstellt. Darüber hinaus erbt *AccessControl* von der Klasse *Referable* für lokale Referenzen. Das Attribut *datamanagementPrinciples* bedeutet die Anbindung an erforderliche Datenrichtlinien und die Benutzerbestätigung und gehört zur Klasse *DatamanagementPrinciples*. Das Attribut *authentication* bezeichnet die Authentifizierungsmethode für den Datenzugriff und die Benutzerauthentifizierung und gehört zur Klasse *Authentication*. Die Klasse *DatamanagementPrinciples* umfasst das Attribut *document* vom Typ File für Datenrichtlinien und das Attribut *userApproval* für die Benutzerbestätigung. Die Attribute *value* und *contentType* der *File*-Klasse repräsentieren den Dokumentpfad und den Inhalt. Die *Authentication*-Klasse enthält *X.509Certificate* zur Benutzerauthentifizierung mit Zertifikaten und *authenticateUser* für die Benutzerauthentifizierung als *Boolean*. Die *Blob*-Klasse, die die Zugangskontrolle der VWS abschließt, umfasst die Attribute *value* und *contentType* für Blob-Instanzen. Schließlich wird die Klasse *SM* zur Benutzerautorisierung durch die Superklasse *Authorizable* erweitert. Die Klasse SM erbt von der Superklasse *Authorizable*, um Zugriffsbeschränkungen durchzusetzen, die eine individuelle Zuweisung basierend auf den Spezifikationen für Rollen- und Rechtemanagement ermöglichen. Es ist bemerkenswert, dass die Annahme der Datenklassifizierung nach Sensibilität integraler Bestandteil bleibt. SM kann mehrfach repliziert und erstellt werden, jeweils mit unterschiedlichen Zugriffsbeschränkungen und zulässiger Sichtbarkeit gemäß den Spezifikationen der SC *Authorizable*.

### <a name="_7.2.2"></a> IDS-Architektur

Nachdem die Governance der Daten beim internen Datenaustausch sichergestellt wurde, wird eine High-Level-Architektur vorgestellt, die einen Weg zum Austausch von Informationen und Diensten über ein interoperables System aufzeigt.

Konzeptionell ist die entwickelte High-Level-Architektur an den Datenaustausch über ein IDS wie Catena-X angelehnt (*Abbildung* 7-5). Der EDC dient in diesem Kontext als Schnittstelle für den Datenaustausch über Catena-X, auch zwischen Unternehmen.

![image](https://github.com/user-attachments/assets/ad3a387c-fb03-4da7-8294-9e9fbc9ae937)    
*Abbildung 7-5: High-Level Architektur unternehmensübergreifender Datenaustauschs mittels IDS*

Bei dem Datenaustausch über Catena-X handelt es sich ausschließlich um sog. „non-operational“ Daten, wie bspw. Kontaktdaten der jeweiligen Unternehmen, die über Catena-X an dem Datenaustausch partizipieren wollen, sowie Statusinformationen des Business-Workflows (siehe *Abbildung* 7-6).

![image](https://github.com/user-attachments/assets/c7649f61-0154-49cb-af77-5cf9ffa5f870)    
*Abbildung 7-6: Übermittlung von non-operational data*

Demgegenüber werden sog. „operational“ Daten, also die konkret produkt- oder prozessbezogenen technischen Informationen, nicht im IDS vorgehalten, sondern in den AAS-Repositories der beteiligten Stakeholder und transparent (d.h. als VWS) über den direkten Weg per EDC zwischen den Unternehmen ausgetauscht (siehe *Abbildung* 7-7).

![image](https://github.com/user-attachments/assets/cd96f80e-667e-4cd0-baa0-ada55b5f464e)    
*Abbildung 7-7: Übermittlung von operational data*

Dafür muss sich zunächst auf einen Rahmenvertrag geeinigt werden (Contract Policy), der die Art und Weise der Datenhandhabung festlegt, wobei stets die Grundsätze der Datensicherheit und Datensouveränität zu wahren sind. Dieser Rahmenvertrag wird ebenfalls über den EDC ausgetauscht und bietet die Grundlage für den weiteren Datenaustausch.

Dieser beinhaltet ein Rollen- und Rechtekonzept, der die Zugriffsrechte auf Basis der mitgegebenen Rollen vorgibt, womit der Datenurheber zu jeder Zeit die Kontrolle darüber hat, auf welche Daten Dritte zugreifen dürfen und in welcher Form, also ob lesend oder manipulierend.

Für die Gewährleistung der Einhaltung des vereinbarten Rahmenvertrages ist das Security-Konzept des Datenurhebers verantwortlich, in dem das Rollen- und Rechtekonzept abgebildet sein muss und welches individuell auf die notwendige Granularität angepasst sein muss. So kann eine Form der Zugriffsrechte sein, dass nur der Zugriff auf einzelne Submodelle möglich ist. Um noch präziser, jedoch mit einem deutlich erhöhten Verwaltungssaufwand die Zugriffsrechte steuern zu können, muss das Rollen- und Rechtekonzept bis auf die Property-Ebene reichen, um dort einzelne Attribute der einzelnen Verwaltungsschalen verwalten zu können (*Abbildung* 7-8).

![image](https://github.com/user-attachments/assets/5da3db2e-446f-4d9f-8120-72d0da9d455d)   
*Abbildung 7-8: Konzept VWS-Security*

### <a name="_7.2.3"></a>  Voraussetzungen für den International Data Space (IDS)

Um einen Use Case über den IDS durchführen zu können, müssen die folgenden Voraussetzungen erfüllt sein:

-   Die Teilnehmer (OEM und Tier-x) müssen registrierte Mitglieder des IDS (z.B. Catena-X) sein
-   Die vom IDS unterstützen Authentifizierungsmethoden müssen bedient werden können, um die Datensicherheit zu gewährleisten und Zugriff zu dem Datenraum zu bekommen. Jedes Unternehmen soll mit den von Catena X angebotenen Sicherheitsstufen einverstanden sein
-   Tier-x müssen VWS-Repositories in einem mit der IDS-Architektur (z.B. Catena-X EDC) kompatiblen Format zur Verfügung haben, um die Datensouveränität jedes Stakeholders zu gewährleisten
-   Submodellelementen können über die Konnektoren des IDS gefunden werden (z.B. Catena-X EDC). Tier-x müssen ein Portfolio von Produkten, Ressourcen und Prozessen (angebotene Dienste) anbieten, um am IDS-Ökosystem teilnehmen zu dürfen
-   Es muss eine vom OEM als Datenurheber bereitgestellte Verwaltungsschale vorliegen, über die die jeweiligen „operational“ Daten ausgetauscht werden. Alle Teilprodukte, Prozesse und Ressourcen, die für die Erzeugung des Beispielproduktes benötigt werden, sind im Datenmodell der Verwaltungsschale abgebildet.
-   Zudem müssen die Repositories, also Ablage- und Verwaltungsorte für die Verwaltungsschalen vorhanden sein, auf die der IDS im Rahmen des festgelegten Rollen- und Rechtekonzeptes zugreifen kann, um den „non operational“ B2B-Workflow abzuwickeln.

Als Basis für die nachfolgend beschriebenen Use Cases zeigt *Abbildung* 7-9 eine OEM-Definition des Kabelbaums, wobei zwei Arten von Variationen möglich sind. Außerdem werden die für die Herstellung dieses Bauteils erforderlichen Entwicklungs- und Produktionsprozesse beschrieben.

![image](https://github.com/user-attachments/assets/671c7f73-91fb-40c4-b798-a7eb7369127b)   
*Abbildung 7-9*: *Definition des Kabelbaums seitens des OEM*

### <a name="_7.2.4"></a>  Datenmonetarisierung

Das Geschäftsmodell eines Unternehmens stellt die Gesamtstrategie dar, die verschiedene Aspekte wie den Zielmarkt, das Wertversprechen und den Ansatz zur Geschäftseffizienz umfasst. Als wesentlicher Bestandteil beschreibt das Monetarisierungsmodell, wie Einnahmen generiert werden.

Im Kontext der Datenmonetarisierung geht es um mehr als nur den direkten Austausch von Daten gegen Geld. Vielmehr umfasst es die Verwertung von Erkenntnissen aus Daten, um monetäre Vorteile zu erzielen. Beispiele hierfür sind die Reduktion von Herstellungskosten und die Steigerung der Produktivität.

Die Monetarisierung von Daten im erweiterten Sinne zielt darauf ab, messbare ökonomische Vorteile zu erzeugen, basierend auf der Verwendung von aggregierten Daten oder Daten-Services [65].

Es gibt zwei Hauptkategorien der Mehrwerte, die durch Datenmonetarisierung erzielt werden können: interne Mehrwerte, die innerhalb des Unternehmens generiert werden, und externe Mehrwerte, die über Unternehmensgrenzen hinausgehen und kundenzentrierte Strategien umfassen.

![image](https://github.com/user-attachments/assets/ec452a19-91df-4219-9412-1dce32771aee)   
*Abbildung 7-10: Framework zur Datenmonetarisierung

Die *Abbildung* 7-10 zur Datenmonetarisierung zeigt zwei Hauptkategorien: die interne und die externe Datenmonetarisierung.

**Interne Datenmonetarisierung** umfasst die Generierung von wirtschaftlichen Vorteilen auf Basis von firmeneigenen oder zugekauften Daten. Dieser Prozess gliedert sich in drei wesentliche Schritte:

-   **Digitalisieren und Vernetzen**: Hierbei werden Daten digitalisiert und miteinander vernetzt, um eine umfassende Datenbasis zu schaffen.
-   **Visualisieren und Analysieren**: In diesem Schritt werden die Daten visualisiert und analysiert, um wertvolle Erkenntnisse zu gewinnen.
-   **Umsetzen und Optimieren**: Schließlich werden die gewonnenen Erkenntnisse umgesetzt und Prozesse optimiert, um wirtschaftliche Vorteile zu realisieren.

**Externe Datenmonetarisierung** bezieht sich auf die Monetarisierung von Daten durch externe Dienstleistungen. Hierbei werden zwei Hauptstrategien unterschieden:

-   **Data as a Service**: Diese Strategie ermöglicht schnelle neue Einkommensströme durch den Verkauf von Daten als Dienstleistung. Unternehmen generieren wertvolle Nebeninformationen neben den Kernprozessdaten. Diese Daten ermöglichen es, Produkte besser anzupassen, was zu erhöhtem Absatz und verbesserter Qualität führt.
-   **Data Solutions as a Service**: Hierbei handelt es sich um verbrauchsabhängige pay-per-use- oder pauschalisierte Abonnement-Modelle, die auf Datenlösungen basieren. Die digitale Marktwirtschaft erhöht die Nachfrage nach bestimmten Datentypen. Das Management muss diese Nachfrage verstehen und datenbasierte Lösungen entwickeln, die Kunden zusätzlichen Mehrwert bieten. Externe Daten können über Data as a Service integriert werden, um den Service zu optimieren. Das Management muss entscheiden, wie dieser Mehrwert am besten an Kunden vermittelt wird, oft durch Abonnement-Modelle.

Ein wichtiger Aspekt bei der externen Datenmonetarisierung ist der Datenschutz und die Datensouveränität, um die Privatsphäre und die Kontrolle über die Daten zu gewährleisten.

#### Angebot von maßgeschneiderten Maschinen

Hierbei sollen, Produkt- und Prozessdaten aus der VWS genutzt werden, um Kunden individuelle Maschinen anzubieten. Dies hilft, Überdimensionierung zu vermeiden und die Maschinen genau auf die Bedürfnisse der Kunden abzustimmen, was zu effizienteren und kostengünstigeren Lösungen führt.

#### Diagnose: Benachrichtigung über Leitungssatz-Ausfälle

Hierbei wird der Digital Twin von Leitungssätzen genutzt zur detaillierten Fehlerlokalisierung und Zustandsüberwachung innerhalb der Produktionsphase. Dadurch kann der Austausch des gesamten Kabels vermieden werden, indem nur die betroffenen Teile ausgetauscht werden. Dies führt zu einer effizienteren Wartung und reduziert die Ausfallzeiten.

Folgend wurde Ansatz 1 Wartung als Dienstleistung basierend auf den Prinzipien des [Business Model Canvas](https://de.wikipedia.org/wiki/Business_Model_Canvas)[^3] betrachtet.

[^3]: <https://de.wikipedia.org/wiki/Business_Model_Canvas>

![image](https://github.com/user-attachments/assets/c4b010af-7248-49ed-8af6-3e55b0409824)    
*Abbildung 7-11: Einfluss digitaler Zwillinge auf den Business Model Canvas [66]*

Wesentlicher Baustein dieses Konzeptes ist die Werterzeugung (value proposition), also die Erzeugung eines Nutzens durch das Produkt oder die Dienstleistung. Dabei ist entscheidend über welche Kanäle der Wert dem Kunden (customers) zu Verfügung gestellt wird. Ein gutes Kundenverhältnis (customer relationships) sichert dabei langfristige Einkommensströme (revenue) ab. Dem Einkommensstrom stehen die Kosten (costs) gegenüber, die für die Schlüsselaktivitäten (key activities), -ressourcen (key resources) und -partnerschaften (key partners) aufgebracht werden müssen.

#### Wartung als Dienstleistung

Diese Idee betrachtet die Wartung aus der Perspektive des Ressourcenanbieters. Es wird vorgeschlagen, individuelle Wartungspläne anzubieten, die auf Daten der VWS basieren. Dies ermöglicht eine maßgeschneiderte Wartung, die auf den spezifischen Bedarf und die Nutzung der Maschinen abgestimmt ist.

Das Monetarisierungskonzept “Wartung als Dienstleistung”, basierend auf dem Konzept der «[Vorbeugenden Instandhaltung](https://de.wikipedia.org/wiki/Instandhaltung#Vorbeugende_Instandhaltung)»[^4] (Proactive Maintenance) zielt darauf ab, durch die Bereitstellung von Wartungsservices feste Einnahmen zu generieren und gleichzeitig den Kunden einen klaren Mehrwert zu bieten. Dieses Konzept basiert auf dem Value Proposition Canvas, dass die Beziehung zwischen dem Kundensegment und dem Wertversprechen verdeutlicht.

[^4]: [https://de.wikipedia.org/wiki/Instandhaltung\#Vorbeugende_Instandhaltung](https://de.wikipedia.org/wiki/Instandhaltung#Vorbeugende_Instandhaltung)

**Wertversprechen**

Das zentrale Wertversprechen dieses Modells besteht in der Bereitstellung fixer Wartungskosten für Maschinenbetreiber. Dies ermöglicht den Kunden eine präzise Kalkulation ihrer Wartungsausgaben und reduziert gleichzeitig die Notwendigkeit eigener Personalkosten für Wartungsarbeiten.

**Kundenbeziehungen**

Eine feste Bindung zwischen dem Anbieter und dem Nutzer der Dienstleistung ist essenziell. Durch den Aufbau von Vertrauen und langfristigen Beziehungen wird sichergestellt, dass die Kunden die Wartungsservices kontinuierlich in Anspruch nehmen.

**Kanäle**

Die Vermarktung und Bereitstellung der Wartungsdienstleistungen erfolgt über verschiedene Webschnittstellen und Verwaltungsschalen. Diese Kanäle ermöglichen einen effizienten Datenaustausch und die Verwaltung wartungsrelevanter Parameter.

**Einnahmen**

Die Einnahmen für den Wartungsanbieter sind verlässlich und basieren auf einer Servicegebühr pro Einheit oder Zeitperiode. Dies schafft eine stabile Einnahmequelle und ermöglicht eine langfristige Planung.

**Ressourcen**

Zu den notwendigen Ressourcen gehören Diagnosesysteme in den Maschinen, eine entsprechende Infrastruktur beim Serviceanbieter sowie Fachkräfte zur Auswertung der Diagnosedaten. Diese Ressourcen sind entscheidend für die Bereitstellung qualitativ hochwertiger Wartungsservices.

**Aktivitäten**

Die Hauptaktivitäten umfassen den Betrieb eines Servicecenters (SLA), die Schulung von Fachkräften sowie die kontinuierliche Auswertung der Verfügbarkeitsdaten. Diese Aktivitäten gewährleisten eine hohe Servicequalität und Kundenzufriedenheit.

**Partner**

Wichtige Partner in diesem Modell sind Wartungspartner und Maschinenbetreiber. Durch die Zusammenarbeit mit spezialisierten Wartungspartnern kann der Serviceanbieter seine Kapazitäten erweitern und eine höhere Servicequalität sicherstellen

#### Use Case „Komponentensuche“

In diesem Use Case sucht Tier 1 nach einer bestimmten Komponente, in diesem Fall einer Leitung, die eine bereits festgelegte Spezifikation hat, zum Beispiel einen bestimmten Durchmesser oder eine bestimmte Farbe. Zu diesem Zweck stellt Tier 1 eine Anfrage zur Suche nach dieser Leitung und ihren Merkmalen auf einem der von verschiedenen Komponentenherstellern angebotenen Portfolios auf dem Marktplatz des IDS.

Basierend auf diesen Annahmen wird die Suche nach einer Leitung angestoßen, die der geforderten Spezifikation entspricht. Wurde eine geeignete Leitung gefunden wird, erfolgt eine Benachrichtigung über den IDS. Der Anforderer (Tier-1) kann nun eine Angebotseinholung anstoßen. Nach Erfüllung der Sicherheitsanforderungen und der Angebotsannahme erhält Tier 1 das betreffende Produkt und seine digitale Repräsentation (VWS). Dazu ist es erforderlich, dass Tier 1 Zugang zu den zugehörigen VWS, ihren Teilmodellen und Merkmalen hat, um diese Informationen und Dienste, in die bereits im Ökosystem von Tier 1 vorhandenen VWS-Repositories aufnehmen und referenzieren zu können.

#### Use Case „Bestellung“

In diesem Use Case möchte der Leitungssatz (LS)-Entwickler (Tier 1) für die Fertigung des Leitungssatzes eine Leitung (Produkt + VWS) bei einem Komponentenhersteller (Tier 2) bestellen. Der LS-Entwickler (Tier 1) greift auf die VWS der Komponentenherstellen (Tier 2) zu, um die VWS der LS-Verbundkomponente in dem Tier 1-Umgebung zu erstellen.

Der Use Case ist durch eine aktive/parallele Arbeit der Beteiligten gekennzeichnet, d.h. beschreibt die kollaborative Arbeit (technisch den kollaborativen Zugriff auf Typ2-VWS) zwischen zwei Unternehmen während des Entwicklungsprozesses über einen IDS als Datenvermittlungsdienst. Im Folgenden werden beispielhaft die einzelnen Teilschritte des Datenaustauschs beschrieben.

##### Schritt 1: Austausch von non operational Data über einen IDS

Tier 1 erstellt eine Ausschreibung und stellt sie über den EDC in Catena-X bereit. Catena-X agiert als B2B-Vermittlungsdienst, siehe *Abbildung* 7-6. Über den Catena-X Marketplace Service wird nach potenziellen Kandidaten, die die Tier 1-Anforderungen erfüllen, gesucht und rückgemeldet. Von diesem Zeitpunkt an findet der in der *Abbildung 7-12* dargestellte Verhandlungsprozess zwischen den potenziellen Unternehmen statt. Dadurch kann die Zahl der Kandidaten, die die Anforderungen erfüllen, verringert werden.

![image](https://github.com/user-attachments/assets/a99ea66c-349d-424f-b86b-32951bc4bc4a)    
*Abbildung 7-12: Ablauf des automatisierten Angebotsverhandlungsprozesses*

Denkbar wäre hierfür die Anwendung des Submodell-Templates [IDTA 02051 „Purchase Request Notification“](https://interopera.de/wp-content/uploads/2024/02/231113-Abschlusspraesentation-InterOpera-Purchase-Teilmodelle-Liedl.pdf) [21], welches jedoch zum Zeitpunkt der Bearbeitung dieses APs noch nicht zur Verfügung stand.

##### Schritt 2: Austausch von operational Data

Nachdem der Prozess der Suche nach einem potenziellen Kandidaten, der die Anforderungen der Tier-1 erfüllt, abgeschlossen ist, erfolgt der Austausch von „operational data“, also die Informationen und Dienstleistungen, die in den internen AAS-Repositories der einzelnen Unternehmen vorhanden sind. In Bezug auf die VWS-Struktur wären dies die Informationen und Dienste, die in den Teilmodellen zu finden sind, sowie die Merkmale, die sie abbilden.

Identitätsmanagement mit geringen organisatorischen Anforderungen

In der Praxis stehen Unternehmen bislang vor Herausforderungen bzgl. eines übergreifenden (»federated«) Identity Managements, das oft an organisatorischen und technischen Hindernissen scheitert. International Data Spaces (IDS) bieten daher ein unternehmensübergreifendes Identitätsmanagement nach modernen Standards und mit geringen organisatorischen Anforderungen. Jeder Konnektor in den IDS verfügt über einen privaten Schlüssel mit einem dazugehörigen [X.509](https://de.wikipedia.org/wiki/X.509)-Zertifikat (»Gerätezertifikat«). Im Gegensatz zu herkömmlichen PKI-basierten Enterprise-IDM-Systemen, dienen diese statischen Zertifikate jedoch lediglich der Authentifizierung und werden nicht zum Austausch von Identitätsattributen verwendet. Letztere werden durch dynamische Tokens übertragen, die die Konnektoren von einem Attributs-Server beziehen. Dieser verwaltet Selbstbeschreibungen und attestierte (zertifizierte) Eigenschaften der Konnektoren und stellt je nach Bedarf Tokens über die erforderlichen Eigenschaften eines Konnektors aus.

Damit ist die Ausstellung der statischen X.509-Zertifikate von Identitätseigenschaften entkoppelt, die sich möglicherweise im Laufe der Zeit ändern können (bspw. durch eine Zertifizierung).

Daher wird die Verwendung des „*Dynamic Attribute Provisioning Service*“ (DAPS) -Konzepts für den operativen Datenaustausch in unserem Anwendungsfall vorgeschlagen. DAPS kann als Attributsserver Auth2-Access-Tokens für International Data Spaces-Konnektoren ausstellen, die für den Zugriff auf die Dienste und Daten anderer Konnektoren benötigt werden. Der DAPS von Fraunhofer ist unter <https://daps.aisec.fraunhofer.de> erreichbar und implementiert [RFC7523](https://www.rfc-editor.org/rfc/rfc7523) JWT bearer client authentication für [OAuth2](https://de.wikipedia.org/wiki/OAuth). Dieses Protokoll ermöglicht es den Konnektoren, sich mit ihrem [X.509](https://de.wikipedia.org/wiki/X.509)-Zertifikat am DAPS zu authentifizieren und im Gegenzug ein Access Token zu erhalten, mit dem sie auf andere Konnektoren zugreifen können.

Die Entscheidung über zulässige Zugriffe trifft hierbei nicht der DAPS, sondern immer der angefragte Konnektor selbst. Der DAPS verwaltet lediglich die IDS-Attribute der registrierten Konnektoren.

Wie in der *Abbildung* 7-7 dargestellt, legt Tier-1 zunächst sein Gerätezertifikat dem DAPS über einen Konnektor vor, um ein „Dynamisches Token-Attribut“ (DAT) zu erhalten. Mithilfe eines DAT kann Tier-1 auf Informationen zugreifen, die von anderen Konnektoren bereitgestellt werden. In diesem Fall sprechen wir vom Tier-2-Konnektor. In Bezug auf die Sicherheit wird ein Transport Layer Security (TLS) verwendet, das ein sicheres Protokoll für den Austausch von Informationen über das Internet bietet, siehe *Abbildung* Schritt 2. In Schritt vier wird schließlich der Zugang zu Informationen und Diensten gewährt, in unserem Anwendungsfall greift Tier-1 auf das AAS-Repository zu.

Der allgemeine Arbeitsablauf ist wie folgt:

-   Ein anfordernder Konnektor legt dem DAPS sein Device Certificate vor, um ein dynamisches Attribut-Token (DAT) zu erhalten.
-   Dieses DAT kann dann für den direkten Zugriff auf eine von einem anderen Konnektor bereitgestellte Ressource verwendet werden. Eine alternative Konfigurationsmöglichkeit wäre die Einführung eines lokalen oder anwendungsfallspezifischen Authentifizierungsdienstes, der ein benutzerdefiniertes Zugriffstoken bereitstellt. Dies ist völlig optional und daher grau markiert.
-   Das entsprechende Token wird dann bei jeder Ressourcenzugriffsanfrage an einen Konnektor übergeben

## <a name="_7.3"></a> AP 7.3 - Pilotierung und Erprobung: Erstellung Implementierungsguideline

Das AP 7.3 „**Pilotierung und Erprobung**“ wurde ursprünglich definiert, um die Architektur der Catena-X-Plattform zu untersuchen in Bezug auf Interoperabilität mit der Verwaltungsschale. Darüberhinaus sollte eine Implementierungsguideline bereitgestellt werden. Diese Aktivitäten wurden dann im Wesentlichen in [AP 8.3 „Vorbereitung der Anbindung an Catena-X“](/TP08/README.md#ap-83-vorbereitung-der-anbindung-an-catena-x) abgearbeitet und dort dokumentiert.

![image](https://github.com/user-attachments/assets/85438c6c-5157-4e49-bd7a-eb020b7004e0)   
*Abbildung 7-13: Demonstrator-Architektur mit Catena-X und BaSyx*

## <a name="_7.4"></a> Fazit

Im Rahmen von VWS4LS-TP7 wurden im AP 7.1 die grundlegenden Anforderungen an die Datengovernance erfasst und in den technischen Gesamtkontext verortet. Zudem wurden Anforderungen und Lösungsansätze zum Thema „Datenmonetarisierung“ zusammengestellt, die jedoch aus Ressourcengründen in der fachlichen Konzeption (AP 7.2) und Pilotierung (AP 7.3) nicht weiterverfolgt wurden.

Das Hauptziel von AP 7.2 war die Spezifizierung und Entwicklung eines Konzepts zur Integration der identifizierten Aspekte eines DG in die bestehende VWS-Struktur, um einen sicheren Datenaustausch zwischen den Herstellern zu gewährleisten. Um die Relevanz des Themas und das Hauptziel basierend auf bestehenden Erkenntnissen und Forschungen zu skizzieren, führten wir zunächst eine umfassende Literaturrecherche durch. Die Literaturrecherche ergab, dass die Anzahl der Publikationen zum Thema AAS in Kombination mit einem DG aufgrund der Neuheit des Themas sehr begrenzt ist. Als Ergebnis konnte keine Veröffentlichung identifiziert werden, die einen Vorschlag oder ein anfängliches Konzept zur Implementierung eines DG für den Datenaustausch zwischen Herstellern, die VWS verwenden, bot.

Es wurden jedoch drei potenziell relevante Aspekte für die Einhaltung des DG während des Datenaustauschs zwischen Herstellern identifiziert, die **Datenrichtlinien**, die **Zugangskontrolle** sowie das **Rollen- und Rechtemanagement**, welche die Grundlage für die Spezifikation der Integration in die Struktur der VWS bilden.

Auf diese Weise wird ein erster Vorschlag für zukünftige Forschungen in diesem Bereich unterbreitet. So sollte die Integration eines DG in die bestehende Struktur der VWS den Zugang zur VWS durch die Zugangskontrolle einschränken, bei der die Benutzer zunächst ein Authentifizierungs- und Autorisierungsverfahren durchlaufen müssen, bevor sie auf die in den Repositories der VWS gespeicherten Informationen und Dienste zugreifen können.

Es wurde aufgezeigt, dass das aktuelle Metamodell der VWS die Aspekte des DG noch nicht berücksichtigt. Dennoch bietet es Spezifikationen, Definitionen und geeignete Elemente zur Integration potenzieller Aspekte des DG. Das bestehende Metamodell umfasst Klassen, SC, Attribute, Datenelemente und Beziehungen, die die Hinzufügung neuer Elemente ermöglichen, um die potenzielle Aspekte des DG integrieren. Das umfasst auch die Einführung von neuen SC wie *UserInformation* und *Authorizable*, sowie die Erstellung der Klasse *AccessControl*.

Zudem wurde eine High-Level- Architektur entwickelt, um die gemeinsame Nutzung von Daten im Bereich der Leitungssatzherstellung über einen IDS zu ermöglichen. Es wurde analysiert, welche Anforderungen und Rahmenbedingungen der Integration einer Data Governance in das Konzept der VWS berücksichtigt werden müssen, sodass ein sicherer herstellerübergreifender Datenaustausch auf Basis der VWS gewährleistet werden soll. Dabei erfolgt eine eingehende Untersuchung des aktuellen herstellerübergreifenden Datenaustauschs entlang der Wertschöpfungskette.

Im AP 7.3 (bzw. [AP 8.3](/TP08/README.md#ap-83-vorbereitung-der-anbindung-an-catena-x)) wurden dies dann konkret in einem Tractus-X basierten Demonstrator verprobt.

## Literaturverzeichnis

|  |  |
|-------|--------|
| [1]   | ISO, „ISO/IEC 27002:2022-02: Information security, cybersecurity and privacy protection - Information security controls,“ 2022. [Online]. Available: www.iso.org/standard/75652.html.  |
| [2]   | „OPC UA Online Reference - Released Specifications,“ 2024. [Online]. Available: https://reference.opcfoundation.org/.         |
| [3]   | OPC Foundation, „OPC 40570: OPC UA for the Wire Harness Manufacturing Industry,“ https://profiles.opcfoundation.org/workinggroup/88, WiP. [Online]. Available: https://profiles.opcfoundation.org/document/214.        |
| [4]   | Prostep ivip, „Harness Description List (KBL),“ prostep ivip, 26 Jun 2022. [Online]. Available: https://ecad-wiki.prostep.org/specifications/kbl/.              |
| [5]   | Prostep ivip, „Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.      |
| [6]   | Industrial Digital Twin Association, „01005-3-0-1: Specification of the Asset Administration Shell Part 5: Package File Format (AASX),“ 2024. [Online]. Available: https://industrialdigitaltwin.org/content-hub/aasspecifications/idta-01005-3-0-1_package_file_format_aasx.                             |
| [7]   | „OPC UA Online Reference - Released Specifications,“ 2024. [Online]. Available: https://reference.opcfoundation.org/.        |
| [8]   | VWS4LS Architektur-Team, „Struktur der VWS (?),“ AREAN2036 e.V., Stuttgart, 2024.           |
| [9]   | „VWS4LS-Github,“ ARENA2036 e.V., [Online]. Available: https://github.com/VWS4LS.        |
| [10]  | Industrial Digital Twin Association, „IDTA 01002-3-0-2: Specification of the Asset Administration Shell Part 2: Application Programming Interfaces,“ June 2024. [Online]. Available: https://industrialdigitaltwin.org/content-hub/aasspecifications/idta_01002-3-0-2_application_programming_interfaces. |
| [11]  | Plattform Industrie 4.0, „Verwaltungsschale in der Praxis,“ 2021. [Online]. Available: https://industrialdigitaltwin.org/wp-content/uploads/2021/09/08_verwaltungsschale_in_der_praxis_de_2020.pdf.      |
