Rad sa datotekama
==================


Upoznati se sa pojmovima : pojam datoteke, tipovi datoteka, inode+data strukturu na datotečnom sustavu, hard i soft (simbolički) linkovi

Naredbe koje se koriste u vježbi: nano, touch, cp, mv, rm, ln, file, locate, find, cat, tac, wget, echo (dodati i izvršavanje naredbi sa backtildima)

**Cilj vježbe**:

**Zadaci**:


1.  Premjestiti se u /etc direktorij.

2.  Proučiti manpage naredbe cat. Saznati značenje riječi "concatenate".

3.  Pozvati naredbu cat te kao argument zadati datoteku sa putanjom
    /etc/timezone (ne zaboraviti korištenje autocomplete značajke za
    završavanje putanje).

4.  Ponoviti prethodni zadatak, no putanju napisati sa svim velikim
    slovima (/ETC/TIMEZONE). Svrha zadatka je uočiti osjetljivost
    operacijskog sustava na velika i mala slova. Osjetljivost vrijedi za
    sve vrste datoteka : regularne (tekstualne, binarne, slike,
    kompresirane), direktorije (isto datoteka) te specijalne (blok
    datoteke – npr. diskovi, simbolički linkovi, socketi...).

5.  Pozvati naredbu cat te zadati dva argumenta : /etc/timezone i
    /etc/hostname. Što se dogodilo?

6.  Nad datotekom /etc/shells kao argumentom isprobati naredbe cat , a
    zatim tac. Koja je razlika u prikazu rezultata? Primijetiti razliku
    u imenu te proučiti manpage naredbe tac.

7.  Premjestiti se u ~/Documents direktorij. Stvoriti novu praznu
    datoteku imena TestnaDatoteka.txt koristeći naredbu "touch" te kao
    argument zadati ime datoteke ( naknadno proučiti manpage naredbe
    touch). Uvjeriti se u postojanje datoteke unutar direktorija.

8.  Pozvati naredbu cat sa argumentom datoteke /proc/cpuinfo, no
    rezultat umjesto na standardni izlaz (monitor) preusmjeriti u
    novostvorenu datoteku, koristeći neki od znakova redirekcije
    (Prisjetiti se znakova <, >, <<, >> ).

9.  Proučiti manpage naredbe nano. Pokrenuti nano tekstualni editor sa
    argumentom datoteke TestnaDatoteka.txt. Isprobati osnovno kretanje
    kroz sadržaj datoteke, te zatim pozvati unutarnji izbonik pomoći
    korištenja aplikacije (^G – Get Help opcija označava kraticu. Znak ^
    označava tipku CTRL, dakle kratica je CTRL+G za pozivanje izbornika
    pomoći). U izborniku pomoći proučiti korištenje kratica , te
    značenje znakova ^ i M.

10. Izvježbati slijedeće operacije:

    a. Pozicionirati kursor na početak aktivne linije

    b. Pozicionirati kursor na kraj aktivne linije

    c. Pozicionirati kursor na početak datoteke

    d. Pozicionirati kursor na kraj datoteke

    e. Pretražiti niz znakova "CPU" (bez navodnika)

    f. Ponoviti prethodnu operaciju, no zahtijevati na pretraživanju
       isključivo navedene veličine slova (eng. case sensitivitiy)
       (Pomoć : Case-Sens opcija)

    g. Zamijeniti sve pojave niza znakova "id" sa "ID"

    h. Izreži 10. Liniju, te ju zalijepi iznad 5. linije (Potrebno je
       koristiti kombinacije opcija ^\_ i ^K, odnosno ^U, proučiti u
       izborniku pomoći značenje)

11. Spremiti promjene te izaći iz nano tekstualnog urednika.

    Objašnjenje korištenja kratica na primjeru :

    Gornja opcija služi za izmjenu traženog niza znakova (eng. String) sa nekim drugim željenim nizom.

    Opciju je moguće aktivirati jednom od tri ponuđene metode :

    ^\\ - CTRL+ALTGR+Q ( CodePage 852)

    F14 - Funkcijska tipka F14 se aktivira kombinacijom SHIFT + F2 (S obzirom da uobičajeno tipke završavaju sa F12, sa SHIFT tipkom se
    nastavlja niz)

    M-R – Tipka M predstavlja ili ALT ili ESC (ako se koristi ESC dovoljno je jednom pritisnuti tipku, ne ju držati). Opcija se aktivira
    kombinacijom ALT+SHIFT+R (sve držati pritisnuto) ili ESC,SHIFT+R (ESC jednom pritisnuti, zatim SHIFT+R pritisnuti)

12. Proučiti manpage naredbe cp. Kopirati datoteku TestnaDatoteka.txt u direktorij /tmp pod imenom TestnaDatoteka.BAK. Kopirati cijeli
    direktorij ~/Documents u direktorij /tmp (proučiti opciju -r ili –R, isprobati kopiranje sa i bez korištenja opcije, te zamijetiti
    razliku), uz korištenje opcije o detaljnom prikazivanju postupka (eng. verbose).

