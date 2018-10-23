Izvršavanje zadataka
============================

**Zadaci:**

1. Pokrenuti naredbenu ljusku.

2. Pokrenuti naredbu za ispis sadržaja direktorija.

3. Ponoviti prethodni zadatak, no kao argument upisati putanju nepostojećeg direktorija /direktorijNEpostoji.

4. Povezati dvije naredbe u lanac, tako da se nakon ispisa sadržaja direktorija prikaže poruka o uspješnosti radnje.

   POMOĆ: Za povezivanje više naredbi koristi se znak ";". Naredbena ljuska će u liniji sve argumente prije navedenog znaka smatrati jednom naredbom, 
   a nakon znaka nekom drugom naredbom, pa sve do slijedećeg znaka ; (ako postoji).

   PRIMJER: 
   
   echo "Ispis korijenskog direktorija";cd /;ls;echo -en "\n";echo "Ispis korisničkog direktorija";cd;ls
   
   U gornjem primjeru je povezano 7 zasebnih radnji u lanac. Svaka naredba će se izvršiti tek po dovršetku prethodne. Bitno je naglasiti
   kako slijedeća radnja ne ovisi o uspješnom pokretanju prethodne, već je bitno samo da se proces dovrši.
   
   Jedina naredba koju bi bilo dobro objasniti je echo -en "\n". Naredba echo služi za ispis nekog teksta na standardni izlaz,
   dok opcija -e služi za raspoznavanje i interpretaciju backslash znakova **\** (podsjetiti se čemu služi \n kombinacija, do
   značenja je moguće doći i čitanjem manpage echo naredbe), a opcija -n ne dodaje još jedan novi redak nakon izvršavanja naredbe.

5. Povezati dvije naredbe u lanac, no sa prvom naredbom pokušati ispisati sadržaj nepostojećeg direktorija /direktorijNEpostoji, 
   a zatim ispisati poruku o grešci. Ovisi li slijedeća naredba o uspješnosti izvršavanja prethodne?

6. Proučiti manpage naredbe **sleep**. Povezati dvije naredbe u lanac, tako da se nakon 20 sekundi spavanja prikaže na ekranu 
   poruka "BUDJENJE". Kada se izvršila druga radnja?

7. Ponoviti prethodni zadatak, no za vrijeme odbrojavanja nasilno prekinuti proces kombinacijom tipki CTRL+C. Je li se izvršila druga
   radnja? Pokušati zaključiti zašto.

8. 

   POMOĆ: Pomoću operatora && i || je moguće uvjetovati izvršavanje slijedeće naredbe, ovisno o uspješnosti prve. Prvi operator zahtijeva
   uspješan završetak za izvršavanje slijedeće naredbe, dok drugi zahtijeva neuspješan završetak.
   U ovom trenutku je potrebno spomenuti termin kod izlaznog statusa (eng. exit code status). Svaki završetak nekog zadatka ili procesa 
   će rezultirati određenom vrijednošću koda izlaznog statusa . Iako su moguće različite vrijednosti, završetak programa će najčešće 
   rezultirati vrijednošću 0 (ako je program izvršen bez grešaka) ili 1 (ako je program neuspješno izvršen). Općenito gledajući, svaki
   završetak programa sa izlaznim kodom **različitim** od nule podrazumijeva neku grešku.

   http://tldp.org/LDP/abs/html/exitcodes.html
    
   Najjednostavniji način za prikaz izlaznih kodova je korištenje dvije aplikacije (proučiti manpage obje aplikacije): **true** i **false**.
   Varijabla $? prikazuje status zadnje izvršene radnje u ljuski. Ako je više naredbi povezano u lanac, prikazuje se status zadnje
   naredbe u lancu. 
   
   ids@ids2 ~ $ true; echo $?

   0

   ids@ids2 ~ $ false;echo $?

   1

   Nakon osnovnog pojašnjenja izlaznih kodova, mogu se uvrstiti operatori && i ||, čija će funkcija biti najbolje prikazana kroz slijedeća
   četiri primjera.

   ids@ids2 ~ $ true && echo USPJEŠNO
   USPJEŠNO
   
   ids@ids2 ~ $ true || echo NEUSPJEŠNO
   
   ids@ids2 ~ $ false && echo USPJEŠNO
   
   ids@ids2 ~ $ false || echo NEUSPJEŠNO
   NEUSPJEŠNO
   

   Kao što se može uočiti , samo dvije kombinacije će prouzročiti prikazivanje prikladne poruke na standardni izlaz. 

   ZADATAK:
   Dobro proučiti gornje kombinacije dok se ne shvati logika izvršavanja.


