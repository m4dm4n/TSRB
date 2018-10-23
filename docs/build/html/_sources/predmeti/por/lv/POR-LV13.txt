LV13
====

Instalacija upravljačkih programa u Windows 10 operacijskom sustavu
------------------------------------------------------------------

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1. Iz **HOME** particije ponovno pokrenuti računalo sa priključenim USB
   pogonom (prema prethodnim uputama). U **Multiboot** izborniku
   odabrati "**System Tools**", te zatim "**Windows 98**" operacijski
   sustav. Volkov Commander aplikaciju pokrenuti sa "**vc**" naredbom.

2. Pomoću aplikacije **MBRWIZD** vratiti sadržaj datoteke
   **H132HBKP.mbr** na **MBR** tvrdog diska, te zatim ponovno pokrenuti
   računalo bez USB pogona. Odabrati **Windows 7** operacijski sustav.

3. Pokrenuti "**Device manager**" konzolu (upisati ime u Start->Search
   bar) i uočiti uređaje sa žutim upitnikom. Što znači taj znak?

   **DODATAK**: Druga tri načina za pristup "**Device manager**" konzoli
   su :

a) Desni klik na Computer->Properties->\ **Device manager**

b) Start->u Search bar upisati "devmgmt.msc" ( msc ekstenzija označava
   Microsoft Management Console Snap-in Control datoteku)

c) Desni klik na Computer->Manage->\ **Device manager**

1.  Spojiti mrežni kabel u računalu na donju mrežnu karticu te odabrati
    "**WORK NETWORK**" opciju prilikom upita.

2.  Instalirati **WINCDEmu** aplikaciju (Setup datoteka nalazi se mrežno
    dijeljenom direktoriju, APPL poddirektorij)

3.  Zapisati putanju mrežno dijeljenog direktorija na kojem se nalaze
    instalacijske datoteke upravljačkih programa
    (**\\\\IP\_ADRESA\\2h\\por\\appl\\driveri**)

4.  Stvoriti novi direktorij imena **DRIVERI** u korijenskom direktoriju
    **BKP** particije

5.  Kopirati sa mrežnog dijeljenog diska u direktorij **DRIVERI**
    datoteke : "**Parallel\_drivers.iso**", "**Serial\_drivers.iso**" i
    "**VGA\_drivers.iso**".

6.  U **Device manager** konzoli, odabrati "**Properties**" na
    "**Ethernet controller**" uređaju, te u slijedećem prozoru odabrati
    karticu **Details**. U istoj kartici, u izborniku "**Property**"
    odabrati opciju "**Hardware IDs**". Zapisati najdulju liniju i
    uočiti stavke **PCI**,\ **VEN**,\ **DEV**, **SUBSYS** i **REV**

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

9.  U stavci "**Ethernet controller**" (u **PCI-Z** aplikaciji) uočiti
    stupce **Vendor** i **Device** te **PCI Device**. Što označavaju
    polja **VEN** (VEN\_10EC) i **DEV** (DEV\_8168) u stupcu **PCI
    Device** za taj uređaj. Koja tvrtka je proizvela ovaj uređaj?

10. U **Device manager** konzoli, odabrati "**Properties**" na
    "**Ethernet controller**" uređaju, te zatim odabrati opciju
    "**Update driver software**". U slijedećem prozoru odabrati opciju
    ručnog lociranja i instalacije upravljačkog programa. U lokaciju
    upisati punu putanju lokacije upravljačkih programa matične ploče,
    mrežni uređaj i upisati potrebnog proizvođača iz popisa. Ostaviti
    uključenu opciju "**Include subfolders**" (prilikom pretraživanja
    upravljačkih programa uređaja, instalacija će gledati i u svim
    poddirektorijima unutar zadanog) i potvrditi pretragu/instalaciju
    upravljačkih programa odabirom opcije "**Next**". Uvjeriti se da je
    instalacija uspješno izvršena.

11. Učitati "**Serial\_drivers.iso**" datoteku (desni klik i **Select
    Drive & Mount** opcija) kao virtualni CD

12. U **Device manager** konzoli, odabrati "**Properties**" na prvom
    "**PCI Serial Port**" uređaju, te zatim odabrati opciju "**Update
    driver software**". U slijedećem prozoru odabrati opciju ručnog
    lociranja i instalacije upravljačkog programa. Odabrati direktorij
    na učitanom virtualnom CD uređaju koji odgovara tipu i verziji
    operacijskog sustava (Microsoft Windows 7, 64 bitni). Ostaviti
    uključenu opciju "**Include subfolders**" i potvrditi
    pretragu/instalaciju upravljačkih programa odabirom opcije
    "**Next**". Uvjeriti se da je instalacija uspješno izvršena.