13. Proučiti manpage naredbe mv. Premjestiti se u korijenski direktorij. Iz pozicije korijenskog direktorija premjestiti datoteku
    TestnaDatoteka.BAK u direktorij ~/Documents koristeći apsolutne putanje. Preimenovati datoteku TestnaDatoteka.BAK u
    TestnaDatoteka.BKP.

14. Proučiti manpage naredbe touch. Stvoriti novu praznu datoteku imena Vazno.txt. Kopirati datoteku TestnaDatoteka.BKP, kao argument
    odredišta navesti datoteku Vazno.txt. Prikazati sadržaj direktorija sa opcijom prikazivanja veličina datoteka. Što se može zaključiti u
    vezi datoteka Vazno.txt i TestnaDatoteka.BKP?

15. Stvoriti novu praznu datoteku imena Vaznije.txt. Kopirati datoteku TestnaDatoteka.txt, kao argument odredišta navesti datoteku
    Vaznije.txt, no koristiti i opciju "-i" (proučiti svrhu opcije). Što se dogodilo? Koja je svrha opcije?

16. Pomoću naredbe touch stvoriti novu datoteku imena Prvoaprilska\_Sala.txt te ručno izmijeniti datum i vrijeme izmjene
    (eng. modify) te datoteke za 01. Travnja 2017. godine u 15:35 sati (proučiti opciju –t). Provjeriti detalje stvorene datoteke. (touch -t
    201704011535 Prvoaprilska\_Sala.txt)

17. Pomoću naredbe touch stvoriti novu datoteku s imenom Starija\_od\_30\_dana.txt te navesti datum izmjene 35 dana unazad od
    današnjeg dana. (proučiti opciju -d) (touch –d "35 days ago" Starija\_od\_30\_dana.txt)

    NAPOMENA: Pojašnjenje od različitih detalja datoteka,vezano uz datume.

    Postoje 4 različite informacije o datoteci vezano uz datum/vrijeme:

    Creation Time (crtime atribut) - Datum i vrijeme stvaranja datoteke
    na datotečnom sustavu

    Change Time (ctime atribut) - Datum i vrijeme izmjene atributa
    datoteke (npr. dozvole)

    Modify Time (mtime atribut) - Datum i vrijeme izmjene samog sadržaja
    datoteke

    Access Time (atime atribut) - Datum i vrijeme zadnjeg pristupa
    datoteci (nebitno radi li se o čitanju ili pisanju)

    Upotreba stat naredbe na primjeru (kako bi se saznali detalji o
    različitim datumima vezano uz datoteku) :

    Potrebno je primijetiti kako nedostaje informacija o stvaranju datoteke (eng. Birth), te je do nje moguće doći kompleksnijom tehnikom.

    Prvo je potrebno saznati inode broj datoteke:

    Zatim je potrebno pokrenuti naredbu debugfs sa argumentom particije na kojoj se nalazi ta datoteka (bitan korak, s obzirom da su inode brojevi
    unikatni isključivo vezano za particiju/datotečni sustav)

    Unutar debugfs konzole, potrebno je pozvati stat opciju sa argumentom inode broja datoteke.

    Izlazne informacije su vrlo slične prethodnom primjeru korištenja stat naredbe, no u ovom slučaju je moguće vidjeti i datum stvaranja datoteke
    na datotečnom sustavu:

    Pozivanjem naredbe ls sa opcijom –l, prikazat će se vrijeme zadnje izmjene datoteke, što se može vidjeti i u slijedećem primjeru:

18. Pomoću naredbe touch stvoriti novu datoteku s imenom Mladja\_od\_10\_dana.txt te navesti datum izmjene 5 dana unazad od
    današnjeg dana.

19. Proučiti manpage naredbe rm, poglavito opcije -i, -I (veliko i slovo), -r, -f i -v. Unutar direktorija ~/Documents stvoriti novi
    direktorij s imenom "OBRISATI". Premjestiti datoteke TestnaDatoteka.BKP i TestnaDatoteka.txt u direktorij OBRISATI.

20. Obrisati datoteku Vazno.txt

21. Obrisati datoteku Vaznije.txt, no upotrijebiti opciju za potvrdu od strane korisnika prije brisanja i detaljnom prikazivanju postupka.

22. Pokušati obrisati direktorij OBRISATI ne koristeći nijednu opciju. Što se dogodilo? Proučiti koju je opciju potrebno koristiti za
    brisanje direktoriju, te ju upotrijebiti (dodatno upotrijebiti i opciju o detaljnom prikazivanju postupka).

    NAPOMENA : Upotrebom naredbe rm, datoteke (i direktoriji) se brišu
    bez mogućnosti oporavka. U komandnoj liniji ne postoji rješenje
    poput "Recycle Bin",

23. Proučiti manpage naredbe find. (NADOPUNITI TOČNE OPCIJE PROUČAVANJA PREMA SLIJEDEĆIM ZADACIMA)

