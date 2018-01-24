LV08
====

Rad u HxD aplikaciji
--------------------

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1.  Iz **HOME** particije ponovno pokrenuti računalo i u Multiboot
    izborniku odabrati "Other OS and Tools", te zatim "Hiren's Boot CD"
    stavku. Pojaviti će se slijedeći izbornik te je u njemu potrebno
    odabrati „Mini Windows XP“ opciju. Nakon učitavanja „Mini Windows
    XP“ sustava, pojaviti će se radna površina.

2.  Pomoću aplikacije MBRWizard spremiti sadržaj Master Boot Record
    sektora tvrdog diska u datoteku imena **h1.mbr** unutar MBRWIZ3
    direktorija na USB pogonu. Provjeriti sadržaj datoteke kako bi se
    uvjerili da je spremljen ispravan MBR (sa HOME particijom u
    tablici).

3.  Izvaditi USB pogon, ponovno pokrenuti računalo i sa HOME particije
    započeti postupak prebacivanja na A1 particiju. Odmah nakon toga
    priključiti USB pogon u računalo kako bi se pojavio MultiBoot
    izbornik. Odabrati „Hiren's Boot CD“ stavku i zatim „Mini Windows
    XP“ opciju.

4.  Spremiti sadržaj Master Boot Record sektora tvrdog diska u datoteku
    imena **a1.mbr** unutar MBRWIZ3 direktorija na USB pogonu.
    Provjeriti sadržaj datoteke kako bi se uvjerili da je spremljen
    ispravan MBR (sa H3 i A1 particijama u tablici).

5.  Pokrenuti HBCD menu i odabrati izbornik Programs, te zatim
    Editors/Viewers. Unutar izbornika odabrati aplikaciju HxD. Povećati
    prozor do veličine ekrana

6.  U izborniku Extras odabrati opciju Open disk. Koji su svi uređaji
    prikazani? Koja je razlika između kategorija „Logical disks“ i
    „Physical disks“? Kako su povezane te dvije kategorije?

7.  Unutar kategorije „Physical disks“, može li se uočiti jasna razlika
    između tvrdog diska u računalu i USB pogona?

8.  Isključiti opciju „Open as read only“, te iz popisa odabrati prvi
    fizički tvrdi disk u računalu (Physical disks, Hard disk 1). Otvoren
    je prozor sa sirovim sadržajem sektora na tvrdom disku, počevši od
    prvog sektora. Koliko je bajtova zapisano u svakoj liniji (uočiti da
    su adrese linija i bajtova u linijama zapisane u heksadecimalnom
    obliku). Iz izbornika „View“ odabrati opciju „Bytes per row“ te
    upisati prikaz od 16 bajtova po liniji. Uočiti kako je automatski
    prikazan i broj sektora sa desne strane.

9.  Što se nalazi na prvom sektoru svakog tvrdog diska? Zapisati početnu
    i završnu adresu MBR područja tvrdog diska. Prema strukturi MBR
    područja (Master Boot Code, Partition table, Magic number 55AA)
    zapisati početnu i završnu adresu svakog dijela MBR područja.

10. Unutar Master Boot Record područja pronaći područje particijske
    tablice, te iščitati broj particija unutar tablice. Koliki je ukupni
    broj primarnih particija podržanih u particijskoj tablici. Na kojoj
    adresi počinje područje particijske tablice, a na kojoj završava? Za
    svaku particiju u bilježnici zapisati originalan zapis od 16B, te iz
    zapisa izvući osnovne informacije (BootFlag, Partition type ID,
    Početni LBA sektor particije, Broj sektora koje particija zauzima na
    disku, izračunati završni sektor particije). Primjer postupka je
    opisan u uputama za odradu laboratorijskih vježbi, poglavlje 6,
    naslov „Proučavanje prvog sektora tvrdog diska“.

11. Obrisati Master Boot Code područje (prvih 446B Master Boot Record
    područja), zapiši promjene na tvrdi disk, te ponovno pokrenuti
    računalo bez USB pogona u njemu. Što se dogodilo? Zapiši eventualne
    poruke o grešci.

