Upravljanje korisnicima
=======================

Cilj vježbe: Ideja vježbe je upoznati se sa pojmom upravljanja korisnicima. Nakon vježbe, polaznik će biti upoznat sa :

	- Identifikacijom prijavljenog korisnika
	- Stvaranjem novih korisnika (raznim metodama),
	- Konfiguracijom profila i radnog okruženja
	- Stvaranja pričuvne kopije profila i podataka korisnika
	- Brisanjem postojećih korisnika sa sustava 

Zadaci:

1. Proučiti manpage naredbe whoami. Pokrenuti navedenu naredbu. Koji je korisnik trenutno prijavljen?

2. Proučiti manpage naredbe id. Pokrenuti navedenu naredbu. U koliko grupa se nalazi prijavljeni korisnik? Čemu služi grupa **adm**?

   NAPOMENA: Opis svih ugrađenih grupa može se proučiti na slijedećim poveznicama.

   LOKALNO : file:///usr/share/doc/base-passwd/users-and-groups.html

   WEB : https://www.togaware.com/linux/survivor/Standard_Groups.html

3. Proučiti manpage naredbe w. Pokrenuti navedenu naredbu. Tko je sve prijavljen u sustav? Koliko pokrenutih procesa ima
   trenutno prijavljeni korisnik?

4. Pomoću naredbe **tail** na zaslonu prikazati posljednih 10 linija datoteke /var/log/messages. Je li radnja uspješna?


5. Pokrenuti grafičko sučelje upravitelja korisnicima i grupama. Maknuti trenutno prijavljenog korisnika iz grupe **adm**.

   POMOĆ: Do upravitelja je moguće doći odabirom izbornika Menu->Administration->Users and Groups

6. Ponovno pokušati prikazati sadržaj /var/log/messages datoteke. Je li radnja uspješna?

7. Odjaviti i ponovno prijaviti korisnika, te ponoviti prethodni zadatak. Što se dogodilo? Zašto korisnik nema ovlasti?
   Zašto su prava izgubljena tek nakon ponovne prijave? Vratiti korisnika kao člana **adm** grupe.

8. Pročitati manpage useradd i passwd naredbi. Pomoću useradd naredbe stvoriti novog korisnika s imenom superman. Pomoću passwd
   naredbe dodati lozinku korisniku (smije biti jednaka korisničkom imenu).

9. Pokušati se prijaviti kao Superman korisnik. Dokumentirati prikazanu poruku.  Koje je njeno značenje? Potvrditi nastavak 
   prijave. Koje je ponašanje sustava nakon prijave? Dokumentirati poruku o grešci i odjaviti se.

10. Provjeriti postoji li **superman** direktorij za korisnika u /home direktoriju. Ručno stvoriti direktorij. Tko je vlasnik 
    tog direktorija? Predati vlasništvo korisniku **superman**. Koji je sadržaj /home/superman direktorija? Ponovno se pokušati 
    prijaviti kao superman korisnik. Je li ovaj put prijava uspješna? Provjeriti sadržaj korisničkog direktorija. Što se 
    promijenilo?

    POMOĆ: Ako se eksplicitno ne navede, **useradd** neće automatski stvoriti i korisnički direktorij, već je to potrebno ručno
           napraviti. Da bi prijava bila uspješna, korisnik mora imati i vlasništvo nad tim direktorijem. Vlasništvo nad datotekama
           i direktorijima se mijenja pomoću naredbe **chown**. Potrebno je napomenuti kako se prilikom stvaranja korisnika ujedno 
           stvara i grupa sa istim imenom.

    PRIMJER:

    chown korisnik:grupa datoteka/direktorij

11. Proučiti manpage naredbe **su**. Čemu služi opcija **-** (ili -l)? Koji efekt se podrazumijeva ako se nakon naredbe **su** ne upiše nijedan argument? Pomoću naredbe **su** prijaviti se u ljusci kao korisnik **superman**. Koja je vrijednost
    varijable okruženja $PWD? Odjaviti se iz ljuske naredbom **exit**, te ponovno prijaviti uz korištenje opcije **-**. Ispisati vrijednost varijable $PWD. Ima li kakve razlike? Zašto?

12. Ispisati sve varijable okruženja (naredba **printenv** ili **env**, eng. environment). Koja je ljuska učitana za korisnika **superman**? Pokušati prikazati zadnjih 15 (proučiti opciju koja to omogućava) linija datoteke /var/log/messages.
    Je li radnja uspješna? Iz iskustva prethodnih zadataka, zaključiti zašto. U kojim grupama se nalazi korisnik **superman**? Odjaviti se iz aktivne ljuske korisnika.

