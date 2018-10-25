LV12
====

Konfiguracija Windows 10 operacijskog sustava
---------------------------------------------

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1. Iz **HOME** particije ponovno pokrenuti računalo i u Multiboot
   izborniku odabrati "Other OS and Tools", te zatim "Hiren's Boot CD"
   stavku. Pojaviti će se slijedeći izbornik te je u njemu potrebno
   odabrati „Mini Windows XP“ opciju. Nakon učitavanja „Mini Windows XP“
   sustava, pojaviti će se radna površina.

2. Spremiti sadržaj Master Boot Record sektora tvrdog diska u datoteku
   imena **h1.mbr** unutar **MBRWIZ3** direktorija na USB pogonu.
   Provjeriti sadržaj datoteke kako bi se uvjerili da je spremljen
   ispravan MBR (sa **HOME** particijom u tablici).

3. Pomoću aplikacije **MBRWIZ** vratiti sadržaj datoteke
   **H132HBKP.mbr** na **MBR** tvrdog diska, te zatim ponovno pokrenuti
   računalo bez USB pogona. Prijaviti se u Windows 10 operacijski
   sustav.

4. Uz pomoć BCD editora , ručno dodati stavku za TinyCore Linux
   distribuciju sa nazivom "TinyCore Linux". Ponovno pokrenuti računalo
   i provjeriti uspješnost podizanja TinyCore Linux distribucije, te se
   zatim vratiti u Windows 10 operacijski sustav

5. Instalirati EasyBCD aplikaciju sa lokacije \\\\IP\_ADRESA\\2h\\por\\appl\\

6. Pokrenuti EasyBCD aplikaciju i proučiti sučelje.

7. Kopirati Hiren's BootCD **iso** datoteku u korijenski direktorij BKP
   particije.

8. Prema dostupnim uputama dodati novu stavku u Boot izbornik Windows 10
   operacijskog sustava s imenom "Hiren's BootCD". Ponovno pokrenuti
   računalo i provjeriti uspješnost podizanja Hiren's BootCD
   distribucije.

9. Na radnoj površini stvoriti direktorij MBRWiz3 i u njega kopirati
   MBRWizard3 aplikaciju i h1.mbr datoteku.
