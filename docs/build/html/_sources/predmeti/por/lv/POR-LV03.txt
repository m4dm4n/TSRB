LV03
====

Stvaranje Multiboot USB pogona
------------------------------

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1. Spojiti USB pogon sa računalom (Prvi USB port sa desne strane).
   Provjeriti tip datotečnog sustava na prijenosnom mediju. U slučaju da
   nije FAT32, stvoriti datotečni sustav (Format, FAT32).

2. Pokrenuti YUMI multiusb creator:

	a) Odabrati željenu oznaku particije za USB pogon.

	b) Iz ponuđenog popisa , odabrati Linux Mint 32bit.

	c) Kliknuti na Browse opciju te pronaći željenu Linux Mint 32bit \*.ISO datoteku

	d) Kliknuti na Create tipku

	|image0|


Pojaviti će se prozor sa informacijom instalacije Syslinux bootloadera na MBR USB pogona. Potvrditi klikom na tipku YES.

	|image1|

3. Isti postupak ponoviti za Hirens BootCD, Partition Wizard,te
   TinyCore.

4. Kopirati YUMI.PNG sliku u Multiboot (Replace).

5. Kopirati SRW98BIG.IMG u Multiboot direktorij.

6. Ručno dodati slijedeći kod u datoteku SYSTEM.CFG koja se nalazi na
   putanji "\\multiboot\\menu\\system.cfg". Tekst dodati nakon linije sa sadržajem "MENU
   SEPARATOR". Obavezno ostaviti praznu liniju prije ubacivanja koda:

   ::

     label unetbootindefault

     menu label DOS - MS WINDOWS 98

     MENU INDENT 1

     kernel memdisk

     append initrd=/multiboot/srw98big.img


7. Ponovno pokrenuti računalo sa USB pogonom u računalu , te provjeriti
   ispravnost instalacije.

.. |image0| image:: media03/image1.png
   :width: 3.22222in
   :height: 2.54167in
.. |image1| image:: media03/image2.png
   :width: 3.14583in
   :height: 2.04167in
