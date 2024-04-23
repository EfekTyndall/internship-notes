# Einführung

- Mein Name ist Martyn Devin Somba. Ich studiere Mechatronik mit der Vertiefung Robotik.
- Von 08.01-28.03.2024 habe ich ein Praktikum bei Daimler Truck AG in Stuttgart absolviert, wo ich meine Kenntnisse in Robotik praktisch anwenden und erweitern konnte.
- Diese Präsentation gibt Einblicke in meine Erfahrungen und das Gelernte während meiner Zeit bei Daimler Truck AG und wie es meine beruflichen Ziele beeinflusst hat.

# Überblick über Daimler Truck AG

- Die Daimler Truck AG ist einer der größten Nutzfahrzeughersteller der Welt mit über 125 Jahren Erfahrung.
- Die Daimler Truck AG beschäftigt mehr als 100000 Mitarbeiter an mehr als 40 Standorten in Nordamerika, Europa, Asien und Lateinamerika.
- Das Portfolio des Unternehmens umfasst eine breite Palette von Lkw und Bussen, mit Marken wie Mercedes-Benz, Freightliner, FUSO, Western Star, Thomas Built Buses, BharatBenz, RIZON und Setra.
- Während des Praktikums wurde ich in das Team "Smart Automation" unter der Abteilung "Technology Management" integriert.
- Die Hauptaufgabe des "Smart Automation"-Teams besteht in der Erforschung und Entwicklung von Konzepten zur Automatisierung und Verbesserung von Fertigungsprozessen unter Verwendung hochentwickelter Technologien wie Robotik, Computer Vision und künstlicher Intelligenz.
- Dies erfolgt in Zusammenarbeit mit Lieferanten, Start-ups und Forschungspartnern in der ARENA2036 der Universität Stuttgart.

# Ziele des Praktikums

Mein persönliches Ziel für dieses Praktikum ist es;

- praktisches Wissen anzuwenden, insbesondere im Bereich der Robotik.
- akademische Fähigkeiten wie Roboterprogrammierung, Computer Vision und maschinelles Lernen, sowie soziale Fähigkeiten, wie Management und Teamarbeit zu entwickeln.
- Einblicke in die Branche zu gewinnen, vor allem in die technologische Entwicklung im Transportsektor.

# Aufgabenstellung

Während meines Praktikums hatte ich vielfältige Aufgaben und die Möglichkeit, an einigen Unternehmensaktivitäten teilzunehmen.

Zu meinen Hauptaufgaben gehörten:

- Teilnahme an der wöchentlichen Teambesprechung, bei der aktuelle Informationen zu Projekten und Aufgaben besprochen werden.
- Einrichtung des lokalen Netzwerks im Arbeitsplatz (ARENA2036) und Sicherstellung, dass alle notwendigen Geräte richtig angeschlossen sind.
- Programmierung und Bedienung von Robotern, insbesondere FANUC-Robotern, sowohl mit Roboguide, der Simulationssoftware als auch mit dem echten Roboter.
- Beteiligung an der Entwicklung von Projekten, die im nächsten Abschnitt näher erläutert werden
- Erstellung von Dokumentationen zu den Projekten und von Anleitungen zur Fehlersuche.
- Durchführung von Tests für einen KI-gestützten Bin-Picking-Roboter, der in Zusammenarbeit von Daimler Truck und Fraunhofer entwickelt wurde. Aus diesem Test habe ich geholfen, einen Key Performance Indicator (KPI) zur Unterstützung von Fraunhofer zu erstellen.
- Ich hatte die Gelegenheit, die LogiMAT zu besuchen, eine führende internationale Fachmesse für Intralogistiklösungen und Prozessmanagement, die mein Verständnis für die Branche erweitert hat.

# Projekte

Ich habe an zwei Projekten mitgearbeitet:

- Das erste ist eine Implementierung eines KI-gestützten Robotersteuerungssystems namens MIRAI, das von Micropsi Industries entwickelt wurde.
- Das zweite ist ein automatisierter Schraubroboter für die Montage von Lkw-Türen, der von einem Bildverarbeitungssystem unterstützt wird, das von Atlas Copco und ISRA Vision entwickelt wurde.

# Implementierung der MIRAI-Robotersteuerung

