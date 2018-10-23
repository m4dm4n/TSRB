Upravljanje paketima
====================

Priprema: Upoznati se sa pojmovima : repozitorij, paketi, zavisnost (eng. dependency) paketa, izgradnja paketa iz izvorišnog koda (eng. building from source). Dodatno, upoznati se sa različitim tipovima paketa (minimalno .deb i .rpm),
          te upraviteljima paketa (apt, apt-get i aptitude za distribucije bazirane na .deb paketima, te yum za .rpm bazirane distribucije). Upoznati čemu služi Synaptic Package Manager.

Uvod: Laboratorijska vježba je predviđena za rad u GNU/Linux Mint Debian Edition 2 distribuciji (verzija 8.10, codename Jessie). S obzirom da pripada grani Debian distribucija, u vježbi će se upravljati .deb tipovima paketa.

Cilj vježbe: Korisnik će biti upoznat sa osnovnim radnjama upravljanja paketima na Debian baziranoj distribuciji. Osnovne radnje podrazumijevaju :

	- pretraživanje dostupnih paketa
	- instalacija paketa
	- prikaz detalja o paketu (opis i svrha, verzija, zavisnost o drugim paketima)
	- deinstalacija paketa


            Navedene radnje biti će opisane u alatima sa grafičkim sučeljem (Software Manager i Synaptic Package Manager), te iz komandne linije (dpkg, apt i aptitude). Korisnik će saznati kako pronaći lokacije instaliranih paketa
            na računalu. Na kraju, korisnik će sa interneta preuzeti izvorišni kod neke aplikacije, te iz nje ručno izgraditi binarne (izvršne) datoteke, popularan termin za takvu radnju je "build from source".

Zadaci:

1. Pokrenuti Software Manager aplikaciju. Proučiti koliko ima dostupnih paketa za instalaciju.

2. Potražiti paket Zenmap. U kojoj se kategoriji nalazi? Koja je funkcija paketa? Proučiti na koju aplikaciju se nadovezuje, te proučiti detalje te aplikacije. Instalirati Zenmap, te ga i pokrenuti. Jesu li postupci uspješni?

3. Unutar Software Manager aplikacije, deinstalirati Zenmap.

4. Pokrenuti Synaptic Package Manager aplikaciju. Detaljno pročitati uvodnu poruku i eventualno zapisati bitne informacije. Proučiti izgled sučelja i usporediti sa Software Manager aplikacijom. Postoje li kategorije u Synaptic Package
   Manager aplikaciji? Pokušati instalirati Zenmap aplikaciju. Koji su koraci potrebni za navedeni postupak?

5. Nakon što je **Zenmap** instaliran, otvoriti **Properties** prozor, te proučiti kartice **Dependencies** i **Installed files**. O kojim paketima je zavisna aplikacija? Koji je preporučeni paket prilikom korištenja Zenmap aplikacije
   (Recommends stavka)? Saznati koja je funkcija preporučene aplikacije (informaciju je moguće naći unutar Synaptic PM sučelja). U koji direktorij je instalirana sama binarna (izvršna) datoteka Zenmap aplikacije(informacija se nalazi
   unutar **Installed files** kartice)?

6. Pokrenuti Software Manager aplikaciju. Koji je status Zenmap aplikacije u tom sučelju, te mogu li se pronaći detalji o zavisnosti o drugim paketima, ili neke druge informacije koje se nude u Synaptic PM sučelju? Slobodno ugasiti
   Software Manager i Synaptic PM aplikacije.

7. Iz komandne linije proučiti manpage aplikacije dpkg (dovoljno je pročitati odlomke NAME i DESCRIPTION za osnovni opis). Pozvati help od aplikacije dpkg, te saznati koja se opcija koristi za prikaz detalja statusa nekog paketa.
   Pomoću **dpkg** saznati detalje o aplikaciji **zenmap**. Sa čime se mogu usporediti prikazani detalji u odnosu na prethodno iskustvo?

