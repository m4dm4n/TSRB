**Što je datotečni sustav**
===========================

Termin datotečnog sustava podrazumijeva neki skup metoda i struktura
podataka sa zadatkom organizacije, manipulacije,navigacije te pristupa
datoteka na nekom disku ili particiji. Uglavnom se sustav definira i
proučava kroz više aspekata pristupa :

-  Pohrana podataka ( eng. Data Storage)

-  Upravljanje nazivima objekata (eng. Namespace)

-  Sigurnosni model (eng. Security Model)

-  API funkcije

Dio koji se tiče same pohrane podataka je uglavnom vezan uz samu
organizaciju objekata na datotečnom sustavu kao što je : organizacijska
struktura direktorija, podrška za velike datoteke, podrška za Dnevnički
sustav ( eng. Journaling), mehanizmi rješavanje problema
fragmentacije...

Svaki datotečni sustav ujedno mora imati riješenu organizaciju
upravljanja nazivima objekata, kao što je recimo ukupan broj znakova u
imenu.

Sigurnosni model uglavnom podrazumijeva metode upravljanja sigurnosnim
dozvolama za korisnike prilikom pristupa datotekama i ostalim objektima.
Još jedan primjer bi bio podrška enkripcije objekata na datotečnom
sustavu

API (eng. Application Programming Interface) funkcije su specifične za
svaku vrstu datotečnog sustava, a njihova svrha je stvoriti određeni
softverski okvir (eng. framework) za korištenje sistemskih poziva
operacijskog sustava kako bi se standardizirao pristup nekom objektu
datotečnog sustava sa aplikacijske razine. Bez ovog podsustava , svaka
aplikacija na operacijskom sustavu bi trebala imati dodatne integrirane
metode i funkcije za korištenje nekog datotečnog sustava.

https://opensource.com/article/17/5/introduction-ext4-filesystem

https://opensource.com/life/16/10/introduction-linux-filesystems


