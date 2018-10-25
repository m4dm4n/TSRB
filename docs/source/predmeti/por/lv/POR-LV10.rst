LV10
====

Instalacija TinyCore operacijskog sustava 
-----------------------------------------

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
   imena **h1.mbr** unutar MBRWIZ3 direktorija na USB pogonu. Provjeriti
   sadržaj datoteke kako bi se uvjerili da je spremljen ispravan MBR (sa
   HOME particijom u tablici).

3. Odabrati radni direktorij MBRFILE na particiji USB pogona. Pomoću
   aplikacije MBRWIZD pregledati sadržaj particijske tablice kja se
   nalazi u datoteci H132HBKP.mbr (/Show opcija). Zapisati osnovne
   informacije svih particija u tablici ( BootFlag, Partition type ID,
   Start Sector, izračunati završni sektor).

   NAPOMENA: Ime datoteke H132HBKP.mbr označava da se u datoteci nalazi
   sadržaj 3 particije (H13 + 2H + BKP)

4. Pomoću aplikacije **MBRWIZ** vratiti sadržaj datoteke
   **H132HBKP.mbr** na **MBR** tvrdog diska, te zatim ponovno pokrenuti
   računalo. U **Multiboot** izborniku odabrati "**System Tools**", te
   zatim "**Partition wizard**" opciju.

5. Provjeriti informacije o particijima na tvrdom disku ( **Partition
   Properties**, **Partition Info**) i usporediti sa dokumentacijom iz
   3. zadatka. Sadržaj se mora poklapati.

6. Ponovno stvoriti FAT32 datotečni sustav (opcija Format) na H13
   particiji. Kao oznaku particije (Partition label) upisati "H13" (bez
   navodnika). Na ostale dvije alocirane particije 2H i BKP, obje
   veličine 20GB, treba postaviti NTFS datotečni sustav.

   Ne zaboraviti **Apply** opciju kao potvrdu.

7. Provjeriti je li H13 particija aktivna ( postavljena BootFlag
   zastavica) i nalazi li se kod 0x0C kao oznaka datotečnog sustava na
   particiji.

8. Izaći iz **Partition Wizard** aplikacije (računalo će se ponovno
   pokrenuti), odabrati "Linux Distributions", te zatim "TinyCore"
   stavku.

9. Instalirati "tc-install" skriptu pomoću tce-load aplikacije

10. Potražiti lokaciju skripte naredbom "find / -name "tc-install.sh"
    (objašnjenje : aplikacija find, pretraživanje počinje od korijenskog
    direktorija /, opcija pretraživanja po imenu -name, unos željenog
    imena kao argument stavljen pod navodnike). Koji rezultat se pojavio
    na ekranu? Može li se uočiti lokacija datoteke?

11. Ponovno upisati liniju iz prošlog zadatka, no na kraju dodati
    "2>/dev/null" (ne upisivati navodnike). Je li došlo do promjene u
    rezultatu? Prikazuju li se poruke o grešci? Mogu li se sad iščitati
    lokacije datoteke "tc-install.sh"?

    NAPOMENA: Područje iz ovog zadatka će biti obrađeno u kasnijim
    vježbama, no u osnovi svaka naredba koja se pokrene rezultate
    prikazuje na standardnom izlazu (eng. standard output, termin koji
    uglavnom podrazumijeva ekran zaslona). S druge strane, standardan
    ulaz (eng. standard input) je uglavnom tipkovnica. Logika se može
    povezati sa programskim jezikom C, u kojem se prije programa mora
    učitati biblioteka stdio.h (#include stdio.h, odnosno STanDard
    Input/Output), kako bi se rezultati tog programa prikazivali na
    ekranu, te kako bi korisnik mogao komunicirati sa programom preko
    tipkovnice.

    No, rezultate bilo koje naredbe/aplikacije je moguće preusmjeriti i
    na neku drugu lokaciju, kao što je datoteka. U tu svrhu se koriste
    znakovi **>** (uvijek prepiši postojeći sadržaj datoteke sa novim )
    ili **>>** (ostavi postojeći sadržaj u datoteci , te samo dodaj
    svježi sadržaj)

    Drugo područje koje je potrebno objasniti su dva tipa standardnog
    izlaza : standard output i standard error. Kao što se može iščitati
    iz samih imena, aplikacija odjeljuje izlazne rezultate prema
    standardnim porukama i porukama o grešci. Svaka poruka o grešci
    (npr. File not found, No permissions, Bad command...) je zapravo
    standard error tip poruke. Pri preusmjeravanju rezultata , razlikuju
    se u identifikaciji brojevima, odnosno 1 označava standard output, a
    2 standard error, što je moguće bolje shvatiti u slijedećim
    primjerima :

    > izlaz.txt preusmjerava standardni izlaz u datoteku izlaz.txt

    1> izlaz.txt preusmjerava standardni izlaz u datoteku izlaz.txt

    2> izlaz.txt preusmjerava standardne greške u datoteku izlaz.txt

    &> izlaz.txt preusmjerava standardni izlaz i standardne greške u
    datoteku izlaz.txt

    Za kraj , /dev/null je posebna vrsta datoteke u Linux sustavima koji
    prihvaća bilo kakav podatak, te ga odbaci. Može ju se smatrati kao
    "crna rupa" za podatke. Svaki podatak koji se preusmjerava u tu
    datoteku nestaje.

    Stoga, primjer iz zadatka "find / -name "tc-install.sh" 2>/dev/null"
    preusmjerava poruke o grešci u /dev/null datoteku koja odbacuje
    iste, te se na standardan izlaz prikazuju samo standardne uspješne
    poruke.

