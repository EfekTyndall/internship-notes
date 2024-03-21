Das Hauptziel dieses Projekts bestand darin, die Effizienz und Genauigkeit der Montagelinie für LKW-Türen zu verbessern. Der Ansatz umfasste die Implementierung eines automatischen Schraubsystems für die Montage von Lkw-Türen, wobei Robotertechnologie eingesetzt wurde, um die Produktivität und die Montagepräzision zu steigern, die manuelle Arbeit zu minimieren und die menschlichen Ressourcen auf Aufgaben zu verlagern, die höhere kognitive Fähigkeiten erfordern. Diese Initiative war strategisch angelegt, um den Produktionsdurchsatz zu erhöhen und eine gleichbleibende Qualität zu gewährleisten, wobei der Schwerpunkt auf der Optimierung der Qualitätskontrolle und der betrieblichen Effizienz lag.

# Operativer Arbeitsablauf

Das System steigert die Effizienz durch eine Zwei-Stationen-Konfiguration. Zunächst werden zwei Montagestationen neben dem Roboter eingerichtet, um Lkw-Türkomponenten für den Schraubvorgang zu sichern. Der Bediener positioniert eine Türkomponente an einer Station und löst den Schraubvorgang mit einer einfachen Steuerung aus, die eine nahtlose Interaktion zwischen Mensch und Roboter ermöglicht. Nach der Aktivierung führt der Roboter die Verschraubung mit hoher Präzision und Konsistenz aus. Da der Roboter auf der einen Seite arbeitet, kann der Bediener das nachfolgende Bauteil an der anderen Station vorbereiten, was einen ununterbrochenen Arbeitsablauf gewährleistet. Sobald der Roboter die Schraubaufgabe beendet hat, wird das montierte Bauteil entnommen, und der Zyklus beginnt mit einem neuen Teil erneut.

# Systemkomponenten

Das System umfasst Schlüsselkomponenten für eine nahtlose Funktionalität:

- **FANUC CRX10iA/L kollaborativer Roboter:**
    
    - **Roboter-Controller:** Steuert die Bewegungen und Aufgaben des Roboters mit Hilfe einer hochentwickelten Software.
    - **Teach Pendant:** Bietet eine benutzerfreundliche Schnittstelle für die Roboterprogrammierung und -bedienung.
- **Atlas Copco & ISRA Vision Verschraubungs- und Vision-System:**
    
    - **Benutzerschnittstelle:** Der Assembly Control Node (ACN) von Atlas Copco ermöglicht eine einfache Interaktion und Beobachtung des Systems.
    - **Automatisierungsinfrastruktur:** Die Automation Control Box (ACB) von Atlas Copco gewährleistet eine nahtlose Integration der Systemkomponenten.
    - **Visuelle Führung:** ISRA Vision bietet Kamera- und Bildverarbeitungstechnologie für eine präzise Schraubenplatzierung durch Echtzeit-Bildanalyse.
- **Schraubenzuführungssystem:**
    
    - **Fastening Tool:** Besteht aus einer Schraubenspindel und einer Zuführeinheit, die dem Roboter kontinuierlich Schrauben zuführt.
    - **Schraubenzuführungsmechanismus:** Verwendet Luftdruck, um Schrauben effizient von der Zuführungseinheit zur Spindel zu befördern, wodurch eine gleichmäßige Schraubenzufuhr für die Befestigung gewährleistet wird.
- **Sicherheitsmechanik:**
    
    - **Überwachungssystem:** Verwendet speicherprogrammierbare Steuerungen (PLCs) und Sensoren, um die Sicherheit des Bedieners zu gewährleisten.
- **Montagestationen:**
    
    - **Stationsaufbau:** Verfügt über zwei Stationen zur sicheren Aufnahme von linken und rechten Türkomponenten.
    - **Haltemechanismus:** Ausgestattet mit einem Hebel und einem Halter, um die Komponente während des Schraubvorgangs sicher zu klemmen.
    - **Pneumatikzylinder:** Verwendet einen Pneumatikzylinder für eine präzise Hebelbetätigung, die ein sicheres Einspannen der Komponenten gewährleistet.
    - **Wegeventil:** Verwendet ein Magnetventil zur präzisen Steuerung der Bewegungen des Pneumatikzylinders.