9. Ponoviti zadatke 2. i 3., te nakon svakog izvršavanja programa ispisati izlazni status (varijabla $?).

10. Ponoviti zadatke 2. i 3., no koristeći operatore && i ||, ispisati poruke o uspješno ili neuspješno izvršenoj radnji. 

11. Pokrenuti process spavanja od 10 sekundi, te zadatak preusmjeriti u pozadinsko izvršavanje. Što se može prvo uočiti? Treba li
    korisnik čekati završetak procesa?


    POMOĆ: Dugotrajni zadaci se često preusmjeravaju u pozadinsko izvršavanje. Radnja se postiže upisivanjem znaka **&** nakon naredbe procesa. Zadatak se u tom trenutku odvaja od ljuske (eng. fork), 
    te dobiva svoj zasebni broj zadatka (eng. job number) i poseban broj procesa (eng. PID, Process ID). Za pregled aktivnih zadataka se koristi naredba **jobs**. Bez dodatnih opcija, u popisu aktivnih zadataka
    prikazivati će se samo redni broj zadatka (uz prikaz zadane naredbe). Ako se želi prikazati i PID zadatka, potrebno je koristiti i opciju **-l**. Za prekidanje izvršavanja zadatka, koristi se naredba **kill**,
    sa argumentom rednog broja zadatka ili broja procesa.
    Svi primjeri su prikazani ispod. 

    PRIMJER:

    ids@ids2 ~/LINUX_PRIMJERI $ sleep 120 &
    [1] 20712
    
    ids@ids2 ~/LINUX_PRIMJERI $ jobs
    [1]+  Running                 sleep 120 &
    
    ids@ids2 ~/LINUX_PRIMJERI $ jobs -l
    [1]+ 20712 Running                 sleep 120 &
    
    ids@ids2 ~/LINUX_PRIMJERI $ kill %1
    [1]+  Terminated              sleep 120
    
    ids@ids2 ~/LINUX_PRIMJERI $ sleep 120 &
    [1] 20817
    
    ids@ids2 ~/LINUX_PRIMJERI $ kill 20817
    [1]+  Terminated              sleep 120


    Za istovremeno pokretanje više pozadinskih zadataka, umjesto standardnog znaka **;**, koristi se **&** znak. Bitno je naglasiti kako se svi pozadinski procesi izvršavaju samostalno, te ne ovise o završetku prethodnog zadatka.
    Dakle, ovakav način izvršavanja se ne može nazivati vezanjem u lanac. Ovakav način izvršavanja je asinkronog tipa (sinkroni zadaci ovise o prethodnima). Slijedeći primjer će prikazati pokretanje 3 pozadinska procesa sa različitim
    vremenima izvršavanja, te se može primijetiti kako se prvo završavaju zadaci sa najkraćim vremenom izvršavanja.  
    

    PRIMJER:

    ids@ids2 ~/LINUX_PRIMJERI $ sleep 20 & sleep 5 & sleep 10 &
    [1] 24740
    [2] 24741
    [3] 24742

    ids@ids2 ~/LINUX_PRIMJERI $ 
    [2]-  Done                    sleep 5
    [3]+  Done                    sleep 10
    [1]   Done                    sleep 20

    

12. Pokrenuti dva zasebna procesa u pozadini koji će ispisivati sadržaj direktorija (jedan proces neka prikaže sadržaj korijenskog direktorija, a drugi /etc direktorija). Koji proces se prvi izvršio do kraja? Zašto? 

13. Pokrenuti proces spavanja od 60 sekundi. Pauzirati proces, te ga preusmjeriti u pozadinsko izvršavanje. Što se dogodilo sa procesom nakon pauziranja? Vratiti nazad proces u prvi plan.

    POMOĆ: Ako se trenutno aktivan proces želi preusmjeriti u pozadinu, potrebno ga je pauzirati kombinacijom tipki CTRL-Z, te naredbom **bg** (eng. BackGround) poslati u pozadinsko izvršavanje. Suprotna radnja se postiže
    naredbom **fg** (eng. ForeGround).


    PRIMJER:

    ids@ids2 ~/LINUX_PRIMJERI $ sleep 30
    ^Z
    [1]+  Stopped                 sleep 30

    ids@ids2 ~/LINUX_PRIMJERI $ bg %1
    [1]+ sleep 30 &

    ids@ids2 ~/LINUX_PRIMJERI $ jobs
    [1]+  Running                 sleep 30 &

    ids@ids2 ~/LINUX_PRIMJERI $ fg %1
    sleep 30

