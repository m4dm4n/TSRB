LV11
====

Instalacija Windows 7 operacijskog sustava
------------------------------------------

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
   računalo bez USB pogona. Uvjeriti se u uspješnost pokretanja TinyCore
   distribucije instalirane u prethodnoj laboratorijskoj vježbi.

4. Staviti instalacijski DVD **Windows 10** operacijskog sustava u DVD
   uređaj,te ponovno pokrenuti računalo. Pritiskom na bilo koju tipku
   potvrditi početak instalacijskog postupka.

5. Instalaciju **Windows 7** sustava izvršiti sa slijedećim parametrima
   i koracima :

a. Engleski jezik, hrvatski oblik prikaza valute i vremena, standardni
   tip tipkovnice

b. Odabrati **Install now** opciju

c. Povrditi **EULA** licencne uvjete

d. Odabrati **CUSTOM** tip instalacije (svježa instalacija Windows
   sustava)

e. **NE PROĆI OVAJ KORAK DOK NASTAVNIK NIJE DOZVOLIO !!!!! RUČNO
   ODABRATI 2H PARTICIJU ( 20GB ) ZA LOKACIJU INSTALACIJE !!!!**

f. Pričekati postupak stvaranja strukture direktorija i prebacivanja
   datoteka na datotečni sustav 2H particije, te završetak instalacije

g. Prilikom informacije "To skip disk checking, press any key within 5
   second(s)", ne dirati tipkovnicu, dopustiti da se izvrši proces
   provjere integriteta datotečnog sustava

h. Odabrati **Customize** opciju

i. Onemogućiti svih 5 ponuđenih opcija i odabrati tipku Next

j. Onemogućiti sve 3 opcije i odabrati tipku Next

k. Ponovno onemogućiti sve 3 opcije i odabrati tipku Next

l. Odabrati opciju "Join a local Active Directory domain"

m. Korisničko ime : **WSxy** (treće radno mjesto računala će imati WS03)

n. Upisati lozinku koja je jednaka korisničkom imenu (paziti na
   mala/velika slova)

o. Ne uključivati Cortana podsustav (Not now opcija)

p. Pričekati neko vrijeme za dovršavanje instalacije

q. Dopustiti otkrivenost računala na mreži

1. Isključiti automatsko obnavljanje zakrpa sustava (u Group Policy
   prozoru)

2. Prema dostupnim uputama izvršiti potrebne korake za postizanje **DUAL
   BOOT** sustava između **TinyCore** sustava na **H13** particiji i
   **Windows 7** sustava na **2H** particiji

3. U korijenskom direktoriju BKP particije stvoriti direktorij imena
   IMAGE. Prekopirati cijeli sadržaj direktorija GHOST na USB pogonu u
   novostvoreni direktorij.

4. Ponovno pokrenuti računalo i u **Multiboot** izborniku odabrati
   "Other **OS and Tools**", te zatim "**Hiren's Boot CD**" stavku.
   Pojaviti će se slijedeći izbornik te je u njemu potrebno odabrati
   „\ **Mini Windows XP**\ “ opciju. Nakon učitavanja „\ **Mini Windows
   XP**\ “ sustava, pojaviti će se radna površina. Pokrenuti aplikaciju
   **Windows Explorer**. U direktoriju **IMAGE** pokrenuti
   **GHOST32.exe** aplikaciju i prema uputama spremiti pričuvne kopije
   **H13** (ime **H13.gho**) i WIN10 (ime **WIN10.gho**) particija.

5. Vratiti se na **HOME** particiju.
