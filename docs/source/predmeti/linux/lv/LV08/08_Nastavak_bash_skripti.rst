Nastavak Bash skripti
=====================

Cilj vježbe: U ovoj laboratorijskoj vježbi će se prikazati različiti primjeri upotrebe funkcija uvjetovanja (eng. if function, ), te petlje (eng. for loop). 

Zadaci:


1. Iz komandne linije provjeriti je li proizvoljno upisan broj jednak broju 10. U pozitivnom slučaju prikazati poruku na na zaslonu "Brojevi su jednaki".

   POMOĆ: 

   Funkcija uvjetovanja služi za provjeru različitih uvjeta (postoji li neka datoteka na sustavu, je li broj veći od zadanog, je li skup znakova jednak zadanom skupu, itd). Ovisno o rezultatu te provjere, moguće je izvršiti
   određene željene radnje. Sa korištenjem te funkcije, skripte počinju poprimati određenu kompleksnost jer je potrebno raditi odluke ovisno o rezultatima.

   OPĆENITA SINTAKSA:

   Osnova sintaksa naredbe počinje sa navođenjem funkcije **if**, te zatim nekih uvjeta u uglate zagrade **[  ]** (Između obje zagrade i uvjeta mora postojati razmak. Nakon provjere radnje je potrebno unijeti aktivnost **then** i
   željenu radnju u slučaju ispunjenja uvjeta. **SVAKA** **if** funkcija mora završiti sa izrazom **fi** (obrnuto od **if**).

   Znači osnovna logika je **if->then** (ako je uvjet ispunjen->onda napravi nešto)

   Logiku je moguće nadograditi sa radnjom u slučaju da uvjet NIJE ispunjen, te se ona skraćeno gleda kao:

   **if->then->else->then** (ako je uvjet ispunjen->onda napravi nešto->ako nije ispunjen, napravi nešto drugo)

   Moguće je koristiti i više zasebnih uvjeta, sa slijedećom logikom:

   **if->then->elseif(piše se elif, moguće je koristiti više elif dodatnih uvjeta)->then->else->then**

   Sve tri kombinacije su prikazane u slijedećim općenitim primjerima.

   if [ neki_uvjet ];then neka_radnja;fi

   if [ neki_uvjet ];then neka_radnja;else neka_druga_radnja;fi

   if [ neki_uvjet ];then neka_radnja;elif neka_druga_radnja;elif neka_treca_radnja;else neka_cetvrta_radnja;fi


   UVJETI:

   Uglate zagrade su zapravo referenca na postojeću naredbu **test**, koja je interna naredba bash ljuske. Kao iznimka pravilu za ostale interne naredbe, postoji manpage za test naredbu (no moguće je pristupiti pomoći preko
   help naredbe). Naredba **test** provjerava zadani uvjet, te ovisno o rezultatu daje 0 (Provjera je pozitivna) ili 1 (Provjera je negativna) kao status izvršnog koda. Postoji mnogo različitih uvjeta (pročitati manpage naredbe test),
   no biti će prikazano samo par primjera, kako bi se shvatila osnovna logika.

   -e ime_datoteke 			# Provjera postoji li navedena datoteka. Ne provjerava se tip datoteke (standardna datoteka, direktorij ili specijalna datoteka)
  
   -d ime_direktorija			# Provjera postoji li direktorij.

   -f ime_datoteke			# Provjera postoji li standardna datoteka.

   ime_datoteke1 -nt ime_datoteke2	# Provjera je li prva datoteka novija od druge (eng. Newer Than)

   ime_datoteke1 -ot ime_datoteke2	# Provjera je li prva datoteka starija od druge (eng. Older Than)

   -z skup_znakova			# Provjera je li skup_znakova prazan, odnosno definirana varijabla nema nikakvu vrijednost (eng. Zero characters)

   -n skup_znakova			# Provjera je li neki skup_znakova zapisan, odnosno definirana varijabla ima neku vrijednost (eng. Not zero characters)

   skup_znakova1 = skup_znakova2	# Provjera jesu li dva skupa znakova jednaki

   skup_znakova1 != skup_znakova2	# Provjera jesu li dva skupa znakova različiti

   broj1 -eq broj2			# Aritmetička operacija **jednakosti**	(eng. EQual)

   broj1 -ne broj2			# Aritmetička operacija **nejednakosti** (eng. Not Equal)

   broj1 -lt broj2			# Aritmetička operacija **manje od x** (eng. Less Than)

   broj1 -gt broj2			# Aritmetička operacija **veće od x** (eng. Greater Than)

   broj1 -le broj2			# Aritmetička operacija **manje od x ili jednako** (eng. Less or Equal than)

   broj1 -ge broj2			# Aritmetička operacija **veće od x ili jednako** (eng. Greatere or Equal than)



   Korisnika se potiče da prouči sve moguće uvjete koji se mogu testirati, te da eksperimentira s njima. No, navedeni primjeri su dovoljni kako bi se zadovoljile osnovne pretpostavke znanja i vještina.


   
2. Nadopuniti skriptu iz prethodne vježbe koja će provjeriti broj upisanih znakova iz parametra nakon poziva skripte. Ako parametar uopće nije naveden, upozoriti korisnika da mora unijeti parametar, te zatim automatski prekinuti 
   izvršavanje skripte 


   POMOĆ: Broj upisanih znakova neke varijable je moguće spremiti u drugu. Koristi se slična metoda (prikazana u prošloj vježbi), gdje jedna varijabla poziva vrijednost neke druge varijable ( npr. VARIJABLA2=$VARIJABLA1 ). 
          No, za brojanje broja znakova nekog parametra, potrebno je parametar spremiti u zasebnu varijablu, te novu varijablu koristiti za brojanje znakova.

   PRIMJER SKRIPTE:


   #!/bin/bash

   VARIJABLA1=deset

   VARIJABLA2=$VARIJABLA1

   BROJAC=${#VARIJABLA2}
 
   PARAMETAR=$1

   echo $VARIJABLA1

   echo $VARIJABLA2

   echo $BROJAC

   echo $PARAMETAR

   echo ${#PARAMETAR}

   exit 0



   IZVOĐENJE SKRIPTE:

   ids@ids2 ~/bash_skripte $ ./brojac_znakova.sh osam

   deset
   deset
   5
   osam
   4


3. Nadopuniti skriptu tako da se prije stvaranja direktorija provjerava postoji li već taj direktorij. U slučaju da postoji, ispisati na zaslon prikladnu poruku, u suprotnom nastaviti stvaranje direktorija.


4. Nadopuniti skriptu tako da se u dijelu za unos imena datoteka vrši provjera nalazi li se ta datoteka u direktoriju (pripaziti na putanje gdje zapravo skripta pretražuje te datoteke). U slučaju da tražena datoteka ne postoji, javiti
   sa prikladnom porukom, te zatim ispisati popis datoteka u ciljanom direktoriju i prekinuti izvršavanje skripte uz zapis izlaznog statusa koda vrijednosti 1.

5. Napisati skriptu koja će provjeriti je li neki direktorij prazan. U slučaju da je prazan, javiti prikladnu poruku. Provjeriti uspješnost skripte tako da se provjeri i prazan i ispunjen direktorij.


   POMOĆ: Navedeni primjer može se riješiti testiranjem rezultata naredbe za prikaz sadržaja direktorija **ls**. Pritom je potrebno kombinirati vrijednost rezultata naredbe sa operatorima uspješnosti izvršavanja.

   PRIMJER:

   #!/bin/bash

   [ "$(ls -A $1)" ] && echo "Direktorij nije prazan" || echo "Direktorij je prazan"

   Opis primjera. Gornju liniju je potrebno razdijeliti na tri zasebna dijela :

   a) [ "$(ls -A $1)" ]

	- Sve što se nalazi unutar zagrada [  ] je zapravo pod provjerom. Zagrade su zapravo zamjena za naredbu **test**. Rezultat može biti uspješan ili neuspješan, odnosno izlazni status koda je 0 ili 1.

	- Naredba **ls -A $1** će prikazati sadržaj nekog direktorija (sve datoteke i direktorije, čak i skrivene, osim standardnih **.** i **..** direktorija). Argument $1 je dodan u slučaju ako korisnik želi dodati parametar skripti
	  da se pretraži neki drugi direktorij osim onog u čijem se okruženju izvršava skripta.

	- "$(ls -A $1)" . Znak $ i zagrade se koriste za izvršavanje naredbi i zapis rezultata na standardni izlaz. Ako se ne koriste dvostruki navodnici, rezultat će biti odvojen na zasebne stavke. Drugim riječima, direktorij
	  sa 10 datoteka će imati 10 zasebnih stavki. Tu se javlja problem, jer naredba **test** (u ovom slučaju prezentirana sa uglatim zagradama) uzima samo jedan argument za testiranje, a prezentirano joj je 10. Zbog toga je potrebno
	  rezultat naredbe staviti pod navodnike, kako bi se gledao kao jedan skup znakova, odnosno jedna stavka.

 
   b) && echo "Direktorij nije prazan"

	- Već poznato korištenje operatora, koji u slučaju uspješno izvršene prethodne radnje izvršava neku drugu zadanu radnju (češto poruka o uspjehu)

   c) || echo "Direktorij je prazan"

	- Već poznato korištenje operatora, koji u slučaju neuspješno izvršene prethodne radnje izvršava neku drugu zadanu radnju (često poruka o neuspjehu)

	- Jedini dodatak je što je prikazano da se operatori && i || mogu kombinirati u istoj liniji

