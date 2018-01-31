Struktura i rad sa direktorijima
================================

Potrebno pripremiti :

Hijerarhija datotečnog sustava :
https://refspecs.linuxfoundation.org/FHS_3.0/fhs-3.0.pdf

Upoznati se sa pojmovima : Tree struktura , apsolutne i relativne putanje, varijable 

Naredbe koje se koriste u ovoj vježbi: cd, tree, pwd, ls, mkdir, rmdir

**Cilj vježbe**:

**Predradnje**: Potrebno je imati pokrenut virtualni stroj (ili fizički stroj, ovisno o okolini u kojoj se nalazi korisnik) sa odabranom Linux distribucijom (baziranom na Debianu). Korisnik treba biti uspješno prijavljen na sustav, te
                pokrenuti neku aplikaciju za korištenje ljuske sustava (poželjno je koristiti bash okruženje).


**Zadaci**:

1. Proučiti ponuđenu dokumentaciju pozivom na "man hier". Proučiti svrhu
   samo navedenih direktorija:

   a. /

   b. /bin

   c. /boot

   d. /dev

   e. /etc

   f. /home

   g. /media

   h. /mnt

   i. /proc

   j. /root

   k. /sbin

   l. /tmp

   m. /var

   n. /var/log

2. Prikazati vizualnu strukturu korijenskog direktorija koristeći tree
   naredbu ( u slučaju da naredba ne postoji, instalirati ju sa "sudo
   apt-get install tree", sam proces (de)instalacije aplikacije bit će
   objašnjen u kasnijim vježbama). Rezultat naredbe će prikazati iznimno
   detaljnu (kompletnu) strukturu datotečnog sustava, te će proces biti
   dugotrajan.

3. Točno izmjeriti vrijeme trajanja izvršavanja procesa koristeći
   **time** naredbu (samo ju upisati ispred prethodne naredbe).
   Objašnjenje :

   a. real stavka prikazuje ukupno trajanje procesa uključujući i
      vrijeme blokiranja procesa (npr. dok čeka izvršavanje I/O
      operacija)

   b. user stavka prikazuje ukupno vrijeme korištenja procesorskih
      resursa u tzv. "user-mode" načinu rada. Ovo je točno vrijeme
      izvršavanja procesa isključivo vezanu za njegovo izvršavanje.

   c. sys stavka prikazuje ukupno vrijeme korištenja procesorskih
      resursa u tzv. "kernel-mode" načinu rada. U ovo vrijeme ulaze
      operacije kao što su sistemski pozivi.

4. Prikazati vizualnu strukturu korijenskog direktorija koristeći tree
   naredbu, ali samo prvu razinu u dubini strukture (opcija –L, učenici
   neka pročitaj **man** naredbe **tree** i tako saznaju za tu opciju)

5. Prikazati vizualnu strukturu korijenskog direktorija, ovaj puta
   prikazati dvije razine u dubini strukture. Ponoviti zadatak, no ovaj
   puta ograničiti prikaz samo na direktorije.

6. Prebaciti se u **home** direktorij trenutno prijavljenog korisnika
   (dovoljno je samo upisati naredbu **cd** bez argumenata).

   NAPOMENA: Linux sustavi su osjetljivi na velika i mala slova, te paziti prilikom upisivanja imena direktorija i datoteka

7. Ispisati putanju trenutno radnog direktorija (koristiti naredbu
   **pwd**)

8. Prikazati vizualnu strukturu **home** direktorija trenutno
   prijavljenog korisnika i to:

   a. Upotrebom pune putanje

   b. Upotrebom varijable koja predstavlja punu putanju home direktorija

   c. Upotrebom ~ znaka (~ ,izgovara se tilde, znak predstavlja drugu
      varijaciju pune putanje home direktorija korisnika)

   d. Kombinacijom osnovnog **home** direktorija i upotrebom varijable
      koja predstavlja trenutno prijavljenog korisnika (/home/ +
      IME\_KORISNIKA)

    Za prikaz svih varijabli okoline mogu se koristiti naredbe env ili
    printenv (dvije različite aplikacije, no sa sličnom/istom namjenom).

    Primjer i opis varijable:

    SHELL=/bin/bash

    SHELL predstavlja ime varijable,a /bin/bash njenu vrijednost

    Poziv neke varijable se koristi upisom $ znaka i imena varijable
    (npr. $SHELL). Želi li se prikazati vrijednost te varijable, može se
    koristiti standardna naredba echo (npr. pozivom echo $HOME će se
    ispisati putanja home direktorija trenutno prijavljenog korisnika).

9. Prebaciti se u Documents direktorij (unutar home direktorija trenutno
   prijavljenog korisnika) upisivanjem pune putanje. (cd
   /home/KORISNIK/Documents). Primijetiti da je prvo slovo Documents
   direktorija veliko, paziti na sintaksu.

   NAPOMENA: Osnovna razlika između apsolutne/pune i relativne putanje je u upisu prvog znaka u putanji. Ako je prvi znak / (na primjer /etc/dhcp
   putanja), podrazumijeva se kako je prvi direktorij u putanji korijenski, te se radi o apsolutnoj putanji. Ako prvi znak ne sadrži /,
   podrazumijeva se da se želi pozvati direktorij u trenutno radnom direktoriju (na primjer KORISNIK/Documents/Primjeri).

   Drugim riječima apsolutna putanja kreće iz korijenskog direktorija, dok relativna putanja kreće iz radnog direktorija.

   Dodatno, u svakom direktoriju na sustavu se nalaze dva posebna direktorija sa imenima "." i "..", kao što se može vidjeti u slijedećem primjeru:

   Znak "." označava trenutni/radni direktorij, a ".." označava direktorij više razine, odnosno prethodni direktorij u strukturi.

