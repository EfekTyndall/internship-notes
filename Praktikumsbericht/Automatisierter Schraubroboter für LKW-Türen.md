Das Hauptziel dieses Projekts bestand darin, die Effizienz und Genauigkeit der Montagelinie für LKW-Türen zu verbessern. Der Ansatz umfasste die Implementierung eines automatischen Schraubsystems für die Montage von Lkw-Türen, wobei Robotertechnologie eingesetzt wurde, um die Produktivität und die Montagepräzision zu steigern, die manuelle Arbeit zu minimieren und die menschlichen Ressourcen auf Aufgaben zu verlagern, die höhere kognitive Fähigkeiten erfordern. Diese Initiative war strategisch angelegt, um den Produktionsdurchsatz zu erhöhen und eine gleichbleibende Qualität zu gewährleisten, wobei der Schwerpunkt auf der Optimierung der Qualitätskontrolle und der betrieblichen Effizienz lag.

# Operativer Arbeitsablauf

Das System steigert die Effizienz durch eine Zwei-Stationen-Konfiguration. Zunächst werden zwei Montagestationen neben dem Roboter eingerichtet, um Lkw-Türkomponenten für den Schraubvorgang zu sichern. Der Bediener positioniert eine Türkomponente an einer Station und löst den Schraubvorgang mit einer einfachen Steuerung aus, die eine nahtlose Interaktion zwischen Mensch und Roboter ermöglicht. Nach der Aktivierung führt der Roboter die Verschraubung mit hoher Präzision und Konsistenz aus. Da der Roboter auf der einen Seite arbeitet, kann der Bediener das nachfolgende Bauteil an der anderen Station vorbereiten, was einen ununterbrochenen Arbeitsablauf gewährleistet. Sobald der Roboter die Schraubaufgabe beendet hat, wird das montierte Bauteil entnommen, und der Zyklus beginnt mit einem neuen Teil erneut.

# Systemkomponenten

Das System umfasst Schlüsselkomponenten für eine nahtlose Funktionalität:

- **FANUC CRX10iA/L kollaborativer Roboter:**
    
    - **Roboter-Controller:** Steuert die Bewegungen und Aufgaben des Roboters mit Hilfe einer hochentwickelten Software.
    - **Teach Pendant:** Bietet eine benutzerfreundliche Schnittstelle für die Roboterprogrammierung und -Bedienung.
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
    - **Pneumatik Zylinder:** Verwendet einen Pneumatik Zylinder für eine präzise Hebelbetätigung, die ein sicheres Einspannen der Komponenten gewährleistet.
    - **Wegeventil:** Verwendet ein Magnetventil zur präzisen Steuerung der Bewegungen des Pneumatik Zylinders.

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

**Dokumentation der Interpolationspunkte**:

- **Orientierung des Ursprungspunkts**: Der Ursprung des User Frames wird durch die Anpassung der Messspitze des Roboters an den ausgewählten Ursprungspunkt auf der Montagestation festgelegt, und diese Position wird aufgezeichnet.
- **Punkt in X-Achsen-Richtung**: Die Messspitze wird auf einen Punkt entlang der X-Achse vom Ursprung aus verschoben, und diese Position wird dokumentiert.
- **Punkt in Richtung der Y-Achse**: Die Messspitze wird vom Ursprung oder der aktuellen Position des Roboters zu einem bestimmten Punkt entlang der y-Achse verschoben, und diese Position wird registriert.

Die anfängliche "Ursprungspunkt-Orientierung" legt den Nullpunkt für den User Frame fest, wobei die folgenden Punkte die positiven Richtungen entlang der x- und y-Achse angeben. Auf diese Weise wird sichergestellt, dass der Arbeitsbereich des Roboters genau mit dem tatsächlichen Layout der Montagestationen korreliert, wodurch die Genauigkeit und Effektivität seiner Aufgaben verbessert wird.

# Point-Teaching

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

# Teach Pendant-Programme

Teach Pendant-Programme wurden speziell für die Steuerung des Schraubvorgangs innerhalb der Montagelinie entwickelt. Diese Programme bestehen aus einem Hauptprogramm, das den Gesamtprozess steuert, und mehreren Unterprogrammen, die jeweils für bestimmte Aufgaben innerhalb des Schraubvorgangs vorgesehen sind.

## Hauptprogramm

 **1. Initialisierung**

- **Start**: Der Beginn des Betriebszyklus wird durch eine Startmarke `LBL[1]` markiert.
- **Initialisierung von IOs und Parametern**:
    - Anfangsbedingungen und Konfigurationen werden durch den Aufruf von `ISRA_CELL_INIT` gesetzt.

 **2. Ausgangsposition prüfen**