13. Proučiti manpage naredbe **usermod** (bitne opcije su : -a, -G, -s, -L -e 1, -l). Promijeniti aktivnu ljusku korisniku **superman** u **bash** umjesto **sh**. Dodati korisnika u grupe **adm**, **users** i **audio**. Provjeriti u kojim
    grupama se korisnik nalazi? Dodatno ga učlaniti u grupu **video**. Koju opciju je potrebno koristiti za tu radnju, ako se žele zadržati prethodna članstva?

    NAPOMENA: Više o usporedbi i razlikama **sh** i **bash** na slijedećim poveznicama. Bitno je zapamtiti kako **sh** nije aplikacija, već se radi o smjernicama za implementaciju u POSIX standardu. Svaka Linux distribucija odabire neku od implementacija
              i veže na **sh** datoteku (simboličkim ili čvrstim poveznicama). 

    IZVORI: https://gist.github.com/mdeguzis/1d429ae8a8ccff78ea82
            http://pubs.opengroup.org/onlinepubs/009695399/utilities/xcu_chap02.html

    PRIMJER:

    ids@ids2 /bin $ ls -alh /bin/sh
    lrwxrwxrwx 1 root root 4 May 11  2017 /bin/sh -> dash 	# Trenutna implementacija je dash aplikacija

14. Proučiti manpage naredbe **chage**. Pomoću passwd i chage naredbi saznati informacije o korisniku **superman**. Koje je značenje slova **P** u izlaznim informacijama **passwd** naredbe? Zaključati korisnika **superman**. 
    Pokušati se prijaviti kao taj korisnik. Što se dogodilo? Ponovno provjeriti informacije za **superman** korisnika. Što se točno promijenilo u odnosu na prvotne rezultate? Otključati korisnika.

15. Proučiti manpage naredbe adduser. Stvoriti korisnika **ironman** pomoću naredbe **adduser** (ne koristiti nikakve dodatne opcije). U čemu se razlikuje postupak između korištenja **useradd** i **adduser** naredbi? Ponovno stvoriti
    proizvoljnog korisnika, no koristiti opciju **debug**. Što se može zamijetiti u procesu stvaranja korisnika naredbom **adduser**? Pokušati se prijaviti kao **ironman** korisnik. Je li radnja uspješna? Odjaviti se i prijaviti kao
    korisnik sa administratorskim ovlastima.

16. Proučiti manpage datoteke **passwd** (navesti 5. sekciju za prikaz). Proučiti značenja polja za korisnike. Pročitati dodatno objašnjenje za lozinke korisnika. Na zaslonu prikazati sadržaj datoteke /etc/passwd, te filtrirati da se
    prikažu samo informacije za korisnika **superman**. Što je zapisano u polju za lozinku korisnika? Koje je značenje toga? Proučiti manpage datoteke **shadows**, te zatim na zaslonu prikazati sadržaj datoteke /etc/shadow. Koje su informacije
    zapisane u toj datoteci?

17. Pokrenuti sučelje za izmjenu prozora prijave korisnika (Login Windows Preferences). Postaviti MDModern temu kao standarnu
    prilikom prijave.

18. Izmijeniti ~/.bashrc datoteku na način da se doda kod koji će u svakom novom prozoru terminala ispisati iznad prompta (NE MIJENJATI OSTATAK DATOTEKE):

	- Sve IPv4 adrese mrežnih sučelja (proučiti naredbu hostname)
	- Trenutno prijavljenog korisnika pod kojim se otvorio prozor
	- Informacije o ukupnoj i slobodnoj memoriji (ne prikazivati swap memoriju, proučiti naredbu free) 

	PROUČITI SVRHU DATOTEKA (kratki opis se može naći u manpageu bash ljuske, kategorija FILES pri samom dnu):

	/etc/profile
	/etc/bash.bashrc
	/etc/bash.bash.logout
	~/.bash_profile
	~/.bashrc
	~/.bash_logout
	~/.inputrc

19. Proučiti manpage naredbe userdel. Obrisati korisnika **hulk**, zajedno sa njegovim **home** direktorijem. 

20. Proučiti manpage naredbe deluser. U čemu se razlikuje u odnosu na prethodnu naredbu? Napisati skriptu koja će spremiti pričuvnu komprimiranu kopiju **home** direktorija korisnika **superman** (spremiti u BACKUP direktorij administratorskog
    korisnika), te zatim obrisati i samog korisnika.

21. Proučiti manpage bash ljuske, poglavlje PROMPTING. Prikazati vrijednost varijable okruženja PS1. Koju funkciju obavlja ta varijabla? Koji se dijelovi varijable mogu prepoznati od onih koji su već pojašnjeni u PROMPTING poglavlju?

    NAPOMENA: U slučaju da dio varijable PS1 zauzima područje sa chroot definicijama, značenje proučiti na slijedećoj poveznici.

    IZVOR: https://askubuntu.com/questions/372849/what-does-debian-chrootdebian-chroot-do-in-my-terminal-prompt

