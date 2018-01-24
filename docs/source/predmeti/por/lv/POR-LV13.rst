LV13
====

Konfiguracija Windows 10 operacijskog sustava
---------------------------------------------

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1. Iz **HOME** particije ponovno pokrenuti računalo i u Multiboot
   izborniku odabrati "Other OS and Tools", te zatim "Hiren's Boot CD"
   stavku. Pojaviti će se slijedeći izbornik te je u njemu potrebno
   odabrati „Mini Windows XP“ opciju. Nakon učitavanja „Mini Windows XP“
   sustava, pojaviti će se radna površina.

2. Spremiti sadržaj Master Boot Record sektora tvrdog diska u datoteku
   imena **h1.mbr** unutar **MBRWIZ3** direktorija na USB pogonu.
   Provjeriti sadržaj datoteke kako bi se uvjerili da je spremljen
   ispravan MBR (sa **HOME** particijom u tablici).

3. Pomoću aplikacije **MBRWIZ** vratiti sadržaj datoteke
   **H132HBKP.mbr** na **MBR** tvrdog diska, te zatim ponovno pokrenuti
   računalo bez USB pogona. Prijaviti se u Windows 10 operacijski
   sustav.

4. 
5. Pokrenuti "**Device manager**" konzolu (upisati ime u Start->Search
   bar) i uočiti uređaje sa žutim upitnikom. Što znači taj znak?

   **DODATAK**: Druga tri načina za pristup "**Device manager**" konzoli
   su :

a) Desni klik na Computer->Properties->\ **Device manager**

b) Start->u Search bar upisati "devmgmt.msc" ( msc ekstenzija označava
   Microsoft Management Console Snap-in Control datoteku)

c) Desni klik na Computer->Manage->\ **Device manager**

1.  Instalirati **WINCDEmu** aplikaciju (Setup datoteka nalazi se mrežno
    dijeljenom direktoriju, APPL poddirektorij)

2.  Zapisati putanju mrežno dijeljenog direktorija na kojem se nalaze
    instalacijske datoteke upravljačkih programa
    (**\\\\IP\_ADRESA\\2h\\por\\appl\\driveri**)

3.  Stvoriti novi direktorij imena **DRIVERI** u korijenskom direktoriju
    **BKP** particije

4.  Kopirati sa mrežnog dijeljenog diska u direktorij **DRIVERI**
    datoteke : "**Parallel\_drivers.iso**", "**Serial\_drivers.iso**" i
    "**VGA\_drivers.iso**".

5.  
6.  U **Device manager** konzoli, odabrati "**Properties**" na "**PCI
    Serial Port**" uređaju, te u slijedećem prozoru odabrati karticu
    **Details**. U istoj kartici, u izborniku "**Property**" odabrati
    opciju "**Hardware IDs**". Zapisati najdulju liniju i uočiti stavke
    **PCI**,\ **VEN**,\ **DEV**, **SUBSYS** i **REV**

    (primjer **PCI\\VEN\_10EC&DEV\_8168&SUBSYS\_76731462&REV\_06)**.

    Što bi za taj uređaj predstavljale stavke **PCI**, **VEN** i **DEV**
    ?

7.  Raspakirati sadržaj komprimirane datoteke **PCI-Z** (datoteka se
    nalazi mrežno dijeljenom direktoriju, APPL poddirektorij) na radnu
    površinu (u direktorij **PCI-Z**). Pokrenuti izvršnu datoteku u tom
    direktoriju. Pročitati informacije o svrsi aplikacije (Help->About
    PCI-Z).

8.  U popisu prikazanih uređaja uočiti stavke sa narančastim trokutom i
    usporediti sa popisom iz 3. zadatka. Podudaraju li se stavke?

9.  U stavci "**PCI Serial Port**" (u **PCI-Z** aplikaciji) uočiti
    stupce **Vendor** i **Device** te **PCI Device**. Što označavaju
    polja **VEN** (VEN\_10EC) i **DEV** (DEV\_8168) u stupcu **PCI
    Device** za taj uređaj. Koja tvrtka je proizvela ovaj uređaj?

10. Učitati "**Serial\_drivers.iso**" datoteku (desni klik i **Select
    Drive & Mount** opcija) kao virtualni CD

11. 
12. U **Device manager** konzoli, odabrati "**Properties**" na prvom
    "**PCI Serial Port**" uređaju, te zatim odabrati opciju "**Update
    driver software**". U slijedećem prozoru odabrati opciju ručnog
    lociranja i instalacije upravljačkog programa. Odabrati direktorij
    na učitanom virtualnom CD uređaju koji odgovara tipu i verziji
    operacijskog sustava (Microsoft Windows 7, 64 bitni). Ostaviti
    uključenu opciju "**Include subfolders**" i potvrditi
    pretragu/instalaciju upravljačkih programa odabirom opcije
    "**Next**". Uvjeriti se da je instalacija uspješno izvršena.

13. Ponoviti postupak za drugi "**PCI Serial Port**" nepoznati uređaj,
    no koristiti automatsko pronalaženje izvora za nadogradnju.

14. Uvjeriti se kako svi uređaji na računalu imaju instalirane
    upravljačke programe.

15. 