- **Bedingung**: Falls sich der Roboter nicht in der Ausgangsposition befindet (`DO[1:PosCheck_HomePos]` ist `OFF`):
    - **Aktion**: Der Roboter wird durch den Aufruf von `AA_HOME` in die Ausgangsposition gefahren.

 **3. Operation Start**

- **Timer Start**: Die Zeitmessung des Betriebszyklus wird mit `TIMER[5]=START` eingeleitet.
- **Vorbereitung**: Die Umgebung wird gescannt, die Bestätigung des Arbeiters auf der linken oder rechten Seite wird überprüft, und der Roboter wird durch den Aufruf von `SAFEMOVE_CHECK_HOME` auf der entsprechenden Seite in eine Vorposition gebracht.

 **4. Schraubprozessentscheidung**

- **Geschwindigkeitseinstellung**: Die Arbeitsgeschwindigkeit wird durch den Wert in `R[4:Fast OVRD]`, der 100% beträgt, auf einen schnellen Override eingestellt.

 **4.1 Linksseitige Vorgänge**

- **Bedingung**: Wenn der Roboter für Operationen auf der linken Seite bereit ist (`DO[2:AtPrePosLH]` ist `ON`) und die Werkerquittierung auf der linken Seite bestätigt ist (`DO[9:werker quittieren links]` ist `ON`):
    - **Aktion**: Der Verschraubungsvorgang auf der linken Seite wird durch den Aufruf von `ISRA_LH_SCREWING` eingeleitet.

 **4.2 Vorgänge auf der rechten Seite**

- **Bedingung**: Bei fehlender Positionierung für linksseitige Vorgänge wird die Bereitschaft des Roboters für rechtsseitige Vorgänge (`DO[3:AtPrePosRH]` ist `ON`) und die Werkerquittierung auf der rechten Seite (`DO[10:werker quittieren rechts]` ist `ON`) geprüft:
    
    - **Aktion**: Der Schraubvorgang auf der rechten Seite wird durch den Aufruf von `ISRA_RH_SCREWING` eingeleitet.
- **Hinweis**: Wenn keine der beiden Bedingungen erfüllt ist, wird das Programm zur Neubewertung zum Startlabel `LBL[1]` zurückgeleitet.
    

 **5. Bewegung nach der Operation**

- **Rückkehr zur linken Seite**: Nach Beendigung der Operationen auf der linken Seite (`DO[2:AtPrePosLH]` ist `ON`) wird der Roboter durch den Aufruf von `SAFEMOVE_CHECK_LEFT` von der linken Seite sicher in die Ausgangsposition zurückbewegt.
    
- **Rückkehr von der rechten Seite**: Nach Abschluss der Vorgänge auf der rechten Seite (`DO[3:AtPrePosRH]` ist `ON`) wird der Roboter durch Aufruf von `SAFEMOVE_CHECK_RIGHT` sicher von der rechten Seite in die Ausgangsposition zurückgebracht.
    

 **6. Betriebsende**

- **Timer Stop**: Die Zeitmessung des Betriebszyklus wird mit `TIMER[5]=STOP` abgeschlossen.
- **Schleife**: Das Programm wird in einer Schleife zum Startlabel `LBL[1]` zurückgeführt, um den nächsten Betriebszyklus zu beginnen.

 **7. Programmabschluss**

- Der Zyklus wird auf unbestimmte Zeit fortgesetzt, bis er durch eine externe Bedingung oder einen externen Befehl unterbrochen oder angehalten wird.

## `ISRA_CELL_INIT`

1. **Initialisierung:**
    - Der Tool Frame wird auf 3 gesetzt, was die Kamera kennzeichnet.
    - Der User Frame wird auf 0 gesetzt, was dem Welt- oder Roboter-Basis-Koordinatensystem entspricht.
    - Die Nutzlast wird auf 1 gesetzt, was die Schraubspindel und die Kamera kennzeichnet.
2. **Einstellungen für den digitalen Ausgang:**
    - Die linke Betriebsanzeige (`DO[4:LH In Process]`) wird ausgeschaltet.
	- Die rechte Betriebsanzeige (`DO[5:RH In Process]`) wird ausgeschaltet.
    - Der linke Abbiegehinweis (`DO[7:Turn_2_LH]`) wird ausgeschaltet.
    - Der rechte Abbiegehinweis (`DO[6:Turn_2_RH]`) wird ausgeschaltet.
    - Der Öffnungszustand des linken Hebels (`DO[101:FixtureOpen]`) wird aktiviert.
    - Der Öffnungszustand des rechten Hebels (`DO[103:FixtureOpen]`) wird aktiviert.
