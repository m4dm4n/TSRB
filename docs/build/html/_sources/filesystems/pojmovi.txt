**Pojmovi**
===========

**Disk/drive -** Uređaj za pohranu podataka. Disk uglavnom podrazumijeva
rotirajuće diskove, dok se Drive terminologija u zadnje vrijeme povezuje
sa solid state uređajima (npr. Solid State Drive).

**Sektor (eng. Sector) -** Najmanja definirana jedinica zapisa na tvrde
diskove, najčešće je veličine 512B (no,moguće su i druge veličine). Na
modernim diskovima, češće se koristi terminologija "logički blok"
(implementacijom LBA adresiranja). Kada se govori o SSD uređajima,
uglavnom se primjenjuje pojam logičkog bloka, koji je u pravilu veličine
4KiB.

**Particija (eng. Partition) -** Definirano područje na tvrdom disku
omeđeno početnom i završnom adresom. Terminologija se može koristiti i u
općenitom području memorije. Na particiju se obično stavlja datotečni
sustav (iako to nije uvijek slučaj, npr. kod korištenja nekih sustava
baza podataka koji implementiraju svoj sustav pohrane podataka), te na
njega operacijski sustav ili općenite datoteke.

**Volumen (eng. Volume) -** Jednaka definicija kao i za particiju, no
kada se priča o volumenu, podrazumijeva se da je na particiju postavljen
datotečni sustav.

**Datotečni sustav (eng. Filesystem) -** Skup metoda i struktura
podataka sa zadatkom organizacije datoteka na disku ili particiji.

**Blok (eng. Block) -** Sa stajališta EXTx datotečnih sustava, blok je
jedna logička cjelina koja se sastoji od jednog ili više sektora (ili
logičkih blokova),u svrhu optimalnije organizacije podataka na
datotečnom sustavu.

**Klaster (eng. Cluster) -** Jednaka definicija kao za blokove, no
terminologija se uglavnom koristi u Microsoft datotečnim sustavima.

**Super Blok (eng. SuperBlock) -** Osnovna struktura na EXTx datotečnim
sustavima. U sebi sadrži osnovne informacije o konfiguraciji datotečnog
sustava, te je kritična za ispravno podizanje.

**Inode (eng. Index NODE)** - Struktura podataka koja sadrži metapodatke
o nekom objektu na datotečnom sustavu (datoteka). Metapodaci su uglavnom
sigurnosne dozvole (eng. permissions), vremena korištenja objekta
(access, modify, created), te pokazivači prema samom sadržaju objekta.

**Linearni zapis (eng. Linear record) -** Tip organizacije strukture
podataka. Podaci se zapisuju u neku memoriju linearnom metodom, jedan
iza drugog.

**Stablasta struktura (eng. Tree structure) -** Tip organizacije
strukture podataka. Podaci se zapisuju u neku memoriju stablastom
strukturom, počevši od korijena, prema razgranatom strukturom.

**Binarno stablo (eng. Binary tree) -** Poseban tip strukture stabla.
Svaki čvor/roditelj u stablu može sadržavati najviše dvoje djece.

**B-tree struktura -** Poseban tip strukture stabla. U usporedbi sa
binarnim stablom, čvorovi u stablu mogu sadržavati i više od dvoje
djece.

**Hash tablica -** Tip zapisa podataka. Tablica nekih podataka u kojoj
se svaki podatak povezuje sa nekom hash vrijednošću (hash funkcija se
često izračunava ili direktno iz vrijednosti samog podataka, odnosno
vrijednosti povezane uz taj podatak).

**Hash-tree struktura -** Poseban tip strukture stabla. Radi se o
kombinaciji B-Tree strukture i Hash tablice.
