Prilog 2 – Opis standardnog Master Boot Record područja
=======================================================

OPIS MASTER BOOT RECORD PODRUČJA,PARTICIJSKA TABLICA

Absolute Sector **0** (Cylinder 0, Head 0, Sector **1**)

0 1 2 3 4 5 6 7 8 9 A B C D E F

0000 33 C0 8E D0 BC 00 7C 8E C0 8E D8 BE 00 7C BF 00 3.....\|......\|..

0010 06 B9 00 02 FC F3 A4 50 68 1C 06 CB FB B9 04 00 .......Ph.......

0020 BD BE 07 80 7E 00 00 7C 0B 0F 85 0E 01 83 C5 10 ....~..\|........

0030 E2 F1 CD 18 88 56 00 55 C6 46 11 05 C6 46 10 00 .....V.U.F...F..

0040 B4 41 BB AA 55 CD 13 5D 72 0F 81 FB 55 AA 75 09 .A..U..]r...U.u.

0050 F7 C1 01 00 74 03 FE 46 10 66 60 80 7E 10 00 74 ....t..F.f\`.~..t

0060 26 66 68 00 00 00 00 66 FF 76 08 68 00 00 68 00 &fh....f.v.h..h.

0070 7C 68 01 00 68 10 00 B4 42 8A 56 00 8B F4 CD 13 \|h..h...B.V.....

0080 9F 83 C4 10 9E EB 14 B8 01 02 BB 00 7C 8A 56 00 ............\|.V.

0090 8A 76 01 8A 4E 02 8A 6E 03 CD 13 66 61 73 1C FE .v..N..n...fas..

00A0 4E 11 75 0C 80 7E 00 80 0F 84 8A 00 B2 80 EB 84 N.u..~..........

00B0 55 32 E4 8A 56 00 CD 13 5D EB 9E 81 3E FE 7D 55 U2..V...]...>.}U

00C0 AA 75 6E FF 76 00\ **[**\ E8 8D 00 75 17 FA B0 D1 E6 64
.un.v....u.....d

00D0 E8 83 00 B0 DF E6 60 E8 7C 00 B0 FF E6 64 E8 75 ......\`.\|....d.u

00E0 00 FB B8 00 BB CD 1A 66 23 C0 75 3B 66 81 FB *54*
.......f#.u;f..\ ***T***

00F0 *43 50 41* 75 32 81 F9 02 01 72 2C 66 68 07 BB 00
***CPA***\ u2....r,fh...

0100 00 66 68 00 02 00 00 66 68 08 00 00 00 66 53 66 .fh....fh....fSf

0110 53 66 55 66 68 00 00 00 00 66 68 00 7C 00 00 66 SfUfh....fh.\|..f

0120 61 68 00 00 07 CD 1A\ **]**\ 5A 32 F6 EA 00 7C 00 00 CD
ah.....Z2...\|...

0130 18 A0 B7 07 EB 08 A0 B6 07 EB 03 A0 B5 07 32 E4 ..............2.

0140 05 00 07 8B F0 AC 3C 00 74 09 BB 07 00 B4 0E CD ......<.t.......

0150 10 EB F2 F4 EB FD\ **[**\ 2B C9 E4 64 EB 00 24 02 E0 F8
......+..d..$...

0160 24 02 C3\ **]**\ 49 6E 76 61 6C 69 64 20 70 61 72 74 69 $..Invalid
parti

0170 74 69 6F 6E 20 74 61 62 6C 65 **00** 45 72 72 6F 72 tion
table\ **.**\ Error

0180 20 6C 6F 61 64 69 6E 67 20 6F 70 65 72 61 74 69 loading operati

0190 6E 67 20 73 79 73 74 65 6D **00** 4D 69 73 73 69 6E ng
system\ **.**\ Missin

01A0 67 20 6F 70 65 72 61 74 69 6E 67 20 73 79 73 74 g operating syst

01B0 65 6D **00** 00 00 **63 7B 9A** D4 34 A0 2E 00 00 **80 01**
em\ **.**..\ **c{.**.4..... 

01C0 **01** 00 **06 FE 3F 02 3F 00** 00 00 04 **BC 00 00 00 00**
!.......... ....

01D0 **00 00 00** 00 00 00 00 00 00 00 00 00 00 00 00 00
................

01E0 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 ................

01F0 00 00 00 00 00 00 00 00 00 00 00 00 00 00 **55 AA**
..............U.

0 1 2 3 4 5 6 7 8 9 A B C D E F

**80 01 01 00 06 FE 3F 02 3F 00 00 00 04 BC 00 00**

0x80 (dec : 128) - Bootflag oznaka

0x000101 - Početna CHS adresa particije u "CSH" obliku

CYLINDER – 0x00

SECTOR – 0x01

HEAD – 0x01

0x06 (dec : 6) – Identifikacija datotečnog sustava particije (za popis
svih oznaka, pogledati u prilogu dokumenta)

0x023FFE – Završna CHS adresa particije u "CSH" obliku

CYLINDER – 0x02

SECTOR – 0x3F

HEAD – 0xFE

0x0000003F – Početna adresa particije u "LBA" obliku

0x0000BC04 – Broj sektora koje particija zauzima na disku (veličina
particije)
