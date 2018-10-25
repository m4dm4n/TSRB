LV04
====

Upoznavanje sa diskovnim podsustavom računala u laboratoriju
------------------------------------------------------------

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1. Ponovno pokrenuti računalo i u Multiboot izborniku odabrati "Other OS
   and Tools", te zatim "Hiren's Boot CD" stavku. Pojaviti će se
   slijedeći izbornik te je u njemu potrebno odabrati „Mini Windows XP“
   opciju. Nakon učitavanja „Mini Windows XP“ sustava, pojaviti će se
   radna površina.

2. U slučaju potrebe za pristup nastavnim sadržajima, potrebno je aktivirati mrežni upravljački program, postaviti automatsko dohvaćanje
   IP adresa, te pristupiti mrežnom dijeljenom direktoriju.

3. Pokrenuti HBCD menu i odabrati izbornik Programs, te zatim
   Partition/Boot/MBR. Unutar izbornika odabrati aplikaciju Disk Genius.
   Proučiti sadržaj osnovna tri dijela ekrana (grafički prikaz gore,
   tekstualni prikaz lijevo, detaljni tekstualni prikaz dolje).

4. Koliko je uređaja za pohranu podataka prikazano u aplikaciji?
   Zaključiti i zapisati o kojim se uređajima radi.

5. Odabrati uređaj USB pogona s popisa na lijevoj strani. Uočiti razliku
   između prijavljene veličine USB pogona (iza naziva modela) i stavke
   **Capacity** (donji dio ekrana) među detaljnim informacijama.

..  important::

     Za domaću zadaću objasniti razlog razlike veličina te pronaći formulu za izračun.

6. Koji je ukupan broj sektora uređaja (stavka Total sectors) ?

7. Uz pomoć ukupnog broja sektora i veličine jednog sektora izračunati
   ukupan kapacitet u gigabajtima.

8. Kliknuti na particiju koja se nalazi na USB pogonu. Što se
   promijenilo u grafičkom prikazu uređaja? Što označava zeleni okvir
   oko uređaja?

9. Odabrati tvrdi disk sa popisa na lijevoj strani. Koja je prijavljena
   veličina uređaja?

10. Koliko je particija prikazano na tvrdom disku? Zašto (sjetiti se dokumentacije strukture tvrdog diska tog računala)?

11. Koji se tip particijske tablice koristi na tom tvrdom disku (stavka Partition table style) ?

    Za domaću zadaću potražiti i zapisati još barem 2 druga tipa struktura particijskih tablica.

12. Odabrati H1 particiju na tvrdom disku te zapisati slijedeće podatke o njoj :

   -  Početni sektor ( stavka Starting sector)
   
   -  Ukupan broj sektora particije ( stavka Total sectors)
   
   -  Tip datotečnog sustava (stavka File system)
   
   -  ID datotečnog sustava (ID stupac)
   
   -  Veličinu particije (stavka Capacity)

13. Uz pomoć podataka početnog sektora i ukupnog broja sektora particije izračunati završni sektor H1 (odnosno HOME) particije. Na što je bitno obratiti pozornost prilikom izračuna?

14. Ponovno pokrenuti računalo bez USB pogona u njemu. Nakon učitanog operacijskog sustava na particiji HOME, pokrenuti skriptu A1.

15. Pokrenuti Disk Genius aplikaciju. Koliko je sada prikazano particija u particijskoj tablici na tvrdom disku? Zašto? Zapisati početne i
    završne sektore za H3 i A1 particiju, te usporediti podatke sa dokumentacijom.

16. Zašto nisu prikazane sve particije na tvrdom disku odjednom? Koliko
    je moguće prikazati particija odjednom (pritom se uvijek misli na
    **primarne** particije)? Što se događa sa onim particijama na tvrdom
    disku koje nisu prikazane?

17. Pokrenuti Partition Wizard (Home Edition) aplikaciju (nalazi se u
    istom izborniku kao i DG aplikacija). Kako se prikazuje nealociran
    prostor na tvrdom disku u Disk Genius aplikaciji, a što piše u
    Partition Wizard aplikaciji? Koja je razlika između nealociranog
    (eng. unallocated) prostora i slobodnog (eng. free)?

18. Unutar aplikacije odabrati izbornik Disk te zatim opciju Partition
    recovery. U otvorenom prozoru odabrati opciju Full disk , te zatim
    Quick scan. Namjena ove opcije je pretraživanje izbrisanih particija
    na tvrdom disku.

..  note::

     Uočiti prilikom pretraživanja, kako nađene particije imaju
     "Lost/Deleted" status. Po definiciji, bilo koja particija koja se ne
     nalazi u particijskoj tablici ( MBR sektor) se može smatrati
     izbrisanom.
     
     Pretraživanje traje između 5-10 minuta, za to vrijeme prodiskutirati
     o vezi između "izbrisanih" particija i dokumentacije tvrdog diska
     računala u laboratoriju.

19. Koje su sve particije nađene nakon pretraživanja? Koje particije iz
    dokumentacije nisu pronađene? Koji bi bili mogući razlozi za to?

20. NE vraćati izbrisane particije, samo izaći iz izbornika (opcija
    Cancel), te izaći iz Partition Wizard aplikacije.

21. Ponovno pokrenuti računalo bez USB pogona, te se vratiti na HOME
    particiju (odabrati H3, te pokrenuti **home** skriptu).