6. Prilagoditi i implementirati kod iz prošle skripte u skriptu za pohranu pričuvnih kopija, tako da se prije onemogućavanja izvršavanja datoteka provjeri je li direktorij prazan. U slučaju da je prazan, prethodno kopiranje nije uspješno, te je potrebno
   prijaviti prikladnu poruku i prekinuti izvršavanje skripte uz zapis izlaznog statusa koda vrijednosti 1.

7. Nadograditi skriptu tako da se prikaže popis datoteka i njihov ukupan broj u direktoriju backup_skripti. Potrebno je koristiti **for** petlju. Kod smjestiti nakon dijela koji onemogućava izvršavanja datoteka.

   for;do set_naredbi;done


   Primjeri brojanja:

   for i in {1..10};do echo $i;done

   for i in {10..1};do echo $i;done

   for i in {10..1..2};do echo $i;done


   Primjer korištenja zasebnih stavki neke varijable:

   SUPERHEROJI="Superman Batman Deadpool Frodo";for ime in $SUPERHEROJI;do echo $ime;done


   Primjeri korištenja radnji nad datotekama u nekom direktoriju:

    for file in /direktorij/\*;do cp $file /tmp;done

    for file in /direktorij/\*.sh;do mv $file /direktorij/$fileBAK;done

    for file in /direktorij/\*.sh;do mv $file /direktorij/$(basename -s sh $file)BAK;done