Beide Montagestationen sind mit Türkomponenten ausgestattet, wobei wichtige Werkzeuge wie die Schraubspindel und die ISRA Vision-Kamera am Roboterflansch montiert sind. Das ACN und das Teach Pendant sind für einen einfachen Systemzugang und eine einfache Überwachung bequem an der Robotergrundvorrichtung angebracht.

# Kalibrierung des Werkzeugkoordinatensystems (Tool Frame)

Die Kalibrierung des Werkzeugkoordinatensystems (Tool Frame) ist von entscheidender Bedeutung für Roboteraufgaben, die hohe Präzision erfordern, wie z. B. Schrauben oder kameragestütztes Positionieren. Das Tool Frame ist von entscheidender Bedeutung, da es die Interaktion zwischen dem Werkzeug des Roboters und seiner Umgebung definiert und präzise Bewegungen und Operationen garantiert.

Diese Kalibrierung legt ein dreidimensionales kartesisches Koordinatensystem fest, das auf den Tool Center Point (TCP) zentriert ist, der für die genaue Positionierung und Ausrichtung des Werkzeugs in Bezug auf den Roboter unerlässlich ist. Der TCP dient als Referenznullpunkt und stellt sicher, dass der Roboter bei Aufgaben, die exakte Bewegungen erfordern, konsistent arbeitet. Durch die Möglichkeit, mehrere Tool Frames einzustellen und zu definieren, erhöht diese Kalibrierung nicht nur die Genauigkeit des Roboters, sondern auch seine Anpassungsfähigkeit, was einen schnellen Werkzeugwechsel und die Ausführung verschiedener Aufgaben erleichtert.

## Kalibrierungstechnik: Die "Drei-Punkte-Methode"

Die "Drei-Punkte-Methode" ist eine effektive Strategie zur Kalibrierung von Tool Frames, die besonders dann von Vorteil ist, wenn die genauen Koordinaten des TCP (Tool Center Point) nicht unmittelbar verfügbar sind. Dieser Ansatz ist von unschätzbarem Wert für die Konfiguration von Tool Frames für verschiedene Werkzeuge, einschließlich der Schraubenspindel und der Kamera, und gewährleistet einen präzisen und konsistenten Werkzeugbetrieb.


**Vorgehensweise**:

1. **Bezugspunkt und Orientierungen**: Das Werkzeug des Roboters wird an einem einzigen bestimmten Punkt positioniert und auf drei verschiedene Orientierungen eingestellt. Dieser Punkt und die verschiedenen Orientierungen dienen als Grundlage für die Bestimmung der genauen Position des TCP.
2. **Fokus auf Orientierung**: Die Bestimmung der Orientierung des TCP steht im Vordergrund, wobei die Position des Werkzeugs statisch gehalten wird.
3. **Notwendige Hilfsmittel**: Es wird ein stationäres Messgerät verwendet, vorzugsweise eines, das einem Punkt im Raum entspricht und sich im Arbeitsbereich des Roboters befindet. Eine Messspitze, die den TCP darstellt, wird an dem Werkzeug angebracht. Für die Spindel wird das Ende als TCP verwendet; für die Kamera wird der TCP in der Mitte des Sichtbereichs positioniert.
4. **Bestimmen des TCP**: Der Roboter wird manuell an den gewünschten Punkt gefahren, und seine Position wird in drei verschiedenen Orientierungen erfasst. Auf diese Weise werden die dreidimensionalen Koordinaten des TCP in Bezug auf die Basis des Roboters genau bestimmt.

**Kalibrierung mit dem Teach Pendant**:

- Das Tool Frame wird auf dem Teach Pendant über MENU > SETUP > Frames > [OTHER] > Tool Frame eingestellt.
- Ein nicht belegter Eintrag wird ausgewählt (z. B. Tool Frame 3 für die Spindel, Tool Frame 4 für die Kamera) und DETAIL wird ausgewählt.
- Die Dreipunktmethode wird durch Auswahl von [METHODE] > Dreipunkt eingeleitet.
- Der TCP wird mit der Spitze des Messgeräts am Anfangspunkt ausgerichtet, und diese Position wird durch Drücken von SHIFT gefolgt von RECORD gespeichert.
- Ähnliche Schritte werden für die beiden folgenden Punkte ausgeführt, wobei unterschiedliche Orientierungen sichergestellt werden, um den TCP genau zu bestimmen.

