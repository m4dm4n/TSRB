LV09
====

Rad u GNU/Linux Fdisk aplikaciji
--------------------------------

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1.  Iz **HOME** particije ponovno pokrenuti računalo i u Multiboot
    izborniku odabrati "Other OS and Tools", te zatim "Hiren's Boot CD"
    stavku. Pojaviti će se slijedeći izbornik te je u njemu potrebno
    odabrati „Mini Windows XP“ opciju. Nakon učitavanja „Mini Windows
    XP“ sustava, pojaviti će se radna površina.

2.  Spremiti sadržaj Master Boot Record sektora tvrdog diska u datoteku
    imena **h1.mbr** unutar MBRWIZ3 direktorija na USB pogonu.
    Provjeriti sadržaj datoteke kako bi se uvjerili da je spremljen
    ispravan MBR (sa HOME particijom u tablici).

3.  Pomoću aplikacije MBRWIZ3 ispisati popis particijskih tablica, te
    zapisati osnovne informacije HOME particije (BootFlag, Partition
    type ID, Početni LBA sektor particije, Broj sektora koje particija
    zauzima na disku, izračunati završni sektor particije)

4.  Izvaditi USB pogon, ponovno pokrenuti računalo i sa HOME particije
    započeti postupak prebacivanja na A1 particiju. Odmah nakon toga
    priključiti USB pogon u računalo kako bi se pojavio MultiBoot
    izbornik. Odabrati "Other OS and Tools", te zatim "Hiren's Boot CD"
    stavku. Pojaviti će se slijedeći izbornik te je u njemu potrebno
    odabrati „Mini Windows XP“ opciju.

5.  Spremiti sadržaj Master Boot Record sektora tvrdog diska u datoteku
    imena **a1.mbr** unutar MBRWIZ3 direktorija na USB pogonu.
    Provjeriti sadržaj datoteke kako bi se uvjerili da je spremljen
    ispravan MBR (sa H3 i A1 particijama u tablici).

6.  Pomoću aplikacije MBRWIZ ispisati popis particijskih tablica, te
    zapisati osnovne informacije H3 i A1 particija (BootFlag, Partition
    type ID, Početni LBA sektor particije, Broj sektora koje particija
    zauzima na disku, izračunati završni sektor particije)

7.  Ponovno pokrenuti računalo sa priključenim USB pogonom. U
    "Multiboot" izborniku odabrati Linux distributions, te zatim "Linux
    Mint" operacijski sustav

8.  Pokrenuti aplikaciju Terminal (gnome-terminal). Pokrenuti novi
    terminal , ovaj put kao root korisnik (ALT+F2, upisati "gksu
    gnome-terminal", bez navodnika). Koja je razlika između dva Terminal
    prozora?

9.  Upisati u oba prozora naredbu "whoami" i uočiti razliku (za pomoć
    oko aplikacije upisati "man whoami"). **Zatvoriti prozor Terminala
    koji je pokrenut pod pravima "root" korisnika (upisati "exit").** U
    budućnosti ne koristiti Terminale učitane sa pravima root korisnika,
    već koristiti "sudo" aplikaciju prilikom potrebe postizanja prava
    root korisnika.

10. U terminalu proučiti manual naredbe fdisk(man fdisk). Detaljno
    proučiti DEVICES, DISK LABELS i OPTIONS poglavlja.

11. Ispisati popis i sadržaj particijskih tablica uređaja za pohranu
    pomoću fdisk naredbe. Što se dogodilo?

12. Ponoviti prošli zadatak, no ovaj puta s pravima root korisnika
    (naredba sudo). Koje uređaje je aplikacija prepoznala?

13. Prepoznati "device id" unutarnjeg hard diska te pokrenuti fdisk
    aplikaciju (s pravima root korisnika, koristiti **sudo**), a kao
    parametar navesti "device id". Obavezno unijeti opciju za
    kompatibilnost sa DOS tipom operacijskog sustava ( -c=dos ).

    NAPOMENA : Primijetiti kako se izgled naredbenog terminala
    promijenio, te je sad aktivan prompt of fdisk aplikacije. U
    aplikaciji su dozvoljena isključivo slova za odabir opcija (navedeno
    u slijedećem zadatku). Bitno je paziti na okolinu u kojoj se
    korisnik nalazi, te koristiti one mogućnosti koje su mu dopuštene u
    toj okolini. Na primjer, nije moguće unutar fdisk aplikacije upisati
    "sudo reboot", te očekivati ponovno pokretanje računala. Fdisk
    aplikacija će prepoznati isključivo prvo slovo "s", te aktivirati
    opciju koju podržava. U tom konkretnom slučaju, aktivirati će se
    opcija "Create a new empty Sun disklabel" na MBR području tvrdog
    diska, odnosno postići će se neželjen efekt radnje.

    Bitno je paziti što se radi, te imati kontrolu nad situacijom

14. Pozvati pomoć unutar aplikacije i detaljni proučiti slijedeće opcije
    : **a, d, n, p, q, t, w.**

15. Ispisati sadržaj particijske tablice hard diska.

16. Obrisati sve unose iz particijske tablice, te kreirati nove prema
    specifikacijama HOME particije. **PROVJERITI adrese i usporediti ih
    sa dokumentacijom!**

17. Potvrditi (zapisati) unesene promjene. Ponovno pokrenuti računalo (
    sudo reboot), te izvaditi USB pogon iz računala. Uvjeriti se kako je
    učitana HOME particija.

18. Ponovno pokrenuti računalo sa priključenim USB pogonom. U
    "Multiboot" izborniku odabrati Linux distributions, te zatim "Linux
    Mint" operacijski sustav

19. U GNU/Linux fdisk aplikaciji obrisati sve unose iz particijske
    tablice, te kreirati nove prema specifikacijama A1 particije.
    **PROVJERITI adrese i usporediti ih sa dokumentacijom!**

20. Potvrditi (zapisati) unesene promjene. Ponovno pokrenuti računalo (
    sudo reboot), te izvaditi USB pogon iz računala. Uvjeriti se kako je
    učitana A1 particija.

21. Vratiti računalo na HOME particiju.

    **ZA DOMAĆU ZADAĆU DETALJNO PROUČITI I OBJASNITI "DOS COMPATIBILITY"
    OPCIJU U ELABORATU. OBVEZNO NAVESTI IZVORE INFORMACIJA ( linkovi sa
    interneta, članci iz časopisa, knjige... )**