12. Priključiti USB pogon u računalo, ponovno ga pokrenuti, te vratiti
    sadržaj datoteke a1.mbr na MBR tvrdog diska (NE ZABORAVITI **/DISK**
    opciju!!). Pokrenuti HxD te se uvjeriti kako je vraćen MBC dio u
    prvi sektor tvrdog diska.

13. Zamijeniti vrijednost BootFlag zastavice iz 0x80 u 0x00 na prvoj
    particiji, zapisati promjene na tvrdi disk, te ponovno pokrenuti
    računalo bez USB pogona u njemu. Što se dogodilo? Zapiši eventualne
    poruke o grešci.

14. U HxD aplikaciji zamijeniti vrijednost BootFlag zastavice iz 0x00 u
    0x80 na drugoj particiji, zapisati promjene na tvrdi disk, te
    ponovno pokrenuti računalo bez USB pogona u njemu. Što se dogodilo?
    Zapiši eventualne poruke o grešci.

15. Priključiti USB pogon u računalo, ponovno ga pokrenuti, te u
    aplikaciji HxD vratiti originalne vrijednosti BootFlag zastavice
    (0x80 na prvu particiju, 0x00 na drugu).

16. U HxD aplikaciji ostaviti vrijednost BootFlag zastavice na prvoj
    particiji, no isprazniti ostatak sadržaja particijske tablice
    (vrijednost 55 AA ostaviti, jer nije dio particijske tablice!).
    Zapisati promjene na tvrdi disk, te ponovno pokrenuti računalo bez
    USB pogona u njemu. Što se dogodilo? Zapiši eventualne poruke o
    grešci.

17. Priključiti USB pogon u računalo, ponovno ga pokrenuti, te vratiti
    sadržaj datoteke a1.mbr na MBR tvrdog diska (NE ZABORAVITI **/DISK**
    opciju!!). Pokrenuti HxD te se uvjeriti kako je vraćen originalni
    sadržaj u prvi sektor tvrdog diska.

18. Zamijeniti vrijednost Partition Type ID polja iz 0x0C u 0x00 na
    prvoj particiji, zapisati promjene na tvrdi disk, te ponovno
    pokrenuti računalo bez USB pogona u njemu. Što se dogodilo? Zapiši
    eventualne poruke o grešci.

19. Vratiti vrijednost iz prošlog zadatka, no ovaj put zamijeniti
    vrijednost istog polja na drugoj particiji iz 0x07 u 0x00, zapisati
    promjene na tvrdi disk, te ponovno pokrenuti računalo bez USB pogona
    u njemu. Što se dogodilo? Koja je razlika u poruci u odnosu na
    prošli zadatak? Vratiti originalnu vrijednost i zapisati promjene na
    tvrdi disk.

20. Obrisati sadržaj polja početne LBA adrese ( veličina polja je 4
    bajta) prve particije u tablici (H3 particija), zapisati promjene na
    tvrdi disk, te ponovno pokrenuti računalo bez USB pogona u njemu.
    Što se dogodilo? Probati pokrenuti Windows 98, i Windows 7
    operacijske sustave. Zapiši eventualne poruke o grešci. Vratiti
    originalnu vrijednost i zapisati promjene na tvrdi disk.

21. Obrisati sadržaj polja broja sektora particije ( veličina polja je 4
    bajta) prve particije u tablici (H3 particija), zapisati promjene na
    tvrdi disk, te ponovno pokrenuti računalo bez USB pogona u njemu.
    Što se dogodilo? Probati pokrenuti Windows 98, i Windows 7
    operacijske sustave. Zapiši eventualne poruke o grešci. Vratiti
    originalnu vrijednost i zapisati promjene na tvrdi disk.

22. Ponoviti postupak iz 20. zadatka, no ovaj put na drugoj particiji u
    tablici (A1 particija).

23. Ponoviti postupak iz 21. zadatka, no ovaj put na drugoj particiji u
    tablici (A1 particija).

