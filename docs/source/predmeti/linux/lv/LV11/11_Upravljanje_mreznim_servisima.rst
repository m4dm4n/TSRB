Upravljanje mrežnom konfiguracijom i servisima
==============================================

Zadaci:

1. Proučiti manpage naredbe ifconfig. Pokrenuti naredbu bez dodatnih opcija. Što se dogodilo? Koja mrežna sučelja su prikazana? Što znače kratice Ethx (x zamijeniti sa prikazanim brojem ili brojevima) i Lo? 
   Koja je svrha Loopback mrežnog sučelja?

2. Zapisati IP (verzija 4) adrese dodijeljene mrežnim sučeljima, zajedno sa pripadajućim mrežnim maskama. Prema MAC adresi saznati proizvođača mrežnog sučelja. Tko je proizvođač kada se radi o virtualnim strojevima?

3. Proučiti manpage naredbe ethtool (ako je potrebno, instalirati potreban paket na sustav). Koja opcija se koristi za dobivanje informacija o upravljačkom programu koji se koristi za upravljanje mrežnim sučeljem? Saznati koji su upravljački 
   programi učitani za svako mrežno sučelje na sustavu? Ima li Loopback mrežno sučelje učitan upravljački program?

4. Pomoću naredbe ifconfig postaviti statičku IP adresu u mreži 192.168.200.0/27 (mrežnu masku zapisati u oktalnom obliku) na mrežno sučelje
   povezano sa mrežom.
   
   Redni broj IP adrese u rangu prilagoditi broju radne stanice u prostoru. Provjeriti ispravnost konfiguracije.

5. Ponovno pokrenuti računalo. Što se dogodilo sa prethodnim postavkama?

6. Proučiti manpage naredbe ip (posebno parametre **addr**, **link**, **monitor**, **neighbour**). Prikazati IP i MAC adrese svih mrežnih sučelja na računalu (parametri **address** i **link**).

   NAPOMENA: Ifconfig je u prošlosti bio najčešći alat za pregled i izmjenu konfiguracije mrežnih sučelja. Zajedno sa još nekim alatima
             (arp, route, netstat...), dio je paketa **net-tools**. Iako se (ovisno o distribuciji) taj alat i dalje koristi, 
             već neko vrijeme je ideja da ga se zamijeni sa novim paketom **iproute2** (u koji spada i već korištena naredba **ip**).
             U izvorima ispod nalazi se tekst sa opisom situacije i razlozima prelaska na novi paket, te primjerima korištenja i razlike
             između dva paketa.

   IZVORI:
 
   https://lwn.net/Articles/710533/

   https://github.com/techniq/wiki/wiki/net-tools-vs-iproute2

   http://xmodulo.com/linux-tcpip-networking-net-tools-iproute2.html

   https://philosophos.github.io/articles/20170411~net-tools-VS-iproute2/

7. Pomoću **ip** naredbe, promijeniti IP adresu mrežnog sučelja kao i prema prethodnom primjeru. Provjeriti ispravnost konfiguracije. Ponovno
   pokrenuti računalo i uočiti što se dogodilo sa mrežnim postavkama.

8. Proučiti manpage naredbe **arp**. Prikazati ARP tablicu za sučelje povezano na mrežu. Postići istu funkciju pomoću **ip** naredbe. Koja metoda je preglednija i informativnija (po osobnom mišljenju)?

9. Pokrenuti skriptu iz prethodnih vježbi koja šalje ICMP zahtjeve unutar mreže, te nakon 20ak sekundi u različitim karticama (eng. tab) prikazati ARP tablice pomoću **arp** i **ip** naredbi. Na koji način se prikazuju stavke IP adresa koje ne odgovaraju
   na ICMP upite (iz obje tablice)? Kakvo značenje imaju zastavice statusa (ARP tablica pomoću **ip** naredbe) : REACHABLE, STALE, FAILED i INCOMPLETE? 

10. Onemogućiti (spustiti) mrežno sučelje povezano na mrežu. Provjeriti detalje *ip addr* naredbe. Što se može uočiti? Provjeriti stanje usmjerničke (eng. routing table) i arp tablice. Što je zapisano u njih? Zašto?

11. Omogućiti (podići) mrežno sučelje iz prethodnog zadatka, te ponovno provjeriti stanje svih sučelja, usmjerničke i arp tablice. Koliko stavaka ima u arp tablici? Objasniti svojim riječima razlog.
    Koliko ima stavaka u routing tablici? Opisati svrhu default rute i 169.254.0.0 rute. Objasniti svrhu opcije **metric** unutar rute.

