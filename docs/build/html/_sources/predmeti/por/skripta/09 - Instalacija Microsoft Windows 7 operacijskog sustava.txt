Instalacija Microsoft Windows 7 operacijskog sustava
====================================================

Ugasiti virtualni stroj, te ponovno maknuti VMUDrive000.vmdk iz popisa.
Dodati ISO sliku Windows7 instalacije u virtualni CD-ROM uređaj
(Settings, kategorija Storage), na način da se odabere ikona CD-a sa
desne strane prozora, te kasnije opcija "Choose Virtual Optical Disk
File...". U otvorenom prozoru potrebno je navigirati do lokacije na
kojoj se nalazi ISO slika instalacijskog CD-a, te ju učitati.

|image0|

Pokrenuti virtualni stroj, te na samom početku pritisnuti tipku F12 i
odabrati podizanje sa CD-ROM uređaja (tipka **c**).

|image1|

Bilo kojom tipkom potvrditi pokretanje instalacije, kao odgovor na
slijedeću poruku:

|image2|

Nakon što se pojavilo grafičko sučelje instalacije, u prvom koraku je
potrebno odabrati jezik za instalaciju, postavku formata za prikaz
vremena, te odabir tipa tipkovnice. Odabrati opcije kao prema slijedećoj
slici:

|image3|

U slijedećem prozoru odabrati opciju "Install now".

|image4|

Potrebno je potvrditi uvjete licence za korištenje ovog operacijskog
sustava, te kliknuti na tipku Next za nastavak.

|image5|

U ovom prozoru se pojavljuju dvije mogućnosti:

-  "Upgrade" ako se na računalu nalazi neka prošla verzija Windows
   operacijskog sustava, te se želi instalirati novija verzija, no sa
   sačuvanim osobnim podacima i postavkama

-  Odabir "Custom" opcije ne čuva podatke na particiji, i instalira novu
   verziju operacijskog sustava

Odabrati **"Custom"** opciju.

|image6|

U slijedećem prozoru je potrebno odabrati lokaciju, odnosno particiju za
instalaciju Windowsa 7.

Potrebno je dobro obratiti pozornost na prikazane particije, te
usporediti informacije sa dokumentacijom. U laboratorijskim uvjetima je
slika nešto drugačija, i prikazana su "Unallocated" područja između
particija. Prisjetiti se kako se na računalima u laboratoriju nalazi
mnogo particija, te da "Unallocated" prostor samo znači da informacije o
particijama nisu unutar particijske tablice. U virtualnom računalu
potrebno je odabrati WIN7 particiju za instalaciju, a u laboratoriju onu
particiju koju zahtijeva zadatak laboratorijske vježbe.

|image7|

U slijedećem koraku je prikazan proces kopiranja datoteka operacijskog
sustava na tvrdi disk. Nakon završetka, operacijski sustav će biti
instaliran, i potrebno je konfigurirati par osnovnih postavki.

|image8|

U slijedećem prozoru, na virtualnom računalu potrebno je kao korisničko
ime upisati PrezimeIme učenika-ce, te za ime računala upisati Razred
učenika ( bez točke iza rednog broja).

|image9|

Iako je uglavnom poželjno zaštititi korisnički račun sa lozinkama, u
ovom slučaju se ovaj korak može preskočiti.

NAPOMENA: Ako se lozinka ipak želi unijeti, potrebno ju je zapisati
negdje za slučaj da se zaboravi.

|image10|

Microsoft Windows 7 nudi mogućnost automatskih nadogradnji raznih
dijelova operacijskog sustava, no potrebno je odabrati opciju "Ask me
later".

|image11|

Provjeriti predloženu vremensku zonu, datum i vrijeme, te upisati točne
podatke.

|image12|

U slučaju da je u računalu ugrađena mrežna kartica i spojena na mrežni
sustav, biti će prepoznata od strane Windows 7 operacijskog sustava, te
će se predložiti 3 moguće postavke, temeljene na sigurnosnoj razini
konfiguracije. Odabrati Work Network opciju.

|image13|

Instalacija Windows 7 operacijskog sustava je završena. Prije bilo
kakvih radnji, potrebno je isključiti opciju Automatske nadogradnje
operacijskog sustava. Pritisnuti tipku Start (WIN tipka na tipkovnici),
u Search polje upisati "Windows update", te iz popisa odabrati "Windows
Update" aplikaciju.

|image14|

U otvorenom prozoru s lijeve strane odabrati opciju "Change settings".

|image15|

Iz izbornika, od ponuđenih odabira, odabrati opciju "Never check for
updates (not recommended)".

|image16|

Za postizanje "dual boot" sustava između Windows 98 i Windows 7,
potrebno je izvršiti dodatnje radnje. Pokrenuti Windows Explorer
aplikaciju ( WIN tipka + E kombinacija), te primijetiti popis prikazanih
particija. Particija sa Windows7 instalacijom će uvijek biti C:
particija. Uočiti da nije prikazana WIN98 particija. Windows 7 neće
automatski podignuti ( i dodati joj slovo) particiju na kojoj se nalazi
FAT32 datotečni sustav, te je potrebno to učiniti ručno.

|image17|

.. |image0| image:: media09/image1.png
   :width: 7.08333in
   :height: 1.76528in
.. |image1| image:: media09/image2.png
   :width: 3.23333in
   :height: 2.21667in
.. |image2| image:: media09/image3.png
   :width: 2.36220in
   :height: 0.40063in
.. |image3| image:: media09/image4.png
   :width: 5.38611in
   :height: 1.77292in
.. |image4| image:: media09/image5.png
   :width: 2.68958in
   :height: 2.50764in
.. |image5| image:: media09/image6.png
   :width: 6.25000in
   :height: 2.21181in
.. |image6| image:: media09/image7.png
   :width: 6.11389in
   :height: 3.05278in
.. |image7| image:: media09/image8.png
   :width: 5.10366in
   :height: 3.54331in
.. |image8| image:: media09/image9.png
   :width: 5.50764in
   :height: 2.40903in
.. |image9| image:: media09/image10.png
   :width: 5.56042in
   :height: 2.37847in
.. |image10| image:: media09/image11.png
   :width: 5.31042in
   :height: 3.11389in
.. |image11| image:: media09/image12.png
   :width: 4.31531in
   :height: 2.75591in
.. |image12| image:: media09/image13.png
   :width: 4.91383in
   :height: 3.54331in
.. |image13| image:: media09/image14.png
   :width: 5.22140in
   :height: 3.14961in
.. |image14| image:: media09/image15.png
   :width: 3.47084in
   :height: 4.33071in
.. |image15| image:: media09/image16.png
   :width: 7.08611in
   :height: 2.14805in
.. |image16| image:: media09/image17.png
   :width: 5.34952in
   :height: 2.75591in
.. |image17| image:: media09/image18.png
   :width: 5.55278in
   :height: 2.06042in
