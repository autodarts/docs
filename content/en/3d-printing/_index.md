---
title: 3D Printing
author: Lars
lang: en
weight: 50
---

Autodarts provides 3D models for the [Winmau Plasma Light](https://winmau.com/plasma-dartboard-light-4300?__cf_chl_tk=PGtC255Z1irSFZJjHqPuQns3DkOSfGvVEftt4Sr9VUo-1676315447-0-gaNycGzNCns).
The Winmau Plasma light has the advantage that the three wall mounts are exactly 120 degrees apart.
We can use the original holes to mount a camera arm to the Winmau Plasma light.

Autodarts does provide 3D models for an entire LED ring to print.

{{<hint type=note icon=gdoc_info_outline >}}
You also can search for printable files on Cults3d and Thingiverse.
{{< /hint >}}


## Camera module sizes

Camera modules come in differnet formats.
The most common formats are 38x38mm (with holes at 34x34mm) and 32x32mm (with holes at 28x28mm).
Sometimes camera modules feature both formats and you can clip off the outer rims to make a 32x32mm module from the 38x38mm original.

Autodarts provides whole arms for 32x32mm modules (or 38x38mm modules with removable rims).
Autodarts also provides modular arms that can be connected to different heads.
In case your camera module does not have removable rims, there is a modular head for 38x38mm modules.

There is also an option to use regular webcams if they feature a standard camera mount thread in their base.

![Camera module measurements](/3d-printing/images/camera_module_measures.jpg)

## Winmau Plasma Light setup

If you have a Winmau Plamsa Light setup at home, you can simply print three camera arms.
Alternatively, you can also print new feet for the Winmau Plasma Light.
A finished Winmau Plasma Light setup may look like this.

![alt text](/3d-printing/images/plasma_assembly_git.png)

### Camera Arms

Which camera arms you need depends on the type of camera that you want to mount.
There are multiple options.

#### 32x32mm modules with 28x28mm holes

This is the original design of the Autodarts arms.
It is only compatible with 32x32mm modules.

![alt text](/3d-printing/images/plasma_arm_assembly_git.png)

Downloads:

- [plasma_arm_32x32.stl](/3d-printing/stl/plasma_arm_32x32.stl)
- [plasma_arm_32x32_lid.stl](/3d-printing/stl/plasma_arm_32x32_lid.stl)

#### Standard webcams

For standard webcams with a camera mount thread, you can use the following arms.

![alt text](/3d-printing/images/plasma_arm_assembly_webcam_git.png)

Downloads:

- [plasma_arm_webcam.stl](/3d-printing/stl/plasma_arm_webcam.stl)
- [plasma_arm_webcam_lid.stl](/3d-printing/stl/plasma_arm_webcam_lid.stl)

#### Modular arm

To make the design a little bit more flexible, there is also a modular version of the arm that does not have a fixed head.

![alt text](/3d-printing/images/plasma_arm_assembly_modular_git.png)

Downloads:

- [plasma_arm_modular.stl](/3d-printing/stl/plasma_arm_modular.stl)
- [plasma_arm_modular_lid.stl](/3d-printing/stl/plasma_arm_modular_lid.stl)

#### 38x38mm modules with 34x34mm holes

For these kinds of modules, you can use the modular arm and the following head.

![alt text](/3d-printing/images/plasma_arm_assembly_modular_git_2.png)

Downloads:

- [modular_head_38x38.stl](/3d-printing/stl/modular_head_38x38.stl)
- [modular_head_38x38_lid.stl](/3d-printing/stl/modular_head_38x38_lid.stl)

#### Moertek MC920

If you have purchased the Moertek MC920 webcams, you can disassemble them and house their modules in this modular head.

Downloads:

- [modular_head_moertek-mc920.stl](/3d-printing/stl/modular_head_moertek-mc920.stl)
- [modular_head_moertek-mc920_lid.stl](/3d-printing/stl/modular_head_moertek-mc920_lid.stl)

### Feet

For the Winmau Plasma Light, there are also alternative feet that you can 3D-print.
The feet feature channels for the cables of the camera modules.
It makes for a neater setup.

Downloads:

- [plasma_foot.stl](/3d-printing/stl/plasma_foot.stl)
- [plasma_foot_lid.stl](/3d-printing/stl/plasma_foot_lid.stl)

### Complete bill of material

You will have to purchase the following hardware:

- 1x Winmau Plasma Light
- 3x compatible camera modules

You will need to print the following models:

- 3x arms
- 3x arm lids
- 3x modular heads (when using modular arm)
- 3x modular head lids (when using modular arm)
- 3x feet
- 3x feet lids

Screws, nuts, and washers:

- 12x DIN 4762 M2x10 screws (mounting camera modules inside the arm or modular head)
- 6x DIN 4762 M4x20 screws (mounting arm and feet to the ring)
- 6x DIN 4762 M4x12 screws (mounting head to the modular arm)
- 12x DIN 9021 M4 washers
- 12x DIN 4032 M4 nuts
- 12x DIN 4762 M3x8 screws (mounting the lids)
- 3x DIN 7997 5x40 screws (mounting the feet to the wall)

## Lars' Autodarts Ring

`@Lars` has also provided a complete 3D LED ring that you can entirely 3D-print.
The design is completely compatible with all arms mentioned above, so you can combine this ring with any of the arms, including the modular arm.
The feet for the Winmau Plasma Light from above are **not** compatible with this ring.
Make sure to print the feet that are linked further down.
A complete setup may look like this.

![alt text](/3d-printing/images/print_assembly_git.png)

![alt text](/3d-printing/images/print_arm_assembly_git.png)

### Pieces

In addition to the arms from above, you will need to print the pieces that make up the ring.

- 3x [ring_foot.stl](/3d-printing/stl/ring/ring_foot.stl)
- 6x [ring_element.stl](/3d-printing/stl/ring/ring_element.stl)
- 2x [ring_mount.stl](/3d-printing/stl/ring/ring_mount.stl)
- 1x [ring_mount_cable.stl](/3d-printing/stl/ring/ring_mount_cable.stl) or [ring_mount_cable_groove.stl](/3d-printing/stl/ring/ring_mount_cable_groove.stl)

In addition to the 3D-prinable pieces, you will need to purchase:

- 1x LED stripe 5m (e.g., [link](https://www.amazon.de/gp/product/B07TJXZNDZ/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1))
- 2x in-line switch (e.g., [link](https://www.amazon.de/UEETEK-Streifen-Aus-schalter-Stecker-Schalter-Wie-gezeigt/dp/B077HKVYRY/ref=sr_1_9?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=14UX4NT2N44A4&keywords=inline+an+ausschalter&qid=1641925914&sprefix=inline+an+aus+schalte%2Caps%2))

Screws, nuts, and washers are the same as for the Winmau Plasma Light setup.

## Contributions

If you want to design your own modular head, you can use the following step file as a basis.

Downloads:

- [modular_head_38x38.stp](/3d-printing/stp/modular_head_38x38.stp)
