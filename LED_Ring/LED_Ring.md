## A guide to 3d print your own camera arms and led ring 

My arms are designed for use with camera modules like the arducam. The dimensions of the modules are 32x32 mm and the distance of the bores is 28x28 mm. They will not work with modules, which exceed these dimensions!!! However, I designed a version that can be used with webcams using a standard camera thread.

The feet are designed in a way, that they will fit the same bores you drilled for the Winmau Plasma Ring feet.

For use with Winmau Plasma Ring you have the following options:

**Option 1**

![alt text](https://github.com/kriminolle/docs/blob/b6edcddc7f2e7db66fc67923cb3ae580d0773348/LED_Ring/ledRingImages/plasma_assembly_git.png)

You want to use it in combination with my arms and feet. You then need to print the following files:
- 3x plasma_arm_foot.stl
- 3x plasma_foot_webcam.stl
- 3x plasma_lid.stl
- 3x plasma_foot_lid.stl

![alt text](https://github.com/kriminolle/docs/blob/e42b9119635a129260e151d60b1203bfb84ab232/LED_Ring/ledRingImages/plasma_arm_assembly_git.png)

The lid is always optional but highly recommended. It does not only serve aesthetic purposes but also is meant as a safeguard for the camera modules!!!

**Option 2**

![alt text](https://github.com/kriminolle/docs/blob/a98cdf8405e9218550d83dada4886847bcfba8bd/LED_Ring/ledRingImages/plasma_arm_assembly_webcam_git.png)

For use with a webcam with a standard camera mount thread, you need to replace the arm and lid file with
- 3x plasma_arm_foot_webcam.stl
- 3x plasma_lid_webcam.stl

### Bill of Material Autodarts:

- 3x camera module (max. dimensions 32x32mm with bores at 28x28mm)
- 1x Winmau Plasma Ring
- 6x DIN 4762 M4x20 (mounting arm and feet to the ring)
- 12x DIN 9021 M4 
- 12x DIN 4032 M4
- 12x DIN 4762 M3x8 (mounting the lids onto the arms and the feet)
- 12x DIN 4762 M2x10 (mounting camera modules to the arms)
- 3x DIN 7997 5x40 Torx (mounting the feet to the wall)

I also designed an alternative for the Winmau Plasma ring, which is completely printable. The system is completely compatible with the arms for the conventional ring. The foot is slightly different, so you have to make sure to print the correct file. 

![alt text](https://github.com/kriminolle/docs/blob/b6edcddc7f2e7db66fc67923cb3ae580d0773348/LED_Ring/ledRingImages/print_assembly_git.png)

You will need to print the following files for the ring:

- 6x print_ring_element.stl
- 2x print_ring_mount.stl
- 1x print_ring_mount_cable.stl or print_ring_mount_cable_groove.stl
- 3x print_foot_webcam.stl
- 3x plasma_foot_lid.stl
- 3x plasma_arm_foot.stl or plasma_arm_foot_webcam.stl
- 3x plasma_lid.stl or plasma_lid_webcam.stl

![alt text](https://github.com/kriminolle/docs/blob/e42b9119635a129260e151d60b1203bfb84ab232/LED_Ring/ledRingImages/print_arm_assembly_git.png)

In addition, you will need a led stripe that is glued to the inside of the ring. You can add an in-line switch if you want to, but it is not necessary. 

- 1x Led Stripe min. 2,2 meter long [LED Stripe](https://www.amazon.de/gp/product/B07TJXZNDZ/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1)
- 1x In-Line Switch [In-Line Switch](https://www.amazon.de/UEETEK-Streifen-Aus-schalter-Stecker-Schalter-Wie-gezeigt/dp/B077HKVYRY/ref=sr_1_9?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=14UX4NT2N44A4&keywords=inline+an+ausschalter&qid=1641925914&sprefix=inline+an+aus+schalte%2Caps%2)

I added a new arm design, which is built modular. The top of the arm has a universal mount, so anybody can design his own camera mount module for his specific camera module or webcam board. I will include the step file of the arm so everyone can measure and built around it. 

![alt text](https://github.com/kriminolle/docs/blob/0abc800cc7dfb11093a5b73170c6b74c796252d1/LED_Ring/ledRingImages/plasma_arm_assembly_modular_git.png)
![alt text](https://github.com/kriminolle/docs/blob/0abc800cc7dfb11093a5b73170c6b74c796252d1/LED_Ring/ledRingImages/plasma_arm_assembly_modular_git_2.png)

You will need to print the following files:
- 3x plasma_arm_foot_modular.stl
- 3x plasma_foot_webcam.stl or print_foot_webcam.stl
- 3x plasma_foot_lid.stl
- 3x plasma_lid.stl
- 3x your self designed modular camera mount

### Download files

- [.stl files](./stl/)
- [.step file for modular mount](https://github.com/kriminolle/docs/blob/aa7a86ecb28a25d0308a71e305a6c66aafe6adf8/LED_Ring/plasma_arm_foot_modular.stp)

Happy printing and feel free to support our project in the discord :)