3. **Timer zurücksetzen:**
    - Der Hauptprogramm-Timer `TIMER[5]` wird auf seinen Anfangszustand zurückgesetzt.
    - Der `SAFEMOVE_CHECK_HOME`-Programm-Timer `TIMER[6]` wird auf seinen Anfangszustand zurückgesetzt.
    - Der `SAFEMOVE_CHECK_LEFT`-Programm-Timer `TIMER[7]` wird auf seinen Anfangszustand zurückgesetzt.
    - Der `SAFEMOVE_CHECK_RIGHT`-Programm-Timer `TIMER[8]` wird auf seinen Anfangszustand zurückgesetzt.

##  `AA_HOME`

1. **Initialisierung:**
    - Setzen Sie den Tool Frame auf 3, der die Kamera angibt.
    - Setzen Sie den User Frame auf 0, was dem Welt- oder Basiskoordinatensystem entspricht.
2. **Bewegung zur Ausgangsposition:**
    - Es wird eine Gelenkbewegung ausgeführt, um den Roboter in die Ausgangsposition zu bewegen, die in dem entsprechenden Positionsregister ``PR[7:Home_center]`` definiert ist.

## `AA_PREPOSLH`

1. **Initialisierung:**
    - Setzen Sie den Tool Frame auf 3, der die Kamera anzeigt.
    - Setzen Sie den User Frame auf 0, was dem Welt- oder Basiskoordinatensystem entspricht.
2. **Vorpositionsbewegung der linken Hand:**
    - Eine Gelenkbewegung zur Bewegung des Roboters in die linke Vorposition, definiert im entsprechenden Positionsregister ``PR[8:Home_left_corr]`` wird ausgeführt.

## `AA_PREPOSRH`

1. **Initialisierung:**
    - Setzen Sie den Tool Frame auf 3, der die Kamera anzeigt.
    - Setzen Sie den User Frame auf 0, was dem Welt- oder Basiskoordinatensystem entspricht.
2. **Vorpositionsbewegung der rechten Hand:**
    - Eine Gelenkbewegung zur Bewegung des Roboters in die rechte Vorposition, die im entsprechenden Positionsregister ``PR[10:Home_Right]`` definiert ist, wird ausgeführt.

## `ISRA_LH_SCREWING` und `ISRA_RH_SCREWING`

``ISRA_LH_SCREWING`` und ISRA_``RH_SCREWING`` haben den gleichen Algorithmus, unterscheiden sich aber in ihren räumlichen Bezügen durch unterschiedliche User Frames für jede Montagestation. ``ISRA_LH_SCREWING`` richtet sich für linke Aufgaben am User Frame 40 aus, während ``ISRA_RH_SCREWING``, im Wesentlichen eine gespiegelte Version, seinen User Frame auf 45 einstellt und für rechte Aufgaben Schraubpunkte im Bereich 21 bis 28 neu definiert.

1. **Initialisierung:**
	- User Frame und Tool Frame einstellen:**
		- Das User Frame ist auf 40 (linke Montagestation) eingestellt.
		- Das Tool Frame ist auf 3 (Kamera) eingestellt.
	- **Prozessbit aktivieren:**
		- Die linke Betriebsanzeige (`DO[4:LH In Process]`) wird eingeschaltet und zeigt damit an, dass der linke Schraubvorgang begonnen hat.
	- **Atlas Copco System initialisieren:**
		- Zur Initialisierung des Atlas-Copco-Systems werden spezielle Atlas-Copco-Programme aufgerufen
	- **Startpunkt setzen:**
		- Die Schraubennummer ``R[22:AC_ScrewNumber]`` wird auf 11 gesetzt, was die erste Schraube im Vorgang anzeigt.
2. **Positionierung und Bewegung:**
	- **Roboterposition zuweisen:**
		- Die neue/ Zielposition ``PR[60:newpos]`` wird auf die Koordinaten in ``PR[R[22]]`` gesetzt, was der ersten Schraube entspricht.
	- **Positionsanpassung anhand der Schraubennummer:**
		- Spezifische Posen für jede Schraubennummer (11-18) werden durch den Aufruf spezifischer Atlas Copco Programme vorbereitet.
	- **Kollisionsvermeidungsstrategie:**
		- Für die Schraubennummern 13 und 18 wird ein Z-Achsen-Offset von 150 mm angewendet, um Kollisionen zu vermeiden.
		- Für alle anderen Schrauben wird ein Z-Achsen-Offset von 50 mm angewandt.
		- Der Offset wird ``PR[31:Temp_prepos150mm]`` zugewiesen.
