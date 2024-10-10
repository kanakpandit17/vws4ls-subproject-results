# TP 8 - Data Storage Policy, Sicherheit, Anbindung an Catena-X
## Inhaltsverzeichnis

[AP 8.1 - Technische Anforderungsanalyse](#8.1)

[AP 8.2 - Technische Umsetzungskonzeption und Zielarchitektur](#8.2)

[AP 8.3 - Vorbereitung der Anbindung an Catena-X](#8.3)

- [8.3.1 Beispielprodukt: Teilleitungssatz](#8.3.1)
- [8.3.2 Das Anwendungsszenario](#8.3.2)
- [8.3.3 Ablauf des Szenarios](#8.3.3)
- [8.3.4 Aufbau der technischen Infrastruktur](#8.3.4)
- [8.3.5 Umsetzung des Use Cases](#8.3.5)
- [8.3.6 Whitespots](#8.3.6)

[8.4 User Interfaces](#8.4)

[8.5 Ausblick](#8.5)
- [8.5.1 Bewertung Status Quo](#8.5.1)
- [8.5.2 Blick in die Zukunft](#8.5.2)

[Literaturverzeichnis](#Literaturverzeichnis)

[Fussnoten](#Fussnoten)

## <a name="8.1"></a>AP 8.1 - Technische Anforderungsanalyse
Im AP 8.1 "**Technische Anforderungsanalyse**“ sollten, ausgehend von den aktuellen Datenhaltungssituationen der Partner, Anforderungen für eine Datenhaltung im Hinblick auf die gemeinsame Nutzung entlang der Wertkette „Leitungssatz“ erarbeitet werden. Die Zielstellung des Arbeitspaketes umfasste die Definition der notwendigen Anforderungen in Bezug zu Data Governance, Data Business Policy sowie Data Storage Policy. Da eine starke inhaltliche Überschneidung gegeben war, wurde das AP 8.1 bereits im Zuge des [AP 7.1 "Anforderungserhebung"](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP07#ap-71---anforderungserhebung) abgearbeitet und die Ergebnisse dort detailliert dokumentiert.

## <a name="8.2"></a>AP 8.2 - Technische Umsetzungskonzeption und Zielarchitektur
Im AP 8.2 „**Technische Umsetzungskonzeption und Zielarchitektur**“ sollten Lösungsansätze erforscht werden für die interoperable Nutzung von Daten der unterschiedlichen Akteure der Wertkette „Leitungssatz“ und über unterschiedliche Ablagestrukturen hinweg (On-Premises, Edge, Cloud). Als Leitbild dieser Lösungsbeschreibung wurde die übergeordnete Vision der Verwaltungsschale als Paradigma der Interoperabilität zwischen Produkt, Komponenten, Prozess und Produktion zugrunde gelegt und eine technische Anbindung mit Catena-X angestrebt. Inhaltlich wurde das AP 8.2 bereits in [AP 7.2 "Fachliche Konzeption der Daten-Policy entlang der Wertkette"](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP07#ap-72---fachliche-konzeption-der-daten-policy-entlang-der-wertkette) erarbeitet und die Ergebnisse dort detailliert dokumentiert.

## <a name="8.3"></a>AP 8.3 - Vorbereitung der Anbindung an Catena-X
Im AP 8.3 „**Vorbereitung der Anbindung an Catena-X**“ wurde die Architektur der Catena-X-Plattform untersucht in Bezug auf Interoperabilität mit der Verwaltungsschale und eine exemplarische Implementierung eines kollaborativen Datenaustauschs anhand des nachfolgend beschriebenen Use Case über Catena-X Komponenten umgesetzt, welche den bidirektionalen Datenaustausch zwischen den Akteuren anhand eines konkreten Szenarios prototypisch demonstriert. Mit diesen nachfolgend detailliert beschriebenen Aktivitäten des AP 8.3 wurde auch das [AP 7.3 "Pilotierung und Erprobung"](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP07#ap-73---pilotierung-und-erprobung-erstellung-implementierungsguideline) inhaltlich mit abgearbeitet.

### <a name="8.3.1"></a>8.3.1 Beispielprodukt: Teilleitungssatz
Für das Demonstrator-Anwendungsbeispiel wurde das vereinfachte Beispiel eines Leitungssatzes verwendet. Dieser besteht aus Stecker, Terminals und Leitungen. Zusätzlich soll die Möglichkeit gegeben sein, eine Auswahl zwischen zwei Varianten auszuwählen. Hierfür ist Variante 1, 2 Stecker, die Terminals und die beiden oberen Leitung in *Abbildung 8-1*, und Variante 2 enthält die beiden Stecker, die Terminals und die beiden unteren Leitungen.

![image](https://github.com/user-attachments/assets/8985f97a-a830-48b7-a9d9-1de542732ea6)   
*Abbildung 8-1: Vereinfachte Darstellung des Leitungssatzes*

### <a name="8.3.2"></a>8.3.2 Das Anwendungsszenario
Ein OEM sendet einen Entwicklungsauftrag für eine 150%-Leitungssatzvariante an den Tier-1. In dem Entwicklungsauftrag ist eine Liste mit zugelassenen Suppliern mit den jeweiligen Komponenten enthalten. Der Tier-1 hat anschließend die Aufgabe alle notwendigen Informationen zu den einzelnen Komponenten von den Product-Ownern (Tier-2) zu aggregieren. Hierfür müssen die richtigen Endpunkte der Tier-2 identifiziert werden. Dazu werden die im Entwicklungsauftrag seitens des OEM hinterlegten Informationen verwendet. Ziel ist es, einen vollständigen aggregierten Digitalen Zwilling beim Tier-1 zu erzeugen, der alle Produktinformationen enthält, die von den einzelnen Tier-2 für Ihr Komponenten zu Verfügung gestellt werden.

In diesem Szenario wird eine Wertschöpfungskette des Leitungssatzes über drei Stufen abgebildet. Insgesamt werden beispielhaft fünf Teilnehmer betrachtet:

1.  Ein OEM als Auftraggeber
2.  Ein Tier 1 als Konfektionär und Auftragsempfänger und Data Consumer von Tier 2
3.  Drei Tier 2 als Lieferanten von Tier 1 und Data Provider

![image](https://github.com/user-attachments/assets/6e02815a-3a37-4a15-8eb9-8bbad80403dc)   
*Abbildung 8-2: Beispielhafte Darstellung der Wertschöpfungskette eines Leitungssatzes*

### <a name="8.3.3"></a>8.3.3 Ablauf des Szenarios
Die Aktionen der Akteure lassen sich grundlegend in zwei Kategorien aufteilen:

1.  **Data Provisioning**
2.  **Data Consumption**

Der Use Case wird in diesem Kapitel auf Business Ebene beschrieben. Die detaillierten Aktionen auf technischer Ebene zur Realisierung des Use Case-Demonstrators mit Catena-X sind im Kapitel „Umsetzung des Use Cases“ beschrieben.

#### OEM: Data Provisioning
Trigger für den Use Case ist die Anforderung des OEMs für einen Leitungssatz. Für unser vereinfachtes Szenario gehen wir davon aus, dass der OEM definiert, von welchem Zulieferer die Komponenten kommen sollen. Diese Anforderungen legt er in Form eines Submodels an und registriert einen Digitalen Zwilling in seiner DTR. Anschließend informiert er seinen Tier 1 (Konfektionär) über den Auftrag.

#### Tier 2: Data Provisioning
Die Tier 2 stellen die Informationen zu ihren Produkten in Form von Digitalen Zwillingen (AAS) bereit. Dazu erstellen sie die notwendigen Submodels. Diese werden dann zunächst in der Asset-Administration-Shell-Environment (AAS-Environment) hochgeladen. Danach werden in Catena-X entsprechende Digitale Zwillinge erstellt und in der DTR registriert.

#### Tier 1: Data Consumption (vom OEM)
Tier 1 greift auf die Submodelle des OEMs zu. In diesem Kontext wird davon ausgegangen, dass der Tier1 vom OEM eine Mitteilung erhält, dass ein Entwicklungsauftrag vorliegt. Er sichtet die Informationen innerhalb des Auftrags und kann anhand der enthaltenen Informationen (BPNs) die erforderlichen Endpunkte der EDCs von den entsprechenden Tier 2 herausfinden.

#### Tier 1: Data Consumption (von den Tier 2)
Mit den vom OEM definierten Zulieferern kann der Tier 1 die entsprechenden Endpunkte der Tier 2 herausfinden und auf die Daten zugreifen. Diese kann er im Anschluss sichten und entsprechende Komponenten für die Aggregation aussuchen.

#### Tier 1: Data Provisioning
Mit den Informationen der Tier 2 (welche Komponenten sie anbieten) kann der Tier 1 nun einen Leitungssatz mit den entsprechenden Komponenten darstellen. Er legt hierfür entsprechende Submodelle an und stellt die Verbindungen zu den ausgewählten Komponenten her. Daraufhin registriert er einen Digitalen Zwilling in seiner DTR mit den entsprechenden Submodels (detaillierte Beschreibung in Abschnitt 0 & 1.3.5.6.5).

![image](https://github.com/user-attachments/assets/dc9183bb-efa8-4544-a196-63af01a3b150)   
*Abbildung 8-3: Prozessdiagramm Use Case*

### <a name="8.3.4"></a>Aufbau der technischen Infrastruktur
Bitte beachten Sie, dass die beschriebenen Links lediglich intern (innerhalb des Netzwerks, der ARENA2036) nutzbar sind.

#### Benötigte Komponenten/Services für Data Provisioning
Wie in Abschnitt 8.3.3 beschrieben sind alle Akteure (OEM, Tier 1, Tier 2) Data Provider. Dementsprechend benötigen sie folgende Komponenten[^1] die im Catena-X Operating Model[^2] als Enablement Services klassifiziert werden:

[^1]: https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Operation%20View%20Digital%20Twin%20Kit\#deployment

[^2]: https://catenax-ev.github.io/docs/next/operating-model/what-service-map

| Komponente             | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Referenzimplementierung                         | Standardisiert in                        |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------|------------------------------------------|
| Konnektor              | Ein Konnektor ist eine dezentrale Softwarekomponente für den Peer-to-Peer Datenaustausch zwischen zwei Datenökosystem-Teilnehmern. Er stellt die Datenendpunkte bereit und kann Nutzungsbedingungen mitgeben, interpretieren und durchsetzen.                                                                                                                                                                                                                                         | Tractus-X Eclipse Dataspace Connector (EDC)[^3] | CX-0018 Dataspace Connectivity v3.0.0    |
| Digital Twin  Registry | Mit einer Registry für Digitale Zwillinge veröffentlicht ein Anbieter digitale Darstellungen der Assets. Diese Daten sind in Teilmodellen gekapselt, die über Anweisungen zugänglich sind, die ein Verbraucher im Register für digitale Zwillinge (DTR) findet. Die DTR hält sich an die AssetAdministrationShellRegistryServiceSpecification[^4] und die DiscoveryServiceSpecification[^5] und enthält daher nur Metadaten. | Tractus-X Digital Twin Registry (DTR)[^6]       | CX-0002 Digital Twins in Catena-X v2.2.0 |
| Submodel Server        | Die Datenquelle, die einer Teilmenge der Submodel-API entspricht, wie sie in AAS Teil-2: Application Programming Interfaces [1] definiert ist. Sie liefert die eigentlichen Daten, nach denen der Verbraucher sucht, über einen strukturierten Endpunkt, der durch die SubmodelServiceSpecification[^7] definiert ist, und gemäß den im Repository für semantische Modelle[^8] definierten strukturierten Datenformaten.                                                              | FA³ST-Framework,  Eclipse BaSyx, AASX Server    | CX-0002 Digital Twins in Catena-X v2.2.0 |

[^3]: https://github.com/eclipse-tractusx/tractusx-edc

[^4]: https://app.swaggerhub.com/apis/Plattform_i40/AssetAdministrationShellRegistryServiceSpecification/V3.0_SSP-002\#/

[^5]: https://app.swaggerhub.com/apis/Plattform_i40/DiscoveryServiceSpecification/V3.0.1_SSP-001

[^6]: https://github.com/eclipse-tractusx/sldt-digital-twin-registry

[^7]: https://app.swaggerhub.com/apis/Plattform_i40/SubmodelServiceSpecification/V3.0_SSP-003

[^8]: https://github.com/eclipse-tractusx/sldt-semantic-models

*Tabelle 8-1: Benötigte Komponenten für Data Provisioning*

Als Anforderung aus dem Projekt soll Eclipse BaSyx[^9] als Quelle der Submodels (Submodel Server) verwendet werden. Die von jedem Teilnehmer deployten Komponenten werden in *Tabelle 8-1* abgebildet.

[^9]: https://eclipse.dev/basyx/

![image](https://github.com/user-attachments/assets/bc8c1edd-dd5e-4911-b01f-0bd1dfa03a22)   
*Abbildung 8-4: Benötigte Services eines Data Providers*

#### Core Services und Onboarding Services
Für den beschriebenen Use Case muss ein komplettes Catena-X Datenökosystem bereitgestellt werden. Neben den in Abschnitt 8.3.4.1 beschriebenen Enablement Services müssen daher noch Core Services und Onboarding Services bereitgestellt werden (siehe Catena-X Operating Model[^10]). Diese werden üblicherweise von einer Catena-X Operating Company bereitgestellt (z.B. Cofinity-X). Für dieses Projekt wird die Operating Company in der ARENA-X-Umgebung simuliert und die entsprechenden Services eigens aufgesetzt.

[^10]: https://catenax-ev.github.io/docs/next/operating-model/what-service-map

Eine komplette Auflistung der für diesen Use Case genutzten Datenökosystem-Services sind in der folgenden Tabelle dargestellt:

| Service                                                                                      | Version        |
|----------------------------------------------------------------------------------------------|----------------|
| [Tractus-X-Umbrella](https://eclipse-tractusx.github.io/docs/tutorials/e2e/connect/)         | 0.17.0         |
| [Portal](https://github.com/eclipse-tractusx/portal)                                         | 1.8.1          |
| [Central-IDP](https://github.com/gematik/ref-idp-server) (Identity Provider)                 | 2.1.0          |
| Shared-IDP (Identity Provider)                                                               | 2.1.0          |
| [Discovery Finder](https://github.com/eclipse-tractusx/sldt-discovery-finder)                | 0.2.5          |
| [Self Description (SD) - Factory](https://github.com/eclipse-tractusx/sd-factory)            | 2.1.19         |
| [BPN Discovery](https://github.com/eclipse-tractusx/sldt-bpn-discovery)                      | 0.2.6          |
| [Managed Identity Wallet (MIW)](https://github.com/eclipse-tractusx/managed-identity-wallet) | 0.4.0          |
| [Semantic-Hub](https://github.com/eclipse-tractusx/sldt-semantic-hub)                        | 0.2.3          |
| [TX-Data-Provider](https://github.com/eclipse-tractusx/tractusx-edc) (OEM)                   | 0.0.5          |
| TX-Data-Provider (EDC Tier One)                                                              | 0.0.5          |
| TX-Data-Provider (EDC Tier Two \#1)                                                          | 0.0.5          |
| TX-Data-Provider (EDC Tier Two \#2)                                                          | 0.0.5          |
| TX-Data-Provider (EDC Tier Two \#3)                                                          | 0.0.5          |
| BaSyx-Services                                                                               | -              |
| AAS-Environment                                                                              | 2.0.0-SNAPSHOT |
| AAS-Registry                                                                                 | 2.0.0-SNAPSHOT |
| SM-Registry                                                                                  | 2.0.0-SNAPSHOT |
| AAS-Discovery                                                                                | 2.0.0-SNAPSHOT |
| AAS-Web-UI                                                                                   | V2-240515      |

*Tabelle 8-2: Zusätzliche Services (Core- und Onboarding Services)*

#### Weitere Services
Neben den Datenökosystem-Services von Catena-X oder BaSyx wurden folgende weitere nennenswerte Services für den Betrieb benutzt. Diese befinden sich teilweise im Cluster und teilweise installiert auf der Ubuntu VM:

-   Ein [nginx](https://nginx.org/en/) (HTTP/S Webserver) in Version **1.18.0**
    -   Ermöglicht den Externen Zugriff auf die Applikationen und leitet Web-Anfragen weiter
-   Ein [MQTT](https://mqtt.org/): (Message-queue Service) in Version **2.0.15**
    -   Wird von den BaSyx Komponenten für die Kommunikation zwischen Services genutzt
-   Mehrer [MongoDBs](https://www.mongodb.com/) (Dokument-orientierte Datenbanken) in Version **5.0.10**
    -   Wird in Catena-X und BaSyx für die Speicherung von Dokument-Daten verwendet
-   Mehrere [HashiCorp Vaults](https://www.hashicorp.com/products/vault) (Secret Management Services) in Version **1.10.3**
    -   Speichert Secrets der einzelnen Services, um sich z.B. bei den Identity Provider Keycloaks zu identifizieren
-   Mehrere [PostgreSQLs](https://www.postgresql.org/) (Relationale Datenbanken) in Version **15.1.0**
    -   Wird von EDCs, Keycloaks, Catena-X Services, konkret z.B. Portal-Services, BPN-Discovery, Discovery-Finder und anderen benutzt, um relationale Daten zu speichern
-   Mehrere [Keycloaks](https://www.keycloak.org/) (Identity and Access Management) in Version **22.0.3**
    -   Sind für die Identity Provider Tätigkeiten im Catena-X Ökosystem nötig, um sowohl Participants als auch einzelne Services selbst zu Authentifizieren und Authorisieren

#### Architektur
##### Übersicht
Ausgehend von *Abbildung 8-5* und mit den in den Kapiteln 8.3.4.1, 8.3.4.2 & 81.3.4.3 beschriebenen benötigten Komponenten ergibt sich folgendes Gesamtarchitekturbild:

![image](https://github.com/user-attachments/assets/144f2f1e-00d9-4fb3-aaa7-90806957dd5b)   
*Abbildung 8-5: ARENA-X-VWS4LS-Architektur*

##### Detail-Architektur

![image](https://github.com/user-attachments/assets/0fc4a58f-9e22-49af-9543-d8065228d023)   
*Abbildung 8-6: Detail-Architektur*

#### Installation Server
Für die Installation wurde ein Ubuntu-Server mit der Version 20.04 unter dem Hostnamen https://tractus-x-06.arena2036.de mit Administrator-Rechten zur Verfügung gestellt. Die Software-Komponenten werden auf einem Minikube Kubernetes Cluster deployt. Das konkrete Deployment der Komponenten, sowie durchzuführende Aufgaben werden in den Abschnitten 1.3.4.6 und 1.3.4.7 beschrieben.

##### Entwickler-Setup
Es gibt mehrere Möglichkeiten für das Entwickler-Setup auf den VMs. Für das von uns genutzte, sind mehrere Voraussetzungen zu erfüllen:
-   Auf dem Entwicklerrechner muss eine X-Server Umgebung installiert sein
-   Auf dem Entwicklerrechner muss eine DISPLAY Environment-Variable definiert sein
-   Man muss sich mit aktiviertem X-Server Support über ssh auf die VM verbinden. Bspw. mit folgender Konfiguration in der \~/.ssh/config:
```
Host arena2036-06
    HostName tractus-X-06.arena2036.de
    User <user>
    ForwardX11 yes
    ForwardX11Trusted yes
```
-   Eine ```.Xauthority Datei``` muss vorhanden sein. Diese kann mit einem Befehl wie ```xauth generate 0.0``` generiert werden und muss als Environment-Variable gesetzt sein:

```    export *XAUTHORITY*=\$HOME/.Xauthority```

-   Wenn die Konfiguration passt, müsste es möglich sein den Browser über den Befehl chromium zu starten
-   Dies kann in den folgenden Schritten nützlich sein, um bspw. von lokal auf Services zuzugreifen oder das Minikube Dashboard anzusprechen. Diese kann über den Befehl minikube dashboard --port 12345 gestartet werden

##### Nginx
Die Installation der Webserver-Lösung „Nginx“ erfolgt mit dem Standard Ubuntu Package Manager „apt“:

```sudo apt install nginx```

Nach der Installation befindet sich die Nginx Installation inkl. der Binärdateien unter /usr/sbin/nginx. Die Konfigurationsdateien können hingegen unter ```/etc/nginx gefunden werden.```
Für die Konfiguration des Nginx müssen nginx.conf-Dateien angelegt werden. Dies ist auf unterschiedliche Weise möglich. Für unser Deployment wurde die Konfiguration für die Services unter der Datei /etc/nginx/conf.d/tractus-x angelegt: Die entsprechende Konfiguration sieht folgendermaßen aus:
```
server {
        # register certificates
        ssl_certificate /etc/nginx/tractus-x-06.arena2036.de.crt;
        ssl_certificate_key /etc/nginx/tractus-x-06.arena2036.de.key;

        # login with password
        auth_basic "Restricted Access";
        auth_basic_user_file /etc/nginx/conf.d/.htpasswd;

        # forward incoming to minikube
        location / {
                proxy_set_header   Host $http_host;
                proxy_pass http://192.168.49.2;
  }
```

###### Passwort-Schutz mit „Basic Authentification“ auf nginx
Um einen einfachen Schutz der Infrastruktur zu haben, wurde eine „Basic Authentication“ für Nginx erstellt.

Um verschlüsselte Passwörter zu definieren, muss zunächst eine Hilf-Applikation installiert werden. Dafür wird htpasswd verwendet. Für htpasswd ist eine Installation von apache2-utils erforderlich. Dies kann durch folgenden Befehle durchgeführt werden:
```
sudo apt-get install apache2-utils
sudo apt get install htpasswd
```
Für die Erstellung der initialen Passwort-Datei für einen Benutzer kann folgender Befehl genutzt werden:

```sudo touch /etc/nginx/conf.d/.htpasswd```

Nach Befehlseingabe kann das Passwort eingegeben werden:

```sudo htpasswd -c .htpasswd \<USER\>```

Weitere verschlüsselte Passwörter können generiert werden. Nach Befehlseingabe kann das Passwort eingegeben werden.
```
openssl passwd -apr1
Enter password: ...
```
Die Passwörter sind in der Datei /etc/conf.d/.htpasswd hinterlegt. Hier sind pro Zeile die Einträge hinterlegt, im Format \<USER\>:\<PASSWORD\>. Ein Beispiel für einen solchen Eintrag ist:

```\<USERNAME\>:\$apr1\$itGWRI3M\$bIzdT/9XJNq7QEmnt4IyD0```

###### Zertifikat
Das Zertifikat wird erstellt und in Nginx hinterlegt. Ein self-signed Zertifikat erfüllt nicht alle Security-Anforderungen, aber es ermöglicht den Zugriff über https für die Subdomains mit wenig Aufwand.

Das Zertifikat wird für die Domain tractus-x-06.arena2036.de, dessen Subdomains und dessen IP erstellt:
```
openssl req -x509 -newkey rsa:4096 -sha256 -days 3650 \\
\-nodes -keyout tractus-x-06.arena2036.de.key -out tractus-x-06.arena2036.de.crt -subj "/CN=tractus-x-06.arena2036.de" \\
\-addext "subjectAltName=DNS:tractus-x-06.arena2036.de,DNS:\*.tractus-x-06.arena2036.de,IP:141.70.214.186"
```
Es resultieren eine Private-Key-Datei /etc/nginx/all.tractus-x-06.arena2036.de.key und eine Zertifikatsdatei /etc/nginx/all.tractus-x-06.arena2036.de.crt. Diese werden in nginx registriert.

Zuletzt sollten die Zertifikate ebenfalls im Betriebssystem installiert werden. Dies passiert in der VM folgendermaßen:
```
sudo cp /etc/nginx/all.tractus-x-06.arena2036.de.crt /usr/local/share/ca-certificates/
sudo chmod 644 /usr/local/share/ca-certificates/all.tractus-x-06.arena2036.de.crt
sudo update-ca-certificates
```
Unter Windows können die Zertifikate per „Rechtsklick \> „Install Certificate” unter den „Trusted Root Certification Authorities Store“ aufgenommen werden.

![image](https://github.com/user-attachments/assets/70295d48-bc4f-4e70-9cd2-58bd467c1c73)   
*Abbildung 8-7: Erzeugte Security-Dateien zur Registrierung in nginx*

###### Firewall-Freischaltung

Für den Zugriff auf dem Server mit http (Port 80) und https (Port 443) ist zusätzlich eine Ubuntu-Firewall-Freischaltung erforderlich. Diese kann mit folgendem Befehl durchgeführt werden:
```
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
```
Zusätzlich kann auch eine Regel für den Nginx erstellt werden, welche mit folgendem Befehl erlaubt werden kann:

```sudo ufw allow "Nginx Full"```

Den Status der Freischaltung kann man mit folgendem Befehl überprüfen:

sudo ufw status

Das Ergebnis kann folgendermaßen aussehen:
```
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere
Nginx Full                 ALLOW       Anywhere
22/tcp (v6)                ALLOW       Anywhere (v6)
Nginx Full (v6)            ALLOW       Anywhere (v6)
```
###### Host-Dateien

Für den Zugriff auf die Komponenten im Minikube Cluster ist die Einrichtung von Redirects in der hosts-Datei erforderlich. Dies erfolgt in der /etc/hosts-Datei, nach dem Beispiel:
```
192.168.49.2    centralidp.tractus-x-06.arena2036.de
192.168.49.2    sharedidp.tractus-x-06.arena2036.de
192.168.49.2    portal.tractus-x-06.arena2036.de
...
```
Standartmäßig entspricht die Minikube IP 192.168.49.2. Diese kann über den folgenden Befehl überprüft werden:

```minikube ip```

Für den Zugriff vom externen Rechner auf den tractus-x-06.arena2036.de Server ist auch die Erweiterung der lokalen Host Datei erforderlich. Diese Datei ist unter Windows hier hinterlegt:

```C:\\Windows\\System32\\drivers\\etc\\hosts```

Die externe IP kann über den folgenden Befehl überprüft werden:

```ping -4 tractus-x-06.arena2036.de```

Die vollständige Liste der Hosts-Einträge für einen externen Zugriff auf tractus-x-06.arena2036.de mit der IP 141.70.214.186 ist die folgende:
```
141.70.214.186	centralidp.tractus-x-06.arena2036.de
141.70.214.186	sharedidp.tractus-x-06.arena2036.de
141.70.214.186	portal.tractus-x-06.arena2036.de
141.70.214.186	portal-backend.tractus-x-06.arena2036.de
141.70.214.186	managed-identity-wallets.tractus-x-06.arena2036.de
141.70.214.186	semantics.tractus-x-06.arena2036.de
141.70.214.186	sdfactory.tractus-x-06.arena2036.de
141.70.214.186	bpndiscovery.tractus-x-06.arena2036.de
141.70.214.186	discoveryfinder.tractus-x-06.arena2036.de
141.70.214.186	oem-controlplane.tractus-x-06.arena2036.de
141.70.214.186	oem-dataplane.tractus-x-06.arena2036.de
141.70.214.186	oem-dtr.tractus-x-06.arena2036.de
141.70.214.186	oem-sdb.tractus-x-06.arena2036.de
141.70.214.186	tierone-controlplane.tractus-x-06.arena2036.de
141.70.214.186	tierone-dataplane.tractus-x-06.arena2036.de
141.70.214.186	tierone-dtr.tractus-x-06.arena2036.de
141.70.214.186	tierone-sdb.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-1-controlplane.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-1-dataplane.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-1-dtr.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-1-sdb.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-2-controlplane.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-2-dataplane.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-2-dtr.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-2-sdb.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-3-controlplane.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-3-dataplane.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-3-dtr.tractus-x-06.arena2036.de
141.70.214.186	tiertwo-3-sdb.tractus-x-06.arena2036.de
141.70.214.186	aas-webui.tractus-x-06.arena2036.de
141.70.214.186	aas-discovery.tractus-x-06.arena2036.de
141.70.214.186      oem-aas-env.tractus-x-06.arena2036.de  
141.70.214.186      tierone-aas-env.tractus-x-06.arena2036.de
141.70.214.186      tiertwo-1-aas-env.tractus-x-06.arena2036.de
141.70.214.186      tiertwo-2-aas-env.tractus-x-06.arena2036.de
141.70.214.186      tiertwo-3-aas-env.tractus-x-06.arena2036.de
141.70.214.186	aas-registry.tractus-x-06.arena2036.de
141.70.214.186	sm-registry.tractus-x-06.arena2036.de
141.70.214.186	pgadmin4.tractus-x-06.arena2036.de
```

#### Aufsetzen der Catena-X-Komponenten
Als Basis für das Catena-X Deployment werden die Umbrella-Helm Charts von Tractus-X genutzt. Diese werden unter dem folgenden Repository bereitgestellt:

-   <https://github.com/eclipse-tractusx/tractus-x-umbrella>

Die genutzte Version ```0.17.0``` entspricht dabei dem, zu dem Zeitpunkt für die 2. Tractus-X-Community-Days vorbereiteten, Stand und Tractus-X Release 2403.

Die fertigen Konfigurationen werden auf einem separaten Fork unter folgendem Repository bereitgestellt:

-   <https://github.com/Arena2036-Umbrella-Charts/tractus-x-umbrella-arena2036>

##### Konfiguration
Für die Installation der Komponenten wurden die folgenden Änderungen an den Umbrella-Helm-Charts von Tractus-X durchgeführt.

Zunächst wurde der bestehen Chart-Release unter [charts/umbrella](https://github.com/Arena2036-Umbrella-Charts/tractus-x-umbrella-arena2036/tree/vws4ls/charts/umbrella) im Repository kopiert und ein neuer Chart-Release unser [charts/umbrella-arena2036](https://github.com/Arena2036-Umbrella-Charts/tractus-x-umbrella-arena2036/tree/vws4ls/charts/umbrella-arena2036) angelegt. Die ursprüngliche Datei [values.yaml](https://github.com/Arena2036-Umbrella-Charts/tractus-x-umbrella-arena2036/blob/vws4ls/charts/umbrella-arena2036/values.yaml) wurde als Grundlage genutzt.

Die folgenden Änderungen fanden, soweit nicht anders beschrieben, in der Datei [charts/umrella-arena2036/values.yaml](https://github.com/Arena2036-Umbrella-Charts/tractus-x-umbrella-arena2036/blob/vws4ls/charts/umbrella-arena2036/values.yaml) statt. Im Allgemeinen gilt, dass die Änderungen allgemein gefasst werden und im Detail im entsprechenden Repository über die Git-History überprüft werden können, unter Revision Nummer ```ba502b927bc0e15fc395ccd2ce9de008508d68d4```. Die entsprechende [values.yaml](https://github.com/Arena2036-Umbrella-Charts/tractus-x-umbrella-arena2036/blob/vws4ls/charts/umbrella-arena2036/values.yaml) ist zusätzlich als [values_reference.yaml](https://github.com/Arena2036-Umbrella-Charts/tractus-x-umbrella-arena2036/blob/vws4ls/charts/umbrella-arena2036/values_reference.yaml) im Ordner ```charts/umbrella-arena2036``` abgelegt.

Wenn von einer Allgemeinen Hostnamen-Anpassung die Rede ist, bezieht sich das auf das Pattern [https://\<service\>.tractus-x-06.arena2036.de]().

###### Zertifikate
Zunächst muss das Zertifikatsmanagement angepasst werden. Dafür wurde eine ```tractus-x-06.cluster-issuear.yaml``` erstellt, die eine Kubernetes-Konfiguration beinhaltet und die auf das Cluster applied werden muss. Außerdem muss das Zertifikat und Key als Secret im Cluster angelegt werden. Die Befehle dafür sind:
```
cd /etc/nginx
kubectl create secret tls tractus-x-06-tls --cert=./all.tractus-x-06.arena2036.de.crt --key=\~/all.tractus-x-06.arena2036.de.key
cd /\<repository-pfad\>/charts/umbrella-arena2036
kubectl apply -f tractus-x-06.cluster-issuer.yaml
```

###### Portal
-   Aktivierung des Portals
-   Anpassung der Host-Namen für
    -   Host, Mailing, Provisioning, Frontend und Backend
-   TLS-Konfiguration für
    -   Frontend, Backend
-   Anpassung der Service-Adressen Environment-Variablen für die Operating-Company-Services auf https://\<service\>.tractus-x-06.arena2036.de
-   Anpassung der Nginx Ingress Regeln für ```cors-allow-origin``` und ```cors-allow-credentials```
-   Konfiguration der PostgreSQL Authentifizierung

###### Central-IDP
-   Aktivierung von [Central-IDP](https://github.com/gematik/ref-idp-server)
-   Anpassung des Host-Namen für Central-IDP
-   TLS Konfiguration für Central-IDP
-   Keycloak Truststore Konfiguration
-   TLS Zertifikats-Store Definition
-   Richtigstellung der Volume-Mounts /realms
-   Konfiguration der PostgreSQL Authentifizierung
-   Konfiguration eines Admin-Users

###### Shared-IDP
-   Aktivierung von Shared-IDP
-   Anpassung des Host-Namens für Shared-IDP
-   TLS Konfiguration für Shared -IDP
-   Keycloak Truststore Konfiguration
-   TLS Zertifikats-Store Definition
-   Richtigstellung der Volume-Mounts /realms
-   Konfiguration der PostgreSQL Authentifizierung
-   Konfiguration eines Admin-Users

###### BPN-Discovery
-   Aktivierung der BPN-Discovery
-   Anpassung des Host-Namens für BPN-Discovery
-   Ingress Konfiguration erstellen, da nicht vorhanden
    -   Ingress-Regeln definieren
-   Authentifizierung für den Central-IDP mit Client Cl22-CX-BPND erstellen
-   Konfiguration der PostgreSQL Authentifizierung

###### Discoveryfinder
-   Aktivierung des Discoveryfinders
-   Anpassung des Host-Namens für Discoveryfinder
-   Ingress Konfiguration anpassen
    -   Ingress-Regeln definieren
-   Initial-Endpoint Konfiguration anpassen
-   Authentifizierung für den Central-IDP mit Client Cl21-CX-DF erstellen
-   Konfiguration der PostgreSQL Authentifizierung

###### Self-Description
-   Aktivierung des Self-Description Services
-   Anpassung des Hostnamens für die Self-Description
-   Ingress Konfiguration erstellen, da nicht vorhanden
    -   Ingress-Regeln definieren
-   Erstellung der Central-IDP Konfiguration
    -   Authentifizierung für den Central-IDP mit Client sa-cl5-custodian-1 erstellen
    -   Setzen von Client-Secret, Realm und Resource
    -   Anpassung des Host-Namens

###### Managed Identity Wallet
-   Aktivierung des Managed-Identity-Wallets
-   Anpassung des Hostnamens für den Managed-Idenity-Wallet
-   Anpassung der Keycloak Konfiguration
-   Ingress Konfiguration anpassen
    -   Ingress-Regeln definieren
-   Seeding Konfiguration erstellen und für unseren Use-Case anpassen
-   Konfiguration der PostgreSQL Authentifizierung

###### Data Seeding
Das Data-Seeding besteht primär aus zwei Komponenten:

-   Keycloak initialisierung
-   Management-Identity-Wallet initialisierung für die Participants

**Keycloak**

Die Tractus-X Umbrella-Charts haben ein gewisses Set an BPNs und Clients, die für verschiedene Use-Cases gedacht sind und tief in die Umbrella-Charts definiert sind. Daher ist die einfachste Möglichkeit für unseren Use-Case die Template-User zu nutzen, anstatt komplett neue BPNs und Clients zu erstellen, da der Mehrwert keinen Aufwand hätte.

Für den Use-Case sind die angebotenen BPNs und Clients folgendermaßen den Participants zugeordnet:

| BPN              | Alias               | ClientId | Zuordnung                    |
|------------------|---------------------|----------|------------------------------|
| BPNL00000003AZQP | BPN_OEM_C           | satest01 | -                            |
| BPNL00000003AYRE | BPN_OEM_A           | satest02 | **OEM**                      |
| BPNL00000003AVTH | BPN_OEM_B           | satest03 | -                            |
| BPNL00000003AWSS | BPN_IRS_TEST        | satest04 | -                            |
| BPNL00000003B0Q0 | BPN_N_TIER_A        | satest05 | **Tier One**                 |
| BPNS0000000008ZZ | BPN_TRACEX_A_SITE_A | satest06 | -                            |
| BPNL00000003CNKC | BPN_TRACEX_B        | satest07 | -                            |
| BPNL00000003B6LU | BPN_DISMANTLER      | satest08 | -                            |
| BPNL00000003CML1 | BPN_TRACEX_A        | satest09 | -                            |
| BPNS00000008BDFH | BPN_TRACEX_B_SITE_A | satest10 | -                            |
| BPNL00000003B2OM | BPN_TIER_A          | satest11 | **Tier Two \#1 (Kostal)**    |
| BPNL00000003CSGV | BPN_TIER_C          | satest12 | **Tier Two \#2 (Coroplast)** |
| BPNL00000003B5MJ | BPN_TIER_B          | satest13 | **Tier Two \#3 (Arena2036)** |
| BPNL00000003AXS3 | BPN_SUB_TIER_B      | satest14 | -                            |
| BPNL00000003B3NX | BPN_SUB_TIER_A      | satest15 | -                            |
| BPNL00000000BJTL | BPN_SUB_TIER_C      | satest16 | -                            |

*Tabelle 8-3: Liste der BPNLs*

Neben der Participants gibt es eine Reihe an Service-Identities. Eine vollständige Auflistung der geseedeten Authentifizierungen befindet sich in der folgenden Tabelle:

| Beschreibung                                                                           | ClientId           |
|----------------------------------------------------------------------------------------|--------------------|
| Confidential client for BPDM                                                           | Cl7-CX-BPDM        |
| Confidential client for BPDM Portal Gate                                               | Cl16-CX-BPDMGate   |
| Confidential client for Managed Identity Wallet                                        | Cl5-CX-Custodian   |
| Service account for Portal-Backend to call Keycloak                                    | sa-cl1-reg-2       |
| Service account Clearinghouse update application                                       | sa-cl2-01          |
| Service account SelfDescription (SD) update application                                | sa-cl2-02          |
| Service account AutoSetup trigger - Portal to Vendor Autosetup                         | sa-cl2-03          |
| Service account Discovery Finder                                                       | sa-cl21-01         |
| Service account BPN Discovery                                                          | sa-cl22-01         |
| Service account for SD Hub Call to Custodian for SD signature                          | sa-cl5-custodian-1 |
| Service account for Portal to call Custodian Wallet                                    | sa-cl5-custodian-2 |
| Service account for Portal to access BPDM for Company Address publishing into the BPDM | sa-cl7-cx-5        |
| Service account for Portal to SD                                                       | sa-cl8-cx-1        |
| Service account in sharedidp master realm for portal backend                           | sa-cl1-reg-1       |

*Tabelle 8-4: Seeding Data Authentifizierung*

Eine kurze Beschreibung der original geseedeten Daten befindet sich u.A. in der Dokumentationsdatei ```concepts/seeds-overall-data.md``` im Repository.

Die eigentlichen Daten befinden sich an den Stellen:

-   Für den Zentralen Identity Provider
    -   ````init-container/iam/centralidp/R2403/CX-Central-realm.JSON````
-   Für den Shared Identity Provider
    -   ````init-container/iam/sharedidp/master-realm.JSON````
    -   ````init-container/iam/sharedidp/CX-Operator-realm.JSON````
    -   ````init-container/iam/sharedidp/CX-Operator-users-0.JSON````

Die Daten werden über einen Docker-Container eingespielt. Dieser basiert auf dem Dockerfile init-container/iam/Dockerfile.

Der Shared-IDP ist dabei der „Identity Provider“ für User für den Central-IDP. Dies ist z.B. auf dem folgenden Screenshot sichtbar:

![image](https://github.com/user-attachments/assets/9b13f22e-15c2-4b5e-9f41-b737f7d9e31b)   
*Abbildung 8-8: Identity Provider*

Management-Identity-Wallet

Die Management-Identity-Wallet Initialisierung sieht so aus, dass nach dem Start jedes EDC pro Participant ein Token Request an den Keycloak gesendet wird, um einen Authentifizierungstoken zu generieren. Mit diesem Token wird zum einen ein User für jeden Participant angelegt als auch ein Wallet im MIW. Dies kann man beispielsweise auf diesem Screenshot sehen:

![image](https://github.com/user-attachments/assets/89940f87-c20d-412c-9356-fc4f872d305b)   
*Abbildung 8-9: Anlegen User*

###### Eclipse Dataspace Connectors
Für die Eclipse-Dataspace-Connectoren und die dazu gehörigen Digital-Twin Registries, müssen die Anpassungen für die verschiedenen, im Use-Case definierten, Participants durchgeführt werden.

Der folgende Abschnitt muss für unseren Use-Case für folgende Participants wiederholt werden:

-   OEM
-   Tier One
-   Tier Two \#1
-   Tier Two \#2
-   Tier Two \#3

Für jeden der folgenden Service-Stacks für jeden oben genannten Participant müssen folgende Anpassungen an den EDCs durchgeführt werden. Die Details und unterschiedlichen Werte dieser Einstellungen pro Participant sind weiter unten beschrieben.

-   Anpassung der Service-URLs auf Kubernetes-Interne-Hostnamen. Am Beispiel vom OEM:
````
  backendUrl: http://{{ .Release.Name }}-oem-submodelserver:8080
  registryUrl: http://{{ .Release.Name }}-oem-dtr:8080/api/v3.0
  controlplanePublicUrl: http://{{ .Release.Name }}-oem-edc-controlplane:8084
  controlplaneManagementUrl: http://{{ .Release.Name }}-oem-edc-controlplane:8081
  dataplaneUrl: http://{{ .Release.Name }}-oem-edc-dataplane:8081
````

-   Setzen der BPN
-   Setzen des zur BPN passenden „edc-miw-keycloak-secret“
-   Setzen des „nameOverride“
-   Setzen des Management-API-Keys
-   Erstellung einer Digital-Twin-Registry Konfiguration, da nicht vorhanden
    -   Deaktivierung des Ingresses für den unten folgenden Patch
-   Anpassung der Hostnamen für:
    -   Control-Plane, Data-Plane, Digital-Twin-Registry
-   Anpassung der MIW-Einstellungen
-   Anpassung der Vault-Einstellungen
-   Konfiguration der Keycloak-Einstellungen
-   Konfiguration der PostgreSQL Authentifizierung

**DTR**

Neben den Konfigurationsaufgaben müssen teilweise noch größere Fixes für unseren Use-Case erfolgen. So ist die Ingress-Konfiguration der Digital-Twin-Registry nicht für unseren Use-Case nutzbar und ein Patch-Ingress muss erstellt werden.

Die Konfiguration von diesem findet in der values.yaml statt:
````
dtr:
  ingress:
    enabled: true
    urlPrefix: /semantics/registry
  service:
    port: 8080
  hosts:
    - host: oem-dtr.tractus-x-06.arena2036.de
      serviceName: umbrella-oem-dtr
    - host: tierone-dtr.tractus-x-06.arena2036.de
      serviceName: umbrella-tierone-dtr
    - host: tiertwo-1-dtr.tractus-x-06.arena2036.de
      serviceName: umbrella-tiertwo-1-dtr
    - host: tiertwo-2-dtr.tractus-x-06.arena2036.de
      serviceName: umbrella-tiertwo-2-dtr
    - host: tiertwo-3-dtr.tractus-x-06.arena2036.de
      serviceName: umbrella-tiertwo-3-dtr
  annotations:
    cert-manager.io/cluster-issuer: "my-ca-issuer"
    nginx.ingress.kubernetes.io/rewrite-target: "/$1"
    nginx.ingress.kubernetes.io/use-regex: "true"
    nginx.ingress.kubernetes.io/enable-cors: "true"
    nginx.ingress.kubernetes.io/cors-allow-credentials: "true"
    nginx.ingress.kubernetes.io/cors-allow-origin: "*"
    nginx.ingress.kubernetes.io/cors-allow-methods: "*"
````

Das dazu passende Helm-Template sieht folgendermaßen aus:
````
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: umbrella-dtr-patch
  annotations:
    {{- with .Values.dtr.annotations }}
    annotations:
      {{- toYaml . | nindent 4 }}
    {{- end }}
spec:
  rules:
    {{- range .Values.dtr.hosts}}
    - host: {{ .host }}
      http:
        paths:
          - path: /semantics/registry
            pathType: Prefix
            backend:
              service:
                name: {{ .serviceName }}
                port:
                  number: {{ $.Values.dtr.service.port }}
    {{- end}}

````
**Service-Stack: OEM**

-   **Kubernetes-Kürzel**: oem
-   **EDC-nameOverride**: oem-edc
-   **BPN**: BPNL00000003AYRE
-   **clientId**: satest02
-   **secretAlias**: edc-miw-keycloak-secret
-   **Data-Plane**: oem-dataplane.\*
-   **Control-Plane**: oem-controlplane.\*
-   **Digital-Twin-Registry**: oem-dtr.\*
-   **Vault**: edc-oem-vault

**Service-Stack: Tier One**

-   **Kubernetes-Kürzel**: tierone
-   **EDC-nameOverride**: tierone-edc
-   **BPN**: BPNL00000003B0Q0
-   **clientId**: satest05
-   **secretAlias**: edc-miw-keycloak-secret
-   **Data-Plane**: tierone-dataplane.\*
-   **Control-Plane**: tierone-controlplane.\*
-   **Digital-Twin-Registry**: tierone-dtr.\*
-   **Vault**: edc-tierone-vault

**Service-Stack: Tier Two \#1**

-   **Kubernetes-Kürzel**: tiertwonoone
-   **EDC-nameOverride**: tiertwo-1-edc
-   **BPN**: BPNL00000003B2OM
-   **clientId**: satest11
-   **secretAlias**: edc-miw-keycloak-secret
-   **Data-Plane**: tiertwo-1-dataplane.\*
-   **Control-Plane**: tiertwo-1-controlplane.\*
-   **Digital-Twin-Registry**: tiertwo-1-dtr.\*
-   **Vault**: edc-tiertwo-1-vault

**Service-Stack: Tier Two \#2**

-   **Kubernetes-Kürzel**: tiertwonotwo
-   **EDC-nameOverride**: tiertwo-2-edc
-   **BPN**: BPNL00000003CSGV
-   **clientId**: satest12
-   **secretAlias**: edc-miw-keycloak-secret
-   **Data-Plane**: tiertwo-2-dataplane.\*
-   **Control-Plane**: tiertwo-2-controlplane.\*
-   **Digital-Twin-Registry**: tiertwo-2-dtr.\*
-   **Vault**: edc-tiertwo-2-vault

**Service-Stack: Tier Two \#3**

-   **Kubernetes-Kürzel**: tiertwonothree
-   **EDC-nameOverride**: tiertwo-3-edc
-   **BPN**: BPNL00000003B5MJ
-   **clientId**: satest13
-   **secretAlias**: edc-miw-keycloak-secret
-   **Data-Plane**: tiertwo-3-dataplane.\*
-   **Control-Plane**: tiertwo-3-controlplane.\*
-   **Digital-Twin-Registry**: tiertwonothree-dtr.\*
-   **Vault**: edc-tiertwonothree-vault

###### Semantic-Hub
-   Aktivierung des Semantic-Hubs
-   Anpassung des Hostnamens für den Semantic-Hubs
-   Ingress Konfiguration erstellen, da nicht vorhanden
    -   Ingress-Regeln definieren
-   Erstellung Keycloak-Konfiguration

###### Post-Install MIW Setup
Die Post-Install MIW-Setup Template-Datei wurde ergänzt um eine Ausgabe der Keycloak Authentifizierung, um ein debuggen zu erleichtern. Die Datei ist charts/umbrella-arena2036/templates/post-install-miw-setup.yaml:

TOKEN=\`cat token \| grep -o '"access_token": \*"[\^"]\*"' \| sed 's\#"access_token":"\\(.\*\\)"\#\\1\#'\` && export TOKEN

echo "wget {{\$keycloakPath}} --header 'Content-Type: application/x-www-form-urlencoded' --post-data 'grant_type=client_credentials&client_id={{ \$miwUser }}&client_secret={{ \$miwSecret }}'"

##### Deployment
Für das Deployment der für den Use-Case konfigurierten Komponenten werden folgende Schritte durchgeführt:

-   Zunächst muss sichergestellt werden, dass die Schritte aus dem **Abschnitt „1.3.4.5. Installation Server“** durchgeführt wurden, da sie für die folgenden Schritte die Voraussetzung sind
-   Das Minikube Cluster kann mit folgendem Befehl initialisiert werden:

    minikube start --cpus=4 --memory 6gb --driver=hyperv

-   Folgende Addons müssen aktiviert werden:

    minikube addons enable ingress

    minikube addons enable ingress-dns

-   Die Hosts- und Zertifikats-Einstellungen sollten in dem oben genannten Kapitel bereits durchgeführt worden sein
-   Für die Installation muss das Helm-Chart-Repository von Tractus-X hinzugefügt und geupdated werden:

    helm repo add tractusx-dev <https://eclipse-tractusx.github.io/charts/dev>

    helm repo update

-   Um, die Helm-Charts zu nutzen muss man zu unseren Umbrella-Charts navigieren und die Dependencies bauen

    cd charts/umbrella-arena2036

    helm dependency build

-   Zuletzt können die Helm-Charts über folgenden Befehl in das Cluster installiert werden

    helm install -f values.yaml umbrella . --namespace umbrella --create-namespace

-   Bei Bedarf kann der Helm-Release aktualisiert,:

    helm upgrade umbrella . -n umbrella --create-namespace

-   Oder deinstalliert werden:

    helm uninstall umbrella -n umbrella

###### Service- & API-Auflistung
Im Folgenden eine Auflistung der deployten Services und APIs:

-   Central-IDP
    -   Admin Console: [https://centralidp.tractus-x-06.arena2036.de/auth/admin/master/console/\#](https://centralidp.tractus-x-06.arena2036.de/auth/admin/master/console/)
-   Shared-IDP
    -   Admin Console: [https://sharedidp.tractus-x-06.arena2036.de/auth/admin/master/console/\#](https://sharedidp.tractus-x-06.arena2036.de/auth/admin/master/console/)
-   BPN-Discovery
    -   API: <https://bpndiscovery.tractus-x-06.arena2036.de/bpndiscovery/swagger-ui/index.html>
-   Discoveryfinder
    -   API: <https://discoveryfinder.tractus-x-06.arena2036.de/discoveryfinder/swagger-ui/index.html>
-   Managed Identity Wallet
    -   API: <https://managed-identity-wallets.tractus-x-06.arena2036.de/ui/swagger-ui/index.html>
-   Self-Description
    -   API: <https://sdfactory.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   Portal
    -   Web: <https://portal.tractus-x-06.arena2036.de>
-   Portal-Backend
    -   Administration & Discovery:
        -   API: <https://portal-backend.tractus-x-06.arena2036.de/api/administration/swagger/index.html>
    -   Notifications:
        -   API: <https://portal-backend.tractus-x-06.arena2036.de/api/notification/swagger/index.html>
    -   Services:
        -   API: <https://portal-backend.tractus-x-06.arena2036.de/api/services/swagger/index.html>
    -   Apps:
        -   API: <https://portal-backend.tractus-x-06.arena2036.de/api/apps/swagger/index.html>
    -   Registration:
        -   API: <https://portal-backend.tractus-x-06.arena2036.de/api/registration/swagger/index.html>
-   PG-Admin
    -   Admin Console: <https://pgadmin4.tractus-x-06.arena2036.de/>
-   **OEM** Service-Stack
    -   OEM EDC-Dataplane
        -   API: <https://oem-dataplane.tractus-x-06.arena2036.de/api>
        -   Public API: <https://oem-dataplane.tractus-x-06.arena2036.de/api/public>
    -   OEM EDC-Controlplane
        -   API: <https://oem-controlplane.tractus-x-06.arena2036.de/api>
        -   Management API: <https://oem-controlplane.tractus-x-06.arena2036.de/management>
        -   Dataspace Protocol: <https://oem-controlplane.tractus-x-06.arena2036.de/api/v1/dsp>
    -   OEM DTR
        -   API: <https://oem-dtr.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   **Tier 1** Service-Stack
    -   Tier 1 EDC-Dataplane
        -   API: [https://tierone-dataplane.tractus-x-06.arena2036.de/api](https://tiertwo-1-dataplane.tractus-x-06.arena2036.de/api)
        -   Public API: <https://tierone-dataplane.tractus-x-06.arena2036.de/api/public>
    -   Tier 1 EDC-Controlplane
        -   API: <https://tierone-controlplane.tractus-x-06.arena2036.de/api>
        -   Management API: <https://tierone-controlplane.tractus-x-06.arena2036.de/management>
        -   Dataspace Protocol: <https://tierone-controlplane.tractus-x-06.arena2036.de/api/v1/dsp>
    -   Tier 1 DTR
        -   API: <https://tierone-dtr.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   **Tier 2 \#1** (Kostal) Service-Stack
    -   Tier 2 \#1 EDC-Dataplane
        -   API: <https://tiertwo-1-dataplane.tractus-x-06.arena2036.de/api>
        -   Public API: <https://tiertwo-1-dataplane.tractus-x-06.arena2036.de/api/public>
    -   Tier 2 \#1 EDC-Controlplane
        -   API: <https://tiertwo-1-controlplane.tractus-x-06.arena2036.de/api>
        -   Management API: <https://tiertwo-1-controlplane.tractus-x-06.arena2036.de/management>
        -   Dataspace Protocol: <https://tiertwo-1-controlplane.tractus-x-06.arena2036.de/api/v1/dsp>
    -   Tier 2 \#1 DTR
        -   API: <https://tiertwo-1-dtr.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   **Tier 2 \#2** (Coroplast) Service-Stack
    -   Tier 2 \#2 EDC-Dataplane
        -   API: <https://tiertwo-2-dataplane.tractus-x-06.arena2036.de/api>
        -   Public API: <https://tiertwo-2-dataplane.tractus-x-06.arena2036.de/api/public>
    -   Tier 2 \#2 EDC-Controlplane
        -   API: <https://tiertwo-2-controlplane.tractus-x-06.arena2036.de/api>
        -   Management API: <https://tiertwo-2-controlplane.tractus-x-06.arena2036.de/management>
        -   Dataspace Protocol: <https://tiertwo-2-controlplane.tractus-x-06.arena2036.de/api/v1/dsp>
    -   Tier 2 \#2 DTR
        -   API: <https://tiertwo-2-dtr.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   **Tier 2 \#3** (Arena2036) Service-Stack
    -   Tier 2 \#3 EDC-Dataplane
        -   API: <https://tiertwo-3-dataplane.tractus-x-06.arena2036.de/api>
        -   Public API: [https://tiertwo-3-dataplane.tractus-x-06.arena2036.de/api/public](https://tiertwo-1-dataplane.tractus-x-06.arena2036.de/api/public)
    -   Tier 2 \#3 EDC-Controlplane
        -   API: <https://tiertwo-3-controlplane.tractus-x-06.arena2036.de/api>
        -   Management API: <https://tiertwo-3-controlplane.tractus-x-06.arena2036.de/management>
        -   Dataspace Protocol: <https://tiertwo-3-controlplane.tractus-x-06.arena2036.de/api/v1/dsp>
    -   Tier 2 \#3 DTR
        -   API: <https://tiertwo-3-dtr.tractus-x-06.arena2036.de/swagger-ui/index.html>

##### Live-Anpassungen und Authentifizierung

###### Keycloak
Da die Seeding-Daten teilweise hardcodiert sind, müssen nach dem Deployment einzelne Anpassungen durchgeführt werden.
Zunächst muss der Sub-Identity-Provider für Central-IDP angepasst werden. Dies kann in der Admin-Console durchgeführt werden:

[https://centralidp.tractus-x-06.arena2036.de/auth/admin/master/console/\#](https://centralidp.tractus-x-06.arena2036.de/auth/admin/master/console/)

![image](https://github.com/user-attachments/assets/515f9bfb-9855-4024-b08e-2ed49409c62f)   
*Abbildung 8-10: Anpassung Sub-Identity-Provider*

Zusätzlich müssen die Redirect-URLs des Portal-Users angepasst werden:

![image](https://github.com/user-attachments/assets/7f6ee3c0-4dfc-4192-bc2a-2af03caa246b)   
*Abbildung 8-11: Anpassung Redirect-URLs des Portal-Users*

Durch einen Fehler in den Seeding-Daten (ein Prozess, bei dem eine Datenbank mit einem anfänglichen Datensatz gefüllt werden), müssen außerdem mehrere Rollen für den Client sa-cl2-reg-2 hinzugefügt werden:

![image](https://github.com/user-attachments/assets/0b303039-d2c7-444b-ac49-229478cca204)   
*Abbildung 8-12: Hinzufügen Rollen*

###### Wallet
-   API: <https://managed-identity-wallets.tractus-x-06.arena2036.de/api>
````
    wget http://centralidp.tractus-x-06.arena2036.de/auth/realms/CX-Central/protocol/openid-connect/token --header 'Content-Type: application/x-www-form-urlencoded' --post-data 'grant_type=client_credentials&client_id=sa-cl5-custodian-2&client_secret=UIqawwoohsvZ6AZOd1llLhnsUTKMWe4D'
````
###### BPN-Discovery
-   API: <https://bpndiscovery.tractus-x-06.arena2036.de/bpndiscovery>
````
wget -q -S -O - http://centralidp.tractus-x-06.arena2036.de/auth/realms/CX-Central/protocol/openid-connect/token --header 'Content-Type: application/x-www-form-urlencoded' --post-data 'grant_type=client_credentials&client_id=sa-cl22-01&client_secret=1yDWW7BNwouRGxYRkDmzkpzqz5FG748f'
````
###### Discoveryfinder
-   API: <https://discoveryfinder.tractus-x-06.arena2036.de/discoveryfinder>

    wget -q -S -O - http://centralidp.tractus-x-06.arena2036.de/auth/realms/CX-Central/protocol/openid-connect/token --header 'Content-Type: application/x-www-form-urlencoded' --post-data 'grant_type=client_credentials&client_id=sa-cl21-01&client_secret=oFbXttMA7vI5MysN7AiEpobX5o3Jfbhp'

###### Portal API CentralIdp User
-   API: <https://portal-backend.tractus-x-06.arena2036.de/api/administration>
````
wget -q -S -O - http://centralidp.tractus-x-06.arena2036.de/auth/realms/CX-Central/protocol/openid-connect/token --header 'Content-Type: application/x-www-form-urlencoded' --post-data 'grant_type=client_credentials&client_id=sa-cl1-reg-2&client_secret=aEoUADDw2aNPa0WAaKGAyKfC80n8sKxJ'
````
###### Portal API SharedIdp User
-   API: <https://portal-backend.tractus-x-06.arena2036.de/api/administration>
````
wget -q -S -O - http://sharedidp.tractus-x-06.arena2036.de/auth/realms/master/protocol/openid-connect/token --header 'Content-Type: application/x-www-form-urlencoded' --post-data 'grant_type=client_credentials&client_id=sa-cl1-reg-1&client_secret=YPA1t6BMQtPtaG3fpH8Sa8Ac6KYbPUM7'
````
Unter Windows kann alternativ zu wget, curl benutzt werden.Ein Request kann bspw. so aussehen:
````
curl `
     -S -o - `
     -X POST `
     -H 'Content-Type: application/x-www-form-urlencoded' `
     --url 'http://centralidp.tractus-x-06.arena2036.de/auth/realms/CX-Central/protocol/openid-connect/token' `
     --data-urlencode 'grant_type=client_credentials' `
     --data-urlencode 'client_id=sa-cl22-01' `
     --data-urlencode 'client_secret=1yDWW7BNwouRGxYRkDmzkpzqz5FG748f'
````

#### Aufsetzen der BaSyx-Komponenten
Als Basis für das BaSyx Deployment wird das Repository [eclipse-basyx/basyx-java-server-sdk (github.com)](https://github.com/eclipse-basyx/basyx-java-server-sdk) genommen. Dieses beinhaltet unter dem Pfad examples/BaSyxMinimal eine einfache Konfiguration, die für unseren Use-Case genutzt werden kann.

Die Minimal Konfiguration besteht aus den folgenden Komponenten:

-   Eine **MongoDB** Datenbank für die Speicherung der Submodelle, Shells und weitere Komponenten
-   Ein **MQTT**-Message-Queue Service, der für die Kommunikation zwischen Services genutzt wird
-   Ein **Asset-Administration-Shell-Environment** Service, welcher die folgenden APIs enthält:
    -   Registry and Discovery Interface
    -   Submodel Repository API
    -   Asset Administration Shell API
    -   Asset Administration Shell Repository API
    -   Concept Description Repository API
    -   Environment API
    -   Serialization API
-   Ein **Asset-Administration-Shell-Registry** Service, welcher die folgende APIs enthält:
    -   Registry and Discovery Interface
-   Ein **Asset-Administration-Shell-Discovery** Service, welcher die folgenden APIs enthält:
    -   Registry and Discovery Interface
    -   Asset Administration Shell Basic Discovery API
-   Ein **Submodel-Registry** Service, welcher die folgenden APIs enthält:
    -   Submodel Registry API
-   Eine **AAS-GUI**, welche ein Web-Interface bereitstellt
-   Für eine detaillierte Auflistung siehe das Kapitel „1.3.4.8 BaSyx-Integration in Use-Case und Infrastruktur“.
-   Zusätzlich sind folgende Konfigurationen vorhanden, die angepasst werden müssen:
-   Eine 'mosquitto.conf' für MQTT
-   Eine 'aas-env.properties' Datei für die AAS-Environment
-   Eine 'aas-discovery.properties' Datei für die AAS-Discovery
-   Eine 'aas-registry.yaml' Datei für die AAS-Registry
-   Eine 'sm-registry.yaml' Datei für die Submodel-Registry

Damit eine reibungslose Kommunikation mit der bestehenden Infrastruktur stattfinden kann benötigt man entsprechende Helm-Charts, die allerdings nicht für die BaSyx-Komponenten vorhanden sind und daher erst erstellt werden müssen.

Als Referenz wird die vorhandene Docker-Compose Konfiguration als Grundlage genommen. Daraus werden entsprechende Helm-Komponenten abgeleitet. Dies wird in den folgenden Kapiteln beschrieben.

##### Konfiguration

Zunächst werden die Konfigurationen in den Ordner charts/umbrella-arena2036/resources kopiert, damit sie für die Helm-Charts verfügbar sind.

In dem vorher definierten Charts-Releases umbrella-arena2036,wird im Ordner charts/umbrella-2036/templates ein neues Template namens basyx.yaml erstellt.

**Für jeden der oben genannten Services** müssen zunächst folgende Kubernetes-Komponenten (**am Beispiel von AAS-Environment**) definiert werden:

-   Ein „Kubernetes-Service“
````
apiVersion: v1
kind: Service
metadata:
  name: {{ $fullName }}-aas-env
spec:
  ports:
    - port: {{ .Values.aasEnv.port }}
      targetPort: {{ .Values.aasEnv.port }}
  selector:
    app: {{ $fullName }}-aas-env
````

-   Ein „Kubernetes-Deployment“
````
apiVersion: apps/v1
kind: Deployment
metadata:
  name: {{ $fullName }}-aas-env
spec:
  selector:
    matchLabels:
      app: {{ $fullName }}-aas-env
  template:
    metadata:
      labels:
        app: {{ $fullName }}-aas-env
    spec:
      containers:
        - name: aas-env
          image: {{ .Values.aasEnv.image }}
          ports:
            - containerPort: {{ .Values.aasEnv.port }}
          volumeMounts:
            - mountPath: /application/application.properties
              subPath: application.properties
              name: aas-env-properties
            - mountPath: /application/aas
              subPath: aas
              name: aas-data
      volumes:
        - name: aas-env-properties
          configMap:
            name: aas-env-config
        - name: aas-data
          persistentVolumeClaim:
            claimName: aas-data-pvc
````
-   Eine „Kubernetes-ConfigMap“
````
apiVersion: v1
kind: ConfigMap
metadata:
  name: aas-env-config
data:
  application.properties: |
    {{ .Files.Get "resources/aas-env.properties" | nindent 4 }}
````
Zusätzlich müssen bei allen BaSyx-Komponenten außer MQTT und MongoDB noch folgende Kubernetes-Komponenten definiert werden:

-   Ein „Kubernetes-PersistentVolumeClaim“
````
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: aas-data-pvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 1Gi
````
-   Ein „Kubernetes-Ingress“
````
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: {{ $fullName }}-aas-env
  annotations:
    {{- with .Values.aasEnv.ingress.annotations }}
    annotations:
      {{- toYaml . | nindent 4 }}
    {{- end }}
spec:
  rules:
    - host: {{ .Values.aasEnv.ingress.hostname }}
      http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service:
                name: {{ $fullName }}-aas-env
                port:
                  number: {{ .Values.aasEnv.port }}
````

Diese Kubernetes-Komponenten müssen außerdem mit den entsprechenden Werten in der values.yaml beschrieben werden. Dazu gehören z.B. Variablen für:

-   Image-Pfad
-   Ports
-   Hostname
-   Ingress Regeln

Das Beispiel anhand des AAS-Environments ist:
````
aasEnv:
  image: eclipsebasyx/aas-environment:2.0.0-SNAPSHOT
  port: 8081
  ingress:
    enabled: true
    annotations:
      cert-manager.io/cluster-issuer: "my-ca-issuer"
      nginx.ingress.kubernetes.io/rewrite-target: "/$1"
      nginx.ingress.kubernetes.io/use-regex: "true"
      nginx.ingress.kubernetes.io/enable-cors: "true"
      nginx.ingress.kubernetes.io/cors-allow-origin: "https://*.tractus-x-06.arena2036.de/*, https://aas-webui.tractus-x-06.arena2036.de"
      nginx.ingress.kubernetes.io/cors-allow-credentials: "true"
    hostname: aas-env.tractus-x-06.arena2036.de

````
##### Deployment

Unter der Annahme, dass ein Deployment schon vorhanden ist und nur erweitert wird, muss lediglich das Helm-Deployment auf dem Kubernetes Cluster aktualisiert werden. Dafür werden folgende Befehle im Repository ausgeführt:

````
cd charts/umbrella-arena2036
helm upgrade umbrella . -n umbrella --create-namespace
````

Die fertig deployten Komponenten sind dann unter den folgenden URLs erreichbar:

-   **OEM** Service-Stack
    -   OEM AAS-Environment
        -   <https://oem-aas-env.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   **Tier 1** Service-Stack
    -   Tier 1 AAS-Environment
        -   <https://tierone-aas-env.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   **Tier 2 \#1** (Kostal) Service-Stack
    -   Tier 2 \#1 AAS-Environment
        -   <https://tiertwo-1-aas-env.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   **Tier 2 \#2** (Coroplast) Service-Stack
    -   Tier 2 \#2 AAS-Environment
        -   <https://tiertwo-2-aas-env.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   **Tier 2 \#3** (Arena2036) Service-Stack
    -   Tier 2 \#3 AAS-Environment
        -   <https://tiertwo-3-aas-env.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   BaSyx-AAS-Discovery
    -   <https://aas-discovery.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   BaSyx-AAS-Registry
    -   <https://aas-registry.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   BaSyx-Submodel-Registry
    -   <https://sm-registry.tractus-x-06.arena2036.de/swagger-ui/index.html>
-   BaSyx-AAS-Web-UI
    -   <https://aas-webui.tractus-x-06.arena2036.de/>

#### BaSyx-Integration in Use-Case und Infrastruktur

Die Services, die in den Einzelnen BaSyx-Komponenten beinhalten, sind in der folgenden Grafik aufgezeichnet. Zusätzlich sind die äquivalenten Services und APIs des Catena-X Digital-Twin Stacks markiert.

Es gibt mehrere Überschneidungen an Digital-Twin-Services in Catena-X, sowie BaSyx bzw. dem IDTA-Standard. Wir haben daher für unseren Use-Case sowohl von Catena-X als auch BaSyx Software-Komponenten genutzt. Konkret nutzen wir von BaSyx primär die AAS-Environment, sowie das inkludierte Submodel-Repository, und von Catena-X die Digital Twin Registry, mit der AAS-Registry API, sowie die Integration mit dem EDC.

Die Überschneidungen an äquivalenten Services, kann man auf der folgenden Abbildung sehen:

![image](https://github.com/user-attachments/assets/e0c7463c-9de0-4b2e-8fb3-7f442c439665)   
*Abbildung 8-13: BaSyx-Integration in Use Case*

### <a name="8.3.5"></a>8.3.5 Umsetzung des Use Cases

#### Catena-X Anforderungen an die VWS des Leitungssatzes

Für die Modellierung der Digitalen Zwillinge wurden im Projekt VWS4LS spezifierte Submodelltemplates der IDTA verwendet.

Catena-X ist hauptsächlich Use-Case getrieben. Die Use Cases beschreiben ihre Anforderungen an Submodels in sog. "Aspektmodellen". Möchte man an einem Use Case von Catena-X teilnehmen, müssen die jeweiligen [Catena-X-Standards](https://catena-x.net/de/angebote-standards/catena-x-standards) eingehalten werden. Der Standardisierungsprozess wird vom Catena-X Verein vorgenommen.

Beide Modellierungskonzepte zielen darauf ab, Daten und Prozesse innerhalb eines Ökosystems zu standardisieren und damit die Interoperabilität und den Datenaustausch zwischen verschiedenen Akteuren und Systemen zu gewährleisten.

Im Folgenden gilt es daher zu klären, welche Unterschiede sich zwischen den IDTA-Submodellen und den Catena-X-Aspektmodellen ergeben und wie diese für eine Anwendung in Catena-X angepasst werden müssen.

##### Catena-X Aspektmodelle

Catena-X beschreibt das Konzept der "[Aspektmodelle](https://catena-x.net/fileadmin/user_upload/Standard-Bibliothek/Archiv/8_PC_Semantics_v2.1/SEM-002_BAMM_PlatformCapabilitySemantics_v2.1.pdf)", um domänenspezifische Sichten oder Aspekte eines digitalen Zwillings zu definieren, die für verschiedene Anwendungsfälle innerhalb des Catena-X-Ökosystems wesentlich sind. Aspektmodelle bieten eine strukturierte Möglichkeit zur Erfassung spezifischer Geschäftsprozesse und Datenanforderungen.
Um ein Datenmodell zu spezifizieren, wird das [Semantic Aspect Meta Model](https://eclipse-esmf.github.io/samm-specification/2.1.0/index.html) (SAMM) verwendet, welches unter Verwendung des [Resource Description Format](https://www.w3.org/RDF/) (RDF) und der [Terse RDF Triple Language Syntax](https://de.wikipedia.org/wiki/Turtle_(Syntax)) (Turtle) spezifiziert, zusammen mit Validierungsregeln in der [Shapes Constraint Language](https://www.w3.org/TR/shacl/) (SHACL). Aspektmodelle werden ebenfalls in RDF/Turtle spezifiziert, wobei die SAMM-Semantik befolgt wird.

*Abbildung 8-14* zeigt beispielhaft die grafische Darstellung des Aspektmodells „PartTypeInformation“. Dafür kann der [Aspect Model Editor](https://eclipse-esmf.github.io/ame-guide/introduction.html) verwendet werden[^12] oder die html-Datei des semantischen Modells aus dem GitHub Repository [eclipse-tractusx](https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main)[^13] geöffnet werden. *In Abbildung 8-15* sieht man das entsprechende JSON dazu.

[^12]: https://eclipse-esmf.github.io/ame-guide/introduction.html

[^13]: https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main

![image](https://github.com/user-attachments/assets/3811cffa-c61a-4735-99ab-b6084d1fbaf5)   
*Abbildung 8-14: Grafische Darstellung des Aspektmodells PartTypeInformation.ttl*

![image](https://github.com/user-attachments/assets/5e2fb4ee-cfa0-49ae-b3bd-5404631563de)   
*Abbildung 8-15: Eigenschaften eines Submodells als JSON*

##### IDTA-Submodelle

Die IDTA verwendet "**Submodel Templates**", um die Darstellung von Informationen innerhalb einer Asset Administration Shell (AAS), einer digitalen Darstellung von Assets, zu standardisieren. Das Submodel-Konzept der IDTA ist breiter angelegt, um verschiedene Industriebereiche abzudecken. Die Templates definieren spezifische Datenstrukturen und Semantiken für verschiedene Arten von Informationen (z. B. technische Daten, Wartungspläne), wodurch der Austausch und die Interpretation von Daten über verschiedene Plattformen und Branchen hinweg erleichtert wird. Die Schablonen sollen die Interoperabilität erleichtern, indem sie einen gemeinsamen Rahmen bieten, der an die verschiedenen industriellen Bedürfnisse angepasst werden kann. Alle registrierten AAS Submodel Templates werden auf der [IDTA-Website](https://industrialdigitaltwin.org/en/content-hub/submodels) gelistet und im [IDTA-Github](https://github.com/admin-shell-io/submodel-templates/tree/main/published) bereitgestellt[^14].

[^14]: <https://industrialdigitaltwin.org/en/content-hub/submodels>

##### Verwendung von Submodel Templates der IDTA in Catena-X

Catena-X schreibt dazu:

-   *“In Catena-X the semantics of a Submodel is described via an Aspect Model conformant to standard CX-0003, preferrable by using standardized properties conformant to standard CX-0044.”*

Der Catena-X-Standard [CX-0003](https://catenax-ev.github.io/docs/next/standards/CX-0003-SAMMSemanticAspectMetaModel) „SAMM Aspect Meta Model v1.1.0“[^15] definiert:

[^15]: <https://catenax-ev.github.io/docs/next/standards/CX-0003-SAMMSemanticAspectMetaModel>

-   *“Every aspect model released or standardized in Catena-X MUST be maintained in Tractus-X - SLDT Semantic Models.”*[^16].
-   *“Every aspect model in Tractus-X - SLDT Semantic Models that has the status "released" or "standardized" MUST be validated without errors against the Semantic Aspect Meta Model […].”*
-   *“Every aspect of a digital twin registered in a digital twin registry (see standard CX-0002) accessible in the Catena-X data space MUST have a semantic description (semantic ID) that is conformant to the unique identifier of the SAMM aspect model associated to it.”*

[^16]: <https://github.com/eclipse-tractusx/sldt-semantic-models>

| Wenn das Projekt VWS4LS einen eigenen Use Case für Catena-X definieren möchte, sollten die verwendeten Submodelle in Catena-X gemäß des Standardisierungsprozesses standardisiert werden. Dann müssen diese dem Standard CX-0003 folgen (s.o.).  Für den Demonstrationszweck können die VWS4LS Submodelle für diesen Use Case technisch übertragen werden, entsprechen aber (außer dem Submodel „Nameplate“) nicht den Catena-X-Spezifikationen und können so nicht von Catena-X Lösungen interpretiert werden. |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

##### Digitale Zwillinge und AAS in Catena-X

In Catena-X basieren die APIs auf den Spezifikationen der Asset Administration Shell (AAS) Spezifikationen der IDTA[^17]. Um Catena-X konform zu sein, werden in der Demonstrator-Umsetzung die einzelnen Submodelle in der DTR registriert. Diese Registrierung zählt im Kontext von Catena-X als „Erschaffung eines Digitalen Zwillings“. Grundsätzlich wird zum aktuellen Entwicklungsstand nicht auf Asset-Ebene zugegriffen, sondern auf die einzelnen Submodelle, die in der DTR zu einem Asset “gebündelt“ werden können. Das JSON-Beispiel im Digital Twin KIT verdeutlicht das[^18]. Die AAS an sich wird daher nicht angesprochen. In der DTR steht lediglich der AAS-Descriptor, der wiederum die verschiedenen Submodel-Descriptoren mit den entsprechenden Endpunkten enthält.

[^17]: <https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Operation%20View%20Digital%20Twin%20Kit>

[^18]: [https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-software-development-view\#registering-a-new-twin](https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-software-development-view#registering-a-new-twin)

![image](https://github.com/user-attachments/assets/9e75c8aa-6fa1-445b-986f-abbe165e1ee6)

*Abbildung 8-16: [Tractus-X Digital Twin Registry - Asset Administration Shell Domain Model](https://github.com/eclipse-tractusx/sldt-digital-twin-registry/tree/main/docs#asset-administration-shell-domain-model) [^19]*

[^19]: [https://github.com/eclipse-tractusx/sldt-digital-twin-registry/tree/main/docs\#asset-administration-shell-domain-model](https://github.com/eclipse-tractusx/sldt-digital-twin-registry/tree/main/docs#asset-administration-shell-domain-model)

Im [Digital Twin KIT](https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-software-development-view#submodel-as-edc-data-asset) von Tractus-X steht zwar, dass ein Data Provider ein Daten Asset per Submodel oder Bundle erstellen kann, gleichzeitig wird aber ausgesagt:

-   *“There is no normative guidance on how to register multiple Submodels bundled together yet. These bundles may include all the Submodels of a specific semanticId, all Submodels of an asset or any other arbitrary quality. This may be added to* [*CX-0002*](https://catenax-ev.github.io/docs/standards/CX-0002-DigitalTwinsInCatenaX) *in future iterations.“* [^20]

[^20]: [https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-software-development-view\#submodel-as-edc-data-asset](https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-software-development-view#submodel-as-edc-data-asset)

| Als Konsequenz werden auch für den Demonstrator die Submodels als einzelne Assets angelegt. |
|---------------------------------------------------------------------------------------------|

##### Der Industry Core von Catena-X

Um zu verhindern, dass jeder Use-Case in Catena-X seine Digitalen Zwillinge unterschiedlich beschreibt, wurde der Industry Core ins Leben gerufen. „Core“ deshalb, weil er den Kern der Industrie, nämlich die Teile/Komponenten betrifft.

Catena-X beschreibt dazu:

-   Der Industry Core ist eine gemeinsame [semantische] Basis für Use Cases, die digitale Zwillinge und Aspektmodelle in Catena-X nutzen[^21].
-   Der Industry Core beschreibt ein physisches Teil, eine Komponente oder ein Material auf Typ- und/oder Instanzebene, macht es im Netz identifizierbar und auffindbar und ermöglicht die Navigation über mehrere Ebenen hinweg[^22].

[^21]: <https://catenax-ev.github.io/docs/next/standards/CX-0126-IndustryCorePartType>

[^22]: <https://eclipse-tractusx.github.io/docs-kits/category/industry-core-kit>

Der Industry Core hat aktuell zwei Standards definiert. Darin wird einmal die Beschreibung eines Teils auf Typ-Ebene ([CX-0126](https://catenax-ev.github.io/docs/next/standards/CX-0126-IndustryCorePartType)) und einmal auf Instanz-Ebene ([CX-0127](https://catenax-ev.github.io/docs/next/standards/CX-0127-IndustryCorePartInstance)) festgelegt sowie jeweils die Verbindung zu „Kind-Teilen“, also Komponenten, die verbaut wurden.

Zusätzlich müssen folgende Punkte aus dem Standard CX-0126 beachtet werden:

-   “The asset's globalAssetId **MUST** be equal to the unique id used in Catena-X.”
-   “The following specific asset IDs[^23] not marked as optional MUST be available when registering a digital twin or when adding the above mentioned submodels to an existing twin for a part type in order to allow discovery.”

[^23]: [https://catenax-ev.github.io/docs/next/standards/CX-0126-IndustryCorePartType\#214-digital-twins-and-specific-asset-ids](https://catenax-ev.github.io/docs/next/standards/CX-0126-IndustryCorePartType#214-digital-twins-and-specific-asset-ids)

Da auch im Projekt VWS4LS physikalische Komponenten betrachtet werden (bspw. Leitungen und Stecker), ist es zu empfehlen, diese mittels der Industry Core Standards zu beschreiben, falls eine Teilnahme an Catena-X angestrebt wird.

| Für den Demonstrator werden daher alle Digitalen Zwillinge mit dem Submodel „PartTypeInformation“ und „SingleLevelBomAsPlanned“ ergänzt. |
|------------------------------------------------------------------------------------------------------------------------------------------|

#### OEM-Anforderungen als Submodel

Der OEM ist mit seinen Anforderungen der Trigger für einen Entwicklungsauftrag beim Tier 1. Für die vereinfachte Demonstration in diesem Projekt sind die Anforderungen eine Liste an autorisierten Entwicklern. Dafür wird hier eine Dummy-AAS „**OEM_SupplierRequirements**“ mit dem mit dem speziell dafür definierten Submodel „**AuthorizedSuppliers**“ erstellt. Hier sind die BPNLs der vom OEM autorisierten Business Partner hinterlegt (siehe folgende Abbildung).

![image](https://github.com/user-attachments/assets/ce09139d-ae60-4976-ae68-8facc5fd613d)

*Abbildung 8-17: Die Anforderungen des OEM als AAS mit Submodel*

#### Aggregation des Digitalen Zwillings

Nachdem der Tier 1 sowohl Zugriff auf die Anforderungen des OEMs als auch auf die bereitgestellten Angebote der Tier 2 hat, erstellt dieser nun einen aggregierten Digitalen Zwilling. Dieser basiert auf den Submodels des Industry Cores von Catena-X (Details siehe Abschnitt zum Industry Core):

-   [PartTypeInformation](https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main/io.catenax.part_type_information/1.0.0/gen)[^24]
-   [SingleLevelBomAsPlanned](https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main/io.catenax.single_level_bom_as_planned/3.0.0/gen)[^25]

[^24]: <https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main/io.catenax.part_type_information/1.0.0/gen>

[^25]: <https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main/io.catenax.single_level_bom_as_planned/3.0.0/gen>

Das Submodel „PartTypeInformation“ enthält die Catena-X ID (entspricht der Global Asset ID) des aggregierten Digitalen Zwillings sowie die Teilenummer und den Namen.

Die eigentliche Aggregation findet über das Submodel „SingleLevelBomAsPlanned“ statt. Dieses stellt die Stückliste (BoM) dar. Hier erfolgt der Link auf alle Komponenten (Catena-X ID´s der AASen), die im aggregierten Digitalen Zwilling verbaut werden können. Die folgende Abbildung zeigt dies beispielhaft (childItems):

![image](https://github.com/user-attachments/assets/0a59b3c0-6fa8-40c1-a52a-333b362d07d6)

*Abbildung 8-18: Zusammenbau Leitungssatz mit Stückliste*

##### <a name="8.3.5.4.1"></a>Zugriffskontrolle (Security)

Das Projekt VWS4LS hat die Anforderung, dass der Zugriff auf einzelne Submodels beschränkt werden kann. Ergänzend zu einer „Role-Based Access Control“ (RBAC) ist also auch eine Art „[Attribute-Based Access Control](https://doi.org/10.6028/NIST.SP.800-162)“ (ABAC) [2] auf Submodell-Ebene notwendig. Hierfür werden im Folgenden mögliche Konzepte vorgestellt. Es wird dabei von folgenden Annahmen ausgegangen:

-   Ein (externer) Benutzer möchte auf eine AAS zugreifen
-   Das Identitätsmanagement wird von einem Identitätsanbieter (IdP) durchgeführt
    -   Der IdP stellt ein Access Token zur Verfügung, das für den AAS-Server relevante Angaben enthält
    -   Das Token (JWT, JSON Web Token) wird vom IdP signiert
-   Der AAS-Server vertraut dem Identity Provider
-   Der Zugang zur AAS wird auf der Grundlage des Access Token und der Zugangsrichtlinien gewährt
-   Die Zugangsrichtlinien (Policies) werden vom AAS-Verantwortlichen eingerichtet

##### IDTA Security Spezifikation

Im Kern müssen zu dem Thema AAS-Security die folgenden Fragestellungen geklärt werden:

1.  Wo sollen die Zugangsrichtlinien (Policies) gespeichert werden?
    -   Innerhalb der AAS selbst?
    -   In einem separaten Policy-Repository?
2.  Wie können die Zugangsrichtlinien abgebildet werden?
    -   Mit AAS-Elementen?
    -   Mit bestehenden Sprachen wie [XACML](https://en.wikipedia.org/wiki/XACML)[^26] oder [ODRL](https://en.wikipedia.org/wiki/ODRL)[^27]?
3.  Wie wird die Zugangsrichtlinien-Entscheidung implementiert?
    -   Mit einem Interpreter, der zum Zeitpunkt der Zugrifffsentscheidung aufgerufen wird?
    -   Integriert in Such- und Abfragestrukturen?

[^26]: <https://en.wikipedia.org/wiki/XACML>

[^27]: <https://en.wikipedia.org/wiki/ODRL>

Folgende Dokumente adressieren bislang das Thema „Security für Verwaltungsschalen“:

-   [Security der Verwaltungsschale](https://www.plattform-i40.de/PI40/Redaktion/DE/Downloads/Publikation/security-der-verwaltungsschale.html) (02/2018)
-   [Zugriffssteuerung für Industrie 4.0-Komponenten zur Anwendung von Herstellern, Betreibern und Integratoren](https://www.plattform-i40.de/PI40/Redaktion/DE/Downloads/Publikation/zugriffssteuerung-industrie40-komponenten.html) (12/2018)
-   [Sicherer Downloadservice](https://www.plattform-i40.de/PI40/Redaktion/EN/Downloads/Publikation/secure_downloadservice.html) (12/2020)
-   [Details of the Asset Administration Shell Part 1, Chapter 6, ABAC & RBAC](https://www.plattform-i40.de/PI40/Redaktion/DE/Downloads/Publikation/Details_of_the_Asset_Administration_Shell_Part1_V3.html) (05/2022)

In „[Details of the Administration Shell](https://admin-shell-io.github.io/aas-specs-antora/IDTA-01003-a/v3.0/index.html)“ war bis V30RC02 ein Security-Konzept für sowohl RBAC als auch ABAC enthalten. Hierfür exisitert auch eine prototypische AAS-Server-Implementierung (<https://v3.admin-shell-io.com/>), siehe *Abbildung 8-19*, jedoch keine Benutzeroberfläche, um Zugriffsrichtlinien für AAS-Elemente zu konfigurieren.

![image](https://github.com/user-attachments/assets/c4c7b960-224f-46ab-8dd7-3cb5c5ae2dbd)   
*Abbildung 8-19: AAS-Security (Quelle: <https://v3.admin-shell-io.com/>)*

Derzeit wird das AAS-Security-Konzept in der IDTA komplett überarbeitet und soll durch eine neue Spezifikation „Security“ ersetzt werden. Hierfür werden in der IDTA-Arbeitsgruppe vier Varianten diskutiert:

1.  Security Meta Model
2.  Security Submodel
3.  External Model [XACL](https://en.wikipedia.org/wiki/XACML)
4.  External Model [ODRL](https://en.wikipedia.org/wiki/ODRL), basierend auf Mechanismen, die auch CATENA-X nutzt.

Eine erste Version der neuen Security-Spezifikation wird für Anfang 2025 erwartet.

Die generelle Zielsetzung der angestrebten Security-Spezifikation wird in der nachfolgenden *Abbildung 8-20* beschrieben:

Für die technische Umsetzung wird als wesentlicher Bestandteil ein “[OpenAuth2.0 Authorization Framework](https://auth0.com/docs/authenticate/protocols/oauth#:~:text=The%20OAuth%202.0%20authorization%20framework%20is%20a%20protocol,revealing%20their%20long-term%20credentials%20or%20even%20their%20identity.)” gesehen. Für das Identitätsmanagement wird [OpenID Connect](https://openid.net/developers/how-connect-works/) vorgeschlagen. Die Kommunikation basiert dabei auf JSON Web Tokens, die Claims entsprechend eines Datenraums enthalten. Diese Claims können dann in ABAC-Security-Regeln verwendet werden und somit den Zugriff regeln. Das soll für Repository und Registry gleichermaßen gelten. Access Rules sollen auch für Properties und nicht nur für ganze Submodelle möglich sein.

![image](https://github.com/user-attachments/assets/9423f866-b955-4f92-bd85-806cdf739781)   
*Abbildung 8-20: Grundsätzliche Interaktion zwischen Konnektoren und Verwaltungsschalen*

*(Quelle: A. Orzelski)*

##### Security in BaSyx

![image](https://github.com/user-attachments/assets/1e3d46f2-31e3-439d-9f81-50c4023f467f)   
*Abbildung 8-21: Dataflow RBAC in BaSyx*

Definitionen für eine Attribut basierende Zugriffskontrolle (Attribute Based Access Control = ABAC) sind von der IDTA derzeit noch nicht abgeschlossen. Das bedeutet, dass auf die Standardisierung von der IDTA gewartet wird, bevor eine Implementierung in BaSyx vorgenommen wird.

Derzeit ist in BaSyx eine einfache rollenbasierte Zugriffskontrolle (Role Based Access Control = RBAC) implementiert. Jeder Service (AAS Discovery, AAS-Environment, AAS Concept Description etc.) benötigt eine eigene Konfigurationsdatei, welche in JSON-Format die Rollen und Rechte spezifisch für bestimmte AAS mit IDs oder Wildcards beschreibt. Hierfür existiert ein dediziertes [Konfigurationsdateiformat](https://wiki.basyx.org/en/latest/content/user_documentation/basyx_components/v2/aas_discovery/features/authorization.html#rbac-rule-configuration) sowie ein SDK-Beispiel namens „[BaSyxSecured](https://github.com/eclipse-basyx/basyx-java-server-sdk/tree/main/examples/BaSyxSecured)“, welches den Authorisierungs-Server [Keycloak](https://www.keycloak.org/docs/latest/server_admin/index.html) verwendet.

In *Abbildung 8-22* wird gezeigt, wie die Authentifizierung in BaSyx konzipiert wurde. In dem Szenario sind Admins für jeden Server (AAS Registry, AAS Repository und SM Repository) vorhanden sowie die Nutzer für AAS Registry, AAS Repository und Submodel Repository. Alle Nutzer authentifizieren sich mittels eines AccessToken von einen Authorisierungs-Server (hier [Keycloak](https://www.keycloak.org/)).

![image](https://github.com/user-attachments/assets/65c24ec2-2bce-4f15-93ed-53f98307a466)   
*Abbildung 8-22: Zugriffskontrolle – Konzept für BaSyx*

##### Security in Catena-X

Datenlieferanten in Catena-X verwenden sog. „[Policies](https://eclipse-tractusx.github.io/docs-kits/kits/Connector%20Kit/Adoption%20View/connector_kit_adoption_view_policies)“, um den Zugang (Access-Policies) und die Nutzung (Usage-Policies) von Daten festzulegen.[^28] Die Policies folgen der ODRL[^29] (Open Digital Rights Language) und werden in JSON-LD beschrieben.

[^28]: <https://github.com/eclipse-tractusx/tractusx-edc/blob/main/docs/usage/management-api-walkthrough/02_policies.md>

[^29]: <https://w3c.github.io/poe/model/>

Weiter wird in [SC-002](https://catena-x.net/fileadmin/user_upload/Standard-Bibliothek/Archiv/3_PC_Sovereign_Data_Exchange_v2.1/SC-002_EDC_PC_Self-Sovereign_Data_Exchange_v2.1.pdf) ausgeführt:

*„A Contract Definition is the connection between a set of* [*Assets*](https://github.com/eclipse-tractusx/tractusx-edc/blob/main/docs/usage/management-api-walkthrough/01_assets.md) *with one Access Policy and one Contract Policy.“*

Die „*Contract Definition*“ ist dann die logische Verbindung zwischen Assets und Policy[^30].

[^30]: [https://github.com/eclipse-tractusx/tractusx-edc/blob/main/docs/usage/management-api-walkthrough/03_contractdefinitions.md\#creating-a-contract-definition](https://github.com/eclipse-tractusx/tractusx-edc/blob/main/docs/usage/management-api-walkthrough/03_contractdefinitions.md#creating-a-contract-definition)

Im EDC können sogenannte Data Assets bereitgestellt werden. Ein Asset ist dabei die grundlegende Darstellung einer beliebigen Backend-Schnittstelle im EDC[^31].

[^31]: <https://github.com/eclipse-tractusx/tractusx-edc/blob/main/docs/usage/management-api-walkthrough/01_assets.md>

Ein Datenanbieter kann ein Data Asset pro Submodel erstellen[^32]. Diesem Data Asset kann mittels einer Contract Definition eine Policy zugeordnet werden.

[^32]: [https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-software-development-view\#submodel-as-edc-data-asset](https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-software-development-view#submodel-as-edc-data-asset)

| Eine Zugriffsbeschränkung für einzelne Submodels im Projekt VWS4LS kann umgesetzt werden, indem den Assets (Submodels) entsprechende Access-Policies im EDC zugeordnet werden. |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

Ein Peer-to-Peer Datenaustausch in Catena-X erfolgt immer über Konnektoren, die das von der IDSA spezifizierte Dataspace Protocol (DSP) implementieren[^33]. Für dieses Projekt wird die Referenzimplementierung „[Tractus-X EDC](https://github.com/eclipse-tractusx/tractusx-edc)“ verwendet[^34].

[^33]: [https://github.com/eclipse-tractusx/tractusx-edc/tree/main/docs/usage/management-api-walkthrough\#introduction](https://github.com/eclipse-tractusx/tractusx-edc/tree/main/docs/usage/management-api-walkthrough#introduction)

[^34]: <https://github.com/eclipse-tractusx/tractusx-edc>

##### Security für dieses Projekt
Aufgrund der Datenarchitektur von Catena-X kann jedem Submodel eine individuelle Policy zugeordnet und somit der Zugriff auf Submodel-Ebene beschränkt werden, wie es auch der Anforderung an dieses Projekt entspricht (siehe Abschnitt [Zugriffskontrolle (Security)](#8.3.5.4.1)).

| Die Zugriffsbeschränkung für diesen demonstrativen Use Case wir mit dem Konzept der Policies nach Catena-X umgesetzt. Die anderen Konzepte (ABAC) finden sich noch in der Definition und können daher in diesem Projekt noch nicht umgesetzt werden. |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

#### Data Provisioning & Data Consumption
Der beschriebene Use Case besteht grundsätzlich aus den Szenarien „Data Provisioning“ und „Data Consumption“ (siehe Abschnitt 8.3.3).

##### Data Provisioning
Ein Data-Provisioning besteht aus mehreren aufeinander folgenden Schritten. Sie beinhalten z.B. das Bereitstellen des Submodells, Registrieren von Digitalen Zwillingen, sowie Erstellungen von EDC Contracts, sowie den dazugehörigen Assets und Policies. Im Folgenden werden die genauen Schritte, die durchzuführen sind, detailliert beschrieben.

Für den sequenziellen Ablauf im gesamten Use-Case siehe Kapitel "Sequenzieller Ablauf des Use Cases".

Man beachte, dass das Data-Provisioning dann für alle Participants, die Daten providen wollen, durchgeführt werden muss.

![image](https://github.com/user-attachments/assets/85490bee-fa73-40d4-86d4-d542f83969c7)

*Abbildung 8-23: Data Provisioning*

In den folgenden Schritten ist oft eine Authentifizierung mit dem Keycloak erforderlich. Für diese müssen in den entsprechenden API-Calls u.A. folgende Properties gesetzt werden, bspw. für den OEM:

-   **clientId**: satest02
-   **clientAlias**: EDC-MIW BPN_OEM_A
-   **clientSecret**: pyFUZP2L9UCSVJUScHcN3ZEgy2PgyEpg
-   **clientSecretAlias:** edc-miw-keycloak-secret
-   **tokenUrl**: <http://centralidp.tractus-x-06.arena2036.de/auth/realms/CX-Central/protocol/openid-connect/token>

###### Anlegen der Submodels
Zuerst müssen die entsprechenden Submodelle über die BaSyx Submodel Repository API hochgeladen werden. Dies muss für jedes Submodell in den oben aufgelisteten Test-Daten durchgeführt werden. Dafür erfolgt ein POST Request an die entsprechende URL. Der Request für den Uplaod kann bspw. folgendermaßen aussehen (der eigentliche Inhalt ist für die Lesbarkeit gekürzt):

-   **POST** <https://aas-env.tractus-x-06.arena2036.de/submodels>
```
{
  "idShort": "Nameplate",
  "id": "www.kostal.com/sm/1215_8002_2042_1144",
  "kind": "Instance",
  "semanticId": {
    "type": "ExternalReference",
    "keys": [
      {
        "type": "Submodel",
        "value": "https://admin-shell.io/zvei/nameplate/1/0/Nameplate"
      }
    ]
  },
  "submodelElements": [
    {
        <...>
        <...>
        <...>
    }
  ],
  "modelType": "Submodel"
}
```
Die Submodelle können mir folgendem Request überprüft werden:

**GET** <https://aas-env.tractus-x-06.arena2036.de/submodels>

Wenn man ein bestimmtes Submodell abfragen will, kann man die Submodell ID mit base64 encoden und das an die oben genannten Request-URL anhängen. Aus:

```www.kostal.com/sm/1215_8002_2042_1144```

wird mit base64-Encoding:

```d3d3Lmtvc3RhbC5jb20vc20vMTIxNV84MDAyXzIwNDJfMTE0NA==```

Der daraus entstehendse Request ist:

-   **GET** <https://aas-env.tractus-x-06.arena2036.de/submodels/d3d3Lmtvc3RhbC5jb20vc20vMTIxNV84MDAyXzIwNDJfMTE0NA==>```
    -   Das Ergebnis entspricht dem vorher hochgeladenen Submodel.

###### **Registrierung der AAS in DTR**
Für die Registrierung einer AAS in Catena-X bzw. der Digital Twin Registry wird das entsprechende Deployment einer DTR genutzt. Dafür wird konkret der Endpoint ```/shell-descriptor``` benutzt. Mit einem POST-Request an die entsprechende URL, wird ein AAS-Deskriptor definiert, der die oben angelegten Submodels referenziert.

-   **POST** <https://oem-dtr.tractus-x-06.arena2036.de:443/api/v3.0/shell-descriptors>
    -   Beispiel-Payload
```
{
  "id": "urn:uuid:e5c96ab5-896a-1234-8761-efd74777ca97",
  "idShort": "<AAS_ID>",
  "specificAssetIds": [
    {
      "name": "manufacturerPartId",
      "value": "123-345-567103",
      "externalSubjectId": {
        "type": "ExternalReference",
        "keys": [
          {
            "type": "GlobalReference",
            "value": "BPNL00000003AYRE"
          }
        ]
      }
    }
  ],
  "submodelDescriptors": [
    {
      "id": "e5c96ab5-896a-482c-8761-efd74777ca97",
      "semanticId": {
        "type": "ExternalReference",
        "keys": [
          {
            "type": "GlobalReference",
            "value": "urn:bamm:io.catenax.material_for_recycling:1.1.0#MaterialForRecycling"
          }
        ]
      },
      "endpoints": [
        {
          "interface": "SUBMODEL-3.0",
          "protocolInformation": {
            "href": "https://aas-env.tractus-x-06.arena2036.de/submodels/d3d3Lmtvc3RhbC5jb20vc20vMTIxNV84MDAyXzIwNDJfMTE0NA==",
            "endpointProtocol": "HTTP",
            "endpointProtocolVersion": [
              "1.1"
            ],
            "subprotocol": "DSP",
            "subprotocolBody": "id=123;dspEndpoint=http://edc.control.plane/api/v1/dsp",
            "subprotocolBodyEncoding": "plain",
            "securityAttributes": [
              {
                "type": "NONE",
                "key": "NONE",
                "value": "NONE"
              }
            ]
          }
        }
      ]
    },
  {
     ...
     Weitere Submodel Deskriptoren…
     ...
  }
  ]
}
```
Genau, wie bei der Submodel Repository API kann über die base64-endodete ID eine Shell-Description wieder angefragt werden:

-   **GET** <https://oem-dtr.tractus-x-06.arena2036.de:443/api/v3.0/shell-descriptors/api/v3.0/shell-descriptors/dXJuOnV1aWQ6YmIyMWI5ZDktZjRiMi00ZDA4LWFmY2UtMTE0N2Y4MTcwNWFl>
    -   Das Ergebnis entspricht dem vorher hochgeladenen Shell-Descriptor.

###### **Registrierung des DTRs im EDC als Asset**
Für die Interaktion zwischen der Digital-Twin-Registry und dem EDC, muss ersteres über die Management API als Asset registriert werden.

-   **POST** <https://oem-controlplane.tractus-x-06.arena2036.de/management/v3/data/assets>
    -   Beispiel-Payload
````
{
  "@context": {
    "edc": "https://w3id.org/edc/v0.0.1/ns/",
    "cx-common": "https://w3id.org/catenax/ontology/common#",
    "cx-taxo": "https://w3id.org/catenax/taxonomy#",
    "dct": "http://purl.org/dc/terms/"
  },
  "@id": "{{ _.edcAssetId }}",
  "properties": {
    "dct:type": {
      "@id": "cx-taxo:DigitalTwinRegistry"
    },
    "cx-common:version": "3.0"
  },
  "privateProperties": {
  },
  "dataAddress": {
    "@type": "DataAddress",
    "type": "HttpData",
    "baseUrl": "{{ _.url_backend }}",
    "proxyQueryParams": "true",
    "proxyPath": "true",
    "proxyMethod": "false",
    "oauth2:tokenUrl": "http://centralidp.tractus-x-06.arena2036.de/auth/realms/CX-Central/protocol/openid-connect/token",
    "oauth2:clientId": "satest02",
    "oauth2:clientSecretKey": "edc-miw-keycloak-secret"
  }
}
````

###### **Erstellung Contract Definition inkl. Asset & Policy im EDC**
Um eine AAS in Catena-X anzubieten, müssen nach dem Anlegen der Submodelle und der Registrierung der AAS, die Contract-Pipeline im jeweiligen EDC durchgeführt werden. Dafür wird die Management API mit ihren Entsprechenden Endpoints „/assets“, „/policydefinitions“ und „/contractdefinitions“ genutzt.

Zunächst wird ein Asset z.B. unter dem folgenden Endpoint erstellt:

**POST** <https://oem-controlplane.tractus-x-06.arena2036.de/management/v3/data/assets>

Eine Beispiel-Payload für eine Submodel-Definition als Asset ist im Folgenden dargestellt:
````
{
  "@context": {
    "edc": "https://w3id.org/edc/v0.0.1/ns/",
    "cx-common": "https://w3id.org/catenax/ontology/common#",
    "cx-taxo": "https://w3id.org/catenax/taxonomy#",
    "dct": "http://purl.org/dc/terms/"
  },
  "@id": "{{ _.assetId }}",
  "properties": {
    "dct:type": {
      "@id": "cx-taxo:SubmodelBundle"
    },
    "cx-common:version": "3.0"
  },
  "privateProperties": {
  },
  "dataAddress": {
    "@type": "DataAddress",
    "type": "HttpData",
    "baseUrl": "{{ _.url_backend }}",
    "oauth2:tokenUrl": "http://centralidp.tractus-x-06.arena2036.de/auth/realms/CX-Central/protocol/openid-connect/token",
    "oauth2:clientId": "satest02",
    "oauth2:clientSecretKey": "edc-miw-keycloak-secret",
    "proxyQueryParams": "false",
    "proxyPath": "true",
    "proxyMethod": "false"
  }
}
````
Daraufhin wird eine Policy erzeugt, z.B. unter dem folgenden Endpoint:

**POST** <https://oem-controlplane.tractus-x-06.arena2036.de/management/v2/data/policydefinitions>

Eine Beispiel-Payload für eine Policyl-Definition zu einem Asset ist im Folgenden dargestellt:
````
{
  "@context": [
    "https://www.w3.org/ns/odrl.JSONld",
    {
      "cx-policy": "https://w3id.org/catenax/policy/"
    }
  ],
  "@type": "Policy",
  "odrl:permission": [
      {
        "odrl:action": "USE",
        "odrl:constraint": {
          "@type": "LogicalConstraint",
          "odrl:and": [
            {
              "@type": "Constraint",
              "odrl:leftOperand": "BusinessPartnerNumber",
              "odrl:operator": {
                "@id": "odrl:eq"
              },
              "odrl:rightOperand": "<ALLOWED_CONSUMER_BPN>"
            },
            {
              "leftOperand": "cx-policy:UsagePurpose",
              "operator": "eq",
              "rightOperand": "cx.core.digitalTwinRegistry:1"
            s}
          ]
        }
      }
   ] 
}
````
Als letztes wird der Contract erstellt, der das zuvor erstellte Asset und die Policy lediglich referenziert und logisch verknüpft. Dies geschieht z.B. unter dem folgenden Endpoint:

**POST** <https://oem-controlplane.tractus-x-06.arena2036.de/management/v2/data/contractdefinitions>

Mit der Beispiel-Payload:
````
{
    "id": "<CONTRACT_ID>",
    "accessPolicyId": "<POLICY_ID>",
    "contractPolicyId": "<POLICY_ID>",
    "criteria": [
        {
            "operandLeft": "asset:prop:id",
            "operator": "=",
            "operandRight": "<ASSET_ID>"
        }
    ]
}
````

##### Data Consumption
![image](https://github.com/user-attachments/assets/331e880a-84c6-449c-913e-10b1cb853205)   
*Abbildung 8-24: Data Consumption*

Zum Suchen des EDC-Endpoints muss die BPN an den Discovery Service übermittelt werden. Zunächst müssen die BPNs über die BPN-Discovery, sowie Discovery-Services über den Discoveryfinder gefunden werden. Diese BPNs können dann bei der, durch den Discoveryfinder gefundene, EDC-Discovery zum Nachschlagen der EDC-Endpoints genutzt werden.

Für die folgenden Request müssen Authentifizierung-Token generiert werden. Diese müssen das in den HTTP-Header in der Form „Authentication: Bearer \<token\>“ zur Authentifizierung hinzugefügt werden. Die Generierung dieser Tokens ist in „**Live-Anpassungen und Authentifizierung**“ beschrieben.

###### **BPN-Discovery**
-   Authentifizierung über Token-Generierung für Client-ID sa-cl22-01
-   **POST** auf <https://bpndiscovery.tractus-x-06.arena2036.de/bpndiscovery/api/v1.0/administration/connectors/bpnDiscovery/search>
Beispiel-Payload:
```
{
  "searchFilter": [
    {
      "type": "oen",
      "keys": [
        "oen-1243",
        "oen-11"
      ]
    },
    {
      "type": "bpid",
      "keys": [
        "oen-satest05",
        "oen-satest02"
      ]
    }
  ]
}
```
Beispiel-Response:
```
{
  "bpns": [
    {
      "type": "oen",
      "key": "oen-satest05",
      "value": "BPNL00000003B0Q0",
      "resourceId": "972262d7-7e05-4578-936f-de236d7feb94"
    },
    {
      "type": "oen",
      "key": "oen-satest02",
      "value": "sBPNL00000003AYRE",
      "resourceId"s: "1b754aeb-c753-4adf-ae6d-52842f5a38b7"
    }
  ]
```

###### **Discoveryfinder**
-   Authentifizierung über Token-Generierung für Client-ID sa-cl21-01
-   **POST** auf <https://discoveryfinder.tractus-x-06.arena2036.de/discoveryfinder/api/v1.0/administration/connectors/discovery/search>
    -   Beispiel-Payload
```
{
  "types": [
    "oen",
    "bpid",
    "bpn"
  ]
}
```
Beispiel-Response:
```
{
    "endpoints": [
        {
            "type": "bpn",
            "description": "Service to discover connector endpoints based on bpns",
            "endpointAddress": "https://portal-backend.tractus-x-06.arena2036.de/api/administration/Connectors/discovery",
            "documentation": "https://portal-backend.tractus-x-06.arena2036.de/api/administration/swagger/index.html",
            "resourceId": "a0b77e6d-1365-48cd-8f37-fed2e2394489"
        }
    ]
}
```

###### **EDC-Discovery (Portal-Backend)**
-   Authentifizierung über Token-Generierung für Client-ID sa-cl1-reg-2
-   **POST** auf <https://portal-backend.tractus-x-06.arena2036.de/api/administration/Connectors/discovery>
    -   Beispiel-Payload
````
[
  "BPNL00000003AYRE",
  "BPNL00000003B2OM"
]
````
    -   Beispiel-Response
````
[
    {
        "bpn": "BPNL00000003AYRE",
        "connectorEndpoint": [
            "oem-controlplane.tractus-x-06.arena2036.de"
        ]
    },
    {
        "bpn": "BPNL00000003B2OM",
        "connectorEndpoint": [
            "tiertwo-1-controlplane.tractus-x-06.arena2036.de"
        ]
    }
]
````

###### Aufrufen des entsprechenden EDC-Endpoints
Für das Aufrufen des entsprechenden Contracts, wird ebenfalls die Management API des EDC-Controlplanes genutzt. Konkret wird der Endpoint [/catalog/request](https://oem-controlplane.tractus-x-06.arena2036.de/management/v2/catalog/request) genutzt. Der Catalog kann folgendermaßen angefragt und gefiltert werden. Der Filter ist optional. Zunächst können wir nach einer registrierten Digital Twin Registry suchen:

-   **GET** [https://oem-controlplane.tractus-x-06.arena2036.de/management/v2/catalog/request](https://oem-controlplane.tractus-x-06.arena2036.de/management/v3/data/assets)
    -   Beispiel-Payload
````
{
   "@context": {
       "edc": "https://w3id.org/edc/v0.0.1/ns/"
   },
   "@type": "CatalogRequest",
   "counterPartyAddress": "{{provider-dsp-endpoint}}",
   "protocol": "dataspace-protocol-http",
   "querySpec": {
       "offset": 0,
       "limit": 50,
       "filterExpression": [
           {
               "@context": {
                   "edc": "https://w3id.org/edc/v0.0.1/ns/"
               },
               "@type": "edc:Criterion",
               "operandLeft": "https://w3id.org/edc/v0.0.1/ns/id",
               "operator": "=",
               "operandRight": "{{assetId}}"
            }
        ]
    }
}
````

Darauf folgend kann man auch einen Shell-Lookup auf die ausgehandelte Digital Twin Registry durchführen:

-   **GET** <https://oem-dtr.tractus-x-06.arena2036.de/api/v3.0/lookup/shells/dXJuOnV1aWQ6MDM5ZDYwNWQtYjZiOC00M2I2LThmMTMtYzUwZDE1YTEzMGY5>
    - Beispiel-Response:
````
[
    {
        "supplementalSemanticIds": [],
        "name": "manufacturerPartId",
        "value": "JJ-55",
        "externalSubjectId": {
            "type": "ExternalReference",
            "keys": [
                {
                    "type": "GlobalReference",
                    "value": "PUBLIC_READABLE"
                }
            ]
        }
    }
]
````
Damit kann man ebenfalls einen spezifischen Shell-Descriptor abfragen. Siehe dafür Kapitel „1.3.5.5.1.2 Registrierung der AAS in DTR“.

#### Testdaten

Die in den folgenden Abschnitten beschriebenen Testdaten werden für den Use Case verwendet. Folgende Submodels mussten eigens für das Projekt erstellt werden, da sie vorher noch nicht existierten:

-   PartTypeInformation 
-   SingleLevelBomAsPlanned
-   OEM_SupplierRequirements

##### Testdaten von Kostal (Terminals)

| AAS                                      | Submodels                 | Benötigte Informationen                                                                                                                      |
|------------------------------------------|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Kostal_Terminal_MLK_1-2_0,5mm_2024_01_25 | PartTypeInformation       | “catenaXId”:  „91d54b9c-d950-4309-85e0-2de72d4797eb“ “manufacturerPartId”: "32140734113 " “nameAtManufacturer”: "Kostal_MLK_1,2_32140734113" |
|                                          | SingleLevelBomAsPlanned   | Keine ChildItems, da unbekannt                                                                                                               |
|                                          | Nameplate [3]             | Vom Projekt vorgegeben                                                                                                                       |
|                                          | ContactInformation [4]    | Vom Projekt vorgegeben                                                                                                                       |
|                                          | HandoverDocumentation [5] | Vom Projekt vorgegeben                                                                                                                       |
|                                          | TechnicalData [6]         | Vom Projekt vorgegeben                                                                                                                       |
|                                          | MCAD [7]                  | Vom Projekt vorgegeben                                                                                                                       |
| Kostal_Terminal_PLK_35mm²_HMI_2024_01_25 | PartTypeInformation       | “catenaXId”:  “248d03b5-9ce1-489d-9c5d-3d158022e3a5” “manufacturerPartId”: "23124690760" “nameAtManufacturer”: "AAS_MLK_14,5_35"             |
|                                          | SingleLevelBomAsPlanned   | Keine ChildItems, da unbekannt                                                                                                               |
|                                          | Nameplate                 | Vom Projekt vorgegeben                                                                                                                       |
|                                          | ContactInformation        | Vom Projekt vorgegeben                                                                                                                       |
|                                          | HandoverDocumentation     | Vom Projekt vorgegeben                                                                                                                       |
|                                          | TechnicalData             | Vom Projekt vorgegeben                                                                                                                       |
|                                          | MCAD                      | Vom Projekt vorgegeben                                                                                                                       |
| Kostal_Terminal_PLK_50mm²_HMI_2024_01_25 | PartTypeInformation       | “catenaXId”: “4bebcdf4-11c2-4ab9-8092-4b6b6761891a” “manufacturerPartId”: "23124690760" “nameAtManufacturer”: "AAS_PLK_14,5_50"              |
|                                          | SingleLevelBomAsPlanned   | Keine ChildItems, da unbekannt                                                                                                               |
|                                          | Nameplate                 | Vom Projekt vorgegeben                                                                                                                       |
|                                          | ContactInformation        | Vom Projekt vorgegeben                                                                                                                       |
|                                          | HandoverDocumentation     | Vom Projekt vorgegeben                                                                                                                       |
|                                          | TechnicalData             | Vom Projekt vorgegeben                                                                                                                       |
|                                          | MCAD                      | Vom Projekt vorgegeben                                                                                                                       |

##### Testdaten von Coroplast (Leitungen)

| AAS                                    | Submodels [JSON]        | Inhalt                                                                                                                              |
|----------------------------------------|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Coroflex_Leitung_0,5mm²_HMI_2024_02_12 | PartTypeInformation     | “catenaXId”:  “fa120983-4d82-4f94-a06a-c6d648f5bfd9” “manufacturerPartId”: "9-2611" “nameAtManufacturer”: "COROFLEX_FLR31_0_5"      |
|                                        | SingleLevelBomAsPlanned | Keine ChildItems, da unbekannt                                                                                                      |
|                                        | Nameplate               | Vom Projekt vorgegeben                                                                                                              |
|                                        | TechnicalData           | Vom Projekt vorgegeben                                                                                                              |
|                                        | ProductDesign           | Vom Projekt vorgegeben                                                                                                              |
|                                        | Documentation           | Vom Projekt vorgegeben                                                                                                              |
| Coroflex_Leitung_35mm²_HMI_2024_01_25  | PartTypeInformation     | “catenaXId”:  “96be3640-cae3-495d-bd20-0c700fae6ef6” “manufacturerPartId”: "9-2611" “nameAtManufacturer”: "COROFLEX_180HV_35"       |
|                                        | SingleLevelBomAsPlanned | Keine ChildItems, da unbekannt                                                                                                      |
|                                        | Nameplate               | Vom Projekt vorgegeben                                                                                                              |
|                                        | TechnicalData           | Vom Projekt vorgegeben                                                                                                              |
|                                        | ProductDesign           | Vom Projekt vorgegeben                                                                                                              |
|                                        | Documentation           | Vom Projekt vorgegeben                                                                                                              |
| Coroflex_Leitung_50mm²_HMI_2024_01_25  | PartTypeInformation     | “catenaXId”:  “e907e75a-1b8e-4bef-bc6a-0826ac0f273b” “manufacturerPartId”: "9-2611 / 50" “nameAtManufacturer”: "COROFLEX_9_2611_50" |
|                                        | SingleLevelBomAsPlanned | Keine ChildItems, da unbekannt                                                                                                      |
|                                        | Nameplate               | Vom Projekt vorgegeben                                                                                                              |
|                                        | TechnicalData           | Vom Projekt vorgegeben                                                                                                              |
|                                        | ProductDesign           | Vom Projekt vorgegeben                                                                                                              |
|                                        | Documentation           | Vom Projekt vorgegeben                                                                                                              |

##### Testdaten von ARENA (Gehäuse)

| AAS                             | Submodels               | Inhalt                                                                                                                       |
|---------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------|
| Kostal_GEHAEUSE_MLK_1-2_2024_01 | PartTypeInformation     | “catenaXId”: “18a3e5f8-cf00-491b-b690-d176cb9a5848” “manufacturerPartId”: "987-654-381” “nameAtManufacturer”: "AAS_GEHAEUSE" |
|                                 | SingleLevelBomAsPlanned | Keine ChildItems, da unbekannt                                                                                               |
|                                 | Nameplate               | Vom Projekt vorgegeben                                                                                                       |
|                                 | HandoverDocumentation   | Vom Projekt vorgegeben                                                                                                       |
|                                 | TechnicalData           | Vom Projekt vorgegeben                                                                                                       |
|                                 | MCAD                    | Vom Projekt vorgegeben                                                                                                       |

##### Testdaten von OEM

| AAS                                 | Submodels           | Inhalt                                                                                                                          |
|-------------------------------------|---------------------|---------------------------------------------------------------------------------------------------------------------------------|
| OEM_SupplierRequirements_2024_08_01 | AuthorizedSuppliers | globalAssetId: f446097f-fa75-435b-a88d-a7d80240df0e AuthorizedSuppliersList: BPNL00000003B2OM BPNL00000003CSGV BPNL00000003B5MJ |

##### Aggregierte Daten von Tier 1

| AAS                     | Submodels               | Inhalt                                           |                  |        |
|-------------------------|-------------------------|--------------------------------------------------|------------------|--------|
| ZusammenbauLeitungssatz | PartTypeInformation     | CatenaXId:  d39a99cd-e6b3-4ad1-8890-2f89b7046aa4 |                  |        |
|                         | SingleLevelBomAsPlanned | CatenaXId  (Kind-Teil)                           | BPNL             | Anzahl |
|                         |                         | fa120983-4d82-4f94-a06a-c6d648f5bfd9             | BPNL00000003B2OM | 6      |
|                         |                         | 96be3640-cae3-495d-bd20-0c700fae6ef6             | BPNL00000003B2OM | 6      |
|                         |                         | e907e75a-1b8e-4bef-bc6a-0826ac0f273b             | BPNL00000003B2OM | 6      |
|                         |                         | 91d54b9c-d950-4309-85e0-2de72d4797eb             | BPNL00000003CSGV | 3      |
|                         |                         | 248d03b5-9ce1-489d-9c5d-3d158022e3a5             | BPNL00000003CSGV | 3      |
|                         |                         | 4bebcdf4-11c2-4ab9-8092-4b6b6761891a             | BPNL00000003CSGV | 3      |
|                         |                         | 18a3e5f8-cf00-491b-b690-d176cb9a5848             | BPNL00000003B5MJ | 2      |

##### 

#### Sequenzieller Ablauf des Use Cases

Im Abschnitt 8.3.3 wurde der generelle sequenzielle Ablauf der Use Cases beschrieben. In diesem Abschnitt wird detailliert auf die einzelnen notwendigen Schritte eingegangen. Die technische Umsetzung wird in Abschnitt 8.3.5.4.4 erklärt.

##### Bereitstellung der Digitalen Zwillinge der Tier 2 und des OEM

Jeder Komponentenhersteller legt automatisch Digitale Zwillinge zu seinen Produkten an. Der OEM legt seine Anforderungen an den Leitungssatz als Digitalen Zwilling an.

###### Tier 2.1 (Kostal): Data Provisioning

-   ContractDefinition (mit Asset & Policies) für DTR im EDC von „Tier 2.1 Kostal“ anlegen
-   Submodels aus erhobenen Daten erstellen (Auflistung Testdaten in Abschnitt 8.3.5.6.1)
-   Submodels in das BaSyx Submodel-Repository von „Tier 2.1 Kostal“ hochladen
-   Registrieren des Digitalen Zwillings in der DTR von „Tier 2.1 Kostal“
-   ContractDefinition (mit Asset & Policies) für jedes Submodel im EDC von „Tier 2.1 Kostal“ anlegen

###### Tier 2.2 (Coroplast): Data Provisioning

-   ContractDefinition (mit Asset & Policies) für DTR im EDC von „Tier 2.2 Coroplast“ anlegen
-   Submodels aus erhobenen Daten erstellen (Auflistung Testdaten in Abschnitt 0)
-   Submodels in das BaSyx Submodel-Repository von „Tier 2.2 Coroplast“ hochladen
-   Registrieren des Digitalen Zwillings in der DTR von „Tier 2.2 Coroplast“
-   ContractDefinition (mit Asset & Policies) für jedes Submodel im EDC von „Tier 2.2 Coroplast“ anlegen

###### Tier 2.3 (ARENA): Data Provisioning

-   ContractDefinition (mit Asset & Policies) für DTR im EDC von „Tier 2.3 ARENA“ anlegen
-   Submodels aus erhobenen Daten erstellen (Auflistung Testdaten in Abschnitt 0)
-   Submodels in das BaSyx Submodel-Repository von „Tier 2.3 ARENA“ hochladen
-   Registrieren des Digitalen Zwillings in der DTR von „Tier 2.3 ARENA“
-   ContractDefinition (mit Asset & Policies) für jedes Submodel im EDC von „Tier 2.3 ARENA“ anlegen

###### OEM: Data Provisioning

-   ContractDefinition (mit Asset & Policies) für DTR im EDC von „OEM“ anlegen
-   Submodels aus erhobenen Daten erstellen (Auflistung Testdaten in Abschnitt 8.3.5.6.4)
-   Submodels in das BaSyx Submodel-Repository von „OEM“ hochladen
-   Registrieren des Digitalen Zwillings in der DTR von „OEM“
-   ContractDefinition (mit Asset & Policies) für jedes Submodel im EDC von „OEM“ anlegen

##### Zugriff des Tier 1 auf die Daten der Tier 2 & des OEM

Der Tier 1 zieht sich die Informationen zu den autorisierten Suppliern vom OEM. Daraufhin greift er auf die Daten der Tier 2 zu. Die technische Umsetzung wird in Abschnitt 8.3.5.5.1 erklärt.

###### ZuTier 1: Data Consumption von OEM

-   Anfrage & Zugriff bei erfolgreicher Contract-Negotiation auf die DTR des OEM
-   Aussuchen der entsprechenden Data-Assets des OEM (in diesem Fall gibt es nur das Submodel „AuthorizedSuppliers“)
-   Anfrage & Zugriff bei erfolgreicher Contract-Negotiation auf das Submodel „AuthorizedSuppliers“ des OEM

###### Tier 1: Data Consumption von Tier 2.1 Kostal

-   Herausfinden des Endpoints von Tier 2.1 Kostal mittels EDC Discovery
-   Anfrage & Zugriff bei erfolgreicher Contract-Negotiation auf die DTR von Tier 2.1 Kostal
-   Aussuchen der entsprechenden Data-Assets von Tier 2.1 Kostal
-   Anfrage & Zugriff bei erfolgreicher Contract-Negotiation auf die Submodels von Tier 2.1 Kostal

###### Tier 1: Data Consumption von Tier 2.2 Coroplast

-   Herausfinden des Endpoints von Tier 2.2 Coroplast mittels EDC Discovery
-   Anfrage & Zugriff bei erfolgreicher Contract-Negotiation auf die DTR von Tier 2.2 Coroplast
-   Aussuchen der entsprechenden Data-Assets von 2.2 Coroplast
-   Anfrage & Zugriff bei erfolgreicher Contract-Negotiation auf die Submodels von 2.2 Coroplast

###### Tier 1: Data Consumption von Tier 2.3 ARENA

-   Herausfinden des Endpoints von Tier 2.3 ARENA mittels EDC Discovery
-   Anfrage & Zugriff bei erfolgreicher Contract-Negotiation auf die DTR von Tier 2.3 ARENA
-   Aussuchen der entsprechenden Data-Assets von Tier 2.3 ARENA
-   Anfrage & Zugriff bei erfolgreicher Contract-Negotiation auf die Submodels von Tier 2.3 ARENA

##### Aggregation und Datenbereitstellung von Tier 1

-   ContractDefinition (mit Asset & Policies) für DTR im EDC von „Tier 1“ anlegen
-   Submodels aus konsumierten Daten erstellen (Auflistung Testdaten in Abschnitt 8.3.5.6.5)
-   Submodels in das BaSyx Submodel-Repository von „Tier 1“ hochladen
-   Registrieren des aggregierten Digitalen Zwillings in der DTR von „Tier 1“
-   ContractDefinition (mit Asset & Policies) für jedes Submodel im EDC von „Tier 1“ anlegen

### <a name="8.3.6"></a>8.3.6 Whitespots

Während der Bearbeitung des Projekts konnten Whitespots identifiziert werden, auf die im Folgenden eingegangen wird.

Für den Kontext der identifizierten Whitespots, wie z.B. genutzte Versionen und Annahmen, siehe auch „Aufbau der technischen Infrastruktur“.

#### Funktionalität

Tractus-X

Aktuell gibt es keine Software, die den Austausch digitaler Zwillinge ermöglicht oder Einblick in die aktuellen Angebote von Cofinity-X gewährt.

-   Trace-X[^35] bietet zwar Funktionen für Data-Provisioning und -Consumption, jedoch ausschließlich mit Tracability-spezifischen Submodellen.
-   Der Simple Data Exchanger[^36] wird wird zurückgehalten und kann nur begrenzt in Deployments integriert werden.

[^35]: <https://github.com/eclipse-tractusx/traceability-foss>

[^36]: <https://github.com/eclipse-tractusx/managed-simple-data-exchanger>

    / <https://github.com/Cofinity-X/cofinity-x-ba-managed-simple-data-exchanger-frontend>

Catena-X e.V. / Cofinity-X GmbH (als kommerzieller Anbieter)

-   Catena-X ist stark auf Use-Cases ausgerichtet. Das bedeutet, dass Support und Software fehlen, wenn man außerhalb eines bestehenden, nicht in Catena-X enthaltenen Use-Cases agiert.
-   Zudem gibt es mehrere parallele Entwicklungen für Transfer-Konzepte im EDC, wie EDRs, Public HTTP und Cloud, die sich in unterschiedlichen Entwicklungsstadien und mit unterschiedlichem Support befinden.
-   Da nicht alle Komponenten alle Transfer-Konzepte unterstützen, muss der kleinste gemeinsame Nenner gefunden werden.

Catena-X e.V. / IDTA e.V.

In Catena-X gibt es derzeit keine Konzepte für das Asset-Bundling:

-   Der Prozess zur kohärenten Registrierung mehrerer Submodelle befindet sich noch in der Entwicklung ("The process for registering multiple submodels in a cohesive manner is still under development.").
-   Zudem existieren keine EDC-Policies auf der Ebene von Submodel-Properties; aktuell sind diese nur auf der Submodel- oder Asset-Ebene verfügbar.

#### Submodels & Semantic Models

Catena-X e.V. / IDTA

Die Submodel Templates der IDTA sind, abgesehen vom IDTA-02006 (Nameplate), nicht standardisiert für die Catena-X Use-Cases ([Part_Type_Information](https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main/io.catenax.part_type_information)). Catena-X-Technologien nutzen keine bestehenden AASen, sondern es werden „eigene“ Digitale Zwillinge in Form von AAS-Deskriptoren in der DTR registriert. In diesen Deskriptoren wird auf bestehende Submodels verwiesen.

Beispiele für Semantic Models finden sich unter [eclipse-tractusx/sldt-semantic-models](https://github.com/eclipse-tractusx/sldt-semantic-models)[^37]. Ein Problem dabei ist, dass die JSON-Dateien keine validen IDTA-Submodelle sind. Zudem funktioniert die Import-Funktion des AASX Package Explorers weder für exportierte Submodelle noch für Catena-X Submodelle.

[^37]: <https://github.com/eclipse-tractusx/sldt-semantic-models>

Ein Workaround für Catena-X besteht daher aus mehreren Schritten: Zunächst wird die AASX-Datei heruntergeladen und als XML exportiert. Diese XML-Datei wird dann im AASX Package Explorer geöffnet und das Submodel als JSON exportiert. Anschließend wird die Ziel-AASX geöffnet und als AASX JSON gespeichert. Im letzten Schritt wird das JSON manuell eingebunden und eine Referenz angelegt, bevor die Datei erneut im AASX Package Explorer geöffnet wird.

#### Security

Catena-X e.V / IDTA / Gaia-X / Eclipse Data Space Group

-   Derzeit existiert kein umfassendes Sicherheitskonzept für die Kommunikation zwischen EDC (Eclipse Data Connector) und AAS. Es mangelt an klaren Konzepten und Richtlinien, die festlegen, wie nach dem EDC-Transfer mit Sicherheits- und Datenschutzaspekten umgegangen werden soll. Weitere Informationen zu den Interaktionsmustern finden sich in der Dokumentation des Digital Twin Kits. [https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-interaction-patterns/\#:\~:text=GET%20%7B%7Bsubmodel%2Ddescriptor/href%7D%7D/%24value](https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-interaction-patterns/#:~:text=GET%20%7B%7Bsubmodel%2Ddescriptor/href%7D%7D/%24value)
-   Seitens der IDTA befindet sich der attributbasierte Zugriffskontrollstandard (ABAC) in der Entwicklung und ist noch nicht verabschiedet. Ein Problem ist, dass Dokumente nicht frühzeitig veröffentlicht werden, was die Implementierung erschwert.
-   In BaSyx gibt es derzeit ein rudimentäres RBAC-Konzept und es wird bzgl. Weiterentwicklung auf die Spezifikation der IDTA gewartet. Daher wird die attributsbasierte Zugriffskontrolle voraussichtlich (ABAC) erst im neuen BaSyx Release V3 erwartet.
-   Eine mögliche Lösung für die Zertifikatsverwaltung ist die Nutzung von Keycloak, es gibt dafür ein SDK-Anwendungsbeispiel „[BaSyxSecured](https://github.com/eclipse-basyx/basyx-java-server-sdk/tree/main/examples/BaSyxSecured)“ [^38] .

[^38]: <https://github.com/eclipse-basyx/basyx-java-server-sdk/tree/main/examples/BaSyxSecured>

#### UI

BaSyx

Das [BaSyx-UI](https://github.com/eclipse-basyx/basyx-aas-web-ui)[^39] und Tractus-X-Komponenten sind derzeit nur eingeschränkt interaktionsfähig. Zwar existiert ein [Bill of Material Submodel-Plugin](https://github.com/eclipse-basyx/basyx-aas-web-ui/blob/main/aas-web-ui/src/components/SubmodelPlugins/BillsOfMaterial.vue), jedoch müsste eine Erweiterung implementiert werden, um Catena-X-konforme BOMs (Aspect Model „SingleLevelBomAsPlanned/Built“) zu unterstützen.

      
![image](https://github.com/user-attachments/assets/5dde440d-f716-4363-9654-b31b5677c9b6)   
*Abbildung 9-25: Darstellung „Bills of Material“ in BaSyx*


[^39]: <https://github.com/eclipse-basyx/basyx-aas-web-ui>

Tractus-X

Der Simple Data Exchanger[^40] von Tractus-X wird derzeit noch zurückgehalten und ist nur begrenzt in Deployments integrierbar. Eine Alternative dazu existiert zum aktuellen Zeitpunkt nicht, da das EDC DataDashboard[^41] stark veraltet ist und nicht mit Catena-X kompatibel ist.

[^40]: https://github.com/eclipse-tractusx/managed-simple-data-exchanger-frontend / https://github.com/Cofinity-X/cofinity-x-ba-managed-simple-data-exchanger-frontend

[^41]: https://github.com/eclipse-edc/DataDashboard

Trace-X[^42] bietet zwar Möglichkeiten für Data-Provisioning und -Consumption, jedoch nur mit Traceability-spezifischen Submodellen.

[^42]: https://github.com/eclipse-tractusx/traceability-foss

#### Helm-Charts

Tractus-X

Der aktuelle Stand der Helm-Charts für Tractus-X zeigt, dass derzeit nur zwei EDCs (Eclipse Data Connectors) mit einem Transfer zwischen ihnen unterstützt werden, wie auf den Tractus-X Community Days erläutert wurde. Ein weiteres Problem ist, dass Ingresses teilweise fehlen oder nicht getestet sind.

Die Seeding-Daten sind oft hard-coded und schwer konfigurierbar. Das Erstellen von Docker-Containern, deren Upload in eine Docker-Registry und die Einbindung in Helm-Charts stellen zusätzliche Herausforderungen dar, insbesondere bei der Anpassung von Keycloak.

Ein ordentliches Zertifikatsmanagement ist nicht Teil von Catena-X, und die Helm-Charts bieten nur eine provisorische Lösung für lokale Tests. Die Sandbox-Umgebung ist entweder vollständig oder gar nicht nutzbar. Im letzteren Fall bedeutet dies, dass im Grunde nur zwei EDCs mit einfachem Transfer unterstützt werden.

Die initiale Einstiegshürde ist hoch, und gleichzeitig ist die vollständige Lösung noch nicht einsatzbereit. Diese Punkte verdeutlichen die aktuellen Herausforderungen und den Bedarf an Weiterentwicklungen, um eine nahtlose Integration und Nutzung der verschiedenen Komponenten innerhalb von Catena-X zu gewährleisten.

BaSyx

Hinsichtlich BaSyx gibt es zum aktuellen Zeitpunkt keine öffentlichen Helm-Charts bzw. Werden diese derzeit noch unter Verschluss gehalten.

**Die IDTA-Spezifikationen werden teilweise unterschiedlich implementiert, was sich in der Namensgebung und der Gruppierung der Services zeigt.**

#### Softwareintegration

Tractus-X

Bei Tractus-X ist die Implementierung der IDTA-Spezifikationen nur sehr begrenzt. Die AAS-Registry API (/shell-descriptors), die Discovery API (/lookup/shells) und die Description API sind Beispiele für die begrenzte Umsetzung.

Weitere Informationen dazu finden sich in der Dokumentation zu Digital Twins in Catena-X: https://catenax-ev.github.io/docs/next/standards/CX-0002-DigitalTwinsInCatenaX

BaSyx / IDTA

Für BaSyx und IDTA gibt es derzeit keine öffentlichen Konzepte oder Unterstützung für EDCs. Obwohl der Wunsch danach in mehreren Projekten vorhanden ist, sind einzelne Demos und Komponenten aufgrund mangelnder Dokumentation und komplexer Konfiguration schwer zu integrieren. Viele Services funktionieren zwar isoliert, haben jedoch Schwierigkeiten bei der Integration in ein umfassendes System.

#### Dokumentation

Tractus-X / Open Source Community

Die Dokumentation im Bereich Tractus-X und der Open Source Community weist einige Lücken auf. Die End-to-End-Tutorials sind begrenzt und decken nicht alle notwendigen Aspekte ab. Darüber hinaus fehlt die Dokumentation für viele der oben genannten Punkte vollständig.

BaSyx

Bei BaSyx gibt es ebenfalls erhebliche Dokumentationslücken. Die Dokumentation für das BaSyx-Java-SDK v2 fehlt, während die Version 1 nicht mehr unterstützt wird. Es mangelt an Tutorials sowie an Übersichten und Diagrammen, die für eine umfassende Nutzung und Integration der BaSyx-Komponenten notwendig wären.

Diese Defizite in der Dokumentation erschweren die Implementierung und Nutzung der entsprechenden Technologien erheblich.

## <a name="8.4"></a>8.4 User Interfaces

Dieses Kapitel dient zur Anforderungsaufnahme an vorhandene und zukünftig wünschenswerte Administrationsbezogene und für Anwendungsfallbezogene User Interfaces in der besprochenen digitalen Wertschöpfungskette, als rudimentäre Ideensammlung für zukünftige Umsetzungsprojekte.

Anzeige der AAS und Catena-X-spezifische Submodels:

Aktuell verwendet das Projekt VWS4LS zwei Programme, um Digitale Zwillinge in Form der AAS und die damit verbundenen Submodels anzuzeigen:

1.  [AASX Package Explorer](https://github.com/admin-shell-io/aasx-package-explorer/releases)[^43]
2.  [Eclipse BaSyx](https://eclipse.dev/basyx/)[^44]

[^43]: <https://github.com/admin-shell-io/aasx-package-explorer/releases>

[^44]: <https://eclipse.dev/basyx/>

![image](https://github.com/user-attachments/assets/8f06ae43-44d1-4fdb-880b-e518d85d1f49)   
*Abbildung 8-26: AASX Package Explorer*

Im AASX Package Explorer können auch Catena-X spezifische Submodels („PartTypeInformation“ & „SingleLevelBomAsPlanned“) angezeigt werden (*Abbildung 8-27*, „[Tier_1_Zusammenbau_Leitungssatz.aasx](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP08/Testdaten/Tier1(Aggregation)/Tier_1_ZusammenbauLeitungssatz.aasx)“[^45]):

[^45]: <https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP08/Testdaten/Tier1(Aggregation)/Tier_1_ZusammenbauLeitungssatz.aasx>

![image](https://github.com/user-attachments/assets/072af68c-2332-4d98-afd4-5b7e29a7b15e)   
*Abbildung 8-27: Integration des Catena-X Submodels "PartTypeInformation"*

![image](https://github.com/user-attachments/assets/41600b55-3542-40bc-88fc-aa40fa960142)   
*Abbildung 8-28: BaSyx-Frontend zeigt ProductID in AAS MES_Info (Screenshot)*

![image](https://github.com/user-attachments/assets/7f8852fd-e4f6-42fe-a793-199c17ebc395)   
*Abbildung 8-29: BaSyx-Frontend zeigt Maintenance_Counter von Machine_1 in AAS MES_Info*

Was zum jetzigen Zeitpunkt noch nicht möglich ist, ist dass eines der beiden Programme das Submodel „*SingleLevelBomAsPlanned*“ interpretiert. In diesem Submodel stehen alle externen Komponenten in Form von Catena-X ID´s, die in dem Teil verbaut sind. Das AAS-Programm müsste sich automatisch Zugriff über den EDC auf die enthaltenen Komponenten verschaffen (d.h. Zugriff auf die Externen DTR´s und Submodel Server) und anzeigen.

Die Open Source Software „[Trace-X](https://github.com/eclipse-tractusx/traceability-foss)“ kann das, aktuell aber nur mit Catena-X standardisierten Submodels.

## <a name="8.5"></a> Ausblick

Im Teilprojekt 8 „**Data Storage Policy, Sicherheit, Anbindung an Catena-X**“ konnte eine Aggregation von Informationen für das Produkt Leitungssatz mittels AAS und den Catena-X Komponenten zwischen den Wertschöpfungspartnern in der Leitungssatzwertschöpfung prototypisch durchgeführt werden.

Es mussten bestehende Tractus-X Umbrella Helm Charts umfänglich konfiguriert werden, um eine Testumgebung mit benötigten Catena-X konformen (simulierten) Core Services bereitzustellen. Eine Zusammenarbeit mit der Cofinity-X GmbH als Anbieter eines kommerziellen Systems war zum Zeitpunkt des Projekts noch nicht realisierbar. Zukünftig sollten aber für eine realistische Testumgebung die realen Core Services von Cofinity-X verwendet werden.

Die dezentralen Tractus-X Komponenten für die Enablement Services (EDC & DTR) mussten ebenfalls umfänglich für den Use Case konfiguriert werden. Die Integration eines „Submodel Servers“ unter Verwendung von BaSyx war mit erheblichem Entwicklungsbedarf verbunden, da hier noch keine öffentlichen Helm-Charts vorhanden waren.

Ein Show-Case mit intuitiven User Interfaces, die sowohl Submodels nach Catena-X Standard als auch Submodels der IDTA e.V. gemeinsam verwalten können, war nicht möglich, da diese User Interfaces noch nicht vorhanden sind. Daher erfolgte die Umsetzung des Datenaustausch rein manuell mit API-Befehlen, was eine Demonstration wenig anschaulich macht.

Ein übergreifendes Security-Konzept bestand zum Zeitpunkt des Projekts noch nicht. Die Security-Konzepte des EDC und die des BaSyx-basierten „Submodel-Servers“ sind noch vollständig entkoppelt. Zwar konnten Policies für den EDC verwendet werden, allerdings war seitens BaSyx das RBAC & ABAC noch nicht vollständig implementiert. Ein Overall-Security-Konzept mit EDC und AAS wird benötigt.

Generell erscheint Catena-X als „eigene Welt“ mit eigenen Architekturprinzipien (zumindest was das Zusammenspiel zwischen DTR & AAS angeht). Zudem besteht eine starke Fokussierung auf die bestehenden Catena-X Use Cases.

Aus technischer Sicht gibt es Herausforderungen, die in den Bereichen der Softwareintegration, der Sicherheitskonzepte und der Datenverwaltung liegen. Die unterschiedlichen Implementierungen der IDTA-Spezifikationen und die fehlende Catena-X-Standardisierung der Submodel-Templates, sowie inkonsistenter Entwicklungsstand der Catena-X Use-Cases erschweren die Integration der verschiedenen Komponenten. Die begrenzte Dokumentation und das Entwicklungsstadium der Helm-Charts sowie die limitierten EDC-Konzepte erhöhen die Komplexität der technischen Implementierung. Zudem gibt es bislang kein ausgereiftes Sicherheitskonzept, um eine sichere und robuste Datenübertragung und -verwaltung zwischen den verschiedenen Systemen zu gewährleisten.

Konzeptionell wird es darum gehen, den in einem Teilmodell “Sicherheit” konfigurierten Rollen und Zugriffsrechte über einen geeigneten Ansatz in dynamisch generierte Policies im Control-Plane des EDC zu generieren. Dies wir eine Überarbeitung der Architektur erfordern.

### <a name="8.5.1"></a> Bewertung Status Quo

Die konzeptionellen Unterschiede zwischen den beiden Ökosystemen („AAS mit Submodellen“ und „CX-Aspektmodelle“) erfordern geeignete Definitionen, um eine nahtlose Integration zu ermöglichen. Ein wesentlicher Punkt dabei ist der Unterschied in der Handhabung der DTR (Decentralized Trusted Registry). Während beide Ökosysteme mit Submodellen und AAS (Asset Administration Shells) arbeiten, liegt der Unterschied darin, dass - anstatt auf bestehende AASen zu verweisen - in der DTR eine neue AAS (Deskriptor) angelegt wird und direkt auf bestehende Submodels verweist.

Dies bedeutet, dass selbst bei bereits vorhandenen AASen diese noch in der DTR angelegt werden müssen, um direkt auf Submodels verweisen zu können. Daher besteht Bedarf an einem Tool, das bestehende AASen automatisch in einer Catena-X-kompatiblen DTR anlegt und die notwendigen Verweise auf die Submodels setzt. Derzeit erfolgt dieser Prozess noch manuell.

Darüber hinaus wurde in beiden Ökosystemen ein Mangel an geeigneten Benutzeroberflächen festgestellt, die sowohl administrative als auch anwendungsbezogene Interaktionen der Anwender mit dem Gesamtsystem unterstützen. Es fehlt insbesondere an UIs, die den Austausch von AASen ermöglichen. Es gibt derzeit keine Benutzeroberfläche, in der digitale Zwillinge nach Catena-X Standards erstellt, bereitgestellt und konsumiert werden können. Die Entwicklung solcher UI-Lösungen ist entscheidend, um die Anwendungskette abzudecken und somit die Akzeptanz dieser Systeme erheblich zu steigern.

Ein ökosystemübergreifendes Konzept für Identity & Access Management (IAM) ist noch nicht ausdefiniert.

### <a name="8.5.2"></a>Blick in die Zukunft

Die zukünftige Entwicklung für die Weiterentwicklung der bisherigen Arbeit hängen von einigen grundsätzlichen Entscheidungen ab:

1.) Auswahl des zukünftigen Identitätsmanagements. Soll in Zukunft auf eine Alternative zu den in Catena-X verwendeten Business Partner Numbers (BPNs) gesetzt werden, z.B. insbesondere die elektronischen Identitäten der EU (eIDAS2.0) für Personen, Unternehmen und Produkte?

2.) Wie wird der Datenzugriff und die Übertragung auf die Verwaltungsschale durchgeführt?

3.) An welchen Ort sollen die Souveränität und damit die Zugriffskontrolle erfolgen?

4.) Und welche Methoden sollen dabei genutzt werden?

Im Folgenden werden einige grundsätzlichen Überlegungen dazu erörtert. Die Entscheidungen erfordern eine weitere Evaluierung auch in Abstimmung mit der Weiterentwicklung mit weiteren Projekten im Rahmen von Manufacturing-X, insbesondere [Catena-X NEXT](https://catena-x.net/de/aktuelles-termine/news-display/cx-next-startet).

Bei der 1. Frage zu den Identitäten ist mit der Einführung von SSI grundsätzlich die Nutzung verschiedener Identitäten und deren Providern möglich. Die entsprechende Weiterentwicklung des Wallets innerhalb von Tractus-X wird sehr wahrscheinlich eine Nutzung von anderen Identitäten ermöglichen. Da anderseits gerade die Leitungssatzbranche per se direkt Bestandteil der Lieferkette der Automobilindustrie ist, ist die Nutzung der von dieser bevorzugten BPNs naheliegend, solange nicht andere Identitäten z.B. durch Produktpässe über die Verwaltungsschale eingeführt werden.

Bei den Fragen zu 2., 3. und 4. geht es darum, wo die Souveränität durch den Datenanbieter (Provider) konfiguriert wird. Folgende mögliche konzeptionelle Lösungsansätze für ein CX-Produktivsystem mit Anbindung an AAS-Infrastrukturen (*Abbildung 8-29*) kommen dabei in Frage:

1.  CX-Anwendung greift direkt auf AAS zu, die Zugriffskontrolle erfolgt über die Verwaltungsschale: Die Catena-X-Infrastruktur wird ausschließlich für die Verwaltung des B2B-Workflows (Kette) über „*non-operational data*“ verwendet. Die eigentlichen Dateninhalte („*operational data*“) des/der Assets im Workflow werden in verteilten AAS-Repositories verwaltet. D.h. aus dem Catena-X-Workflow heraus wird nur eine Verlinkung auf die jeweils relevante AAS mit den Dateninhalten benötigt und bei Bedarf (z.B. Datenmanipulation) aus der CX-Anwendung auf die entsprechende AAS-Anwendungstoolkette „abgesprungen“. Die Rechteverwaltung für Submodelle und einzelne Datenpunkte findet dabei ausschließlich im AAS-Repository statt. So können die beiden Welten parallel miteinander koexistieren und interagieren, sind aber technisch stark entkoppelt.
2.  CX-Anwendung greift über ein Aspekt-Modell des EDC auf Teilmodelle der AAS zu, die Zugriffskontrolle erfolgt nur über angepasste Policies im EDC: Grundsätzlich getrennte Datenhaltung wie oben beschrieben, aber mit Anpassung des EDC, der dann als Gateway für den Zugriff auf die AAS-Infrastruktur dient. Dies würde einen tieferen Eingriff in dem EDC-System bedeuten, könnte aber die Komplexität auf Seiten der CX-Anwendungen, die mit einer VWS-Infrastruktur interagieren möchten, deutlich verringern.
3.  CX-Anwendung greift über ein angepasstes Asset des EDC auf die komplette AAS zu, die Zugriffskontrolle erfolgt über die AAS: Es ist eine Architekturanpassung im Control-Plane des EDC vorzunehmen, die erlaubt, dass die in einem Teilmodell “Sicherheit” konfigurierten Rollen und Zugriffsrechte über einen geeigneten Ansatz in dynamisch generierte Policies in den Control-Plane des EDC übertragen werden. Dafür wird man neben dem EDC auch die entsprechende dDTR konzeptionell erweitern müssen. Die Änderungen würde auch das Protokoll der “Vertragsaushandlung” zwischen zwei EDC betreffen das Protokoll würde die dDTR einbeziehen müssen (*Abbildung 8-29*).

![image](https://github.com/user-attachments/assets/4bbb1602-5916-4848-884b-72ed300742c1)   
*Abbildung 8-30: Interaktion Tractus-X und AAS via EDC*

Für die Anwendung in der Leitungssatz-Branche müsste eine der oben aufgezählten Optionen mit den anderen Manufacturing-X-Projekten abgestimmt, weiter detailliert und dann zukünftig umgesetzt werden.

Um die erkannten Mängel in den beteiligten Ökosystemen zu beseitigen, wären sinnvolle nächste Maßnahmen:

**Tractus-X**:

1.  Implementierung einer AAS-Schnittstelle mit/ohne EDC nach einem der obigen Konzepte.
2.  Entwicklung einer „VWS4LS-App“ für die Leitungssatz-Wertschöpfungskette.
3.  Implementierung einer Funktionalität für die Transformation von AAS-Security-Modellen in CX-Policies (mit/ohne Interpretation durch EDC)

**BaSyx**:

1.  Entwicklung eines „VWS4LS-Plugins“ zur Erzeugung und Verwaltung von LS-AAS.
2.  Entwicklung eines „Security-Plugins“ zur Konfiguration des Rollen- und Rechte-Managements für AAS, Submodelle und Attribute.


# <a name="Literaturverzeichnis"></a>Literaturverzeichnis

|||
| :- | :- |
| [1]   | Industrial Digital Twin Association e.V., „IDTA 01002-3-0-2: Specification of the Asset Administration Shell Part 2: Application Programming Interfaces,“ June 2024. [Online]. Available: https://industrialdigitaltwin.org/content-hub/aasspecifications/idta_01002-3-0-2_application_programming_interfaces.                                             |
| [2]   | V. C. Hu, D. Ferraiolo, R. Kuhn, A. Schnitzer, K. Sandlin, R. Miller und K. Scarfone, „Guide to Attribute Based Access Control (ABAC) Definition and Considerations,“ National Institute of Standards and Technology Special Publication, Gaithersburg, 2014.                                                                                              |
| [3]   | Industrial Digital Twin Association e.V., „IDTA 02006-2-0 Digital Nameplate for Industrial Equipment,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Digital%20nameplate/2/0.                                                                                                                              |
| [4]   | Industrial Digital Twin Association e.V. , „IDTA 02002-1-0: Submodel for Contact Information,“ May 2022. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Contact%20Information/1.                                                                                                                            |
| [5]   | Industrial Digital Twin Association e.V., „IDTA 02004-1-2 Handover Documentation,“ March 2023. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Handover%20Documentation/1/2.                                                                                                                                 |
| [6]   | Industrial Digital Twin Association e.V., „IDTA 02003-1-2: Generic Frame for Technical Data for Industrial Equipment in Manufacturing,“ [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Technical_Data/1/2.                                                                                                  |
| [7]   | Industrial Digital Twin Association e.V., „IDTA 02026-1-0 Provision of 3D Models,“ June 2024. [Online]. Available: https://github.com/admin-shell-io/submodel-templates/tree/main/published/Provision%20of%203D%20Models/1/0.                                                                                                                              |
| [8]   | VDI 2860, „Montage- und Handhabungstechnik; Handhabungsfunktionen, Handhabungseinrichtungen; Begriffe, Definitionen, Symbole,“ Beuth Verlag, Berlin, 1990.                                                                                                                                                                                                 |
| [9]   | M. Fechter, C. Seeber und S. Chen, „Integrated Process Planning and Resource Allocation for Collaborative Robot Workplace Design,“ 0, 2018.                                                                                                                                                                                                                |
| [10]  | V. C. Hu, D. Ferraiolo, R. Kuhn, A. Schnitzer, K. Sandlin, R. Miller und K. Scarfone, „Guide to Attribute Based Access Control (ABAC) Definition and Considerations,“ National Institute of Standards and Technology Special Publication, Gaithersburg, 2014.                                                                                              |
| [11]  | D. Trauth, „Monetization of Data at the Example of Manufacturing Machines,“ Springer, Berlin, Heidelberg, 2023.                                                                                                                                                                                                                                            |
| [12]  | OPC Foundation, „OPC 40570: OPC UA for the Wire Harness Manufacturing Industry,“ https://profiles.opcfoundation.org/workinggroup/88, WiP. [Online]. Available: https://profiles.opcfoundation.org/document/214.                                                                                                                                            |
| [13]  | „VWS4LS-Github,“ ARENA2036 e.V., [Online]. Available: https://github.com/VWS4LS.                                                                                                                                                                                                                                                                           |
| [14]  | „ETL-Prozess,“ [Online]. Available: https://de.wikipedia.org/wiki/ETL-Prozess.                                                                                                                                                                                                                                                                             |
| [15]  | C. Diedrich, A. Belyaev, R. Blumenfeld, J. Bock, S. Grimm, J. Hermann, T. Klausmann, A. Köcher, M. Maurmaier, K. Meixner, J. Peschke, M. Schleipen, S. Schmitt, B. Schnebel, G. Stephan, M. Volkmann, A. Wannagat, K. Watson, M. Winter und P. Zimmermann, „Information Model for Capabilities, Skills & Services,“ Plattform Industrie 4.0, Berlin, 2022. |
| [16]  | OPC Foundation, „OPC 10000-210: Industrial automation - Relative Spatial Location,“ 2023. [Online]. Available: https://reference.opcfoundation.org/RSL/v100/docs/.                                                                                                                                                                                         |
| [17]  | Prostep ivip, „Vehicle Electric Container (VEC),“ prostep ivip, 8 Jan 2024. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v210/.                                                                                                                                                                                                   |
| [18]  | IEC, „IEC 61360-4 - IEC/SC 3D - Common Data Dictionary,“ [Online]. Available: https://cdd.iec.ch/cdd/iec61360/iec61360.nsf/TreeFrameset?OpenFrameSet.                                                                                                                                                                                                      |
| [19]  | ECLASS e.V., „Technical Specification Conceptual Data Model,“ 2020.                                                                                                                                                                                                                                                                                        |
| [20]  | Industrial Digital Twin Association e.V., „IDTA 02031-1-0 Bill of Process (WiP),“ [Online]. Available: https://industrialdigitaltwin.org/content-hub/teilmodelle.                                                                                                                                                                                          |
| [21]  | Plattform Industrie 4.0, „Digitale Ökosysteme global gestalten,“ 2019. [Online]. Available: https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/Leitbild-2030-f%C3%BCr-Industrie-4.0.pdf?__blob=publicationFile&v=1.                                                                                                                        |
| [22]  | Plattform Industrie 4.0, „Interoperability at Runtime - Exchanging Information via Application Programming Interfaces,“ 2021. [Online]. Available: https://www.plattform-i40.de/IP/Redaktion/EN/Downloads/Publikation/Details_of_the_Asset_Administration_Shell_Part2_V1.pdf?__blob=publicationFile&v=1.                                                   |
| [23]  | Plattform Industrie 4.0, „Vertrauensinfrastrukturen,“ 03 2021. [Online]. Available: https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/Vertrauensinfrastrukturen.pdf?__blob=publicationFile&v=1.                                                                                                                                           |
| [24]  | Industrial Digital Twin Association e.V., 01002-3-0 Specification of the Asset Administration Shell Part 2: Application Programming Interfaces, 2023, Frankfurt.                                                                                                                                                                                           |
| [25]  | Industrial Digital Twin Association, „01005-3-0-1: Specification of the Asset Administration Shell Part 5: Package File Format (AASX),“ 2024. [Online]. Available: https://industrialdigitaltwin.org/content-hub/aasspecifications/idta-01005-3-0-1_package_file_format_aasx.                                                                              |
| [26]  | Plattform Industrie 4.0, „Beziehungen zwischen I4.0-Komponenten – Verbundkomponenten und intelligente Produktion,“ 2017. [Online]. Available: https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/beziehungen-i40-komponenten.pdf.                                                                                                          |
| [27]  | Plattform Industrie 4.0, „Information Model for Capabilities, Skills & Services,“ 11 2022. [Online]. Available: https://www.plattform-i40.de/IP/Redaktion/DE/Downloads/Publikation/CapabilitiesSkillsServices.pdf?__blob=publicationFile&v=1.                                                                                                              |
| [28]  | ECLASS e.V., „ECLASS-Standard,“ [Online]. Available: https://eclass.eu/eclass-standard/content-suche/search.                                                                                                                                                                                                                                               |
| [29]  | Prostep ivip, „ECAD-Wiki,“ 2023. [Online]. Available: https://ecad-wiki.prostep.org/specifications/vec/v202/component-characteristics/geometric-properties-of-connector-housings-definitions/. [Zugriff am 01 6 2023].                                                                                                                                     |

# <a name="Fussnoten">Fussnoten
