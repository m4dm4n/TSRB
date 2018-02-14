Osnove bash skriptnog jezika
============================

**Cilj vježbe:** Korisnici će u ovoj vježbi biti upoznati sa osnovama izrade bash skripti, kroz različite jednostavnije primjere. Težište će biti na primjerima iz prošlih vježbi (kako bi se korisnici podsjetili na njih), no 
                 biti će prikazani i neki novi praktični primjeri. Vježba bi trebala postaviti osnovne temelje za kasnije nadogradnje, te izradu kompleksnijih skripti. Od korisnika se očekuje fleksibilnost i kreativnost u rješavanju
                 novih izazova.


**Zadaci:**


1. U osnovnom direktoriju korisnika ( ~/home/KORISNIK ) stvoriti direktorij **bash_skripte**.

2. U stvorenom direktoriju iz prethodnog zadatka stvoriti novu praznu datoteku imena **prvi_primjer.sh** (iako ekstenzije nisu nužne,dobro je označavati datoteke radi lakšeg
   raspoznavanja, *.sh ekstenzija je standardna ekstenzija za bash skripte). Ispisati sadržaj direktorija bash_skripte, no bez **.** i **..** direktorija.

   .. hint::
      POMOĆ: Prava pristupa datoteka i direktorija su objašnjene detaljnije u uputama, no za ovu vježbu je bitno raspoznati tri prava pristupa : čitanje (eng. read), 
      pisanje (eng. write) i pokretanje (eng. execute). Da bi datoteka bila izvršna, mora imati aktiviran eXecute bit u pravima. Svaka datoteka ima 10 zastavica, od
      kojih prva zastavica označava tip datoteke (d za direktorij, - za standardnu datoteku, ostala slova za tip specijalne datoteke), a slijedećih 9 prava pristupa raspoređenih
      u tri grupe korisnika na koje se primjenjuju ta prava (vlasnik datoteke, grupa korisnika, sve ostale grupe i korisnici na sustavu). Zastavice su postavljene u 
      rasporedu rwxrwxrwx (Read,Write,Execute). Ako se umjesto slova nalazi znak **-**, znači da ta zastavica nije aktivna, odnosno korisnik/grupa (na kojeg se primjenjuje to pravo)
      neće moći koristiti to pravo. Bitno je napomenuti da se na vlasnika datoteke primjenjuju ovlasti isključivo vezane uz vlasnika, te ostale ovlasti nemaju utjecaj na tog
      korisnika.
      Koncept je najbolje pojasniti na slijedećem primjeru.

   PRIMJER:

   ids@ids2 ~/bash_skripte $ ls -Alh

   -rw-r--r-- 1 ids ids 0 Feb  8 09:29 prvi_primjer.sh

   Za datoteku **prvi_primjer.sh** se može primijetiti kako je prva zastavica **-**, što označava da se radi o standardnoj datoteci (nije direktorij, niti poseban tip datoteke).
   Slijedeće zastavice se odvajaju u tri kategorije :

   rw- (primjenjuje se na vlasnika) - Vlasnik datoteke može **čitati i mijenjati** sadržaj datoteke, no nema pravo izvršavanja.
   
   r-- (primjenjuje se na grupu)

   r-- (primjenjuje se na ostale)



   ids@ids2 ~/bash_skripte $ ./prvi_primjer.sh
   bash: ./prvi_primjer.sh: Permission denied



3. U datoteku upisati slijedeći sadržaj, i zatim spremiti promjene.

   #!/bin/bash

   echo "Welcome to wonderland. Let's continue to see how deep this rabbit hole goes." 
   
