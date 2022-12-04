Willkommen in der Autodarts Hilfe !

Hier werden die wichtigsten Dinge zu autodarts erklärt. Falls du doch weitere Hilfe benötigst kannst du nagilo im Discord Kanal kontaktieren.

Ich erkläre hier schnell was man tun kann. Dazu muss man (fast) immer zuerst das Programm Konsole (Terminal) starten. Links unten in der Ecke findest du den Anwendungs-Starter. Unter Anwendungen->System findest du dann das Programm Konsole. Alternativ kannst du auch konsole in die Suche eintippen, die sich öffnet sobald du auf den Anwendungs-Starter drückst.

Wenn alles geklappt hast dann hat sich ein schwarzes Fenster geöffnet in dem der Schriftzug "player@debian:~$ " zu sehen ist. Nun kann es los gehen. Im folgenden findest du immer wieder Befehle die du in der Konsole eingeben kannst. Am besten kopieren sonst vertippt man sich leicht.

Falls du nach einem Passwort gefragt wirst - das Passwort lautet autodarts !

1. Autodarts

Autodarts läuft immer sofort automatisch, so dass man weder einen Monitor noch sonst etwas braucht. Das ist der Idealzustand. Also am besten du siehst das hier gar nicht. Falls doch hier was du tun kannst.

1.1 Autodarts Stoppen

Zum stoppen von Autodarts nutzt man den folgenden Befehl

systemctl stop autodarts.service

1.2 Autodarts Starten im Hintergrund

Zum starten von Autodarts so dass der Dienst im Hintergrund läuft nutzt man folgenden Befehl

systemctl restart autodarts.service

1.2 Autodarts Starten im Vordergrund

Wenn man autodarts vorher gestoppt hat kann man das System auch im Vordergrund starten. Das ist hilfreich falls man die Ausgaben von Autodarts sehen möchte. Der Befehl dazu lautet einfach autodarts. Wenn man Autodarts im Vordergrund wieder beenden möchte drückt man <strg>+c .

autodarts

2. Konfiguration

Die Konfiguration von Autodarts befindet sich im Verzeichnis .autodarts . Achtung der erste Punkt ist wichtig, das ist ein vertecktes Verzeichnis. 

2.1 Öffnen und Editiren der Konfigurationsdatei 

Wenn du deine Board-ID und deinen Schlüssel editieren willst, dann nutzen wir am besten einen Dateimanager. Das kann man auch auf der Konsole machen aber naja mit Grafik gehts halt einfacher. Zum Starten des Dateimanagers im richtigen Verzeichnis gibt man auf der Konsole folgenden Befehl ein. Dann öffnet sich ein Fenster in dem du alle Dateien siehst, die sich gerade in deinem Konfigurationsverzeichnis befinden. Wenn du auf eine der Dateien klickst (nur ein mal !!!) dann öffnet sich ein Editor und du kannst alles anpassen. In dem Verzechnis landet später auch die Datei für die Kamerakalibrierung falls notwendig.

dolphin .autodarts

3. Teamviewer als direkte Hilfe von Extern

Ja es gibt auch direkt die Möglichkeit externe Hilfe zu bekommen. Teamviewer ist vorinstalliert. Im Anwedungs-Starter findest du unter Internet das Programm TeamViewer. Der Kontakt wird über discord hergestellt.

4. Kalibrierung der Kameras

Auf dem System ist auch alles zum Kalibrieren der Kameras installiert. Dazu muss man aber Autodarts zuerst beenden wie oben beschrieben.

4.1 Aufnehmen der Bilder

Wir wechseln zuerst in das richtige Verzechnis und starten dann das Programm zum Aufnehmen der Bilder. Dann starten wir die Bildaufnahme. Bitte die Auflösung der Kameras korrekt eintragen. Die Bilder landen im Verzechnis cam-calibration/calibrationImages. Die Bilder kann man sehen, wenn man den die Dateiverwaltung Dolphin startet und in das Verzeichnis wechselt.

cd cam-calibration
python3 main.py generate -camIds 0 2 4 -fps 30 -w 1920 -h 1080

4.2 Starten der Kalibrierung

Wieder im gleichen Verzeichnis kann man dann die Kalibrierungs starten. Auch hier wieder Auflösung anpassen. Es ensteht eine Datei distortion.json die man wieder mit Dolphin in das Verzechnis .autodarts kopieren kann. (Wer dabei Hilfe braucht kurze Nachricht - Tipp: Dolphin).

python3 main.py distortion -w 1920 -h 1080

5. Anzeigen und einstellen der Kameras

Wenn ihr die Kameras einstellen wollt dann könnt ihr das tun. Autodarts stopppen und dann folgendes auf der Konsole eingeben. Die Kameras drei Kameras haben bei mir die Nummern 0, 2 und 4 aber das kann bei euch anders sein. Stoppen wieder mit <strg>+c .

guvcview -d /dev/video4

6. Noch mehr ?

Natürlich geht noch viel viel mehr. Einfach in Discord ansprechen.