8. Prikazati na zaslonu popis svih paketa na računalu (potražiti koja opcija dpkg aplikacije nudi takvu funkcionalnost). Preusmjeriti izlazne podatke te naredbe u ulazne podatke naredbe **less** (proučiti manpage naredbe **less** i **more**).
   Potražiti nalazi li se u popisu Zenmap aplikacija.

   POMOĆ: Dodatak operatorima za redirekciju iz prethodne vježbe je cijevni operator **|** (eng. pipe). Svrha ovog operatora je preusmjeriti rezultate neke naredbe kao ulazne parametre za drugu naredbu.

   PRIMJER:

   ids@ids2 ~ $ ls
   Adrese.txt  backup  backup_skripti  backup.tar.gz  bash_skripte  cookies.txt  core  Desktop  Documents  Downloads  LINUX_PRIMJERI  Music  Pictures  Public  Templates  Videos

   ids@ids2 ~ $ ls | grep "backup"
   backup
   backup_skripti
   backup.tar.gz

   ids@ids2 ~ $ ls | grep "backup" | grep "tar"
   backup.tar.gz



   U gornjem primjeru je prikazan sadržaj korisničkog HOME direktorija pomoću naredbe **ls**. U slijedećem primjeru je postupak ponovljen, no ovog puta je rezultat naredbe **ls** preusmjeren kao ulazni podatak standardne naredbe
   za filtriranje **grep**. S obzirom da je definiran filter "backup", iz cjelokupnog popisa, prikazati će se samo one linije koje u sebi sadrže riječ "backup". Potrebno je napomenuti, bez obzira što je rezultat naredbe **ls** prikazan
   u jednoj liniji, svaka stavka je zapravo zasebna i gleda se kao da se nalazi u posebnoj liniji (što se može provjeriti i kompleksnijim primjerom "ls -alh", gdje je svaka stavka u zasebnoj liniji). Zadnji primjer se u praksi ne koristi
   na taj način, te je stavljen samo kao pokazni primjer preusmjeravanja rezultata druge naredbe kao ulazni podatak posljednje naredbe. Moguće je povezati u lanac mnogo takvih kombinacija.

9. Prikazati na zaslonu popis svih paketa pomoću naredbe **dpkg**, no upotrijebiti filter tako da se prikazuje samo linija sa Zenmap aplikacijom.

10. Pomoću **dpkg** naredbe obrisati Zenmap paket sa sustava (saznati koja se opcija koristi u tu svrhu).

11. Proučiti manpage naredbi apt-get (bitne opcije su **update**, **upgrade**, **install**, **remove**, **purge** i **autoremove**) i apt-cache (bitne opcije
    su **showpkg** i **search**). Pomoću naredbe apt-get sinkronizirati lokalnu bazu paketa sa online repozitorijem. Nakon sinkronizacije, upisati naredbu za
    nadograđivanje verzije paketa, no NE nastaviti sa nadogradnjom, već prekinuti proces nakon ponude. Koliko paketa je moguće nadograditi, i koliko je potrebno
    podataka preuzeti sa interneta?

12. Pomoću naredbe apt-cache pretražiti bazu za paket sa imenom **zenmap**. Je li radnja bila uspješna? Prikazati detalje u spomenutom paketu (opcija showpkg).

13. Pomoću naredbe apt-get , instalirati paket iz prethodnog zadatka. Je li radnja bila uspješna? Može li se instalirati paket sa standardnim korisničkim
    ovlastima?

    NAPOMENA: Uz apt-get, koriste se i upravitelji aptitude i apt. Apt je trenutno najmodernije rješenje koje zamjenjuje obje apt-get i apt-cache naredbe.
              Sintaksa je jednostavnija, te je pregled informacija o izvršavanju procesa čitkiji. Iako je apt-get/apt-cache kombinacija još uvijek najčešća
              u primjeni (ujedno i razlog zašto se koristi u ovoj vježbi), korisnika se potiče da se educira na modernijoj implementaciji **apt**. 

14. Pomoću naredbe apt-get obrisati Zenmap paket sa sustava.

15. Sa web pretraživačem otvoriti slijedeću adresu : http://hisham.hm/htop/

16. Kliknuti na poveznicu koja usmjeruje na stranicu sa najnovijim izdanjem aplikacije. Primijetiti mogućnost preuzimanja u obliku izvornog koda i 
    prethodno kompajlirane izvršne (binarne) datoteke. Koja je razlika između njih dvoje?

17. Odabrati preuzimanje u obliku izvornog koda. Koja je razlika između Stable i Development verzija? Koja verzija je uglavnom preporučena za korištenje?

18. Kliknuti na poveznicu koja upućuje na najnoviju verziju izvornog koda, te na slijedećoj stranici odabrati direktorij sa najsvježijim datumom.