12. U jednoj kartici terminala pokrenuti naredbu **ip monitor**, a u drugoj skriptu koja šalje ICMP zahtjeve. Pratiti stanje na prvoj kartici. Što se može uočiti? U kojoj situaciji se pojavljuje status FAILED? Što znači status STALE
    (originalno je status bio REACHABLE)?

13. Ispisati sadržaj arp tablice. Isprazniti sadržaj arp tablice pomoću **ip link set** naredbe (potrebno je deaktivirati i ponovno aktivirati). Nakon deaktivacije tablice, proučiti sadržaj **ip link** naredbe za aktivno mrežno sučelje.
    Što se može uočiti? Dok tablica još nije aktivna, probati poslati ICMP zahtjev na gateway mreže. Ima li odgovora? Zašto? Aktivirati tablicu i ponoviti prethodni postupak. Ima li kakvih promjena?

14. Proučiti manpage konfiguracijske datoteke **interfaces** (prisjetiti se kako). Za INET obitelj (eng. address family) proučiti dva tipa konfiguracije: **static** i **dhcp**. U tekstualnom editoru otvoriti datoteku  
    /etc/network/interfaces. Konfigurirati statičke postavke za mrežno sučelje (prema primjeru ispod). Spremiti izmjene u datoteku i provjeriti IP postavke sučelja. Ima li kakvih promjena?

    PRIMJER KONFIGURACIJE:

    #Sučelje eth0 zamijeniti prema potrebi
 
    auto eth0

    #Definirati sučelje (eng. interface, skraćeno **iface**) kao dio **inet** obitelji (standardan naziv za IPv4) i statičan tip konfiguracije

    iface eth0 inet static


	address	   192.168.70.2xx
	netmask    24
	broadcast  192.168.70.255
	gateway    192.168.70.1
	metric     500

15. Sa root ovlastima, ponovno pokrenuti **networking** servis unutar /etc/init.d direktorija. Provjeriti IP postavke sučelja. Ima li promjena? Što se dogodilo sa starim postavkama? Ponovno pokrenuti računalo
    i provjeriti IP postavke. Što se dogodilo?

   NAPOMENA: Osnovni opis funkcije /etc/init.d direktorija nalazi se na priloženoj poveznici.

   IZVOR: https://www.ghacks.net/2009/04/04/get-to-know-linux-the-etcinitd-directory/
	
16. Pomoću **ifdown** naredbe (koristiti **verbose** opciju), spustiti sučelje. U tekstualnom editoru zakomentirati postojeću konfiguraciju sučelja, te upisati novu za dinamičko adresiranje (iface eth0 inet dhcp). Podići sučelje
    koristeći **ifup** naredbu (koristiti **verbose**). Može li se uočiti proces dinamičkog dodjeljivanja adresa? Provjeriti IP postavke sučelja. Je li radnja uspješna?

17. Proučiti manpage naredbe **dhclient**. Sa root ovlastima izvršiti naredbu dhclient nad aktivnim mrežnim sučeljem (koristiti **verbose** opciju). Je li se izvršio potpuni proces dodjeljivanja adresa? Zašto?
    Naredbom dhclient osloboditi trenutnu adresu u najmu (koristiti **verbose** opciju), te ponovno zatražiti novu adresu. Ima li promjena u odnosu na na prošli primjer? Proučiti oba procesa u wireshark
    aplikaciji.


DIJELJENJE DIREKTORIJA


18. Proučiti manpage naredbe smbclient (opcija -L). Pomoću naredbe prikazati popis dostupnih dijeljenih direktorija sa dostupnog poslužitelja (lozinku ostaviti praznu). Povezati se na jedan od dostupnih
    dijeljenih direktorija.

    NAPOMENA: S obzirom da se u UNC putanjama koriste obrnute kose crte (eng. backslash, simbol \ ), potrebno je izbjeći interpretaciju znakova od strane terminala (eng. character escaping). Simbol koji terminalu kaže da slijedeći znak
              ne interpretira,odnosno da ga shvati doslovno, je već navedeni **backslash**. U ovoj konkretnoj situaciji znači da će UNC putanja zapravo imati redudantne znakove, kao što je prikazano u slijedećem primjeru:


    UNC Putanja: 		\\Server\DijeljeniDirektorij

    Ispravljena UNC putanja : 	\\\\Server\\DijeljeniDirektorij


