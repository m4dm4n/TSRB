Simboličke i čvrste poveznice
=============================

1. Proučiti manpage naredbe ln (LN malim slovima). Unutar direktorija ~/Documents stvoriti novu datoteku imena Original.txt. Ispisati
    sadržaj datoteke /proc/cpuinfo, no rezultat preusmjeriti u datoteku Original.txt. Koja je veličina datoteke?

2. Unutar direktorija ~/Documents stvoriti novi direktorij LINKANJE. Ispisati sadržaj direktorija sa opcijama "-alh" (prisjetiti se svrhe tih opcija).

    Prije objašnjenja termina čvrstih i simboličkih poveznica (eng. Hardlinks and soft/symbolic links ), potrebno je ukratko pojasniti osnove
    EXT datotečnih sustava (EXT2, EXT3 i EXT4), točnije, dio koji se tiče same strukture.

    /dev/sda1 - 40 134 656 sektora, 20548943872 bajta (cca 19,5GB)

    https://www.ics.uci.edu/computing/bin/img/perms1.png

    NAPOMENA : U prvoj slici je prikazano objašnjenje svake stavke long
    listing rezultata naredbe ls. U drugoj slici je prikazan stvarni
    primjer, sa posebno označenim dijelom sa brojem čvrstih poveznica
    (eng. Hard link) na datoteke i direktorije. Svaki stvoreni
    direktorij počinje sa dvije poveznice, Ime\_direktorija i znak "."
    koja označava taj direktorij i upućuje na njega. Dodatno, svaki
    direktorij u popisu sadrži i oznaku ".." koja upućuje na prethodni
    direktorij u strukturi. Čak i korijenski direktorij u sebi sadrži
    dvije oznake, kao što je vidljivo na slici ispod. Ono što je
    specifično za korijenski direktorij je što obje oznake "." i ".."
    upućuju na isti direktorij, odnosno korijenski direktorij ( eng.
    Root directory, oznaka "/" ). Isto tako je na slici ispod vidljivo
    kako obje oznake imaju isti "inode" broj (broj 2), odnosno radi se o
    istom direktoriju.

3. Unutar direktorija LINKANJE, stvoriti 3 datoteke : kopirati.txt, premjestiti.txt i obrisati.txt

4. Stvoriti 3 čvrste poveznice sa imenima HLkopirati, HLpremjestiti i HLobrisati, te ih povezati sa datotekama iz prošlog zadatka, sukladno imenima.

5. Stvoriti 3 simboličke poveznice sa imenima SLkopirati, SLpremjestiti i SLobrisati, te ih povezati sa datotekama iz pretprošlog zadatka, sukladno imenima.

    NAPOMENA : Kao rezultat, sadržaj direktorija bi trebao biti kao prema slici.

    

6. Proučiti Inode brojeve čvrstih poveznica i simboličkih poveznica. U odnosu na originalne datoteke, što se može zaključiti?

7. Koji je broj čvrstih poveznica (eng. number of hard links) sva tri tipa datoteka? Zašto?

8. Kopirati datoteku kopirati.txt u prethodni direktorij ( /home/KORISNIK/ ) pod imenom kopija.txt. Koji je Inode broj kopirane datoteke? Je li se promijenio koji atribut sa postojećim datotekama u direktoriju LINKANJE (broj čvrstih poveznica, Inode broj)?

9. U datoteku kopirati.txt upisati svoje prezime. Što se promijenilo sa veličinom datoteka kopirati, HLkopirati i SLkopirati? 

10. Na zaslon ispisati sadržaj datoteka iz prošlog zadatka. Koji je rezultat?

11. Premjestiti datoteku premjestiti.txt u prethodni direktorij ( /home/KORISNIK/ ).

12. U datoteku HLpremjestiti.txt upisati svoje ime. Što se promijenilo sa veličinom datoteka premjestiti, HLpremjestiti i SLpremjestiti?

13. Na zaslon ispisati sadržaj datoteka iz prošlog zadatka. Koji je rezultat? Što se može zaključiti oko datoteke SLpremjestiti.txt?

14. U datoteku obrisati.txt upisati trenutnu godinu.

15. Na zaslon ispisati sadržaj datoteka obrisati.txt, HLobrisati.txt i SLobrisati.txt.

16. Obrisati datoteku obrisati.txt, te zatim na zaslon ispisati sadržaj datoteka HLobrisati.txt i SLobrisati.txt. Što se može zaključiti za datoteku SLobrisati.txt?

17. Što se dogodilo sa brojem čvrstih poveznica za datoteku HLobrisati.txt? Što se može zaključiti?

18. Podići particiju sa EXT4 datotečnim sustavom (stvorena u jednoj od prijašnjih vježbi) unutar direktorija /mnt/EXT4. U navedenom direktoriju stvoriti novu datoteku imena MickeyMouse.txt (pripaziti na prava pristupa, sjetiti se uporabe chown naredbe).

19. U direktoriju /home/KORISNIK/LINKANJE stvoriti simboličku poveznicu SLMickey.txt. 

20. Proučiti manpage naredbe readlink , te zatim ispisati punu putanju na koju poveznica SLMickey.txt upućuje.

21. Pokušati stvoriti čvrstu poveznicu HLMouse.txt na datoteku MickeyMouse.txt. Što se dogodilo? Saznati zašto.


PITANJA:

1. Navesti barem 3 razlike između čvrstih i simboličkih poveznica.

2. Koje prednosti ima čvrsta poveznica nad simboličkima?

3. Koje prednosti ima simbolička poveznica na čvrstima?
