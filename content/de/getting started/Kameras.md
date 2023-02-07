---
title: "Kameras"
draft: true
author: "Steve_Mutter"
weight: "1"
lang: "de"
---

[comment]: <> (Fact Check | TO DO)
[comment]: <> (Spelling | DONE)

Autodarts unterstützt eine breite Palette von Webcams. Es ist jedoch nicht empfehlenswert, einfach die billigsten Kameras zu kaufen. Basierend auf den Erfahrungen der Community haben wir bereits eine Auswahl an geeigneten Kameras zusammengestellt.

###### Bei der Auswahl der Kameras gilt es einige Faktoren zu beachten.

> FOV - Das Sichtfeld sollte zwischen 80° und 110° liegen

> Objektive sollten keine Verzerrung aufweisen

> Geringer Stromverbrauch

> Länge des Kabels (je kürzer das Kabel, desto geringer der Spannungsabfall)

> Stabile Framerate mit ca. 30FPS

> Die meisten Systeme werden mit Auflösungen von 640x480 bis 1280x720 gespielt (höhere Auflösungen haben derzeit fast keine Auswirkungen auf die Genauigkeit)

![Boards by Resolution](/statistics/images/boards_by_resolution.png)

Bei den meisten Kameras ist es relativ einfach, die Objektive nachträglich auszutauschen, um das gewünschte Sichtfeld zu erhalten. 

Viele Kameras haben Verzerrungen, die aber mit den richtigen Objektiven ausgeglichen werden können. Wir bieten auch Software an, mit der sich die Verzeichnung verbessern lässt.

Beim Stromverbrauch ist es wichtig, die USB-Standards und die Angaben des Herstellers, zu prüfen. In einigen Fällen kann die Verwendung externer USB-Hubs mit eigener Stromversorgung hilfreich sein.

| Spezifikation | Spannung | Strom | Leistung
| --- | --- | --- | --- |
| USB 1.0/1.1 | 5V | 100mA | 0,5W
| USB 2.0 | 5V | 500mA | 2,5W
| USB 3.o/3.1 | 5V | 900mA | 4,5W

Es gibt noch weitere Faktoren, die bei Kameras eine Rolle spielen können. Diese sind jedoch die wichtigsten. Hier sind ein paar Beispiele aus der Community, die bereits von unseren Nutzern verwendet werden und gute Ergebnisse liefern.