8. Ispisati sadržaj HOME direktorija korisnika. Preusmjeriti izlazni sadržaj u datoteku /dev/null, umjesto na zaslon.

   POMOĆ: Za preusmjeravanje podataka koriste se osnovni operatori za redirekciju <, >, >> . Umjesto na standardni izlaz, podaci se preusmjeravaju na neku drugu lokaciju, recimo u datoteku.

   PRIMJER: 
 
   ls > /home/korisnik/izlaz.txt	# Rezultat naredbe **ls** se preusmjerava u datoteku **izlaz.txt**. Prethodni sadržaj datoteke se briše.

   ls >> /home/korisnik/izlaz.txt	# Rezultat naredbe **ls** se preusmjerava u datoteku **izlaz.txt**. Prethodni sadržaj datoteke ostaje, novi sadržaj se nadopunjuje.

   ls < /home/korisnik/direktorij.txt	# Naredba **ls** kao parametar uzima sadržaj datoteke **direktorij.txt**


   NAPOMENA: Datoteka **/dev/null** je posebna datoteka u sustavu, poznata kao "crna rupa". Sve što se preusmjeri u tu datoteku nestaje. Isto tako je moguće očistiti sadržaj neke datoteke tako da se preusmjeri /dev/null u nju.

9. Ispisati sadržaj nekog nepostojećeg direktorija, te preusmjeriti izlazni sadržaj u datoteku /dev/null. Što se dogodilo? Je li se pojavila koja informacija na zaslonu?

   POMOĆ: Aplikacije komuniciraju sa sustavom pomoću tri različita komunikacijska kanala :

	- Standardni ulaz (eng. Standard input, STDIN)	 	# Kanal preko kojeg aplikacija dobiva neke parametre, najčešće tipkovnica, ili neka datoteka

	- Standardni izlaz (eng. Standard output, STDOUT)	# Kanal preko kojeg aplikacija prikazuje izlazne informacije, najčešće monitor, ili neka datoteka

	- Standardna greška (eng. Standard error, STDERR)	# Kanal preko kojeg aplikacija prikazuje greške prilikom izvođenja, najčešće monitor, ili neka datoteka

   U ovom konkretnom slučaju, ako se koristi samo znak redirekcije **>**, standardno se preusmjerava samo STDOUT tip podataka u datoteku, dok će se STDERR i dalje prikazivati na zaslonu.

   Za upravljanje koji se tip informacije preusmjerava, potrebno je navesti identifikacijski broj :

	- STDOUT = 1

	- STDERR = 2

   PRIMJERI:


   ls /postojeći/direktorij					# Sadržaj direktorija je prikazan na zaslonu

   ls /NEpostojeći/direktorij					# Poruka o grešci je prikazana na zaslonu

   ls /postojeći/direktorij 1>Rezultat.txt			# Sadržaj direktorija je preusmjeren u datoteku Rezultat.txt

   ls /NEpostojeći/direktorij 2>Greška.txt			# Poruka o grešci je preusmjerena u datoteku Greška.txt 

   ls /NEpostojeći/direktorij 1>Rezultat.txt 2>Greška.txt	# Sadržaj direktorija je preusmjeren u datoteku Rezultat, a eventualne poruke o greškama u datoteku Greška.txt

   **ls /Nepostojeći/direktorij >Datoteka.txt 2>&1**		# Često korištena varijacija prethodnog primjera, sve se zapisuje u jednu datoteku. Prvi argument kaže se STDOUT poruke preusmjeravaju u datoteku Datoteka.txt.
								# Slijedeći argument preusmjerava STDERR poruke na lokaciju u koju zapisuje STDOUT.

  

