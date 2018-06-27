Priprema novog tvrdog diska za korištenje
=========================================


.. admonition:: Cilj vježbe
    
    Svrha vježbe je upoznati korisnike sustava sa konfiguracijom novih tvrdih diskova (stvaranje particija i datotečnih sustava). Korisnik će uspješno dodati novi virtualni
    tvrdi disk, particionirati ga, te postaviti različite datotečne sustave na particije. Zatim će uspješno podići novostvorene particije (u obliku samo za čitanje, a zatim
    i sa mogućnošću zapisivanja na njih), te saznati detalje o njima.


.. admonition:: Predradnje
    
    Potrebno je imati ugašen virtualni stroj.


**Zadaci**:


1.  Dodati novi tvrdi disk u virtualni stroj, veličine 1GB (stvoriti novi disk). Pokrenuti virtualni stroj, te se prijaviti u operacijski sustav.

2.  Ispisati popis tvrdih diskova iz komandne linije (aplikacija ``fdisk``, koristiti sa **root** ovlastima)

3.  Proučiti **Master Boot Record** polja od postojećeg i novog diska. Koja je razlika? Zašto?

4.  Koristeći ``fdisk`` aplikaciju stvoriti prazan **DOS MBR** na novom disku i provjeriti rezultat
    (dodan serijski broj diska i 55AA).

5.  Pomoću ``fdisk`` aplikacije, na novostvorenom MBR sektoru stvoriti dvije 512MB particije. Tip datotečnog sustava prve particije je EXT4, a druge
    NTFS. Zapisati promjene.

6.  Ponovno proučiti MBR novog tvrdog diska. Što se može uočiti? Zapisati podatke o novim particijama

7.  Na ekranu prikazati sadržaj prvog sektora prve i druge particije novog diska (kombinacija aplikacija ``dd`` i ``xxd``). Što se može zaključiti? Zašto su sektori prazni?
    
8.  Stvoriti EXT4 datotečni sustav na prvoj particiji (aplikacija ``mkfs.ext4``, Label max 16 znakova, opcija ``verbose``)

9.  Stvoriti NTFS datotečni sustav na drugoj particiji (aplikacija ``mkfs.ntfs``, opcije ``fast``, ``verbose`` i ``label``)

10. Ponovno proučiti izgled prvog sektora prve i druge particije novog diska. Što se može zaključiti? Saznati zašto je prvi sektor EXT4 datotečnog sustava i dalje prazan.

11. Stvoriti dva direktorija PrvaEXT4 i DrugaNTFS unutar **/mnt/** direktorija.

12. Podići (eng. mount) EXT4 particiju (``type``, ``device``, ``dir``, ``verbose``, ``-o rw``) unutar PrvaEXT4 direktorija.

13. Pokušati stvoriti direktorij unutar PrvaEXT4 direktorija. Je li radnja uspješna? Koje je značenje poruke?

14. Promijeniti vlasnika mount točke (direktorij PrvaEXT4) kao prijavljenog korisnika (aplikacija ``chown``)

15. Ponovno pokušati stvoriti direktorij unutar PrvaEXT4 direktorija. Što se dogodilo? Je li radnja uspješna?

16. Podići NTFS particiju (``type``, ``device``, ``dir``, ``verbose``, ``-o ro``) unutar DrugaNTFS direktorija.

17. Pokušati promijeniti vlasnika mount točke. Je li radnja uspješna? Koje je značenje poruke?

18. Spustiti (eng. unmount) NTFS particiju.

19. Ponovno ju podići, ali ovaj puta sa pravima trenutno prijavljenog
    korisnika (koristiti opciju UID, točan ID korisnika saznati u
    ``/etc/passwd`` datoteci).

20. Pokušati stvoriti neki direktorij unutar DrugaNTFS direktorija. Što se dogodilo? Zašto?

21. Ponovno pokrenuti virtualni stroj. Što se dogodilo sa EXT4 i NTFS particijama,jesu li još uvijek podignute unutar direktorija?

22. Saznati UUID particija (aplikacija ``blkid``)

23. Proučiti sadržaj ``/etc/fstab`` datoteke (aplikacija ``man``).

24. Dodati particije u ``/etc/fstab`` datoteku prema UUID broju.

25. Spremiti pričuvnu kopiju MBR sektora novog diska (koristeći redirekciju u datoteku).