Der Schlüssel zu diesem Kalibrierungsprozess ist die präzise Orientierung des TCP mit dem Messgerät an jedem Punkt, wobei verschiedene Orientierungen zur Erhöhung der Präzision berücksichtigt werden. Sobald der Vorgang abgeschlossen ist, berechnet und aktualisiert das System automatisch das Koordinatensystem des Werkzeugs und zeigt die x-, y- und z-Koordinaten an, was die erfolgreiche Kalibrierung bestätigt.

# Kalibrierung benutzerdefinierter Koordinatensysteme (User Frames)

Die Kalibrierung von benutzerdefinierten Koordinatensystemen (User Frames) ist wichtig, um die Interaktion des Roboters in verschiedenen Bereichen seiner Betriebsumgebung anzupassen. Diese Frames passen die räumlichen Bezugspunkte des Roboters an bestimmte Aufgaben oder Arbeitsbereiche an, um seine Anpassungsfähigkeit und Effizienz zu verbessern.

User Frames verändern die räumlichen Bezugspunkte des Roboters und richten seine Aktivitäten auf bestimmte Bereiche oder Aufgaben im Arbeitsraum aus. Die Möglichkeit, mehrere User Frames zu setzen, erhöht die Flexibilität des Roboters und erleichtert nahtlose Übergänge zwischen verschiedenen Aufgaben oder Werkzeugen. Im Bereich der Programmierung dienen User Frames als Basis für alle Positionsdaten und stellen sicher, dass die Bewegungen des Roboters mit der vordefinierten Arbeitsraumkonfiguration übereinstimmen. Darüber hinaus ermöglichen User Frames eine schnelle Neukalibrierung als Reaktion auf Änderungen im Arbeitsbereich, wie z. B. das Verschieben von Vorrichtungen, wobei die Genauigkeit mit den vordefinierten Frames erhalten bleibt.

Für diese Initiative ist die Einrichtung von User Frames sowohl für die linke als auch für die rechte Montagestation entscheidend, um eine präzise Synchronisierung mit der Arbeitsumgebung zu gewährleisten.

## Kalibrierungstechnik: Die "Drei-Punkt-Methode"

Die "Drei-Punkte-Methode" wird auch für die Kalibrierung von User Frames verwendet, ähnlich wie bei den Tool Frame-Einstellungen. Dieser Ansatz bestimmt die Position und Orientierung von User Frames durch die Identifizierung von drei Referenzpunkten an jeder Montagestation und bietet einen klaren und präzisen räumlichen Rahmen für die Operationen des Roboters in bestimmten Bereichen des Arbeitsbereichs.
**Vorgehensweise**:

1. **Auswahl der Referenzpunkte**: Drei Bohrlöcher an jeder Montagestation werden vom Roboter manuell angefahren und dienen als spezifische Interpolationspunkte.
2. **Dokumentation der Punkte**: Die Positionen dieser drei Bohrungen auf der Station werden mit einer Messspitze, die mit einem kalibrierten Tool Frame korrespondiert, genau dokumentiert.
3. **Berechnung des User Frame**: Diese Punkte werden vom Steuerungssystem des Roboters verarbeitet, um die Orientierung und Lage des User Frame zu bestimmen und ihn am Basis- oder WELT-Koordinatensystem auszurichten.

**Konfiguration der User Frames mit dem Teach Pendant**:

- Das Tool Frame für die Messspitze, z. B. Tool Frame 4 für die Schraubenspindel, wird aktiviert.
- Der Zugriff auf die User Frame-Einstellungen erfolgt über das Teach Pendant, indem Sie durch MENU > SETUP > Frames > [OTHER] > User Frame navigieren.
- Ein verfügbarer Speicherplatz für das neue User Frame (z. B. User Frame 40 für die linke Station und User Frame 45 für die rechte Station) wird ausgewählt, und DETAIL wird ausgewählt.
- Die Kalibrierung mit der Dreipunktmethode wird durch Auswahl von [METHOD] > Dreipunkt eingeleitet.

**Dokumentation der Interpolationspunkte**:

- **Orientierung des Ursprungspunkts**: Der Ursprung des User Frames wird durch die Anpassung der Messspitze des Roboters an den ausgewählten Ursprungspunkt auf der Montagestation festgelegt, und diese Position wird aufgezeichnet.
- **Punkt in X-Achsen-Richtung**: Die Messspitze wird auf einen Punkt entlang der X-Achse vom Ursprung aus verschoben, und diese Position wird dokumentiert.
- **Punkt in Richtung der Y-Achse**: Die Messspitze wird vom Ursprung oder der aktuellen Position des Roboters zu einem bestimmten Punkt entlang der y-Achse verschoben, und diese Position wird registriert.

Die anfängliche "Ursprungspunkt-Orientierung" legt den Nullpunkt für den User Frame fest, wobei die folgenden Punkte die positiven Richtungen entlang der x- und y-Achse angeben. Auf diese Weise wird sichergestellt, dass der Arbeitsbereich des Roboters genau mit dem tatsächlichen Layout der Montagestationen korreliert, wodurch die Genauigkeit und Effektivität seiner Aufgaben verbessert wird.

# Punkt-Teaching

Nach der Kalibrierung des Tool Frame und des User Frame ist der nächste wichtige Schritt das "Point Teaching". In dieser Phase werden dem Roboter genaue Anweisungen zu den entscheidenden Punkten für die Schraubaufgabe an LKW-Türen gegeben. Dazu gehören die genauen Positionen der Schraubenlöcher sowie strategisch festgelegte Offset-Punkte, um mögliche Kollisionen während des Vorgangs zu vermeiden. Zusätzlich werden weitere wichtige Punkte, die den Schraubvorgang unterstützen, identifiziert und dem Roboter beigebracht.

## Schritte des Punkt-Teachings:

1. **Lage der Schraubenlöcher**: Die Schraubenspindel des Roboters wird von einem Bediener manuell in der Nähe der vorgesehenen Schraubenlöcher an den LKW-Türen positioniert. In dieser Anfangsphase ist keine exakte Präzision erforderlich; eine grobe Positionierung ist ausreichend.
    
2. **Positionsdokumentation**: Sobald die Spindelspitze auf ein Schraubenloch positioniert ist, wird diese Position im System des Roboters als "Positionsregister" aufgezeichnet. Diese Register dienen als digitale Landmarken, die die Programmierung des Roboters erleichtern, indem sie eine schnelle Navigation zu diesen vorbestimmten Punkten über ihre jeweiligen Register ermöglichen.
    
3. **Einrichtung von Offset-Punkten**: Offset-Punkte werden festgelegt, um die betriebliche Effizienz und Sicherheit zu erhöhen. Diese Punkte werden strategisch ausgewählt, um die Bewegungen des Roboters zu lenken und so mögliche Kollisionen mit den LKW-Türen oder anderen Teilen der Montagestation zu vermeiden.
    
4. **Zusätzliche Spezifikation der Punkte**: Andere wichtige Punkte, die für den Schraubprozess von Bedeutung sind, wie z. B. Startpositionen, Vorpositionen oder bestimmte Arbeitswege, werden festgelegt, und der Roboter wird entsprechend instruiert.


In der Phase des Point-Teachings steht nicht die exakte Positionierung der Schraublöcher im Vordergrund, da das ISRA Vision System später eine wichtige Rolle spielt. Dieses System erkennt dynamisch die exakten Positionen der Schraubenlöcher und stellt sich darauf ein, so dass der Roboter eventuelle Abweichungen von den eingelernten Positionen korrigieren kann, wodurch eine genaue Schraubenplatzierung auch bei leichten Abweichungen in der Türausrichtung oder der Positionierung der Löcher gewährleistet ist.

Es ist wichtig zu beachten, dass die in den Positionsregistern gespeicherten Positionen relativ zu den aktiven Tool- und User Frames sind. Daher ist es von entscheidender Bedeutung, dass während dieses Lernprozesses die richtigen Rahmen ausgewählt werden, um Konsistenz und Genauigkeit zu gewährleisten.

## Punkte für die linke Seite der Tür

Für die linke Seitentür werden bestimmte Punkte mit Tool Frame 4 (für die Schraubenspindel) und User Frame 40 (für die linke Montagestation) programmiert:

