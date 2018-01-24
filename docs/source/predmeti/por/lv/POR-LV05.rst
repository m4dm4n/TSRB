LV05
====

Rad u Total Commander aplikaciji
--------------------------------

**Cilj vježbe**:

Sve postupke, korištene naredbe i dobivene rezultate po točkama zadataka
zapisivati u bilježnicu. Odgovoriti u bilježnicu na postavljena pitanja
vezana uz ovu vježbu.

**Zadaci:**

1.  Iz **HOME** particije ponovno pokrenuti računalo i u Multiboot
        izborniku odabrati "Other OS and Tools", te zatim "Hiren's Boot
        CD" stavku. Pojaviti će se slijedeći izbornik te je u njemu
        potrebno odabrati „Mini Windows XP“ opciju. Nakon učitavanja
        „Mini Windows XP“ sustava, pojaviti će se radna površina.

2.  Pokrenuti HBCD menu i odabrati izbornik Programs, te zatim
        Browsers/File managers. Unutar izbornika odabrati aplikaciju
        Total Commander.

3.  Postaviti RAMDRIVE ( B: ) aktivnu particiju na lijevom prozoru, a
    MULTIBOOT ( D: ) na desnom prozoru.

4.  U korijenskom direktoriju D: particije stvoriti novi direktorij s
    imenom LV\_POR.

5.  Unutar LV\_POR direktorija stvoriti novu datoteku s imenom razreda
    (bez točke iza rednog broja) i trenutne godine, a kao ekstenziju
    upisati tekstualni tip datoteke (npr 3C2016.txt). Spremiti praznu
    datoteku I Izaci Iz uredjivaca teksta. Koja je velicina datoteke?
    Zasto?

6.  U datoteku upisati posebno u svaki red ime i prezime učenika na
    radnom mjestu. Spremiti promjene i izaći iz datoteke. Koja je sad
    velicina datoteke? O cemu tocno ovisi velicina datoteke?

7.  Iz Total Commander aplikacije odabrati opciju pregleda sadržaja
    datoteke. Mogu li se vršiti izmjene nad datotekom? Zašto?

8.  Iz Total Commander aplikacije odabrati opciju za izmjenu sadržaja
    datoteke. Iza imena svakog učenika dodati razred. Spremiti promjene
    i izaći iz datoteke.

9.  U korijenskom direktoriju B: particije stvoriti novi direktorij pod
    imenom POR\_PRIMJER.

10. Preimenovati POR\_PRIMJER direktorij u POR\_TEST. Postaviti
    direktorij kao radni direktorij.

11. Sa putanje X:\\i386 kopirati datoteke explorer.exe, I\_view32.exei
    direktorij INF, u odredišni direktorij POR\_TEST. Dodatno u isti
    direktorij kopirati datoteku s imenom razreda. Potvrditi da je
    postupak premještanja uspješno izvršen.

12. Unutar direktorija B:\\INF, odabrati sve datoteke I komprimirati ih
    koristeci 7zip ugradjen u kontekstualni izbornik. Komprimiranu
    datoteku nazvati Backup\_Inf.

13. Premjestiti Backup\_Inf datoteku u korijenski direktorij B:
    particije. Obrisati sve datoteke iz B:\\INF direktorija.

14. Pokrenuti komandnu liniju, te postaviti direktorij B:\\POR\_TEST kao
    radni direktorij. Raspakirati sadrzaj Backup\_Inf.7z datoteke u
    B:\\POR\_TEST\\INF direktorij.

15. Iz Total Commander aplikacije odabrati direktorij INF , te datoteke
    Backup\_Inf.7z i explorer.exe. Nad odabranim objektima postaviti
    skriveni (eng. Hidden) atribut.

16. Iz komandne linije ispisati sadrzaj B:\\POR\_TEST direktorija. Koje
    su sve datoteke vidljive? Zasto?

17. Iz komandne linije iskljuciti skrivene atribute svim objektima
    unutar B:\\POR\_TEST direktorija, koristeci “wildcard” znakove.

18. Sto se dogodilo sa skrivenim atributom INF direktorija? Koje opcije
    je potrebno koristiti u attrib naredbi kako bi se obuhvatili I
    direktoriji? Skinuti skriveni atribut navedenom direktoriju Iz
    naredbene linije.

1. Postaviti atribut samo za citanje nad datotekom s imenom razreda.
   Pokusati izmijeniti sadrzaj datoteke. Je li izmjena uspješno
   spremljena? Je li se dogodilo što drukčije u odnosu na spremanje
   datoteke sa početka ove vježbe? Može li se izmijeniti ime datoteke?
   Zašto?

1. U komandnoj liniji upisati naredbu za prikaz sadržaja direktorija
   B:\\POR\_TEST. Ponoviti postupak, no filtrirati izlazni rezultat
   upotrebom „wildcard“ znakova kako bi se prikazala samo datoteke sa
   “exe” ekstenzijom.

2. U komandnoj liniji ispisati sadrzaj direktorija B:\\POR\_TEST\\INF,
   no prikazati samo datoteke koje pocinju sa slovom “p”.

3. Ponovno pokrenuti računalo bez USB pogona, te se uvjeriti u podizanje
   sustava na HOME particiji.
