LV07
====

Osnove rada u TinyCore GNU/Linux distribuciji
---------------------------------------------

Nove aplikacije i naredbe korištene u vježbi : pwd, ls, touch, mkdir,
cp, mv, rmdir, rm, cd, file, dd, fdisk

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1. Iz **HOME** particije ponovno pokrenuti računalo i u Multiboot
   izborniku odabrati "Linux Distributions", te zatim "TinyCore" stavku.

2. Upisati pwd (eng. Print Working Directory) naredbu za ispis putanje
   radnog direktorija. Koja je putanja prikazana? Koji znak odjeljuje
   direktorije? Koji znak se koristi u Microsoft Windows sustavima?

3. Upisati naredbu "cd.." (eng. Change Directory, upisati bez navodnika
   i točno onako kako je napisano) za prijelaz u viši direktorij u
   strukturi. Probati napisati "CD .." (između naredbe i argumenta je
   razmak). Koje su poruke ispisane na ekranu nakon obje naredbe?
   Ponovno upisati naredbu, no ovog puta "cd .." . Zašto su u prva dva
   slučaja ispisane poruke o grešci?

    NAPOMENA : U Linux distribucijama bitno je paziti na mala/velika
    slova prilikom poziva naredbi ili datoteka, te je bitno koristiti
    ispravnu sintaksu.

    Naredba opcija argument

1.  Upisati naredbu pwd. Što se promijenilo u odnosu na 2. Zadatak.

2.  Ponovno upisati naredbu za prijelaz u viši direktorij i zatim za
    ispis radnog direktorija. Može li se prijeći u viši direktorij? Kako
    se zove direktorij iznad kojeg nema drugog direktorija, već se svi
    iz njega granaju?

3.  Upisati naredbu za izmjenu direktorija, no bez ikakvih argumenata.
    Je li se radni direktorij promijenio?

4.  Upisati naredbu za prijelaz u **korijenski** (odgovor na pitanje iz
    5. zadatka) direktorij koristeći putanju direktorija. Vratiti se u
    home direktorij korisnika koristeći punu putanju direktorija.

5.  Ispisati sadržaj radnog direktorija naredbom ls (eng. List Directory
    Contents). Što se ispisalo?

6.  Naredbom touch stvoriti praznu datoteku imena "Batman.btm".

7.  Naredbom mkdir stvoriti direktorij imena "SuperHeroji". Ponovno
    ispisati sadržaj radnog direktorija. Što se promijenilo? Može li se
    u ispisu uočiti razlika između datoteke i direktorija?

8.  Naredbom cp kopirati datoteku Batman.btm u direktorij SuperHeroji.
    Provjeri uspješnost radnje.

9.  Naredbom mv preimenovati datoteku Batman.btm u Hulk.avg. Istu
    naredbu upotrijebiti za prebacivanje u direktorij SuperHeroji. Zašto
    se može koristiti ista naredba za dvije različite radnje? Koja je
    razlika između preimenovanja datoteke i micanja? Što se dogodilo sa
    originalnom Batman.btm datotekom?

10. Naredbom rm obrisati datoteku Hulk.avg. Potvrditi sa slovom "y".

11. Naredbom rmdir pokušati obrisati direktorij SuperHeroji. Koja je
    poruka prikazana? Upisati istu naredbu bez ikakvih argumenata. Može
    li naredba obrisati direktorij koji nije prazan?

12. Naredbom rm pokušati obrisati direktorij SuperHeroji. Koja je poruka
    prikazana? Upisati istu naredbu bez ikakvih argumenata i proučiti
    opcije. Saznati što znači termin "recursive". Upotrijebiti opciju -r
    te ponovno pokušati obrisati direktorij. Na svako pitanje odgovoriti
    potvrdno. Koji su koraci naredbe prilikom brisanja direktorija?

13. Stvoriti direktorij Backup\_MBR. Pokušati ući u direktorij
    upisivanjem "cd backup\_mbr". Što se dogodilo? Zašto?

