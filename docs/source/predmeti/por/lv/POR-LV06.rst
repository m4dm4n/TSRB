LV06
====

Rad u MBRWizard aplikaciji
--------------------------

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1.  Iz **HOME** particije ponovno pokrenuti računalo i u Multiboot
    izborniku odabrati "Other OS and Tools", te zatim "Hiren's Boot CD"
    stavku. Pojaviti će se slijedeći izbornik te je u njemu potrebno
    odabrati „Mini Windows XP“ opciju. Nakon učitavanja „Mini Windows
    XP“ sustava, pojaviti će se radna površina.

2.  Pokrenuti Windows Explorer aplikaciju, odabrati USB pogon, te u
    njemu odabrati direktorij sa imenom razreda (2x,3x ili 4x)

3.  Desnom tipkom miša odabrati MBRWiz.exe aplikaciju, te odabrati
    opciju Command Prompt Here. Što se dogodilo? Koji je trenutno radni
    direktorij u komandnoj liniji?

4.  Pokrenuti **mbrwiz.exe** aplikaciju sa opcijom **/?** (pozivanje
    izbornika pomoći). Ponovno pokrenuti aplikaciju , no bez upisivanja
    ".exe" ekstenzije. Je li se što promijenilo? Zaključi zašto.
    Proučiti sve opcije, a zapisati i opisati slijedeće opcije :
    **/List, /Disk, /Save, /Restore, /Show, /Confirm, /Shutdown,
    /Active, /WriteIni**. Čemu služi znak **"#"** , a čemu **"X"** u
    popisu opcija?

5.  Pomoću MBRWizard aplikacije ispisati sadržaj particijskih tablica
    svih uređaja za pohranu. Po čemu se može prepoznati da je jedan od
    prikazanih uređaja USB pogon? Koliko particija se nalazi trenutno na
    tvrdom disku? Prema dokumentaciji tvrdog diska, o kojoj se particiji
    radi?

6.  Zapisati osnovne informacije particijske tablice USB pogona (Početni
    sektor, izračunati završni sektor, Boot status, tip datotečnog
    sustava).

7.  Spremiti sadržaj Master Boot Record sektora USB pogona u datoteku
    imena sa inicijalima učenika vlasnika USB pogona i dodatka teksta
    **"\_USB.mbr"**.

..  note::

     Primjer : ``PP\_USB.mbr`` za ime Pero Perić

8.  Spremiti sadržaj Master Boot Record sektora tvrdog diska u datoteku
    imena **h1.mbr**.

9.  Koje veličine su spremljene datoteke? Zašto?

10. Pregledati sadržaj datoteka koristeći opciju **/Show**, te usporediti sa
    informacijama iz 6. zadatka. Što se može zaključiti, odgovara li
    sadržaj spremljenih datoteka stvarnom stanju na uređajima?

..  note::

    Primjer: ``mbrwiz /Show=file /Filename=h1.mbr``

11. Izvaditi USB pogon, ponovno pokrenuti računalo i sa HOME particije
    započeti postupak prebacivanja na A1 particiju pokretanjem
    **a1.bat** datoteke. Odmah nakon toga priključiti USB pogon u
    računalo kako bi se pojavio MultiBoot izbornik. Odabrati "Hiren's
    Boot CD" stavku. Pojaviti će se slijedeći izbornik te je u njemu
    potrebno odabrati „Mini Windows XP“ opciju.

12. Ponoviti postupak iz 5. zadatka. Koliko se sad particija nalazi u
    particijskoj tablici na tvrdom disku? Zašto?

13. Spremiti pričuvnu kopiju A1 particije pod imenom **a1.mbr** u
    direktorij MBRWIZD na USB pogonu, koristeći apsolutnu putanju u
    **/Filename** opciji.

..  note::

     Primjer: 
     ``mbrwiz.exe /Disk=1 /Save=MBR /filename=C:\\IME\_RAZREDA\\MBRWiz3\\a1.mbr``

     **C: zamijeniti sa slovom USB pogona, a IME\_RAZREDA sa oznakom tvojeg razreda**

14. Zamijeniti sadržaj MBRa na tvrdom disku koristeći **h1.mbr**
    datoteku. Ponovno pokrenuti računalo bez USB pogona. Na kojoj se
    particiji nalazite? Zašto?

15. Ponovno pokrenuti računalo i u Multiboot izborniku odabrati "Other
    OS and Tools", te zatim "Hiren's Boot CD" stavku. Pojaviti će se
    slijedeći izbornik te je u njemu potrebno odabrati „Mini Windows XP“
    opciju.

16. Stvoriti datoteku sa imenom **a1.bat** i spremiti ju u postojeći
    direktorij **MBRWiz3** na USB pogonu.

17. Upisati slijedeći tekst u datoteku iz 17. zadatka:

    ::
      
      @echo off
      cls
      echo Skripta za prebacivanje na A1 particiju (H3 i A1)
      mbrwiz /disk=1 /restore=MBR /filename=a1.mbr /confirm /shutdown=4


    Spremiti datoteku.

18. Koja je funkcija **/confirm** i **/shutdown=4** opcija? Pokrenuti
    datoteku **a1.bat** (operacijski sustav automatski prepoznaje
    datoteke sa \*.bat ekstenzijom kao izvršne datoteke, isto kao i
    \*.exe ili \*.com) i izvaditi USB pogon iz računala.

19. Na kojoj se particiji nalazite? Objasniti **a1.bat** datoteku.

20. Kopirati **a1.bat** datoteku u korijenski direktorij particije USB
    pogona i pokrenuti je. Koji je rezultat te radnje? Zašto? Što bi se
    moglo izmijeniti u datoteci kako bi postala funkcionalna?

21. Stvoriti datoteku sa imenom **h1.bat** i spremiti ju u direktorij
    MBRWiz3 na USB pogonu.

22. Upisati slijedeći tekst u datoteku iz 21. zadatka:

    ``mbrwiz /disk=1 /restore=MBR /filename=h1.mbr /confirm /shutdown=4``

    
    Spremiti datoteku.

23. Pokrenuti datoteku **h1.bat** i izvaditi USB pogon iz računala.

24. Uvjeriti se da se računalo nalazi na **HOME** particiji, te složiti
    radno mjesto.
