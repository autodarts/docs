---
draft: true
author: "TmO"
lang: "de"
---



## In diesem Abschnitt erfährst du, wie das Systems konfiguriert werden kann.

Hier werden die Bewegungserkennung und die Dart-Erkennung erklärt, damit diese besser an dein System angepasst werden können.

{{< hint type=hint icon=gdoc_error_outline >}}
<p>Da die Config Seite aktuell nur in Englisch verfügbar ist verwenden wir in diesem Abschnitt auch die Englischen Begriffe.<br>
<br>
Diff Image = Bilddifferenz<br>
Treshold= Schwellenwert<br>
Motion Detection= Bewegungserkennung<br>
Dart Detection= Darterkennung<br>
Object Detection= Objekterkennung<br>
Dart Size= Dartpfeilgröße<br>
Hand Size= Handgröße<br>
ROI/Region of Interest= Region/Bereich von Interesse</p>
{{< /hint >}}

Beginnen wir zunächst mit den beiden wichtigsten.
Die Funktion `Bilddifferenz(Diff Image) und Schwellenwert(Treshold)` wird sowohl unter `Bewegungserkennung(Motion Detection)` als auch unter `Darterkennung(Dart-Detection)` verwendet, um den Unterschied zwischen dem Bild vor dem Dart-Treffer und dem Bild direkt danach zu berechnen.

Für optimale Ergebnisse sollte dieses Bild kristallklar sein.
Das heißt, die Umrisse des Dartpfeils sollten klar erkennbar sein, aber es sollten keine Artefakte im Hintergrund zu sehen sein.
Das kannst du am besten überprüfen, indem du ein paar Darts wirfst und die Registerkarte `Motion` im Board Manager beobachtest.
Ein höherer `Schwellenwert(Treshold)` führt in der Regel zu weniger sichtbaren Konturen des Pfeils, aber auch zu weniger Hintergrund.
Niedrigere `Schwellenwert(Treshold)` Werte führen zu klareren Konturen des Pfeils, allerdings auf Kosten der Erfassung des Hintergrunds.
Stellen Sie ihn so ein, dass Sie genau dazwischen liegen.

Im Allgemeinen wird empfohlen, die Einstellung `Bilddifferenz(Diff Image) und Schwellenwert(Treshold)` für die `Bewegungserkennung(Motion Detection)` und die `Darterkennung(Dart Detection)` gleich zu halten, aber es kann sich positiv auswirken, sie unterschiedlich einzustellen.

Spielen Sie mit diesen Werten, um die `Bilddifferenz(Diff Image)` zu optimieren.
Das wird sich auf die Erkennung insgesamt ziemlich stark auswirken.

{{< tabs "Install Tab" >}}
{{< tab "Motion Detection" >}} 

# Gaußsches Weichzeichnen

Als nächstes folgt der `Gaußsche Kernel`.
Er wird verwendet, um die `Bilddifferenz(Diff Image)` unscharf/weicher zu machen und Hintergrundrauschen zu entfernen.
Der Wert kann nur in ungeraden Schritten eingestellt werden.
Höhere Werte benötigen mehr Zeit für die Berechnung, weshalb sie standardmäßig auf "3" für `Bewegungserkennung(Motion Detection)` und "5" für die `Pfeilerkennung(Dart Detection)` eingestellt sind.
Sie haben keinen großen Einfluss auf die Erkennung, daher sollten die Standartwerte so belassen werden, solange es keine Probleme damit gibt.

{{< hint type=hint icon=gdoc_error_outline >}}
Eine typische Softwarelösung zur Weichzeichnung von digitalen Fotos ist der Gaußsche Weichzeichner mit Hilfe des Gauß-Filters. Der Name beruht dabei auf der „Gaußschen“ Normalverteilung, die durch Johann Carl Friedrich Gauß entwickelt wurde. 
{{< /hint >}}

{{< /tab >}}

{{< tab "Object Detection" >}} 

# Objekterkennung

Die `Object Detection(Objekterkennung)` enthält die Konfigurationsparameter für die Unterscheidung zwischen Pfeil und Hand.
Vereinfacht gesagt ist ein Dartpfeil kleiner als eine Hand, und so wird er von der Software erkannt (ob Sie es glauben oder nicht).
`Dart Size: Min` und `Dart Size: Max` sind Werte, die festlegen, wie klein ein Objekt mindestens sein muss, und wie groß es maximal sein darf um als Dartpfeil erkannt zu werden. Diese Werte stellen Bereiche im Bild dar, aber Sie können sie sich als die Gesamtzahl der Pixel in Ihrem Bild vorstellen, aus denen der Dart besteht. Normalerweise ist der Wert für `Hand Size: Min` viel höher an als die `Dart Size: Max`, aber es gibt keinen wirklichen Grund dafür.
Sobald ein Objekt mehr Pixel hat als der Wert für `Dart Size: Max`, wird es als Hand betrachtet.

{{< /tab >}}
{{< tab "Dart Detection" >}}

# Darterkennung

Unter `Darterkennung(Dart Detection)` gibt es einen Unterabschnitt mit der Bezeichnung `ROI Detection`.
Die ROI ist die Region von Interesse im Bild mit voller Auflösung. Ich verwende die Bewegungserkennung, die mit einer viel geringeren Auflösung läuft (um schnell zu sein), um zu berechnen, wo sich der Dartpfeil im Bild mit voller Auflösung befinden würde. Um den ROI zu ermitteln, fasse ich alle so genannten Blobs (Objekte im Bild, die aus Pixeln bestehen) zusammen, die eine bestimmte Größe (wiederum in Pixeln) überschreiten. Die ROI ist einfach die Bounding Box (ein Rechteck) dieser kombinierten Blobs. (Der blaue Rahmen um die Pfeile in der Registrierkarte "Dart"). Ich setze diesen Wert normalerweise recht niedrig an, niedriger als die `Dart Size: Min`. Beachten Sie, dass sich die Anzahl der Pixel hier auf die Bewegungsauflösung bezieht, die 4 Mal kleiner ist als die Erkennungsauflösung.

{{< /tab >}}
{{< tab "Hough Line Detection" >}}

# Linien Erkennung / Barrel Erkennung

Schließlich gibt es noch die `Hough Line Detection`.
Dieser Unterabschnitt enthält alle Werte rund um den Algorithmus, der die Linie in das Barrel einpasst.
Der `Treshold(Schwellenwert)` ist ziemlich wichtig, derzeit wird noch daran gearbeitet um diesen passend zur Auflösung zu skalieren.
Ich verwende in der Regel Werte im 50er-Bereich für meine Setups (bei 800x600 und 1280x720).
Wenn Sie diesen Wert höher einstellen, findet der Algorithmus weniger Linien, da nur Linien mit einer bestimmten Anzahl von Stimmen berücksichtigt werden.
Der `Schwellenwert(Treshold)` legt fest, wie viele Stimmen eine Zeile benötigt.
Die Werte `Min Line Length(minimale Linienlänge)` und `Max Line Gap(maximaler Lienienabstand)` sollten eigentlich selbsterklärend sein.
Auch hier bezieht sich der Wert auf Pixel. 
Es ist also zu berücksichtigen, wie lang eine Linei mindestens sein muss und wie weit zwei Linien voneinander entfernt sein dürfen, damit sie zu einer einzigen langen Linie zusammengefasst werden können.

{{< /tab >}}
{{< /tabs >}}