- **PR[11] - PR[18]**: In diesen Registern werden die Positionen für die Schraubenpositionen an der linken Tür gespeichert, wobei jedes Register von PR[11] bis PR[18] einer bestimmten Schraube zugeordnet ist. Sie sind von Schraube_11_LH bis Schraube_18_LH beschriftet, so dass jedes Positionsregister auf eine bestimmte Schraubenposition an der Tür ausgerichtet ist.
    
- **PR[2] = Offset_Z_PR18lh**: Dieses Register wird als Offset-Punkt bezeichnet, um einen ausreichenden räumlichen Abstand zu gewährleisten und mögliche Kollisionen zu vermeiden, insbesondere im Bereich zwischen den Schrauben 17 und 18 an der linken Tür.

## Punkte für die rechte Seite der Tür
  
Für die rechte Seitentür werden die Punkte mit Hilfe von Tool Frame 4 (für die Schraubenspindel) und User Frame 45 (für die rechte Montagestation) definiert:

- **PR[21] - PR[28]**: Diese Positionsregister, von PR[21] bis PR[28], enthalten die Positionen für die Schraubenplatzierung an der rechten Tür. Jedes Register entspricht einer bestimmten Schraube, bezeichnet als Schraube_11_RH bis Schraube_18_RH, so dass jede Position mit einer bestimmten Schraubenposition an der Tür ausgerichtet ist.
    
- **PR[1] = Offset_Z_PR18rh**: PR[1] wird als Offset-Punkt zugewiesen, um den nötigen Spielraum zu schaffen, eine reibungslose Bewegung zu gewährleisten und mögliche Kollisionen zwischen den Schrauben 17 und 18 auf der rechten Seite zu vermeiden.

# ISRA Vision System

Das ISRA Vision System ist entscheidend für die dynamische Lokalisierung und Anpassung an die exakte Position der Schraublöcher. Es nimmt vor jedem Schraubvorgang ein Bild auf, um den Abstand zwischen dem Tool Center Point (TCP) und dem Loch zu bestimmen. Diese Integration der Rückmeldung des Bildverarbeitungssystems ermöglicht es dem Roboter, Abweichungen von den ursprünglich programmierten Positionen selbstständig auszugleichen und eine präzise Schraubenplatzierung selbst bei geringen Abweichungen in der Positionierung der Türen oder der Schraubenlöcher zu gewährleisten.

Die Kamera, die für das Bildverarbeitungssystem wichtig ist, wird auf dem Flansch der Montageplatte neben der Spindel montiert. Um eine optimale Leistung zu erzielen, wird die Kamera durch den Assembly Control Node (ACN) mittels eines photogrammetrischen Ansatzes kalibriert. Dabei werden Bilder eines bekannten Musters aufgenommen, wobei die Kamera die Verschraubungspunkte anhand der Konturen der Löcher identifiziert. Das System berechnet dann die Position des Lochs und übermittelt diese Information an den Roboter-Controller, entweder als absolute Position oder relativ zum TCP.

Um eine genaue Erkennung zu gewährleisten, wird das Bildverarbeitungssystem darauf trainiert, die Konturen jedes Schraubenlochs zu erkennen, wobei das Bild und die Konturen jedes Lochs als "Produkt" im ISRA Vision System gespeichert werden.

Wenn das Bildverarbeitungssystem Positionsdaten an den Roboter-Controller weitergibt, werden diese Koordinaten in einem Positionsregister zur Verwendung im Programm gespeichert. Wenn die Daten eine Korrektur des TCP darstellen, wird der Roboter angewiesen, sich auf diese Koordinaten als Offset von der vorgegebenen Position einzustellen. Bei jeder Schraubaufgabe positioniert sich der Roboter zunächst am Bildaufnahmepunkt (der während des Punkt-Teachings festgelegt wurde), nimmt etwa eine Sekunde lang ein Bild auf und justiert dann seine Position auf der Grundlage der berechneten x- und y-Korrekturen relativ zum Koordinatensystem des Werkzeugs. Nach dieser Anpassung fährt der Roboter die neue Position an und bewegt sich in der positiven Z-Richtung des Werkzeugs, um mit dem Schrauben zu beginnen.