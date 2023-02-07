---
title: "3D Druck"
draft: true
author: "TmO"
lang: "de"
---


## Anleitung zum Drucken von Kameraarmen und LED Ring

Die Arme sind für die Verwendung mit Kameramodulen konzipiert, die das gleiche Layout verwenden wie die [arducam](https://www.arducam.com/product/120fps-global-shutter-color-usb-camera-board-1mp-ov9782-uvc-webcam-module-with-low-distortion-m12-lens-without-microphones-for-computer-laptop-android-device-and-raspberry-pi-arducam/) oder [diese](https://de.aliexpress.com/item/1005003639087817.html?srcSns=sns_Copy&spreadType=socialShare&bizType=ProductDetail&social_params=60139065475&aff_fcid=586c8c83c6df43d5b5f42286c4ff23c3-1644578883184-08842-_vO4Id4&tt=MG&aff_fsk=_vO4Id4&aff_platform=default&sk=_vO4Id4&aff_trace_key=586c8c83c6df43d5b5f42286c4ff23c3-1644578883184-08842-_vO4Id4&shareId=60139065475&businessType=ProductDetail&platform=AE&terminal_id=6af8ab94ca69415fbf623544797fc5d7).
Wir empfehlen jedoch NICHT die arducam!!! Die Abmessungen der Module sind 32x32 mm und der Abstand der Bohrungen ist 28x28 mm. Sie funktionieren nicht mit Modulen, die diese Maße überschreiten!!! Ich habe jedoch eine Version entworfen, die mit Webcams mit einem Standard-Kamera-Gewinde verwendet werden kann. Es gibt auch die Möglichkeit, eine eigene Halterung für mein modulares System zu entwerfen, die ich später in diesem Beitrag vorstelle.
Die Füße sind so konzipiert, dass sie in die gleichen Bohrungen passen, die Sie für die Winmau-Plasmaring-Füße gebohrt haben.
Für die Verwendung mit dem Winmau Plasma Ring haben Sie die folgenden Möglichkeiten:

**Option 1**

![alt text](/3d-printing/images/plasma_assembly_git.png)

Sie wollen es in Kombination mit meinen Armen und Füßen verwenden. Sie müssen dann die folgenden Dateien drucken:

- [3x plasma_arm_foot.stl](stl/plasma_arm_foot.stl)
- [3x plasma_foot_webcam.stl](stl/plasma_foot_webcam.stl)
- [3x plasma_lid.stl](stl/plasma_lid.stl)
- [3x plasma_foot_lid.stl](stl/plasma_foot_lid.stl)

![alt text](/3d-printing/images/plasma_arm_assembly_git.png)

Der Deckel ist immer optional, aber sehr empfehlenswert. Er dient nicht nur der Ästhetik, sondern auch als Schutz für die Kameramodule!!!

**Option 2**

![alt text](/3d-printing/images/plasma_arm_assembly_webcam_git.png)

Wenn Sie eine Webcam mit einem Standardgewinde für die Kamerabefestigung verwenden möchten, müssen Sie den Arm und die Deckeldatei ersetzen durch

- [3x plasma_arm_foot_webcam.stl](stl/plasma_arm_foot_webcam.stl)
- [3x plasma_lid_webcam.stl](stl/plasma_lid_webcam.stl)

### Stückliste Autodarts:

- 3x Kameramodul (max. Abmessungen 32x32mm mit Bohrungen bei 28x28mm)
- 1x Winmau Plasma Ring
- 6x DIN 4762 M4x20 (Befestigung des Arms und der Füße am Ring)
- 12x DIN 9021 M4
- 12x DIN 4032 M4
- 12x DIN 4762 M3x8 (Befestigung der Deckel an den Armen und den Füßen)
- 12x DIN 4762 M2x10 (Befestigung von Kameramodulen an den Armen)
- 3x DIN 7997 5x40 Torx (Befestigung der Füße an der Wand)

Ich habe auch eine Alternative für den Winmau-Plasmaring entworfen, der komplett Druckbar ist. Das System ist vollständig kompatibel mit den Armen für den herkömmlichen Ring. Der Fuß ist etwas anders, so müssen Sie sicherstellen, dass Sie die richtige Datei zu drucken.

![alt text](/3d-printing/images/print_assembly_git.png)

Sie müssen die folgenden Dateien für den Ring ausdrucken:

- [6x print_ring_element.stl](stl/print_ring_element.stl)
- [2x print_ring_mount.stl](stl/print_ring_mount.stl)
- [1x print_ring_mount_cable.stl](stl/print_ring_mount_cable.stl) oder [print_ring_mount_cable_groove.stl](stl/print_ring_mount_cable_groove.stl)
- [3x print_foot_webcam.stl](stl/print_foot_webcam.stl)
- [3x plasma_foot_lid.stl](stl/plasma_foot_lid.stl)
- [3x plasma_arm_foot.stl](stl/plasma_arm_foot.stl) oder [plasma_arm_foot_webcam.stl](stl/plasma_arm_foot_webcam.stl)
- [3x plasma_lid.stl](stl/plasma_lid.stl) oder [plasma_lid_webcam.stl](stl/plasma_lid_webcam.stl)

![alt text](/3d-printing/images/print_arm_assembly_git.png)

Darüber hinaus benötigen Sie einen LED-Streifen, der auf die Innenseite des Rings geklebt wird. Sie können einen Schalter hinzufügen, wenn Sie wollen, aber es ist nicht notwendig.

- [1x Led Stripe min. 2,2 Meter Lang](https://www.amazon.de/gp/product/B07TJXZNDZ/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1)
- [1x Schalter](https://www.amazon.de/UEETEK-Streifen-Aus-schalter-Stecker-Schalter-Wie-gezeigt/dp/B077HKVYRY/ref=sr_1_9?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=14UX4NT2N44A4&keywords=inline+an+ausschalter&qid=1641925914&sprefix=inline+an+aus+schalte%2Caps%2)

Ich habe ein neues Armdesign hinzugefügt, das modular aufgebaut ist. Die Oberseite des Arms hat eine Universalhalterung, so dass jeder sein eigenes Gehäuse für sein spezifisches Kameramodul oder Webcam-Board entwerfen kann. Ich werde die Step Datei des Arms beifügen, so dass jeder messen und um ihn herum bauen kann. Das unten gezeigte Beispiel ist für die Arducam Style Cams und kann in dem Ordner mit den anderen stl Dateien gefunden werden.

![alt text](/3d-printing/images/plasma_arm_assembly_modular_git.png)
![alt text](/3d-printing/images/plasma_arm_assembly_modular_git_2.png)

Sie müssen die folgenden Dateien ausdrucken:

- [3x plasma_arm_foot_modular.stl](stl/plasma_arm_foot_modular.stl)
- [3x plasma_foot_webcam.stl](stl/plasma_foot_webcam.stl) oder [print_foot_webcam.stl](stl/print_foot_webcam.stl)
- [3x plasma_foot_lid.stl](stl/plasma_foot_lid.stl)
- [3x plasma_lid_modular.stl](stl/plasma_lid_modular.stl)
- 3x Ihre selbst entworfene modulare Kamerahalterung oder...
- option moertek mc920:
  - [3x modular_webcam_moertek.stl](stl/modular_webcam_moertek.stl)
  - [3x modular_webcam_moertek_lid.stl](stl/modular_webcam_moertek_lid.stl)
  - [3x arm_extender.stl](stl/arm_extender.stl) optional (zur besseren Kalibrierung)

### Download

- [STL Dateien](./stl/)
- [Step Dateien für die modulare Montage](./step/)

Viel Spaß beim Drucken und unterstützt unser Projekt gerne im Discord :)