24.  Pomoću naredbe find pretražiti sve datoteke unutar /etc direktorija.
     (find /etc)

25.  Ponoviti prošli zadatak, no ograničiti se na pretraživanje isključivo /etc direktorija, ne i ostalih poddirektorija u
     strukturi. (find /etc -maxdepth 1)

26.  Pomoću naredbe find pretražiti sve datoteke sa imenom "passwd" unutar /etc direktorija. ( Ne obraćati pažnju na poruke o grešci,
     "access denied", pojam redirekcije errora će biti kasnije obrađen) (find /etc -name passwd)

27.  Stvoriti novu praznu datoteku imena "PAsswd" unutar direktorija ~/Documents.

28.  Pomoću naredbe find pretražiti sve datoteke sa imenom "passwd", a kao putanju zadati dva direktorija : /etc i ~/Documents. (find /etc
     ~/Documents -name passwd)

29.  Izmijeniti prošli zadatak tako da pretraživanje ignorira veličinu slova u imenu. (find /etc ~/Documents -iname passwd)

30.  Pomoću naredbe find prikazati sve direktorije (proučiti opciju -type) unutar /etc direktorija, no ograničiti se na pretraživanje
     isključivo tog direktorija, ne i ostalih poddirektorija u strukturi. (find /etc -type d -maxdepth 1)

31.  Pomoću naredbe find prikazati sve datoteke sa ekstenzijom "conf" unutar /etc direktorija, no isto ograničiti pretraživanje isključivo
     unutar navedenog direktorija, ne i ostalih poddirektorija.

32. Pomoću naredbe find prikazati sve datoteke/direktorije unutar ~/Documents direktorija, koje su starije od 3 dana (za orijentir
    starosti datoteke, koristiti atribut koji se prikazuje prilikom poziva "ls -l", prisjetiti se koji je atribut datoteke vidljiv)
    (find ~/Documents/ -mtime +3)

33. Pomoću naredbe find prikazati sve datoteke unutar ~/Documents direktorija, koje su starije od 35 dana, te pretragu ograničiti
    isključivo na datoteke (podsjetiti se opcije -type).

34. Nadopuniti prethodni zadatak tako da se datoteke, koje odgovaraju uvjetima, kopiraju u direktorij /tmp/BACKUP (potrebno ga je
    prethodno stvoriti). Proučiti uporabu opcije –exec.

    (Pomoć u korištenju, niz znakova {} predstavljaju ime svake datoteke koja odgovara nekom uvjetu. Ponekad je potrebno taj niz staviti u
    jednostruke/dvostruke navodnike kako bi se izbjegli problemi oko obrade znakova. Nadalje, naredba koja se poziva iza –exec opcije
    mora završiti sa znakom ";", te se često mora i zaštititi, odnosno upisati "\\;". Proučiti termin "escaping characters").

    ( find ~/Documents -maxdepth 2 –type f –mtime +3 –exec cp '{}' \\; )

35. Proučiti manpage naredbe locate.

    NAPOMENA : U odnosu na naredbu find, osnovna prednost je brzina
    pretraživanja, s obzirom da se datoteke prethodno i redovno
    indeksiraju (za osvježavanje same baze je odgovorna aplikacija
    updatedb). S druge strane, za razliku od aplikacije find, podaci se
    ne pretražuju u realnom vremenu, već se pretražuje baza sa moguće
    zastarjelim podacima, te je prije svakog korištenja locate naredbe
    dobro osvježiti bazu (updatedb). Nadalje, naredba locate ne nudi
    dodatne filtere za pretraživanje datoteka, niti pozivanje drugih
    naredbi nakon što su izvršeni uvjeti, odnosno, potrebno je uvesti
    druge mehanizme /naredbe kako bi se izvršio željeni proces.

36. Pomoću naredbe locate, potražiti sve datoteke sa imenom "passwd". Nadopuniti zadatak tako da pretraga ignorira veličinu slova.

37. Unutar direktorija ~/Documents stvoriti novu praznu datoteku s imenom "Nova.txt". Pomoću naredbe locate, potražiti sve datoteke s imenom
    "Nova.txt". Što se dogodilo?

38. Osvježiti bazu, te ponoviti prethodni zadatak. Što se promijenilo?


!!! DODATNO !!!

44. Skinuti translator za shell – wget git.io/trans

45. Pogledati tip skinute datoteke – file trans

46. Dodati executable permissions za skinutu datoteku – chmod +x trans

47. Pokušati pokrenuti datoteku – samo upisati ime trans. Neće raditi jer se lokacija ne nalazi na default putanji.

48. Ponovno pokušati pokrenuti datoteku, no upisati lokaciju - ./trans (oznaka trenutnog direktorija i ime datoteke). Upisati primjer neke
    željene riječi za prijevod (potvrditi tipkom enter). Prekinuti izvođenje kombinacijom CTRL-C

49. Pozvati pomoć za korištenje skripte koristeći ime skripte i uobičajeni znak opcije za pomoć.