12. Postaviti /usr/local/bin kao radni direktorij (ne prepisivati sve,
    navikavati se na korištenje TAB tipke za autocomplete)

13. Ispisati sadržaj direktorija i pronaći tc-install.sh datoteku.

14. Upisati u naredbenu liniju samo tc-install.sh (ekstenzija **sh**
    označava kako se radi o izvršnoj skripti ljuske, odnosno **SH**\ ell
    skripti, kao što je npr. **BAT**\ ch skripta u MS DOS/Windows
    operacijskim sustavima)

15. Ponoviti prethodni zadatak, no prije imena upisati naredbu sudo za
    pokretanje skripte sa root ovlastima.

16. Odabrati opciju skidanja potrebnih paketa sa interneta (opcija n)

17. Odabrati opciju instalacije 32bitne verzije operacijskog sustava
    (opcija 32)

18. Odabrati opciju Frugal (opcija f) za instalaciju na particiju tvrdog
    diska. Ostale dvije opcije se koriste za instalaciju na USB pogon te
    se cijeli uređaj ponovno particionira u samo jednu particiju (NE
    KORISTITI NIJEDNU OD TIH OPCIJA!!!)

19. Odabrati opciju za instalaciju na particiju (redni broj 2)

20. Pročitati popis ponuđenih particija, no ne nastaviti sa odabirom,
    već nasilno izaći iz skripte koristeći kombinaciju tipki CTRL+c

21. Pozvati aplikaciju "fdisk" sa opcijom "-l" za prikaz svih
    prepoznatih uređaja za pohranu i particija na njima. Prema
    prikazanim informacijama odlučiti koju oznaku ima particija od 258MB
    na koju će se instalirati TinyCore distribucija. Provjeriti
    ispravnost odluke sa nastavnikom i kolegama.

22. Ponoviti radnje od 15.-19. Zadatka. U popisu particija upisati redni
    broj oznake koja odgovara željenoj particiji.

23. Dopustiti instalaciju bootloader programa za podizanje operacijskog
    sustava (opcija y). Bootloader će se instalirati u dva dijela, u
    Master Boot Code područje, te na samu particiju.

24. Kao lokaciju za dodatne pakete navesti putanju **/tmp/tce**

25. S obzirom da je proces postavljanja struktura datotečnih sustava već
    odrađen u Partition Wizard aplikaciji, odabrati redni broj opcije sa
    NONE nazivom.

26. Postaviti boot flag na SDA1 particiju (opcija y).

27. Prepisati žuto označen tekst, kao dodatne opcije bootloadera.

28. Potvrditi instalaciju (opcija y)

29. Ponovno pokrenuti računalo bez USB pogona u njemu, te se uvjeriti u
    uspješnost instalacije operacijskog sustava.

30. Vratiti računalo na HOME particiju, te složiti radno mjesto.