19. Unutar ~/Downloads direktorija, stvoriti novi direktorij pod imenom HTOP, te preuzeti sve datoteke prikazane u prethodnom zadatku u HTOP direktorij.

    NAPOMENA: Više o .asc datotekama na slijedećoj poveznici: https://logological.org/signature

              Prije izvršavanja datoteka preuzetih iz neslužbenih izvora, dobro je provjeriti autentičnost, kako bi se korisnik uvjerio da sadržaj nije 
              izmijenjen od treće strane.
              Provjera se najčešće sastoji ili od klasične provjere md5 sume, ili provjere potpisivanja javnim ključem.

              MD5 metoda - Još uvijek česta metoda gdje se nad sadržajem neke datoteke izvrši hash funkcija MD5 algoritma, te se kao proizvod dobije 128 bitna
              vrijednost (16 znakova). Prilikom preuzimanja te datoteke, ponovno se izvrši MD5 hash funkcija, te se usporedi sa postojećom vrijednošću. Ako 
              poklapaju, datoteka je zadržala integritet.

              Potpisivanje javnim ključem - Dosta kompleksnija metoda, u kojoj se sadržaj neke datoteke potpisuje javnim ključem autora. Svatko tko preuzme 
              tu datoteku, može (uz uvjet da je preuzeo i javni ključ autora) provjeriti priloženi potpis datoteke. Za cijeli proces je potrebno imati 
              3 komponente : originalnu datoteku za preuzimanje, datoteku sa potpisom, te javni ključ.

20. Proučiti manpage aplikacije **gpg** (eng. GNU Privacy Guard), bitne opcije su **verify**, **import**, **list-keys** i **delete-key**. Pomoću naredbe **gpg**
    verificirati htop-x.y.z.tar.gz datoteku (slova x,y,z zamijenjuju verziju aplikacije). Koji detalji se mogu iščitati iz potpisa? Koja poruka se javlja
    vezano uz javni ključ?

    PRIMJER:

    gpg --verify potpis_datoteke originalna_datoteka	# Kao argumenti se prvo navodi ime datoteke sa potpisom, nakon koje slijedi ime originalne datoteke
 
21. Sa slijedeće poveznice kopirati kompletan tekst javnog ključa (sve što je uokvireno, ne izostaviti nijedan znak), te ga spremiti u datoteku hisham.gpg koja
    će se nalaziti u ~/Downloads/HTOP direktoriju. Uvesti (eng. import) javni ključ autora u lokalnu bazu.

    PRIMJER:

    gpg --import javni_ključ.gpg


22. Ponovno verificirati datoteku sa potpisom. Ima li kakvih promjena? Koji se sad detalji mogu iščitati iz potpisa?

    NAPOMENA: Uz detalje će se javiti upozorenje kako javni ključ nije potvrđen od strane povjerljivog autoriteta. Iako je cijela tema kompleksna, dovoljno
              je reći kako se cijeli sustav temelji na povjerenju u neku treću stranu. U ovom slučaju, korisnik vjeruje u autentičnost javnog ključa autora.

23. Nakon provjere integriteta arhivske datoteke, raspakirati htop-x.y.z.tar.gz datoteku, te postaviti novostvoreni direktorij kao radni direktorij. Ispisati
    sadržaj novog direktorija. Koje ekstenzije imaju većinski broj datoteka u direktoriju? Što uglavnom opisuju ekstenzije \*.c i \*.h?

24. Pročitati sadržaj datoteke INSTALL, dovoljno je poglavlje **Basic Installation**.

25. Pokrenuti proces konfiguracije, prije kompajliranja izvornih datoteka u binarne. Ima li kakvih grešaka u procesu?

    NAPOMENA: S obzirom da se u ovom procesu paketi ručno izgrađuju i instaliraju, ne postoji sustav koji provjerava ovisnost paketa i automatski instalira
              ostale potrebne pakete. To je ujedno i osnovna boljka ručne instalacije, zbog koje se uglavnom preporučuje instalacija već pripremljenih paketa,
              pomoću nekog automatiziranog sustava (apt,apt-get...). Kod svake ručne instalacije, mogući su određeni problemi, u kojima korisnik sam treba zaključiti
              što je potrebno izmijeniti ili dodatno instalirati.

    PRIMJER: U ovoj situaciji , moguća je poruka greške **configure: error: You may want to use --disable-unicode or install libncursesw**. Potrebno je 
             instalirati paket **libncursesw5-dev**, te ponoviti proces konfiguracije.

26. Nakon uspješne konfiguracije (bez grešaka i upozorenja), potrebno je izgraditi binarne datoteke iz datoteka sa izvornim kodom. Dovoljno je samo upisati naredbu
    **make**.

27. Zadnji korak u procesu je prebacivanje izvršnih datoteka u potrebne direktorije, uglavnom /usr/local/bin. Proces se aktivira naredbom **make install**.
    Ima li kakvih grešaka, vezano uz dozvole? Kako bi se mogao riješiti taj problem?

28. Provjeriti lokaciju instalacije aplikacije htop (naredba **which**). Pokrenuti aplikaciju htop kako bi se potvrdila uspješna instalacija.