13. Ponoviti postupak za drugi "**PCI Serial Port**" nepoznati uređaj.

14. U **Device manager** konzoli, odabrati "**Properties**" na "**SM Bus
    Controller**" uređaju, te u slijedećem prozoru odabrati karticu
    Details. U istoj kartici, u izborniku "**Property**" odabrati opciju
    "**Hardware IDs**". Zapisati stavke VEN i DEV. Pomoću aplikacije
    PCI-Z prepoznati radi li se o **Chipset SMBus** kontroleru (
    **System Management Bus**), proizvođač **Intel** (uočiti znakovitost
    **VEN** polja).

15. Na mrežno dijeljenom disku pronaći direktorij sa upravljačkim
    programima matične ploče, tip "**chipset**", proizvođač **Intel**. U
    poddirektorijima ručno potražiti u svakoj "**MSIinst.xml**"
    (otvoriti u Notepad aplikaciji, pronaći **<VIDDID>** kategoriju)
    liniju koja sadrži i odgovara **VEN&DEV** poljima iz prošlog
    zadatka. Iz tog direktorija pokrenuti instalacijsku datoteku
    "**infinst\_autol.exe**" i potvrdno odgovoriti na sva pitanja. Na
    kraju instalacije dozvoliti ponovno pokretanje računala i provjeriti
    ispravnost instalacije.

16. Desnim klikom na virtualni CD uređaj odabrati opciju "**Mount
    another disc image**" i odabrati "**Parallel\_drivers.iso**". Pomoću
    aplikacije **PCI-Z** doznati proizvođača i model kontrolera za
    paralelne portove, te na virtualnom CD uređaju odabrati prikladan
    direktorij (Proizvođač, model, verzija i tip operacijskog sustava) i
    pokrenuti "**MOSCHIP\_Setup.exe**" instalacijsku datoteku. Nakon
    završene instalacije provjeriti promjenu u **Device manager**
    konzoli. Ako nema promjena, odabrati opciju "**Scan for hardware
    changes**" u "**Action**" izborniku. Ima li promjena?

17. Pomoću aplikacije **PCI-Z** uočiti zadnji uređaj koji nema
    instaliran upravljački program, te saznati proizvođača i model
    (Intel Management Engine Interface Controller). U **Device manager**
    konzoli, odabrati "**Properties**" na "**PCI Simple Communications
    Controller**" uređaju, te zatim odabrati opciju "**Update driver
    software**". U slijedećem prozoru odabrati opciju ručnog lociranja i
    instalacije upravljačkog programa. U lokaciju upisati punu putanju
    lokacije upravljačkih programa matične ploče, "**OtherDriver**" i
    odabrati "**Intel ME Driver**" direktorij. Ostaviti uključenu opciju
    "**Include subfolders**" i potvrditi pretragu/instalaciju
    upravljačkih programa odabirom opcije "**Next**". Uvjeriti se da je
    instalacija uspješno izvršena.

18. Desnim klikom na virtualni CD uređaj odabrati opciju "**Mount
    another disc image**" i odabrati "**VGA\_drivers.iso**". Pokrenuti
    "**Launch.exe**" datoteku, te odabrati **Ati Easy Install** opciju (
    Windows 7 operacijski sustav). Odabrati **Custom** instalaciju (
    dozvoliti stvaranje direktorija), te od svih odabranih opcija za
    instalaciju isključiti "**Catalyst Control Center 2**", ostale
    opcije ostaviti. Na kraju instalacije dozvoliti ponovno pokretanje
    računala i provjeriti ispravnost instalacije. Je li rezolucija
    monitora promijenjena?

19. Ponovno pokrenuti računalo i u **Multiboot** izborniku odabrati
    "**Other OS and Tools", te zatim "Hiren's Boot CD**" stavku.
    Pojaviti će se slijedeći izbornik te je u njemu potrebno odabrati
    "**Mini Windows XP**" opciju. Nakon učitavanja "**Mini Windows XP**"
    sustava, pojaviti će se radna površina. Pokrenuti aplikaciju
    **Windows Explorer**. U direktoriju **IMAGE** pokrenuti
    **GHOST32.exe** aplikaciju i prema uputama spremiti pričuvne kopije
    **H13** (ime **H13appl.gho**) i **WIN7** (ime **WIN7appl.gho**)
    particija.

20. Vratiti se na **HOME** particiju uz pomoć skripte iz prošle
    laboratorijske vježbe (potrebno je pokrenuti skriptu iz
    **Windows98** operacijskog sustava na **H13** particiji).