[comment]: <> (| Manufacture | FOV | 30FPS @ 800x600 | 30FPS @ 1024x768 | Link)
[comment]: <> (| --- | --- | --- | --- | --- |)
[comment]: <> (| ELP USB Camera | 75° | &check; | &check; | https://tinyurl.com/3cme9664)
[comment]: <> (| MOERTEK MC920 Streamcam | 85° | &check; | &check; | https://tinyurl.com/2bh6wnc7)
[comment]: <> (| Pasonomi*¹ | 110°  | &check; | &check; | https://tinyurl.com/2p9fverc)
[comment]: <> (| Logilink UA 0378 | 100° | &check; | &check; | https://tinyurl.com/7m7ntyd3)
[comment]: <> (| ELP OTG Wide Angle | 100° | &check; | &check; | https://tinyurl.com/y4emp7yt)


[comment]: <> (| Manufacture | Description | Requires "distorsion.json" | Platform | Kernel Hack)
[comment]: <> (| --- | --- | --- | --- | --- |)
[comment]: <> (| Aukey | PC-LM1E | X | Raspberry Pi 4 | X)
[comment]: <> (| MOERTEK | MC920 Streamcam | X | Raspberry Pi 4 )
[comment]: <> (| MOERTEK | MC920 Streamcam | X | Fujitsu Futro 920s 414GC | X)
[comment]: <> (| ELP | 2MP USB Cameramodule 1080P H.264 Webcam Low Light 100° | X | X )
[comment]: <> (| Waveshare | 2MP USB Cameramodule OV2710 145° | &check; | Raspberry Pi 4 | &check;)
[comment]: <> (| Waveshare | 2MP USB Cameramodule OV2710 100° | X | Raspberry Pi 4 |&check;)
[comment]: <> (| Pasonomi | 110°  | &check; | Raspberry Pi 4 | X)
[comment]: <> (| VESSTT | Webcam 1080P | &check; | Raspberry Pi 4 | X)
[comment]: <> (| IRARUCQ | Webcam 2K | &check; | Raspberry Pi 4 | X)
[comment]: <> (| Nortec | 1080P | &check; | Mac Mini | X)
[comment]: <> (| Nortec | 1080P | &check; | Ubuntu Desktop | X)
[comment]: <> (| Arducam | 8MP IMX219 Cameramodule | X | Raspberry Pi 4 | X)
[comment]: <> (| Lycander | USB Webcam | &check; | Asus eeePC 1012p | X)
[comment]: <> (| ZYXH | OV9732 Cameramodule 100° | X | Raspberry Pi 4 | X)
[comment]: <> (| Garosa | OV3660 Cameramodule 110° | X | Raspberry Pi 4 | X)
[comment]: <> (| ZYXH | OV9732 Cameramodule 100° | X | Raspberry Pi 4 | X)
[comment]: <> (| Logilink | UA 0378 100° | &check; | Raspberry Pi 4 | X)



[comment]: <> ({{< hint type=hint icon=gdoc_info_outline >}})
[comment]: <> (X = Is not needed | &check; = Is needed)
[comment]: <> ({{< /hint >}})

# Vergleich verschiedener Kameras

|Bewertung [0-4]|Skala [1-5]|Bild|Hersteller|Typ|Preis [EUR]|FOV [°]|Verzerrung|Überbelichtung|Einstellungen|Autofokus|Pro|Contra|Info|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|4|1+|![img](/camera-comp/images/elp_otg.png)|ELP|OTG HD 5mp|60|100|Keine|Keine|Manuell|Nein| Stabile Bauform / Hohe Qualität / Benötigt keine distortion.json / 3m USB 2.0 Kabel / Klein / Hochwertige CMOS Linse |Teuer|Kaufempfehlung hat nur kleine Probleme|
|4|1.5|![img](/camera-comp/images/mortek_mc920.png)|MOERTEK|MC920 1080P HD|8 - 18|85|Fast keine|Nein|Automatisch|Ja|Stabil / Sieht aus wie die Logitech C920 / gute Verpackung / eigene Website / Große Firma aus China / Günstig / Benötigt keine distortion.json||Kaufempfehlung|
|3|2.5|![img](/camera-comp/images/ahnunva_c5.png)|Ahnunva C5|HD 2K 1080P|23|130|gering|gering|Manuell|Nein|kleine Stabile Bauform|Benötigt >40cm Abstand vom Board / Probleme mit dem Fokus / Benötigt distortion.json||
|2|3.5|![img](/camera-comp/images/anke_power.png)|Anke Power|1080P HD|16|110|Ja|Nein|Automatisch|Ja|massiv + stabil|viel Verzerrung / zu Teuer / Benötigt distortion.json|KEINE Kaufempfehlung|
|1|4|![img](/camera-comp/images/irarucw_2k.png)|IRARUCW|2K HD|16|120|Ja|Nein|Automatisch|Ja||Benötigt >45cm Abstand zum Board|KEINE Kaufempfehlung|
|1|5|![img](/camera-comp/images/aode_1080.png)|AODE|1080 HD USB 2.0|10|90|Ja|Ja|Automatisch|Ja|Stabile Bauform| viel Verzerrung / zu Teuer / Probleme mit USB Anschluss|Keine Kaufempfehlung|

###### Kameras, die nicht funktionieren

| Hersteller | Link
| --- | ---|
| Rollei R-Cam 100 | https://tinyurl.com/mwj7uvrd 
| Makoty Webcam | https://tinyurl.com/4e5pmtjy
| GuangTouL Webcam | https://tinyurl.com/3dek8m2a