14. Upisati "cd Ba", te zatim stisnuti tipku TAB. Što se dogodilo?

    NAPOMENA : Tipka TAB služi za automatsko dovršavanje poznatih
    naredbi (one koje su definirane u putanjama sustava) ili postojećih
    datoteka/direktorija u radnom direktoriju. Ako postoji više objekata
    koji odgovaraju upisanom uvjetu (iz vježbe npr. Backup i Batman),
    dvostruskim pritiskom na tipku TAB će se prikazati svi objekti koji
    odgovaraju uvjetu.

1. Unutar direktorija stvoriti praznu datoteku home.mbr.

2. Naredbom **file** pokušati saznati informacije o sadržaju datoteke
   home.mbr. Koji je rezultat?

3. Upisati naredbu "tce-load" , te proučiti opciju "-wi".

4. Naredbom "tce-load -wi parted" instalirati aplikaciju Parted
   (PARTition EDitor).

5. Pokrenuti parted aplikaciju i proučiti izgled ekrana. Primijetiti
   promjenu u terminal promptu. Sad je aktivna ljuska od aplikacije.
   Pozvati pomoć od aplikacije prema uputama , te proučiti opcije
   naredbe "print".

6. Upisati naredbu "print devices". Iz prikazanog, koji uređaj je USB
   pogon, a koji je tvrdi disk? Prema čemu je izveden zaključak? Izaći
   iz aplikacije i primijetiti promjenu u izgledu prompta.

7. Pozvati aplikaciju "fdisk" bez argumenata te proučiti opcije. Posebno
   obratiti pažnju na opciju "-l". Svojim riječima opisati svrhu opcije.

8. Upisati "fdisk -l" naredbu. Primijetiti u ispisu /dev/sda i /dev/sdb
   uređaje. Što predstavljaju oznake sda1, odnosno sdb1? Objasniti
   zašto.

    NAPOMENA : Na Unix/Linux distribucijama, sve je prikazano kao
    datoteka. Čak i svi uređaji. Tom logikom su i tvrdi diskovi
    prikazani kao uređaji. Svi uređaji se nalaze u direktoriju /dev
    (eng. DEVices).

    /dev/sda je prvi tvrdi disk u računalu (od prvog do zadnjeg sektora,
    prvi sektor je MBR)

    /dev/sda1 je prva particija na prvom tvrdom disku (ograničena je
    veličinom particije, odnosno prvi sektor datoteke je boot sektor
    particije)

    Drugim riječima, cijela sda1 datoteka je samo dio sda datoteke.

1. Stvoriti dvije prazne datoteke : HOMEbootsectfromSDX.bst i
   HOMEbootsectfromSDX1.bst (slovo X zamijeniti sa slovom uređaja koji
   predstavlja tvrdi disk na sustavu).

2. Koji je početni sektor particije HOME?

3. Naredbom dd spremiti prvi sektor particije sda1 u datoteku
   HOMEbootsectfromSDX1.bst

4. Naredbom dd spremiti 64. sektor tvrdog diska sda u datoteku
   HOMEbootsectfromSDX.bst (s obzirom da se sektori počinju brojati od
   nule, potrebno je preskočiti prva 63 sektora).

5. Naredbom diff (eng. Difference) usporediti dvije datoteke. U slučaju
   da su datoteke iste, aplikacija neće dati nikakav poseban rezultat.
   Što se dogodilo? Koji se zaključak može izvesti iz izvršenih radnji?

6. Spremiti prvi sektor tvrdog diska u datoteku home.mbr.

7. Ponovno naredbom file pokušati saznati informacije datoteke home.mbr.
   Ima li kakvih promjena u odnosu na 19. zadatak? Primijetiti string
   "MS-MBR Windows 7" (MicroSoft-MasterBootRecord , installed by Windows
   7 version). Može li se iščitati struktura particijske tablice? Koliko
   se particija nalazi u njoj, zapisati početne i završne sektore. O
   kojoj se particiji radi?

8. Naredbom file saznati informacije datoteke HOMEbootsectfromSDX.bst.
   Koji je tip sektora? Koji je naziv (eng. Label) particije? Radi li se
   o HOME particiji?

9. DODATI JOS ZADATAKA ZA RESTORANJE HOMEA PREKO Dda, provjere u fdisku
   i vracanje na home.