22. Izmijeniti standardni izgled prompta sa nekim po vlastitoj želji. Za izmjenu koristiti neku od ponuđenih poveznica, na kojoj se generira vrijednost PS1 varijable. Koristiti mogućnost izmjene boja,ugrađenih znakova (prikaz korisnika, direktorija, datuma...),
    te dodatnih specijalnih znakova. U slučaju trajne izmjene izgleda prompta, obvezno sačuvati originalnu vrijednost.

    IZVOR:

    http://ezprompt.net/

    http://omar.io/ps1gen/

    https://xta.github.io/HalloweenBash/

    http://bashrcgenerator.com/    
 



DODATNI ZADACI:

23. Pretpostavlja se da je korisnik zaboravio lozinku, te je potrebno izmijeniti lozinku i prisiliti korisnika da izmijeni novostvorenu lozinku pri slijedećoj prijavi na sustav. Kopirati tekst iz komandne linije koji pokazuje postupak.
Napisati skriptu koja će automatizirati postupak (novu lozinku i korisnika upisati kao argument prilikom pokretanja skripte).   

24. Napisati skriptu koja će provjeriti postoje li nove e-mail poruke na Gmail računu. U slučaju da postoje, izmijeniti izgled prompta, u kojem će se prikazati neka poruka o novim porukama. U slučaju da nema novih 
    poruka, vratiti standardni izgled prompta. Korisničko ime upisati kao parametar prilikom pokretanja skripte, a lozinku kao unos za vrijeme izvršavanja skripte (ne prikazivati znakove na ekranu).

    POMOĆ: Gmail podržava povlačenje svježih informacija pomoću Atom sustava. Iz ljuske je moguće koristiti "curl" kao klijent za preuzimanje HTTP prometa (proučiti čemu služe opcije -u i --silent u donjem primjeru). Informacije se 
           preuzimaju i prikazuju u xml obliku. Broj novih e-mail poruka nalazi se unutar <fullcount> oznake.


    IZVOR: https://developers.google.com/gmail/gmail_inbox_feed#about_atom

    PRIMJER:

    curl -u USERNAME\@gmail.com:PASSWORD --silent "https://mail.google.com/mail/feed/atom"

.. hint::

    PRIMJER RJEŠENJA ZADATKA:

    #!/bin/bash

    USERNAME="$1"

    read -sp 'Lozinka: ' PASSWORD
    echo
    
    UNREADMAIL=$(curl -u $USERNAME\@gmail.com:$PASSWORD --silent "https://mail.google.com/mail/feed/atom" | cut -d"<" -f8 | cut -d">" -f2)
    
    
    if [ $UNREADMAIL -gt 0 ]
      then
      echo "You have unread mail"
    #  PS1="\[\e[33m\]_NEW-MAIL_\[\e[m\]\[\e[33m\]\u\[\e[m\]\[\e[33m\]\\$\[\e[m\]\[\e[33m\]\h\[\e[m\]\[\e[33m\]-\[\e[m\]\[\e[33m\]\w\[\e[m\]\[\e[33m\]\\$\[\e[m\] "
       PS1="\[\e[33m\]_NEW-MAIL_\[\e[m\]\[\033[01;32m\]\u@\h\[\033[01;34m\] \w \$\[\033[00m\] "
    else
      echo "Zero unread mail"
      source ~/.bashrc
    fi


.. tip::

    NAPOMENA: Bitno je napomenuti da se nakon pokretanja skripte stvara novi proces sa novom ljuskom u kojem će se ta skripta izvršavati. Kao posljedicu, svaka izmjena varijable okruženja će ostati vezana za taj proces. U ovom slučaju, skripta
              će uspješno izmijeniti izgled prompta, no nakon završetka kontrola se vraća originalnoj ljusci i procesu, sa prethodno definiranim izgledom prompta. Rješenje problema je tzv. "source scripting", odnosno, pokretanje skripte
              u postojećem okruženju. Detaljni opis problematike se nalazi na slijedećoj poveznici.

    IZVOR: https://superuser.com/questions/176783/what-is-the-difference-between-executing-a-bash-script-vs-sourcing-it
    


PRIMJER RJEŠENJA 18. ZADATKA:

Izgled prompta:

IP adresa: 192.168.70.44
Korisnik : ids

             total       used       free     shared    buffers     cached
Mem:          2.0G       1.7G       219M        86M        20M       259M
ids@ids2 ~ $ 


Početni dio sadržaja ~/.bashrc datoteke:

# ~/.bashrc: executed by bash(1) for non-login shells.
# see /usr/share/doc/bash/examples/startup-files (in the package bash-doc)
# for examples

#ISPIS INFORMACIJA
IP=$(hostname -I)
echo IP adresa: $IP
echo Korisnik : $USER
echo
free -ht | egrep 'total|Mem'
/OSTATAK DATOTEKE