10. Ispisati putanju trenutno radnog direktorija (koristiti naredbu **pwd**). Pozvati naredbu za promjenu direktorija, te za argument
    upisati znak ".". Što se dogodilo (provjeriti ispisom radnog direktorija)? Ponovno pozvati naredbu za promjenu direktorija,no ovaj
    put kao argument upisati znak "..". Što se sad promijenilo ?

11. Vratiti se u home direktorij (/home), no ovaj put koristiti relativnu putanju. Znak koji predstavlja direktorij veće razine su dvije točke
    ".." (bez navodnika, primjer korištenja za vraćanje 4 direktorija iznad : "**cd ../../../..**" ).

12. Prebaciti se u /etc direktorij korištenjem relativne putanje.

13. Prebaciti se nazad u /home/KORISNIK/Documents koristeći značajku automatskog dovršavanja (autocomplete) tipkom TAB. (Upisati cd /h,
    zatim tipku TAB za automatsko dovršavanje imena direktorija,itd...).

    NAPOMENA: U slučaju da autocomplete značajka ne može jednoznačno
    dovršiti upis (recimo, postoje dva objekta koja počinju sa upisana
    dva slova Do, "Documents" i "Downloads"), nakon dva pritiska TAB
    tipke, prikazat će se sva moguća imena koja odgovaraju početnim
    uvjetima.

    Navikavanjem na značajku automatskog dovršavanja imena smanjuje se
    mogućnost pogreške u sintaksi. Ova značajka vrijedi i za izvršne
    datoteke, ne samo za direktorije i obične datoteke.

14. Ispisati sadržaj radnog direktorija. (ls)

15. Pozvati manpage naredbe ls, te proučiti opcije –a (u čemu se
    razlikuje –A opcija?), -l i –h.

16. Stvoriti novi direktorij imena XXYY unutar ~/Documents direktorija.
    (mkdir)

17. Stvoriti 3 direktorija imena RAZINA1, RAZINA2 I RAZINA3. Zadatak je potrebno riješiti jednim pozivom naredbe mkdir, te korištenjem jedne
    od njenih opcija. Koju je opciju potrebno iskoristiti? (proučiti opciju -p)

    Rezultat bi trebao izgledati kao na slici:

18. Ispisati sadržaj direktorija ~/Documents. Zatim dodati redom opcije
    -a, -al, -alh i –alhi , te zabilježiti što se točno promijenilo
    dodavanjem nove opcije. Čemu služi zadnja opcija "-i" (provjeriti
    manpage naredbe ls) ?

    (opcije je moguće pisati posebno, no slova je moguće i spojiti kao
    kombinaciju. Primjer: "ls -a -l -h - -i" je moguće spojiti i u
    slijedeću kombinaciju "ls -alhi". Drugi primjer se najčešće koristi
    iz praktičnih razloga)

19. Vratiti se u home direktorij prijavljenog korisnika te ispisati
    sadržaj direktorija, prvo bez ikakvih opcija, a zatim dodati –alh
    opcije, te uočiti razlike. Što predstavljaju datoteke i direktoriji
    koji počinju sa točkom (ne ubrajajući posebne direktorije "." i
    ".."), zašto se nisu prikazali samo pozivom "ls" naredbe?

20. Ispisati sadržaj /bin direktorija koristeći -l opciju. Dodati još
    zatim i -h opciju. Koja se promjena može uočiti?

21. Premjestiti se u ~/Documents direktorij. Proučiti manpage naredbe
    rmdir (svrhu naredbe, te opcije -p i -v ).

22. Unutar ~/Documents direktorija stvoriti 3 direktorija imena LEVEL1,
    LEVEL2 I LEVEL3 (jedan unutar drugog, kao u jednom od prethodnih
    primjera). Zadatak je potrebno riješiti jednim pozivom naredbe mkdir,
    te korištenjem jedne od njenih opcija.

23. Koristeći naredbu rmdir, obrisati direktorij XXYY.

24. Koristeći naredbu rmdir, obrisati strukturu direktorija sa imenom
    RAZINA u njima. Zadatak je potrebno riješiti jednim pozivom na
    naredbu, te korištenjem jedne od njenih opcija.

25. Ponoviti prethodni zadatak, no ovaj puta za direktorij sa imenom
    LEVEL, te dodati opciju –v. Uočiti razlike u odnosu na prethodni
    zadatak.

    !!! DODATNO !!!

26. Uočiti imena direktorija unutar home direktorija prijavljenog
    korisnika. Pokušati pronaći u kojoj se konfiguracijskoj datoteci
    nalaze postavke stvaranja strukture direktorija svakog novog
    korisnika. Kao filter pretraživanja koristiti ime jednog direktorija
    unutar **home** direktorija prijavljenog korisnika (koristiti grep
    naredbu, rekurzivno, na temelju prvog zadatka zaključiti u kojem se
    direktoriju nalaze konfiguracijske datoteke).

27. Ponoviti prošli zadatak, ali ne ispisivati poruke u grešci
    (redirekcija errora na /dev/null, 2>/dev/null ).