24. Zamijeniti vrijednost zadnja dva bajta u prvom sektoru (magični
    broj) iz 0x55AA u 0x0000 , zapisati promjene na tvrdi disk, te
    ponovno pokrenuti računalo bez USB pogona u njemu. Što se dogodilo?
    Zapiši eventualne poruke o grešci. Vratiti originalnu vrijednost i
    zapisati promjene na tvrdi disk.

25. U aplikaciji HxD označiti kompletan sadržaj prvog sektora tvrdog
    diska,kopirati ga, te zalijepiti na 40. sektor.

26. Ručno obrisati kompletan prvi sektor ( označiti željeni sadržaj, te
    koristiti opciju Fill Selection u Edit izborniku, te odabrati već
    preporučenu vrijednost 00). Ponovno pokrenuti računalo bez
    priključenog USB pogona. Što se dogodilo?

27. Vratiti sadržaj iz 40. sektora u 1. sektor tvrdog diska, zapisati
    promjene i ponovno pokrenuti računalo bez priključenog USB pogona.
    Što se dogodilo? Odabrati podizanje Windows 7 operacijskog sustava i
    utvrditi ispravnost.

28. U izborniku „Extras“ odabrati opciju „Open disk“, te odabrati
    fizički USB pogon (Physical disks, Removable disk 1). Isključiti
    opciju „Open as Readonly“.

29. Nalazi li se na prvom sektoru ispravno MBR područje (mora sadržavati
    Master Boot Code, Particijsku tablicu i na kraju 55AA)? Ako je
    odgovor pozitivan, označiti kompletan sadržaj prvog sektora,
    kopirati ga, te zalijepiti na prvi slijedeći prazan sektor na
    uređaju.

    NAPOMENA : Neki USB pogoni nemaju MBR područje, već se na prvom
    sektoru nalazi Boot Sector, odnosno prvi sektor particije. Sa takvom
    strukturom, USB pogon neće biti prepoznat (od strane BIOS sustava)
    kao USB tvrdi disk, već kao USB Floppy. Razlog tomu je što se na
    disketama mogla nalaziti isključivo jedna particija, te je ona
    zauzimala kompletno područje medija. Početak particije je bio na
    prvom sektoru.

    U tom slučaju , potrebno je aplikacijom Rufus stvoriti MBR strukturu
    na USB pogonu (upute su na mrežno dijeljenom disku), te ponoviti
    postupak Yumi Multiboot instalacije.

30. OVAJ ZADATAK ODRADITI SAMO NA JEDNOM USB POGONU, samo zbog
    demonstracije. ZA ODRADU OVOG ZADATKA OBVEZNO JE IMATI DRUGI
    ISPRAVAN USB POGON. Ručno obrisati kompletan prvi sektor USB pogona,
    te ponovno pokrenuti računalo sa USB pogonom u njemu. Što se
    dogodilo? Pokreće li se MultiBoot izbornik? Zaključi zašto. Ponovno
    pokrenuti računalo sa drugim USB pogonom. Učitati Mini Windows XP
    sustav, te zatim ubaciti drugi USB pogon u računalo. Pokrenuti HxD
    aplikaciju, te vratiti kopiju MBR područja na ispražnjen sektor
    "neispravnog" USB pogona. Provjeriti ispravnost radnje.

    NAPOMENA: Ponekad se događa situacija da se, prilikom vraćanja
    različitih MBR područja pomoću aplikacije MBRWizard, upiše
    neispravna vrijednost "/Disk" opcije, te se kopija spremi na USB
    pogon, umjesto prvi sektor tvrdog diska. U tom slučaju je dobro
    imati pričuvnu kopiju MBR područja USB pogona, kako bi se uređaju
    brzo vratila funkcionalnost. U suprotnom je potrebno ponovno
    stvoriti particiju na uređaju, te ponoviti postupak instalacije YUMI
    Multiboot sustava.

31. Ponovno pokrenuti računalo sa priključenim USB pogonom, te vratiti
    sadržaj datoteke h1.mbr na Master Boot Record tvrdog diska
    (MBRWizard aplikacija), ponovno pokrenuti računalo bez USB pogona.

32. Uvjeriti se u uspješnost podizanja Windows 98 operacijskog sustava
    na HOME particiji.