10. Poslati ICMP zahtjev (naredba **ping**) na prvih 10 adresa unutar mreže. Poslati samo jedan ICMP zahtjev po adresi, i čekati samo jednu sekundu prije nego prijeđe na slijedeću. 

11. Izmijeniti prethodni zadatak tako se ne prikazuju nikakve informacije ping naredbe na zaslonu, već samo poruke o uspješno obavljenoj radnji (te poruke ispisati ovisno o uspješno izvršenoj naredbi).



12. Napisati skriptu koja će poslati ICMP zahtjev na prvih 50 adresa unutar mreže (zadane od strane korisnika). Adrese koje odgovaraju na zahtjev zapisati u datoteku. Dodatni uvjeti za skriptu su:

   a) Skriptu spremati u HOME direktorij korisnika ( proučiti i koristiti sistemsku $HOME varijablu okruženja korisnika - popis svih varijabli ispisuje se naredbom **env**, eng. environment)

   b) Ime datoteke se može unijeti kao parametar prilikom pokretanja skripte, ili kao unos za vrijeme izvršavanja skripte

   c) Provjeriti postoji li već takva datoteka, te ako postoji, isprazniti ju ( pomoć : koristiti redirekciju i **/dev/null** datoteku)

   d) Ping naredba treba poslati samo jedan ICMP zahtjev po adresi, i čekati samo jednu sekundu prije nego prijeđe na slijedeću adresu
   
   e) Ne prikazivati nikakve informacije ping naredbe na zaslon, već samo poruke o adresama koje odgovaraju na ICMP zahtjeve

   f) Na kraju skripte ispisati sadržaj datoteke sa popisom aktivnih adresa

 
   POMOĆ: Izgled izvršavanja skripte bi trebao biti otprilike kao u primjeru ispod.

   ids@ids2 ~/bash_skripte $ ./ping.sh 

   Direktorij u koji će se spremati rezultati je /home/ids
   Upiši datoteku u koju će se spremati rezultati: Adrese.txt
   Datoteka već postoji, praznim njen sadržaj
   Upisi mrezni dio IP adrese (npr 192.168.100 ): 192.168.70 
   
   IP adresa 192.168.70.1 odgovara na ICMP upit,zapisujem u datoteku
   IP adresa 192.168.70.11 odgovara na ICMP upit,zapisujem u datoteku
   IP adresa 192.168.70.45 odgovara na ICMP upit,zapisujem u datoteku
   IP adresa 192.168.70.46 odgovara na ICMP upit,zapisujem u datoteku
   
   Aktivne IP adrese su:
   192.168.70.1
   192.168.70.11
   192.168.70.45
   192.168.70.46


13. Napisati skriptu koja će poslati po 2 ICMP zahtjeva svakoj IP adresi iz popisa koji se nalazi u datoteci stvorenoj u prethodnom zadatku. Nije potrebno preusmjeravati rezultate.

14. Poslati ICMP zahtjev (naredba **ping**) na prvih 10 adresa unutar mreže. Poslati samo jedan ICMP zahtjev po adresi, i čekati samo jednu sekundu prije nego prijeđe na slijedeću. Umjesto **for** naredbe, koristiti **while**.

    POMOĆ: **While** petlja je slična **For** petlji, no razlika je u tome što se **For** petlja uglavnom koristi kad se zna koliko će puta biti izvršena. **While** petlja se, s druge strane izvršava sve dok se ne ispuni neki
           određeni uvjet. Točnije, korištenjem **while** petlje, uvjet se testira PRIJE samog izvršavanja, a u **for** petlji, nakon što je izvršen jedan korak.

    BROJ=0				# Obvezno je definirati i postaviti početnu vrijednost varijable

    while [ $BROJ -le 10 ]		# Ovdje počinje **while** petlja. Petlja će se izvoditi sve dok vrijednost varijable BROJ bude manja ili jednaka broju 10. Uvjet se provjerava PRIJE izvršavanja novog koraka
    do 

    echo $BROJ
    (($BROJ++))

    done

15. Ponoviti 13. zadatak, no za to koristiti **while** naredbu umjesto **for**.
