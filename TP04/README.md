# TP 4 - Montageprozesse des Leitungssatzes in der Karosserie
## Zielsetzung
Im Teilprojekt 4 "**Montageprozesse des Leitungssatzes in der Karosserie**" wurden Möglichkeiten untersucht, die Montageprozesse beim OEM über Verwaltungsschalen als standardisierte Digitale Zwillinge abzubilden. Dazu wurden die einzelnen Teilprozesse der Montage eines Leitungssatzes in der Fahrzeugkarosserie analysiert, relevante Informationen abgeleitet und semantisch beschrieben, um diese in einem Teilmodell der Verwaltungsschale zu hinterlegen und für die Prozesse automatisiert abrufbar bereitzustellen.

Der Leitungssatz besitzt die Aufgabe, die Endverbraucher innerhalb eines Fahrzeugs miteinander zu verbinden und somit eine gezielte Ansteuerung einzelner Komponenten zu ermöglichen. Er ist ein Produkt, welches eine hohe Varianz in seinen Einzelteilen besitzt, kundespezifisch (Losgröße 1) produziert wird und schwer handzuhaben ist, da er keine eigene Steifigkeit in sich selbst besitzt. 

Das Zielbild war, die automatisierte Montage des Leitungssatzes im Fahrzeug möglichst vollständig zu automatisieren. Das bedeutet, dass alle Informationen zur Bahnplanung, Geometrie etc. semantisch beschrieben, digital bereitgestellt, abgerufen und bei Bedarf aktualisiert werden müssen. Als Startpunkt wurde die Anlieferung der Packtasche inklusive des Leitungssatzes an der Montagezelle beim OEM angenommen.  

Von der Vorgehensweise her wird der Montageprozess in Teilprozesse unterteilt, die in den weiteren Kapiteln einzeln betrachtet und analysiert werden. Dabei soll der Fokus auf notwendige Informationsbedarfe und Fähigkeiten gelegt werden, die für die einzelnen Prozessschritte benötigt und anschließend in einem Submodell der Verwaltungsschale standardisiert werden sollen. 
Für die Vereinfachung des Prozesses werden aufgrund der Komplexität einige Annahmen getroffen, die im folgenden Kapitel erläutert und anschließend in den einzelnen Kapiteln berücksichtigt werden. 
