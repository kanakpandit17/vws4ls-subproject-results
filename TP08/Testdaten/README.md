## Testdaten
Dieser Abschnitt beschreibt die für den [Use Case in TP 8](https://github.com/VWS4LS/vws4ls-subproject-results/edit/main/TP08/readme) verwendeten Testdaten.

### OEM-Anforderungen
Der OEM ist mit seinen Anforderungen der Trigger für einen Entwicklungsauftrag beim Tier 1. Für die vereinfachte Demonstration in diesem Projekt sind die Anforderungen eine Liste an autorisierten Entwicklern. Hierfür wurde hier eine Dummy-AAS "**[OEM_SupplierRequirements](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP08/Testdaten/OEM)**" mit dem speziell dafür definierten Submodel "**AuthorizedSuppliers**" erstellt. Dort sind die BPNs der vom OEM autorisierten Business Partner hinterlegt:

![image](https://github.com/user-attachments/assets/a8dfcdf0-5478-4f74-9e28-f9ea3dcdc7e0)

### Aggregierter Digitaler Zwilling 
Nachdem der Tier 1 sowohl Zugriff auf die Anforderungen des OEMs als auch auf die bereitgestellten Angebote der Tier 2 hat, erstellt dieser nun einen aggregierten Digitalen Zwilling mittel der AAS "**[ZusammenbauLeitungssatz](https://github.com/VWS4LS/vws4ls-subproject-results/tree/main/TP08/Testdaten/Tier%201%20(Aggregation))**". Dieser  basiert auf den Submodels des Industry Cores von Catena-X (Details siehe Abschnitt zum Industry Core):
-	[PartTypeInformation](https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main/io.catenax.part_type_information/1.0.0/gen) 
-	[SingleLevelBomAsPlanned](https://github.com/eclipse-tractusx/sldt-semantic-models/tree/main/io.catenax.single_level_bom_as_planned/3.0.0/gen)
  
Das Submodel „PartTypeInformation“ enthält die Catena-X ID (entspricht der Global Asset ID) des aggregierten Digitalen Zwillings sowie die Teilenummer und den Namen.
Die eigentliche Aggregation findet über das Submodel „SingleLevelBomAsPlanned“ statt. Dieses stellt die Stückliste (BoM) dar. Hier erfolgt der Link auf alle Komponenten (Catena-X ID´s der AASen), die im aggregierten Digitalen Zwilling verbaut werden können. Die folgende Abbildung zeigt dies beispielhaft (childItems):

![image](https://github.com/user-attachments/assets/522cf574-0164-499a-8971-0753307d40a9)

### Kostal (Terminals)

**[Kostal_Terminal_MLK_1-2_0,5mm](https://github.com/VWS4LS/vws4ls-subproject-results/blob/main/TP08/Testdaten/Kostal/Kostal_Terminal_MLK_1-2_0%2C5mm)**

SM "PartTypeInformation":
```
"catenaXId":  "91d54b9c-d950-4309-85e0-2de72d4797eb"
"manufacturerPartId": "32140734113 "
"nameAtManufacturer": "Kostal_MLK_1,2_32140734113"
```
**[Kostal_Terminal_PLK_35mm²](https://github.com/VWS4LS/vws4ls-subproject-results/tree/main/TP08/Testdaten/Kostal/Kostal_Terminal_PLK_35mm%C2%B2)**

SM "PartTypeInformation":
```
"catenaXId": "248d03b5-9ce1-489d-9c5d-3d158022e3a5"
"manufacturerPartId": "23124690760"
"nameAtManufacturer": "AAS_MLK_14,5_35"
```

**[Kostal_Terminal_PLK_50mm²](https://github.com/VWS4LS/vws4ls-subproject-results/tree/main/TP08/Testdaten/Kostal/Kostal_Terminal_PLK_50mm%C2%B2)**

SM "PartTypeInformation":
```
"catenaXId": "4bebcdf4-11c2-4ab9-8092-4b6b6761891a"
"manufacturerPartId": "23124690760"
"nameAtManufacturer": "AAS_MLK_14,5_35"
```

### Coroplast (Leitungen)

**[Coroflex_Leitung_0,5mm²]()**

SM "PartTypeInformation":
```
"catenaXId":  "fa120983-4d82-4f94-a06a-c6d648f5bfd9"
"manufacturerPartId": "9-2611"
"nameAtManufacturer": "COROFLEX_FLR31_0_5"'
```

**[Coroflex_Leitung_35mm²]()**

SM	"PartTypeInformation"
```
"catenaXId":  "96be3640-cae3-495d-bd20-0c700fae6ef6"
"manufacturerPartId": "9-2611"
"nameAtManufacturer": "COROFLEX_180HV_35"
```

**[Coroflex_Leitung_50mm²]()**

SM	"PartTypeInformation"
```
"catenaXId": "e907e75a-1b8e-4bef-bc6a-0826ac0f273b"
"manufacturerPartId": "9-2611 / 50"
"nameAtManufacturer": "COROFLEX_9_2611_50"
```
### ARENA2036 (Gehäuse)
**[Kostal_GEHAEUSE_MLK_1-2]()**

SM	"PartTypeInformation"
```
"catenaXId": "18a3e5f8-cf00-491b-b690-d176cb9a5848"
"manufacturerPartId": "987-654-321"
"nameAtManufacturer": "AAS_GEHAEUSE"
```