- Das Ziel dieses Projekts ist die Automatisierung komplexer Montageaufgaben, die eine Hand-Augen-Koordination erfordern, um die Flexibilität der Produktion zu erhöhen.
- Der Anwendungsbereich, in dem diese Technologie getestet wurde, ist die präzise Handhabung von LKW-Schaltern in Halterungen.
- Meine Aufgabe in diesem Projekt war es, MIRAI Skills für diese spezielle Aufgabe zu entwickeln, indem ich ein handgeleitetes Training durchführte.
- Die entwickelten MIRAI Skills wurden dann in das FANUC Roboterprogramm integriert.

# Überblick über MIRAI

- MIRAI ist ein fortschrittliches Roboter-Steuerungssystem, das maschinelles Lernen nutzt und von Micropsi Industries entwickelt wurde.
- Es nutzt intuitives, handgeleitetes Training anstelle der traditionellen, skriptbasierten Programmierung.
- Dieses handgeführte Training wird dann in Form von Videos, den sogenannten "Episodes", gespeichert und mit Hilfe der cloudbasierten Algorithmen von Micropsi Industries in "MIRAI Skills" umgewandelt.
- Diese MIRAI Skills können dynamisch auf visuelle Eingaben von einer Kamera reagieren, ohne dass eine Neuprogrammierung erforderlich ist.

# Hardware Einrichtung

Für diese Implementierung besteht die Hardware aus:

- FANUC CRX-10iA/L Roboter und R-20iB Controller
- MIRAI Controller und Trainingstablett
- Ximea xiQ USB3 Kamera mit Fujinon Objektiv und Ringlicht
- ATI Kraft-/Drehmomentsensor
- Greifer

# Kalibrierung des Werkzeugkoordinatensystems (Tool Frame)

Der Zweck der Tool Frame-Kalibrierung ist es:

- Legt fest, wie das Werkzeug des Roboters mit der Umgebung interagiert, um einen präzisen Betrieb zu gewährleisten.
- Richtet ein dreidimensionales kartesisches Koordinatensystem ein, das um den Werkzeugmittelpunkt (TCP) zentriert ist.
- Ermöglicht es dem Roboter, bei verschiedenen Aufgaben und Werkzeugwechseln mit gleichbleibender Präzision zu arbeiten.

# Kalibrierungstechnik „Die Drei-Punkte-Methode“

Um den Tool Frame für die Schraubenspindel und die Kamera zu kalibrieren, wird die Drei-Punkte-Methode verwendet:

- Das Werkzeug des Roboters wird an einem einzigen bestimmten Punkt positioniert und auf drei verschiedene Orientierungen eingestellt.
- Es wird ein stationäres Werkstück verwendet, das einem Punkt im Raum entspricht und sich im Arbeitsbereich des Roboters befindet.
- Für die Spindel wird das Ende als TCP verwendet; für die Kamera wird der TCP in der Mitte der Kamera positioniert.

Vorgehensweise:

- Der TCP wird mit der Spitze des Werkstücks am Startpunkt ausgerichtet und diese Position wird gespeichert.
- Ähnliche Schritte werden für die beiden folgenden Punkte durchgeführt, wobei unterschiedliche Orientierungen zur genauen Bestimmung des TCP sichergestellt werden.

# Kalibrierung benutzerdefinierter Koordinatensysteme (User Frames)

Der Zweck der User Frame-Kalibrierung ist es:

- Operationen für spezifische Bereiche optimieren und Präzision steigern.
- Anpassungsfähigkeit verbessern für nahtlose Aufgabenübergänge.
- Schnelle Neukalibrierung bei Arbeitsbereichsänderungen für Genauigkeit.
- Synchronisation mit Montagestationen für präzise Abläufe essenziell.
- Vielseitige Aufgabenbewältigung durch anpassbare User Frame-Einstellungen.

# Kalibrierungstechnik „Die Drei-Punkte-Methode“

Ähnlich wie bei der Kalibrierung des Tool Frames wird die Drei-Punkte-Methode angewandt

- Drei Bohrlöcher an jeder Montagestation werden vom Roboter manuell angefahren und dienen als spezifische Interpolationspunkte.
- Die Positionen dieser drei Bohrungen auf der Station werden mit Hilfe der bereits kalibrierten Spindel TCP genau dokumentiert.
- Diese Punkte werden vom Steuerungssystem des Roboters verarbeitet, um die Orientierung und Position des User Frames zu bestimmen und ihn mit dem Basis- oder WELT-Koordinatensystem auszurichten.