3. **Messreihenfolge:**
	- Der TCP wird auf ``PR[60:newpos]`` verschoben, wobei der Offset des Werkzeugs aus ``PR[31:Temp_prepos150mm]`` übernommen wird.
	- Spezifische Atlas Copco-Programme werden aufgerufen, um das Schraubwerkzeug vorzubereiten, die Schraube von der Zuführung anzufordern und den ISRA Vision-Messprozess vorzubereiten.
	- **Pneumatische Hebelverwaltung:**
		- Der linke pneumatische Hebel wird durch Umschalten von `DO[101:FixtureOpen]`` auf ON geöffnet, wenn die Schraubennummer ``R[22:AC_ScrewNumber]`` auf 15 gesetzt ist.
		- Der linke pneumatische Hebel wird geschlossen, indem `DO[101:FixtureOpen]` auf OFF geschaltet wird, wenn die Schraubennummer ``R[22:AC_ScrewNumber]`` auf 17 gesetzt ist.
	- **Messungspositionierung:**
		- Der TCP wird auf die Messposition ``PR[60:newpos]`` bewegt.
	- **Messung und Datenerfassung:**
		- Spezifische Atlas Copco Programme werden aufgerufen, um die Positionsmessung zu initiieren.
4. **Anzugsreihenfolge:**
	- **Messung und Werkzeugvorbereitung:**
		- Spezifische Atlas Copco-Programme werden aufgerufen, um das Messergebnis abzurufen.
		- Das Tool Frame wird auf 4 geschaltet, was auf die Schraubenspindel hinweist.
	- **Einstellung der Schraubposition:**
		- Der aus dem Messergebnis ermittelte Offset der x- und y-Koordinaten wird zu `PR[60:newpos]`` addiert.
	- **Vorsichtsmaßnahme zur Kollisionsvermeidung:**
		- Der TCP wird auf eine Zwischenposition ``PR[2:Offset_Z_PR[18]]`` verschoben, um Kollisionen zu vermeiden, wenn die Schraubennummer ``R[22:AC_ScrewNumber]`` auf 18 gesetzt ist.
	- **Schraubenposition anfahren:**
		- Der TCP wird unter Berücksichtigung des Offsets von ``PR[30:Temp_10mm_pos]`` in Richtung der aktualisierten ``PR[60:newpos]`` bewegt.
	- **Sensor-Management:**
		- Deaktivieren Sie den Kraftsensor des Roboters, indem Sie `DO[70:F_Sensor_1_OFF_0_ON]` auf ON schalten.
	- **Endgültige Positionierung der Schraube:**
		- Fahren Sie die exakte Schraubenposition ``PR[60:newpos]`` für den Anziehvorgang an.
	- **Schraubenausführung:**
	    - Spezifische Atlas Copco-Programme werden aufgerufen, um die Bereitschaft der Schraube zu bestätigen, den Schraubvorgang zu starten, den Prozess zu überwachen und den Kopfhub zu erhöhen.
	- **Verfahren nach dem Anziehen:**
	    - Spezifische Atlas Copco-Programme werden aufgerufen, um den Abschluss des Schraubvorgangs zu überprüfen und den Kopfhub zurückzuziehen.
	    - Der TCP wird auf ``PR[60:newpos]`` zurückgefahren, wobei der Offset des Werkzeugs von ``PR[31:Temp_prepos150mm]`` übernommen wird.
	- **Sensor Reaktivierung und Betriebsbestätigung:**
	    - Der Kraftsensor wird durch Umschalten von ,,DO[70:F_Sensor_1_OFF_0_ON]" auf ,, OFF" reaktiviert.
	    - Spezifische Atlas Copco-Programme werden aufgerufen, um das erfolgreiche Anziehen und den Kopfhubrückzug zu bestätigen.
	- **Schraubennummer-Update:**
	    - Die Schraubennummer ``R[22:AC_ScrewNumber]`` wird um eins erhöht und die Schleife zurück zu Schritt 2 (Positionierung und Bewegung) für die nächste Schraube, wenn die Schraubennummer ``R[22:AC_ScrewNumber]`` innerhalb des Bereichs der Schraubennummern liegt, in diesem Fall 18.
5. **Beendigung:**
	- **Zurück zur Vorpositionierung:**
	    - Der TCP wird in eine linke Vorposition gefahren ``PR[8:Home_left_corr]``
	- **Pneumatische Hebelsteuerung:**
	    - Der linke pneumatische Hebel wird durch Umschalten von `DO[101:FixtureOpen]` auf ON geöffnet.
	- **Prozess-Bit deaktivieren:**
	    - Die linke Betriebsanzeige (`DO[4:LH In Process]`) wird auf AUS gesetzt, um anzuzeigen, dass der linke Schraubvorgang gestoppt wurde.