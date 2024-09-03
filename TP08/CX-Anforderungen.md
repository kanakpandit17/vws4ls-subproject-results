## Catena-X Anforderungen an die VWS des Leitungssatzes
Für die Modellierung der Digitalen Zwillinge wurden im Projekt VWS4LS standardisierte Submodelltemplates der IDTA verwendet. 

Catena-X ist hauptsächlich Use-Case getrieben. Die Use Cases beschreiben ihre Anforderungen an Submodels in sog. "Aspektmodellen". Möchte man an einem Use Case von Catena-X teilnehmen, müssen die jeweiligen [Catena-X-Standards](https://catena-x.net/de/angebote-standards/catena-x-standards) eingehalten werden. Der Standardisierungsprozess wird vom Catena-X Verein vorgenommen.

Beide Modellierungskonzepte zielen darauf ab, Daten und Prozesse innerhalb eines Ökosystems zu standardisieren und damit die Interoperabilität und den Datenaustausch zwischen verschiedenen Akteuren und Systemen zu gewährleisten.

Im Folgenden gilt es daher zu klären, welche Unterschiede sich zwischen den IDTA-Submodellen und den Catena-X-Aspektmodellen ergeben und wie diese für eine Anwendung in Catena-X angepasst werden müssen.

### Catena-X Aspektmodelle
Catena-X beschreibt das Konzept der "[Aspektmodelle](https://catena-x.net/fileadmin/user_upload/Standard-Bibliothek/Archiv/8_PC_Semantics_v2.1/SEM-002_BAMM_PlatformCapabilitySemantics_v2.1.pdf)", um domänenspezifische Sichten oder Aspekte eines digitalen Zwillings zu definieren, die für verschiedene Anwendungsfälle innerhalb des Catena-X-Ökosystems wesentlich sind. Aspektmodelle bieten eine strukturierte Möglichkeit zur Erfassung spezifischer Geschäftsprozesse und Datenanforderungen.

Um ein Datenmodell zu spezifizieren, wird das [Semantic Aspect Meta Model (SAMM)](https://eclipse-esmf.github.io/samm-specification/2.1.0/index.html) verwendet, welches unter Verwendung des Resource Description Format (RDF, [rdf11]) und der Terse RDF Triple Language Syntax (TTL, [turtle]) spezifiziert, zusammen mit Validierungsregeln in der Shapes Constraint Langu-age (SHACL, [shacl]). Aspektmodelle werden ebenfalls in RDF/Turtle spezifiziert, wobei die SAMM-Semantik befolgt wird. 

Abbildung  zeigt beispielhaft die grafische Darstellung des Aspektmodells „PartTypeInformation“. Dafür kann der [Aspect Model Editor](https://eclipse-esmf.github.io/ame-guide/introduction.html) verwendet werden  oder die html-Datei des semantischen Modells aus dem GitHub Repository [eclipse-tractusx](https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main)  geöffnet werden. In der folgenden Abbildung sieht man das entsprechende JSON dazu.

 ![image](https://github.com/user-attachments/assets/13f17433-b75b-473e-8f90-22e603706a1d)
 
Abbildung: Grafische Darstellung des Aspektmodells PartTypeInformation.ttl
 
![image](https://github.com/user-attachments/assets/9d7bc065-bdb2-45bc-83c8-7eb16d45d89b)

Abbildung: Eigenschaften eines Submodells als JSON

### IDTA Submodelle
Die IDTA verwendet "[Submodel Templates](https://industrialdigitaltwin.org/en/content-hub/submodels)", um die Darstellung von Informationen innerhalb einer Asset Administration Shell (AAS), einer digitalen Darstellung von Assets, zu standardisieren. Das Submodel-Konzept der IDTA ist breiter angelegt, um verschiedene Industriebereiche abzudecken. Die Templates definieren spezifische Datenstrukturen und Semantiken für verschiedene Arten von Informationen (z. B. technische Daten, Wartungspläne), wodurch der Austausch und die Interpretation von Daten über verschiedene Plattformen und Branchen hinweg erleichtert wird. Die Schablonen sollen die Interoperabilität erleichtern, indem sie einen gemeinsamen Rahmen bieten, der an die verschiedenen industriellen Bedürfnisse angepasst werden kann. Alle registrierten AAS Submodel Templates werden auf der [IDTA-Website](https://industrialdigitaltwin.org/en/content-hub/submodels) gelistet und im [IDTA-Github](https://github.com/admin-shell-io/submodel-templates/tree/main/published) bereitgestellt.

###	Verwendung von Submodel Templates der IDTA in Catena-X
Catena-X schreibt dazu:
> “In Catena-X the semantics of a Submodel is described via an Aspect Model conformant to standard CX-0003, preferrable by using standardized properties conformant to standard CX-0044.”

Und der Catena-X Standard [CX-0003](https://catenax-ev.github.io/docs/next/standards/CX-0003-SAMMSemanticAspectMetaModel) definiert: 
> “Every aspect model released or standardized in Catena-X MUST be maintained in Tractus-X - SLDT Semantic Models.”

> “Every aspect model in Tractus-X - SLDT Semantic Models that has the status "released" or "standardized" MUST be validated without errors against the Semantic Aspect Meta Model […].”

>	“Every aspect of a digital twin registered in a digital twin registry (see standard CX-0002) accessible in the Catena-X data space MUST have a semantic description (semantic ID) that is con-formant to the unique identifier of the SAMM aspect model associated to it.”

**Wenn das Projekt VWS4LS einen eigenen Use Case für Catena-X definieren möchte, sollten die verwendeten Submodelle in Catena-X gemäß des Standardisierungsprozesses standardisiert werden. Dann müssen diese dem Standard CX-0003 folgen (s.o.). Für den Demonstrationszweck können die VWS4LS Submodelle für diesen Use Case technisch übertragen werden, entsprechen aber (außer dem Submodel „Nameplate“) nicht den Catena-X-Spezifikationen und können so nicht von Catena-X Lösungen interpretiert werden.**

### Digitale Zwillinge und AAS in Catena-X 
In Catena-X basieren die APIs auf den Spezifikationen der Asset Administration Shell (AAS) Spezifikationen der IDTA . Die Besonderheit von Catena-X ist es, dass dort nicht auf die AAS an sich zugegriffen wird, sondern direkt auf die Submodels. Die Registrierung eines Digitalen Zwillings in der DTR entspricht einer „Erstellung“ eines Digitalen Zwillings. Das JSON-Beispiel im Digital Twin KIT verdeutlicht das. Die AAS an sich wird nicht angesprochen. In der DTR steht lediglich ein AAS-Descriptor. Dieser enthält wiederum die verschiedenen Submodel-Descriptors mit den entsprechenden Endpunkten.

 ![image](https://github.com/user-attachments/assets/8795d7ff-1a12-41a0-ad8e-8abd3bd8ed9b)
 
Abbildung: [Tractus-X Digital Twin Registry - Asset Administration Shell Domain Model](https://github.com/eclipse-tractusx/sldt-digital-twin-registry/tree/main/docs#asset-administration-shell-domain-model)

Im [Digital Twin KIT](https://eclipse-tractusx.github.io/docs-kits/kits/Digital%20Twin%20Kit/Software%20Development%20View/dt-kit-software-development-view#submodel-as-edc-data-asset) von Tractus-X wird zwar ausgeführt , dass ein Data Provider ein Daten Asset per Submodel oder Bundle erstellen kann, gleichzeitig wird aber ausgesagt:
>“There is no normative guidance on how to register multiple Submodels bundled together yet. These bundles may include all the Submodels of a specific semanticId, all Submodels of an asset or any other arbitrary quality. This may be added to [CX-0002](https://catenax-ev.github.io/docs/standards/CX-0002-DigitalTwinsInCatenaX) in future iterations.“  

**Als Konsequenz werden auch für den Demonstrator die Submodels als einzelne Assets angelegt.**

####	Der Industry Core von Catena-X
Um zu verhindern, dass jeder Use-Case in Catena-X seine Digitalen Zwillinge (Teile/Komponenten) unterschiedlich beschreibt, wurde der Industry Core ins Leben gerufen. „Core“ deshalb, weil er den Kern der Industrie, nämlich die Teile/Komponenten betrifft.

Catena-X schreibt dazu:
-	Der Industry Core ist eine gemeinsame [semantische] Basis für Use Cases, die digitale Zwillinge und Aspektmodelle in Catena-X nutzen. 
-	Der Industry Core beschreibt ein physisches Teil, eine Komponente oder ein Material auf Typ- und/oder Instanzebene, macht es im Netz identifizierbar und auffindbar und ermöglicht die Navi-gation über mehrere Ebenen hinweg.
  
Der Industry Core hat aktuell zwei Standards definiert. Darin wird einmal die Beschreibung eines Teils auf Typ-Ebene [(CX-0126)](https://catenax-ev.github.io/docs/next/standards/CX-0126-IndustryCorePartType) und einmal auf Instanz-Ebene [(CX-0127)](https://catenax-ev.github.io/docs/next/standards/CX-0127-IndustryCorePartInstance) festgelegt sowie jeweils die Verbindung zu „Kind-Teilen“, also Komponenten, die verbaut wurden.

Zusätzlich müssen folgende Punkte aus dem Standard CX-0126 beachtet werden:
>	“The asset's globalAssetId MUST be equal to the unique id used in Catena-X.”

>	“The following specific asset IDs  not marked as optional MUST be available when registering a digital twin or when adding the above mentioned submodels to an existing twin for a part type in order to allow discovery.”

Da auch im Projekt VWS4LS physikalische Komponenten betrachtet werden (bspw. Leitungen und Stecker), ist es zu empfehlen, diese mittels der Industry Core Standards zu beschreiben, falls eine Teilnahme an Catena-X angestrebt wird.

**Für den Demonstrator werden daher die Digitalen Zwillinge mit den Submodellen „PartTypeInformation“ und „SingleLevelBomAsPlanned“ ergänzt.**

 