4. Pokušati pokrenuti datoteku. Što se dogodilo? Zašto?

   **POMOĆ:** Svaka bash skripta bi trebala početi sa linijom #!/bin/bash koja upućuje na aplikaciju pomoću koje se ta skripta treba izvršiti. Za daljnje informacije 
          proučiti termin "shebang".

   **IZVOR:** https://en.wikipedia.org/wiki/Shebang_(Unix)    

   **POMOĆ2:** Svaka izvršna datoteka koja se ne nalazi u varijabli sa spremljenim putanjama ( varijabla $PATH, varijable su kasnije objašnjene) mora biti pokrenuta sa navedenom
          putanjom te datoteke. Za razliku od Microsoft DOS/Windows operacijskih sustava, putanja radnog direktorija nije implicitna (ne podrazumijeva se), te ju je potrebno
          navesti uz ime datoteke. S obzirom da je ime trenutnog direktorija već spomenut znak točke **.**, potrebno je dodati oznaku **/** da se radi o direktoriju i nakon
          toga navesti ime izvršne datoteke.


   PRIMJER:


   ids@ids2 ~/bash_skripte $ ./prvi_primjer.sh
          

5. Aktivirati execute bit za vlasnika na datoteku prvi_primjer.sh , te ponovno pokušati pokrenuti datoteku. Koji je rezultat? 

   **POMOĆ:** Izmjena prava pristupa neke datoteke vrši se pomoću naredbe **chmod** (proučiti manpage naredbe chmod). Postoje različite mogućnosti na koji način je moguće izmijeniti
          prava pristupa datoteke, te će biti prikazani i objašnjeni najčešći primjeri korištenja.

   **PRIMJER1:** Kao parametre naredbe chmod prvo se upisuje slovo na koga će se postaviti ili maknuti dozvola : u(eng. user owner, vlasnik datoteke), g(eng. group, grupa korisnika),
             o(eng. other, ostali korisnici) i a(eng. all, dozvola utječe na sve korisnike i grupe). Nakon slova se bez razmaka upisuje znak plusa ili minusa za postavljanje,
             odnosno ukidanje dozvole. Zadnji korak prije unosa datoteke/direktorija na koju će se postaviti dozvola je unos slova ili kombinacije slova dozvola. 
 
   **OPĆENITA SINTAKSA:**
 
   chmod [u][g][o][a]+permission(s) filename
   chmod [u][g][o][a]-permission(s) filename

   **KONKRETNA PRIMJENA:**

   chmod u+r datoteka.txt     # Postavlja se dozvola za čitanje vlasniku datoteke datoteka.txt         

   chmod g-rw datoteka.txt    # Ukidaju se dozvole za čitanje i pisanje grupi korisnika za datoteku datoteka.txt
         
   chmod a+rwx datoteka.txt   # Postavljaju se dozvole za čitanje,pisanje i izvršavanje svim korisnicima za datoteku datoteka.txt


   **PRIMJER2:** Mala izmjena iz zadnjeg primjera koja se tiče svih korisnika. U toj situaciji nije potrebno eksplicitno navesti slovo za sve korisnike, već je dovoljno
             navesti jednu ovlast ili kombinaciju koja će se postaviti ili ukinuti


   **OPĆENITA SINTAKSA:**

   chmod +permission(s) filename
   chmod -permission(s) filename

   **KONKRETNA PRIMJENA:**

   chmod +x datoteka.txt     # Postavlja se dozvola za izvršavanje svim korisnicima za datoteku datoteka.txt

   chmod -rwx datoteka.txt   # Ukidaju se sve dozvola svim korisnicima za datoteku datoteka.txt
         

   **PRIMJER3:** U ovom primjeru se uz eksplicitan unos korisnika ili grupe, na koju utječu ovlasti, upisuju točne ovlasti koje se žele primijeniti na njih. Ne unose se znakovi
             za postavljanje/ukidanje, jer se unesene ovlasti direktno primjenjuju bez obzira na prethodno stanje.


   **OPĆENITA SINTAKSA:**

   chmod who=permissions filename

   **KONKRETNA PRIMJENA:**

   chmod g=rw datoteka.txt  # Postavljaju se dozvole za čitanje i pisanje na grupu korisnika za datoteku datoteka.txt. U slučaju da je grupa imala prethodno i dozvolu za izvršavanje,
                              ona u ovom slučaju ne ostaje, nego se briše.
       


   **PRIMJER4:** Zadnji primjer se koristi kod administratora sa iskustvom. Iako se na prvu ruku čini o najkompleksnijoj metodi, sa najmanje upisanih znakova se može postići
             željena kombinacija ovlasti.

             Najbitnije je shvatiti kako su dozvole implementirane, a to je zapis u oktalnom sustavu. Ukupna vrijednost u oktalnom sustavu je 7, i to sa zbrojem 4+2+1.
             U ovom slučaju se radi o zbroju r(4)+w(2)+x(1), zato je praksa uvijek i spominjati dozvole u ovom redoslijedu.

             +-------+-------+
             |OKTALNO|DOZVOLA|         
             +-------+-------+
             |   0   |  ---  |
             +-------+-------+
             |   1   |  --x  |
             +-------+-------+
             |   2   |  -w-  |
             +-------+-------+
             |   3   |  -wx  |
             +-------+-------+
             |   4   |  r--  |
             +-------+-------+
             |   5   |  r-x  |
             +-------+-------+
             |   6   |  rw-  |
             +-------+-------+
             |   7   |  rwx  |
             +-------+-------+

    

     OPĆENITA SINTAKSA: 

     chmod bit_values filename


     KONKRETNA PRIMJENA: 

     chmod 755 datoteka.txt   # Postavljaju se sve dozvole za vlasnika datoteke, te dozvole čitanja i izvršavanja za grupu korisnika i ostale korisnike




6. Nadopuniti skriptu prvi_primjer.sh tako da izgleda prema tekstu ispod. Ponovno pokrenuti skriptu. Što se dogodilo? Koja je svrha naredbe "exit 0" u zadnjoj liniji?

   #!/bin/bash

   echo "Welcome to wonderland. Let's continue to see how deep this rabbit hole goes."

   mkdir Alice

   cd Alice

   touch MadHat.txt

   echo "Done"

   exit 0


7. Nadopuniti skriptu tako da se prije poruke "Done" izbrišu datoteka MadHat.txt i direktorij Alice. Način izvođenja je po volji korisnika, no pokušati riješiti u što manje 
   linija (poželjno u samo jednoj). Ponovno pokrenuti skriptu, te zapisati sve eventualne poruke o greškama. Uočiti ujedno i je li direktorij Alice obrisan. U slučaju da nije,
   pokušati zaključiti zašto.

8. Nadopuniti prvu liniju skripte tako da se iza naredbe bash upiše opcija **-x**, te spremiti promjene. Linija bi trebala izgledati kao u tekstu ispod. Ponovno pokrenuti
   skriptu. Što se može uočiti? Koju funkciju obavlja opcija **-x**?

   #!/bin/bash -x

   POMOĆ: Korištenje opcije -x je u svrhu dijagnostike funkcionalnosti koda i otklanjanja grešaka (eng. debugging). Prije izvršavanja svake linije u skripti, prikazati će se 
          linija sa znakom +, koja će ispisati točnu sintaksu kako ju je interpretirao program za izvršavanje (npr. bash). Zatim se prikazuje rezultat izvršene naredbe, i
          eventualne greške. U slučaju grešaka, moguće je saznati na kojoj je liniji najvjerojatniji problem.

   PRIMJER: Za primjer se koristi prethodna skripta koja bi nakon stvaranja direktorija i datoteke, trebala obrisati iste.

   #!/bin/bash -x

   echo "Welcome to wonderland. Let's continue to see how deep this rabbit hole goes."

   mkdir Alice

   cd Alice

   touch MadHat.txt

   rm -vrI Alice   # u mapage naredbe rm proučiti svrhu opcija -v i -I

   echo "Done"

   exit 0

   REZULTAT:

   ids@ids2 ~/bash_skripte $ ./prvi_primjer.sh 
   + echo 'Welcome to wonderland. Let'\''s continue to see how deep this rabbit hole goes.'
   Welcome to wonderland. Let's continue to see how deep this rabbit hole goes.
   + mkdir Alice
   mkdir: cannot create directory ‘Alice’: File exists
   + cd Alice
   + touch MadHat.txt
   + rm -vrI Alice
   rm: remove 1 argument recursively? Y
   rm: cannot remove ‘Alice’: No such file or directory
   + echo Done
   Done
   + exit 0

   UZROK: Iz navedene greške o nepostojećem direktoriju i prošlih naredbi je moguće zaključiti mogući uzrok. Problem je jedna od prethodnih naredbi "cd Alice" koja postavlja Alice kao radni direktorij, no kasnije nije unesena naredba
          za vraćanje u prethodni direktorij.

   RJEŠENJE: Ili je potrebno koristiti pune putanje direktorija, ili je potrebno dodati naredbu za vraćanje u prethodni direktorij.

9. Izmijeniti postojeću skriptu na način da se uvedu varijable umjesto imena direktorija i datoteke. U skripti se pozivati na te varijable. 

   POMOĆ: U ovim primjerima će biti prikazani osnovni oblici definiranja i pozivanja varijabli. Varijabla se definira tako da se upiše ime varijable, zatim znak jednakosti i na kraju vrijednost varijable. Poziv na varijablu se postiže
          unosom znaka $ i odmah iza tog znaka unos imena varijable. Imena varijabli se često pišu velikim slovima kako bi se isticala unutar skripte, no to nije uvjet. No, imena varijabli su osjetljiva na male i velike znakove,
          te je potrebno obratiti pozornost na takve situacije. Vrlo kvalitetan izvor sa detaljnijim objašnjenjima je ispod.

   IZVOR: https://ryanstutorials.net/bash-scripting-tutorial/bash-variables.php

   PRIMJER SKRIPTE:

   #!/bin/bash -x

   IME=Mirko				#Defiranje skupa znakova, odnosno riječ

   BROJ_1=10				#Definiranje broja

   BROJ_2=3				#Definiranje broja

   KORISNIK_1='$Ime$Broj_1'		#Definiranje varijable koja se sastoji od vrijednosti prethodnih varijabli, no korištenjem jednostrukih navodnika bash ljuska neće prevesti varijable u vrijednost, već
					 će se prikazati doslovno uneseni znakovi (znak $ neće više upućivati na varijablu)

   KORISNIK_2="$Ime$Broj_2"		#Definiranje varijable koja se sastoji od vrijednosti prethodnih varijabli, korištenjem dvostrukih navodnika će se pri ispisu prikazati vrijednosti navedenih varijabli

   KOMBINACIJA_1=Dobar dan		#S obzirom da bash ljuska interpretira ono što je uneseno, riječi odvojene razmakom koje se ne nalaze unutar navodnika se neće ispravno interpretirati, te neće biti prikazane, uz grešku

   KOMBINACIJA_2="Dobar dan"		#Ispravno definirana varijabla 

   KOMBINACIJA_3='Dobar Dan'		#Isto ispravno definirana varijabla, moguće je koristiti jednostruke navodnike, uz gorenavedene uvjetee
   
   NAREDBA_1=`uname -a`			#U varijable je moguće unijeti i rezultate izvršavanja određenih naredbi. Takve naredbe je potrebno staviti unutar jednostrukih stražnjih navodnika (eng. backward single quote, tipka lijevo od 
					 znamenke 1. U tu svrhu se koriste Prilikom poziva na varijablu, prvo će se izvršiti naredba, te će se prikazati rezultat

   NAREDBA_2=`(uname -a;ls)`		#Naredbe je moguće kombinirati. Takve kombinacije se stavljaju unutar standardnih zagrada

   NAREDBA_3=$(echo "NAREDBA 3")	#Moguća je još jedna varijacija, gdje se varijabla definira pozivom na drugu varijablu, koja se zapravo sastoji od izvršavanja neke naredbe. Te naredbe je potrebno staviti unutar standardnih
					 zagrada
  
   echo $IME

   echo $BROJ_1

   echo $BROJ_2

   echo $KORISNIK_1

   echo $KORISNIK_2

   echo $KOMBINACIJA_1

   echo $KOMBINACIJA_2

   echo $NAREDBA_1

   echo $NAREDBA_2

   echo $NAREDBA_3


10. Napisati novu skriptu koja će stvoriti direktorij i datoteku unutar tog direktorija. Ime skripte je novi_direktorij.sh. Ti parametri će se unositi prilikom pozivanja imena skripte, kao dodatni argumenti.


    POMOĆ: 

    PRIMJER SKRIPTE: 


    #!/bin/bash

    echo "Parametri koji se navode prilikom pozivanja skripte označavaju se znakom $ i zatim rednim brojem"

    echo "Prvi parametar je zapravo nulti parametar, a on je uvijek naziv skripte"

    echo "Nulti parametar: " $0

    echo "Ostali parametri se navode nakon unesenog naziva skripte. U slučaju da se parametar sastoji od više riječi, potrebno ga je staviti unutar navodnika."

    echo "Prvi parametar: " $1

    echo "Drugi parametar: " $2

    echo "Treći parametar: " $3

    echo "Četvrti parametar: " $4

    exit 0


    IZVOĐENJE SKRIPTE:

    ids@ids2 ~/bash_skripte $ ./argumenti.sh  1 2 Išao "medo u dućan"

    Parametri koji se navode prilikom pozivanja skripte označavaju se znakom $ i zatim rednim brojem

    Prvi parametar je zapravo nulti parametar, a on je uvijek naziv skripte

    Nulti parametar:  ./argumenti.sh

    Ostali parametri se navode nakon unesenog naziva skripte. U slučaju da se parametar sastoji od više riječi, potrebno ga je staviti unutar navodnika.

    Prvi parametar:  1

    Drugi parametar:  2

    Treći parametar:  Išao

    Četvrti parametar:  medo u dućan


11. Napisati skriptu koja će upitati korisnika za unos nekog podatka, te će taj podatak spremiti u varijablu.

    POMOĆ: Umjesto unosa argumenata prilikom pozivanja skripte, dodatna metoda upita korisnika za unos podatka je korištenje naredbe **read**. Moguće je unijeti više riječi, te ih spremiti u varijablu za daljnje korištenje.
           Dodatne korisne opcije omogućavaju prikaz neke poruke kao upit korisniku (eng. prompt, opcija -p), vremenski limit za unos podatka (eng. timeout, opcija -t), te skrivanje unosa znakova sa tipkovnice (eng. silent, opcija -s).
           Kao i za svaku drugu naredbu implementiranu unutar bash ljuske (eng. builtin command), ne postoji poseban manpage za nju, već je potrebno otvoriti manpage od naredbe bash, te pretraživati cijeli tekst.
           Jednostavniji način je korištenje naredbe **help**. Pozivanjem same naredbe će se ispisati popis svih ugrađenih naredbi bash ljuske (sa kratkim opisom korištenja). Za detaljan prikaz pomoći neke specifične naredbe, potrebno 
           je pozvati naredbu **help**, te kao argument upisati željenu naredbu (u ovom slučaju **read**).

    PRIMJERI: 

    ids@ids2 ~/bash_skripte $ read var;echo $var								# Jednostavan primjer traženja unosa korisnika, spremanja u varijablu **var**, te ispis vrijednosti varijable
    Superman
    Superman

    ids@ids2 ~/bash_skripte $ read -p 'Upiši najdražeg superheroja: ' superhero; echo $superhero		# Zahtjev za unosom od strane korisnika uz dodatnu poruku, te ispis vrijednosti varijable
    Upiši najdražeg superheroja: DeadPool
    DeadPool

    ids@ids2 ~/bash_skripte $ read -sp 'Upiši još kojeg heroja: ' superheroes;echo;echo $superheroes		# Jednak primjer kao i prethodni uz dodatak da je unos korisnik skriven i ne prikazuje se na zaslonu
    Upiši još kojeg heroja: 
    Aquaman Wonderwoman Hulk

    ids@ids2 ~/bash_skripte $ read -t 10 -p 'Upiši zločinca unutar 10 sekundi: ' villain; echo $villain		# Zahtjev za unosom od strane korisnika uz dodatnu poruku i vremensko ograničenje za unos (10 sekundi)
    Upiši zločinca unutar 10 sekundi: Joker
    Joker


12. Napisati skriptu koja će :

		- Unutar direktorija **/home/KORISNIK** stvoriti direktorij **backup_skripti** 
		  (direktorij unijeti kao parametar skripte)

		- Postaviti /home/KORISNIK/bash_skripte direktorij kao radni direktorij

		- Tražiti upit korisnika koje skripte želi spremiti kao pričuvne kopije (spremiti skripte prvi_primjer.sh 
		  i novi_direktorij.sh), te ih spremiti u zasebne varijable

		- Kopirati te datoteke (koristeći varijable) u direktorij **backup_skripti**

		- Isključiti mogućnost izvršavanja pričuvnih kopija skripti

		- Arhivirati direktorij (naredba tar) **backup_skripti** sa gzip kompresijom, arhiva koristi isto ime 
		  direktorija, no koristiti ispravan redoslijed tar i gz ekstenzija

		- Na zaslon ispisivati informacije o izvršavanju svakog koraka, te nakon svake radnje ispisati vrijednost uspješnosti zadnje radnje (sjetiti se funkcije varijable $? iz prethodne laboratorijske vježbe)



   POMOĆ: U skripti slobodno koristiti opciju -x za bash ljusku prilikom dijagnosticiranja funkcionalnosti skripte. Skriptu pisati i testirati korak po korak, te ju tako nadograđivati, radi lakšeg praćenja procesa izvođenja,
          te ispravaka eventualnih grešaka. Ne zaboravljati unositi ispravne parametre i nazive varijabli, jer o njima ovisi ispravno funkcioniranje skripte.