19. Odabrati neku datoteku za preuzimanje, te saznati informacije o njoj (pomoć: naredba stat). Koja je veličina datoteke u KiB? Opisati ukratko funkciju svakog zapisa vremena : Access, Modify i Change. Preuzeti tu datoteku 
    iz dijeljenog direktorija. U kojem lokalnom direktoriju je ta datoteka spremljena?

20. Provjeriti je li na sustavu instaliran paket **cifs-utils**, te ga instalirati ako je potrebno. Stvoriti direktorij ~/MrezniDirektorij. Koristeći mount
    naredbu (definirati tip datotečnog sustava kao **cifs**), povezati dijeljeni direktorij sa direktorijem stvorenim u prethodnom koraku. Hoće li nakon ponovnog pokretanja
    računala dijeljeni direktorij i dalje biti dostupan lokalno?

21. Izmijeniti konfiguraciju /etc/fstab datoteke tako da se, prilikom svakog podizanja računala, dijeljeni direktorij (sa popisom laboratorijskih vježbi predmeta)
    povezuje sa lokalnim /mnt/LV direktorijem. Ispravno konfigurirati korisničke dozvole na lokalnom direktoriju.

22. Provjeriti je li na sustavu instaliran paket **samba**, te ga instalirati ako je potrebno. Stvoriti direktorij /media/DijeljeniDirektorij. Proučiti manpage samba paketa i saznati njegovu svrhu. Saznati ime konfiguracijske datoteke koju koristi
    **samba** paket. S obzirom na kompleksnost već postavljene konfiguracijske datoteke (nema smisla u početku proučavati samu datoteku), proučiti manpage te datoteke, poglavito slijedeće teme:

	- Struktura datoteke (sekcije i vrijednosti unutar sekcija)
	- Svrha **[global]** sekcije
	- Objašnjenje **%m** varijable iz donje konfiguracije (odlomak VARIABLE SUBSTITUTIONS)
	- Objašnjenje svake vrijednosti iz donje konfiguracije (odlomak EXPLANATION OF EACH PARAMETER) 

    Posebno objasniti svrhu vrijednosti **map to guest**.
    Spremiti pričuvnu kopiju originalne konfiguracijske datoteke (dovoljno je u imenu na kraju samo dodati BAK, ili na bilo koji način izmijeniti ime).
    U novu datoteku sa istim imenom kao i originalna unijeti doljenavedenu konfiguraciju. Pokušati se povezati na dijeljeni direktorij (pomoću smbclient aplikacije, te ako je moguće, iz Windows operacijskog sustava).
    Što se dogodilo? Je li radnja uspješna? U slučaju da nije, što govori poruka o grešci?

    PRIMJER KONFIGURACIJE:

    [global]

    workgroup = WORKGROUP
    interfaces = 127.0.0.0/8 eth0

    log file = /var/log/samba/log.%m
    log level = 1

    server role = standalone server
    map to guest = bad user
    usershare allow guests = yes


    [linux]
    comment = TestShare
    public = yes
    path = /media/DijeljeniDirektorij
    writeable = no
    guest ok = yes
    guest only = yes
    browsable = yes

23. Ponovno pokrenuti **samba** servis i još jednom se pokušati povezati na dijeljeni direktorij? Zašto je bitno ponovno pokrenuti servis nakon izmjene konfiguracije?


24. Proučiti osnovne informacije manpage naredbi **netstat** (dio net-tools paketa) i **ss** (dio iproute2 paketa). Pokrenuti naredbu **ss** bez dodatnih argumenata. 
    Mogu li se iščitati i prepoznati neke poznate informacije? Koji tipovi komunikacije (stupac NetId) su prikazani. Koja je razlika između 
    Unix socketa (u_str, u_seq, u_dgr) i TCP/UDP socketa? Koja stanja su prikazana (stupac State) i koje je njihovo značenje (opis svih stanja priložen je na poveznici)?


    NAPOMENA: Iako je **netstat** i dalje u dokumentacijama vrlo popularan alat, zamijenjen je sa modernijom implementacijom **ss**.

    IZVOR: OPIS TCP STANJA - https://blog.confirm.ch/tcp-connection-states/
  
25. Pomoću naredbe **ss** prikazati samo tcp i udp veze (prikazati SVA stanja socketa). Isključiti prevođenje broja portova u poznata imena usluga (port 80 će biti prikazan kao http).
    Mogu li se prepoznati portovi **samba** servisa? 

