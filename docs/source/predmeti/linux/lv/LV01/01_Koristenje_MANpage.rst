Korištenje MANpage aplikacije i opcija pomoći raznih aplikacija
===============================================================

**Cilj vježbe**: Svrha vježbe je upoznati korisnike sustava sa metodologijom korištenja različitih mogućnosti pomoći prilikom otkrivanja načina za korištenje nepoznatih opcija aplikacija. S obzirom da se korisnici često nalaze u 
                 situacijama gdje je potrebno postići neke željene radnje sa aplikacijama s kojima nisu dosad imali iskustva (ili su zaboravili točan postupak), iznimno je bitno naučiti metode kako je moguće pomoći sam sebi, te 
                 samostalno otkriti nove funkcije i mogućnosti aplikacija.


**Predradnje**:  Potrebno je imati pokrenut virtualni stroj (ili fizički stroj, ovisno o okolini u kojoj se nalazi korisnik) sa odabranom Linux distribucijom (baziranom na Debianu). Korisnik treba biti uspješno prijavljen na sustav, te
                 pokrenuti neku aplikaciju za korištenje ljuske sustava (poželjno je koristiti **bash** okruženje).

**Zadaci**:


1.  Pozvati manpage bez ikakvih opcija i argumenata, te uočiti rezultat.
    (samo man)

2.  Pozvati pomoć za korištenje manpage aplikacije. Uočiti kako se često
    opcije mogu upisati u skraćenom i punom obliku (-a ili --all). (man
    -h, man --help, man -?)

3.  Pozvati manpage , a u argument upisati ponovno ime aplikacije. Tako
    će se učitati manual za korištenje manpage aplikacije. (man man)

4.  Izvježbati kretanje unutar manuala (isprobati svrhu navigacijskih
    tipki, page up down tipki, space). Uočiti podjelu manuala na
    kategorije (NAME,SYNOPSIS,DESCRIPTION...). Detaljno pročitati
    DESCRIPTION dio za upoznavanje sa svrhom aplikacije, posebno
    obratiti pozornost na brojeve sekcija i njihov opis. Izaći iz
    manpage aplikacije ( tipka q).

5.  Pozvati manpage za aplikaciju passwd ( aplikacija služi za izmjenu
    lozinke korisnika). (man passwd). Uočiti na vrhu zaslona kod imena
    aplikacije dodatan broj upisan unutar zagrade, on označava sekciju
    unutar koje je kategoriziran. Navigirati skroz do dna manpaga do
    odjeljka „SEE ALSO“, te uočiti još jedan manpage sa imenom passwd,
    no sa drukčijim brojem sekcije (broj 5). Izaći iz manpage
    aplikacije.

6.  Pretražiti sve manpage stranice vezane uz riječ passwd (proučiti
    svrhu opcije -**k**, primjer korištenja : "man -k mkdir").

7.  Ponoviti prošli zadatak, no ograničiti pretragu samo na željene
    sekcije 1 i 5 (proučiti svrhu opcije –S, primjer korištenja "man –S
    1,3,7 –k mkdir"). Uočiti kako se u rezultatima nalazi i manpage za
    passwd iz sekcije 5 (File formats) sa opisom "the password file".

8.  Pozvati manpage za opis strukture passwd datoteke. Potrebno je
    prilikom poziva upisati željenu sekciju (primjer korištenja : "man 2
    mkdir"). Proučiti osnovni opis namjene i strukture datoteke, te
    njenu lokaciju.

9.  Pomoću aplikacije man pronaći lokacije manpage dokumenta za riječ
    passwd (proučiti svrhu opcije –w, primjer korištenja : "man –w
    mkdir"). Primijetiti kako je prikazana samo jedna lokacija
    dokumenta, a tiče se passwd aplikacije (broj 1 u imenu passwd.1.gz
    označava kako dokument spada u sekciju 1, a to je "Executable
    programs or shell commands"). Kako bi se saznale lokacije svih
    dokumenata, to je potrebno navesti opcijom (proučiti svrhu opcije
    –a, primjer korištenja : "man –a –w mkdir").

10. Otvoriti manpage dokument direktnim pozivanjem na datoteku. (primjer
    korištenja : "man puna\_putanja\_datoteke").

NAPOMENA: Manpage je samo aplikacija koja učitava pripremljenu
dokumentaciju korištenja različitih aplikacija na sustavu, strukture
bitnih konfiguracijskih datoteka, sistemskih funkcija... Neke
dokumentacije u sebi sadrže i primjere korištenja, no sama ideja
sadržaja je više tehničke naravi, a ne detaljnih uputa za korištenje.

No, bez obzira, radi se o aplikaciji koja je uglavnom prva točka za
pomoć korištenja i upoznavanja različitih izvršnih ili konfiguracijskih
datoteka, te servisa.

11. Postaviti korijenski direktorij kao radni direktorij, te prikazati njegov kompletan sadržaj (prisjetiti se kako su sakrivene datoteke na datotečnom sustavu). Koju opciju je potrebno koristiti?

12. Iz korijenskog direktorija, prikazati sadržaj /etc direktorija, s uvjetima da se prikazuje kompletan sadržaj, sa detaljima svake stavke (dozvole, vlasnik, veličina, datum i vrijeme izmjene...), te veličinom datoteka prikazanom
    u ljudski čitljivom obliku.

13. Iz korijenskog direktorija prikazati sadržaj **Documents** direktorija korisničkog **/home** direktorija. Upotrebom kombinacije opcije postići slijedeće:

    - Prikazati kompletan sadržaj direktorija, osim ugrađenih **.** i **..** direktorija
    - Prikazati detalje svake stavke direktorija
    - Prikazati veličine u ljudski čitljivom obliku
    - Prikazati sve poddirektorije (rekurzivni prikaz)


