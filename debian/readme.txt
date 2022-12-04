Willkommen in der Autodarts Hilfe !

Hier werden die wichtigsten Dinge zu Autodarts unter Debian erklärt. Falls Du doch weitere Hilfe benötigst kannst Du nagilo in Discord kontaktieren.

Ich erkläre hier schnell was man tun kann. Dazu muss man (fast) immer zuerst das Programm Konsole (Terminal) starten. Links unten in der Ecke findest Du den Anwendungs-Starter. Unter Anwendungen->System findest Du dann das Programm Konsole. Alternativ kannst Du auch Konsole in die Suche eintippen, die sich öffnet sobald Du auf den Anwendungs-Starter drückst.

Wenn alles geklappt hast dann hat sich ein schwarzes Fenster geöffnet, in dem der Schriftzug "player@debian:~$ " zu sehen ist. Nun kann es los gehen. Im folgenden findest Du immer wieder Befehle die Du in der Konsole eingeben kannst. Am besten kopieren sonst vertippt man sich leicht.

Falls Du nach einem Passwort gefragt wirst - das Passwort lautet autodarts !

1. Autodarts

Autodarts läuft immer sofort automatisch, so dass man weder einen Monitor noch sonst etwas braucht. Das ist der Idealzustand. Also am besten Du siehst das hier gar nicht. Falls doch hier was Du tun kannst.

1.1 Autodarts Stoppen

Zum Stoppen von Autodarts nutzt man den folgenden Befehl. Man wird aber zuerst nach dem Passwort gefragt.

systemctl stop autodarts.service

1.2 Autodarts Starten im Hintergrund

Zum Starten von Autodarts so dass der Dienst im Hintergrund läuft nutzt man folgenden Befehl.

systemctl restart autodarts.service

1.2 Autodarts Starten im Vordergrund

Wenn man Autodarts vorher gestoppt hat kann man das System auch im Vordergrund starten. Das ist hilfreich falls man die Ausgaben von Autodarts sehen möchte. Der Befehl dazu lautet einfach autodarts. Wenn man Autodarts im Vordergrund wieder beenden möchte drückt man <strg>+c .

autodarts

2. Konfiguration

Die Konfiguration von Autodarts befindet sich im Verzeichnis .autodarts . Achtung der erste Punkt ist wichtig, das ist ein verstecktes Verzeichnis. 

2.1 Öffnen und Editieren der Konfigurationsdatei 

Wenn Du deine Einstellungen manuell ändern willst nutzen wir den Dateimanager. Das kann man auch auf der Konsole machen aber naja mit Grafik gehts halt einfacher. Zum Starten des Dateimanagers im richtigen Verzeichnis gibt man auf der Konsole folgenden Befehl ein. Dann öffnet sich ein Fenster in dem Du alle Dateien siehst, die sich gerade in deinem Konfigurationsverzeichnis befinden. Wenn Du auf eine der Dateien klickst (nur ein mal klicken !!!) dann öffnet sich ein Editor und Du kannst alles anpassen. In dem Verzechnis landet später auch die Datei für die Kamerakalibrierung falls notwendig.

dolphin .autodarts

3. Teamviewer als direkte Hilfe von Dritten

Ja es gibt auch direkt die Möglichkeit externe Hilfe zu bekommen. Teamviewer ist vorinstalliert. Im Anwedungs-Starter findest Du unter Internet das Programm TeamViewer. Der Kontakt wird über Discord hergestellt.

4. Kalibrierung der Kameras

Auf dem System ist auch alles zum Kalibrieren der Kameras installiert. Dazu muss man aber Autodarts zuerst beenden wie oben beschrieben.

4.1 Aufnehmen der Bilder

Du wechselst zuerst in das richtige Verzechnis und startest dann das Programm zum Aufnehmen der Bilder. Dann startest Du die Bildaufnahme. Bitte die Auflösung der Kameras korrekt eintragen. Die Bilder landen im Verzechnis cam-calibration/calibrationImages. Die Bilder kann man sehen, wenn man die Dateiverwaltung Dolphin startet und in das Verzeichnis wechselt.

cd cam-calibration
python3 main.py generate -camIds 0 2 4 -fps 30 -w 1920 -h 1080

4.2 Starten der Kalibrierung

Wieder im gleichen Verzeichnis kann man dann die Kalibrierung starten. Auch hier wieder Auflösung anpassen. Es ensteht eine Datei distortion.json die man wieder mit Dolphin in das Verzechnis .autodarts kopieren kann. (Wer dabei Hilfe braucht kurze Nachricht - Tipp: Copy und Paste).

python3 main.py distortion -w 1920 -h 1080

5. Anzeigen und einstellen der Kameras

Wenn Du die Kameras einstellen willst, dann kannst Du das auch tun. Autodarts stopppen und dann folgendes auf der Konsole eingeben. Die drei Kameras haben bei mir die Nummern 0, 2 und 4 aber das kann bei euch anders sein. Stoppen wieder mit <strg>+c .

guvcview -d /dev/video4

6. Noch mehr ?

Natürlich geht noch viel viel mehr. Einfach in Discord ansprechen.
