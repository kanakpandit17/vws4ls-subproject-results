# AP3.4 Proof of Concept
## Zielsetzung
In AP3.4 „Proof of Concept“ wurde basierend auf dem Arbeitspaket 3.3 ein Digitaler Zwilling in einer Simulationsumgebung aufgebaut, der unter Verwendung von OPC UA Dateninhalte und Signalrückmeldungen einen Digitalen Schatten der Originalproduktion abbilden kann.
Dabei wird ein Use Cases anhand der zuvor definierten Modelle dargestellt und an dieser Stelle eine Instanziierung eines Leitungssatzes vorgenommen. Unter Einbezug eines repräsentierenden Unternehmens für jede einzelne Wertschöpfungsstufe wird in jeder Stufe eine Verwaltungsschale mit Daten und Informationen der jeweiligen Wertschöpfungsstufe generiert und in der Kette an das nachfolgende Glied übermittelt. Die Verwaltungsschale wird in die nachfolgende Systemlandschaft importiert und relevante Daten für die Produktion in dieser Stufe verarbeitet. Es entsteht eine angereicherte Verwaltungsschale für die nächste Stufe, in der wiederum die Daten und Informationen zunächst importiert, verarbeitet und schließlich mit den eigenen Daten nochmals angereichert werden. Dieser Vorgang wiederholt sich bis zur letzten Stufe (OEM), in der die VWS in das Endprodukt (Fahrzeug) einfließt.
## Datamapping Service
Quellsysteme liefern Daten unterschiedlich strukturiert, d.h. es kann sich um un- bzw. semistrukturierte Daten handeln. Für die zugrunde liegende Datenstruktur in der VWS wurde daher ein Data Mapping Service entwickelt, der die Kompatibilität zwischen bestehenden Systemlandschaften (Brownfield) und der VWS ermöglicht, um in beide Richtungen kommunizieren zu können. Um die Konvertierung zu gewährleisten, ist eine Validierung zwingend erforderlich, welche in verschiedenen Schritten der Datenerhebung und Datenverarbeitung durchgeführt wird. Abbildung 1 zeigt die schematische Darstellung des Data Mapping Service.

 ![image](https://github.com/user-attachments/assets/d5c950f7-0df2-4f92-8c27-f32db6ed927b)

Abbildung 1: Exemplarische Darstellung des Data Mapping Services mit VWS als Zielsystem

Die Ziele des generischen Ansatzes für Data Mapping mit anschließender Validierung waren:

-	Konvertierung von un- bzw. semistrukturierten Daten
-	Unterbrechungen im Datenfluss verhindern
-	Strukturelle Veränderungen erkennen
-	Vermeidung unvollständiger Daten
-	Steigerung der Datenqualität
-	Reduzierung des manuellen Aufwands

Der Data Mapping Service nutzt die [Eclipse BaSyx DataBridge](https://github.com/eclipse-basyx/basyx-databridge), um Daten von einer distinkten Datenquelle an einen oder mehrere Asset Administration Shell Endpunkt(e) zu transferieren. 
Die Funktionalität ermöglicht es Daten aus einer einzelnen Datenquelle auf mehrere Datensenken zu schreiben. Das beinhaltet ebenfalls die Zuordnung der jeweiligen Transformationsschritte innerhalb der Route zwischen Quelle und Senke, um komplexe Datenobjekte herunterzubrechen.

Die Databridge wurde wie folgt beschrieben mittels statischer Konfigurationsdateien konfiguriert. 

### Konfiguration der Route – Fall 1 (Keine Datensenkenzuordnung)
Datei: routes.json
```
[
	{
		"datasource": "mqttSource",
		"transformers": [
			"transformer1",
			"transformer2",
			"transformer3"
		],
		"datasinks": [
			"sink1",
			"sink2",
			"sink3"		],
		"trigger": "event"
	}
]
```
Das oben aufgeführte Beispiel zeigt die Konfiguration einer Route in der routes.json, in welcher ein Datenpunkt der Quelle datasource auf drei Datensenken (`sink1`, `sink2`, `sink3`) zugewiesen wird. Dabei werden in diesem Fall immer alle drei hier konfigurierten Transformatoren (`transformer1`, `transformer2`, `transformer3`) durchlaufen.

![image](https://github.com/user-attachments/assets/c15ec80d-8cb8-492d-9bfb-c2c1ab5f8d71)

### Konfiguration der Route – Fall 2 (Mit Datensenkenzuordnung)
Das nachfolgend aufgeführte Beispiel zeigt die Konfiguration einer Route in der routes.json, in welcher ein Datenpunkt der Quelle `datasource` auf drei Datensenken (`sink1`, `sink2`, `sink3`) zugewiesen wird. Dabei wird im Unterschied zum vorangegangenen Beispiel nun für jede Senke eine Liste an zu durchlaufenden Transformatoren angegeben. Im Fall von `sink3` wären dies z.B. `transformer2` und `transformer3`.

Datei: routes.json
```
[
	{
		"datasource": "mqttSource",
		"transformers": [
			"transformer1",
			"transformer2",
			"transformer3"
		],
		"datasinks": [
			"sink1",
			"sink2",
			"sink3"
		],
		"datasinkMappingConfiguration":
		{
			"sink1": ["transformer1"],
			"sink2": ["transformer2"],
			"sink3": ["transformer2", "transformer3"]
		},
		"trigger": "event"
	}
]
```

![image](https://github.com/user-attachments/assets/c23b9637-7bac-48c0-a547-6ce4197191af)

**Randbedingungen**
1. Wurden Routen mit Datensenken (`datasinks`) definiert, die nicht Teil der Datensenkenzuordnung (`datasinkMappingConfiguration`) sind, so durchlaufen diese keine Transformatoren und werden somit nicht innerhalb der Route modifiziert.
2. Wurden mehr Transformatoren definiert, als in der Datensenkenzuordnung (`datasinkMapping-Configuration`) verwendet werden, so werden diese ignoriert.

## Integration in Demonstrator
- Die Ergebnisse des Data Mapping Service wurden in den Demonstrator des Projektes integriert werden ([TP9](TP09))
- Der Demonstrator beinhaltet getestete Fälle für ein Data Mapping mit anschließender Validierung zu Demonstrationszwecken

![image](https://github.com/user-attachments/assets/32086f67-831a-438d-9124-603379948958)
  
Als Arbeitspaketergebnis wurde der Demonstrator, der Industrie 4.0 Produktionsprozesse mit deren Datenflüssen repräsentiert, aufgebaut und im vollem Funktionsumfang gemäß der Anforderungen ausgeführt.

## Ablaufsteuerung
- TODO: IESE-Ergebnisse