26. Prikazati samo ipv4 tcp veze (isključiti prevođenje imena usluga), te prikazati koji procesi koriste otvorene sockete. Filtrirati samo one veze kojima je vlasnik proces samba paketa (saznati koje je točno ime procesa). Na kojim portovima 
    sluša samba usluga? Koja je razlika između tih portova?

27. S nekog računala pristupiti dijeljenom direktoriju te ponoviti prethodni zadatak. Što se može uočiti? Koje je stanje nove veze i na koji port se računalo povezalo? Zašto?

28. Provjeriti jesu li na sustavu instalirani paketi sa ssh klijenta i poslužitelja, te ih instalirati ako je potrebno. Provjeriti status servisa ssh poslužitelja (prisjetiti se lokacije), te ga postaviti aktivnim ako je potrebno.

29. Proučiti manpage naredbe **ssh**. Postoji li ~/.ssh direktorij? Pomoću ssh klijenta povezati se na lokalno računalo (kao trenutno prijavljeni korisnik) te na susjedno računalo (paziti na identitet korisnika kojim se radi prijava, korisnik mora postojati lokalno na računalu). 
    Pojavljuje li se kakva poruka prije povezivanja na susjedno računalo? Koje je značenje te poruke? Provjeriti sadržaj ~/.ssh direktorija. Prikazati status svih veza ssh procesa ( i klijenta i poslužitelja). Na kojem portu sluša
    poslužiteljski ssh servis?

30. Zamijeniti IP adrese sa susjednim računalom, te se ponovno pokušati povezati ssh protokolom na susjedno računalo. Što se dogodilo? Koje je značenje poruke? Odraditi korake prema
    preporuci iz poruke i pokušati ponovno. Je li radnja uspješna? Što se može zaključiti? Isprobati što će se dogoditi ako se na računalu (na koje se već ranije 
    povezivalo sa ssh klijentom) promijeni IP adresa. Hoće li povezivanje biti uspješno?


DODATNO

31. Isprobati povezivanje na ssh poslužitelj pomoću privatno-javnih ključeva. Na ssh poslužitelju je potrebno stvoriti (ako već ne postoji) datoteku ~/.ssh/authorized_keys, te joj
    postaviti dozvole 600 (rw,-,-). Na strani klijenta je potrebno stvoriti kombinaciju privatno-javnih ključeva, pomoću naredbe ssh-keygen (proučiti manpage naredbe). Pokrenuti navedenu naredbu bez dodatnih opcija, ne upisivati lozinku 
    za zaštitu privatnog ključa. Koje su se datoteke stvorile u ~/.ssh direktoriju? Ispisati sadržaj obje datoteke na standardni izlaz. Koja datoteka sadrži privatni ključ, a koja javni?

32. Prekopirati potpun sadržaj datoteke javnog ključa korisnika u datoteku authorized_keys na ssh poslužitelju (cijeli sadržaj mora biti upisan u jednoj liniji u datoteci). Pokušati
    se povezati sa klijenta na ssh poslužitelj. Je li bilo potrebno upisivati lozinku prilikom povezivanja?

33. Na ssh poslužitelju stvoriti novog korisnika sshwsxy (xy zamijeniti sa brojem radne stanice). Pokušati se s klijenta povezati koristeći identitet novog korisnika. Je li radnja bila uspješna? 
    Je li moguće povezati se bez korištenja lozinke korisnika? Zašto? Odraditi postupak kako bi se mogla izvršiti prijava pomoću ključeva, te provjeriti uspješnost radnje.

    NAPOMENA: U slučaju pojave greške sa porukom "Agent admitted failure to sign using the key.", moguć razlog je što ssh-add proces (zadužen za prosljeđivanje privatnog ključa ssh autentikacijskom agentu)
              nije mogao pronaći aktivan proces. U toj situaciji je potrebno izvršiti evaluaciju aktivnosti agenta, te ručno pokušati dodati ključ.

    PRIMJER:

    yyy@zzz ~/.ssh $ ssh superman@192.168.xx.yy
    Agent admitted failure to sign using the key.
    superman@192.168.xx.yy's password: 

    ids@ids2 ~/.ssh $ eval $(ssh-agent);ssh-add
    Agent pid 15315
    Identity added: /home/yyy/.ssh/id_rsa (rsa w/o comment)

34. Prijaviti se ssh protokolom na poslužitelj koristeći **verbose** opciju (moguće je povećati razinu opširnosti informacija dodavanjem dodatnih slova, do razine 3). Proučiti cijeli
    proces prijave te ga pokušati na skraćen način opisati.


 
