**NOTE FROM THE AUTHOR:**
*Nemojte uzeti ovu skriptu zdravo za gotovo. Neke zadatke sam sama rješavala i nisu provjereni. Also ovim putem želim napisati da ako netko nauči nešto krivo iz ove skripte i sj\*\*\* zadatak na ispitu, nisam kriva. Tko vam kriv što niste išli provjerit negdje da ja nisam luda. :D* 
*also, ovo je napravljeno u markdown editoru koji mi je default za sve, zato je editing off jer nemam pageve.*


## IP adrese
// note: razumijem zadatke s IP adresama, nisam ih objasnjavala, vidi IP calc stranicu da ti pomogne shvatit (at least i did it that way)
1. 1. **Uspostavljena je komunikacija između računala s adresama 79.144.98.159/18 i 79.144.68.116/18. Jesu li ona povezana usmjeriteljem?**	 
 - nisu
 
<br>

1. 2. **IP adresa računala je 156.149.149.50/20. Adresa mreže u kojoj se nalazi to računalo je:**
 - 156.149.144.0

<br>

1. 3. **IP adresa klase A koja odgovara nekom konkretnom računalu u mreži sastoji se od:**
 - mrežnog prefiksa i računalnog dijela

<br>

1. 4. **IP adresa računala je 131.129.141.128/19. Adresa mreže u kojoj se nalazi to računalo je:**
 - 131.129.128.0

<br>

1. 5. **U podmreži u kojoj se nalazi računalo s adresom 161.53.114.131/19, najveći broj računala koje je moguće adresirati je:**
- 2^(32-19) - 2 = 8190 

<br>

1. 6. **Proizvođač mrežne kartice svakoj kartici dinamički dodjeljuje IP adresu.**
 - netočno



<br>
<br>
<br>

## Postupci i akcije u procesu usmjeravanja
2.  **Koji postupak slijedi ako je u procesu usmjeravanja utvrđena neispravnost zaglavlja IP - datagrama?** 
 - IP - datagram se odbacuje, bez slanja ICMP poruke o pogrešci pošiljatelju.
 
<br>

3. **Koju od sljedećih akcija izvršava čvor u procesu usmjeravanja ako koristi algoritam preplavljivanja?**
 - Prati „već viđene” pakete, kako bi se duplikati mogli odbaciti.

<br>

3. 1. **Ako u tablici usmjeravanja ne postoji odredište koje se podudara s odredištem datagrama kojeg je potrebno proslijediti, usmjeritelj će:**
 - ispustiti datagram i poslati ICMP poruku na izvorište paketa

<br>

3. 2. **Preplavljivanje kao statički algoritam usmjeravanja određuje prosljeđivanje svih dolaznih paketa u komutacijskom čvoru:**
 - Na sva sučelja, osim onog po kojem je primio paket, ako se radi o paketu koji taj čvor nije već ranije primio.


<br>
<br>
<br>
<br>

## Ping
5.  **Koristite alat ping da biste poslali IP-datagram veličine 2000 okteta. Koju zastavicu koristite?**
 - \-s
 
 <br>

<br><br> 
<br>


## Slike topologije
6. **Na slici je prikazana mrežna topologija. Može li računalo pc1 ARP-upitom saznati MAC-adresu računala server?** ![[Pasted image 20210417134605.png]]
 - ne

<br>

## Mrežni promet, wireshark, traceroute, ping
7. 1. **Između izvorišta i odredišta je 10 usmjeritelja. Na izvorištu pokrećemo naredbu traceroute i nastojimo saznati put do odredišta. Istovremeno, na četvrtom usmjeritelju (na sučelju koje je bliže odredištu) pokrećemo mrežni analizator prometa Wireshark i snimamo promet. Koji promet je snimljen?**
 - Svi datagrami u kojima je TTL bio postavljen na 5 ili više.

<br>

7. 2. **Traceroute radi tako da:**
 - od svakog čvora na putu do odredišta saznaje IP adresu na temelju ICMP poruka u greški



8. **Računalo PC 1 i računalo PC 2 nalaze se u istoj lokalnoj mreži. Na mrežnom sučelju eth0 računala PC 1 vrijednost MTU-a je postavljena na 500 okteta. S računala PC 1 poslan je ICMP Echo Request s parametrom veličine podatkovnog polja postavljenim na 1000 okteta. Koliko fragmentiranih IP-datagrama će primiti računalo PC 2?**
 - 3

<br>

## Struktura
9. 1. **Mreže koje su temeljene na potpuno različitim arhitekturama i protokolnim složajevima moraju se povezati usmjeriteljima (router).**
 - netočno

<br>

9. 3. **Mreže koje su temeljene na potpuno različitim arhitekturama i protokolnim složajevima povezuju se prilazima (gateway).**
 - točno


9. 2. **Koji uređaj razdvaja domene sudara, ali ne razdvaja MAC broadcast domene?**
 - Ethernetski komutator - eternetski switch

<br>

9. 22. **Koji uređaj razdvaja domene sudara i MAC broadcast domene?**
 - usmjeritelj

<br> 

9. 23. **Koji uređaj ne razdvaja ni domene sudara ni MAC broadcast domene?**
 - parični obnavljač - hub

<br>

9. 3. **Logička topologija 10BASE5 mreže je:**
 - Sabirnica

<br>

9. 24. **Logička topologija mreže povezane obnavljačem je:**
 - sabirnica

<br>

9. 25. **Logička topologija Token Bus mreže je:**
 - sabirnica

<br>

9. 26. **Logička topologija Token Ring Mreže je**
 - prsten

<br>

9. 4. **Fizička topologija mreže povezane komutatorom je:**
 - zvijezda

<br>

9. 21. **Fizička topologija 10BASE5 mreže je:**
 - sabirnica

<br>

9. 23. **Fizička topologija 10BASE-T mreže je:**
 - zvijezda

<br>

9. 22. **Fizička mrežna topologija najčešće korištena kod izvedbe lokalnih mreža tehnologijom Gigabitnog Etherneta?**
 - zvijezda

<br>


9. 5. **Nedostatak komutatora (switcha) u odnosu na parični obnavljač (hub) leži u činjenici da obnavljač uklanja mogućnost kolizije.**
 - netočno

<br>

9. 22. **Prednost komutatora u odnosu na parični obnavljač leži u činjenici da komutator uklanja mogućnost kolizije.**
 - točno

<br>

9. 23. **Prednost obnavljača u odnosu na koaksijalni kabel leži u činjenici da obnavljač uklanja mogućnost kolizije.**
 - netočno

<br>



9. 6. **Kako se zove uređaj kojim se povezuje mreže temeljene na potpuno različitim mrežnim arhitekturama i protokolnim složajevima?**
 - prilaz - gateway

<br>

9. 7. **Koliko bita je dugačka MAC adresa mrežnih kartica koja se danas najčešće koristi?**
 - 48 bita

<br>

9. 9. **Svaki krajnji uređaj mora imati jedinstvenu hardversku (MAC) adresu u cijelom svijetu.**
 - točno


9. 8. **U svakom mrežnom uređaju koji podržava neki od protokola mrežnog sloja nužno postoji i podrška za protokole svih nižih slojeva**
 - točno

<br>

9. 10. **S obzirom da komutator kapaciteta 10Mbit/s mora obavljati obradu primljenih okvira, njegov efektivni kapacitet je manji od paričnog obnavljača (hub) istog kapaciteta.**
 - netočno

<br>

9. 11. **Kod nespojne usluge bez potvrde primitka okvira NIJE implementirano upravljanje tokovima pri upravljanju logičkom poveznicom.**
 - točno 

<br>

9. 12. **Kod nespojne usluge bez potvrde primitka okvira implementirano JE upravljanje tokovima pri upravljanju logičkim linkom**
 - netočno 


<br>

9. 12. **Zadnja 24 bita u hardverskoj (MAC) adresi mrežne kartice označavaju:**
 - karticu pojedinog proizvođača

<br>

9. 14. **Prva 24 bita u hardverskoj (MAC) adresi mreže kartice označavaju:**
 - proizvođača kartice

<br>

9. 13. **Kašnjenje transfera informacija između dvije krajnjh točaka u lokalnoj mreži manje je u odnosu na kašnjenje u javnoj mreži.**
 - točno

<br>

9. 14. **Prilikom slanja okvira na mrežu, šalje se preambula okvira. Njena je uloga:**
 - sinkronizacija takta


<br>
<br>
<br>
<br>
<br>

### Lokalne mreže
9. 9. **U lokalnim mrežama uglavnom se koristi decentralizirano upravljanje pristupom prijenosnom mediju**
 - točno

<br>

9. 10. **Na rad lokalnih mreža ne utječu elektromagnetske smetnje.**
 - netočno

<br>

9. 11. **Krajnji uređaji u lokalnim mrežama međusobno komuniciraju na načelu ravnopravnosti.**
 - točno

<br>

9. 12. **Koja od navedenih karakteristika nije karakteristika lokalne mreže (LAN-a)**
 - Mreža je obično instalirana na širem geografskom području (npr. grad)
 - Velika vjerojatnost nastupa pogreške
 

<br>

9. 13. **Svi okviri u LAN-u moraju sadržavati adresu pošiljatelja i adresu odredišta.**
 - točno

<br>

9. 14. **Mostovi uče topologiju LAN-a na osnovu odredišnih adresa upisanih u primljene okvire.**
 - netočno

<br>

9. 13. **Kašnjenje transfera informacija između dvije krajnjh točaka u lokalnoj mreži manje je u odnosu na kašnjenje u javnoj mreži.**
 - točno

<br>

9. 14. **Kako bi se omogućio dvosmjerni prijenos u lokalnoj mreži, nužno je koristiti:**
 - ethernetski komutator - switch

<br>

9. 15. **U LANu se tipično koriste mreže veće od 1 Mbit/s.**
 - točno

<br>

9. 26. **U LANu se tipično koriste prijenosne brzine manje od 10 Gbit/s.**
 - točno

<br>

9. 27. **U LANu se za komunikaciju može koristiti dijeljeni medij.**
 - točno

<br>

9. 28. **U LANu je broj umreženih stanica ograničen.**
 - točno

<br>

9. 29. **LAN mreža je obično u vlasništvu jedne organizacije.**
 - točno



9. 16. **U 10BROAD36 LAN-u prijenos se obavlja:**
 -  širokopojasno

<br>

9. 17. **Podsloj upravljanja logičkom poveznicom jednak je za sve vrste lokalnih mreža.**
 - točno

<br>

9. 22. **Fizička mrežna topologija najčešće korištena kod izvedbe lokalnih mreža tehnologijom Gigabitnog Etherneta?**
 - zvijezda

<br>

9. 23. **Krajnji uređaji u lokalnim mrežama međusobno komuniciraju na načelu ravnopravnosti.**
 - točno

<br>


<br>
<br>
<br>

### Ethernet
9. 8. **U ethernetu se problem višestrukog pristupa mediju rješava pomoću:**
 - metode otkrivanja nosioca

<br>


9. 1. **Kod etherneta izvedenog pomoću neoklopljenih parica (UTP), dio koji povezuje stanicu i priključak na obnavljaču naziva se:**
 - Segment

<br>

9. 2. **Kod paričnog etherneta, dio koji povezuje stanicu i priključak na obnavljaču naziva se: **
 - segment

<br>


9. 9. **Područje u ethernetskoj mreži unutar kojeg može doći do sudara naziva se**
 - domena sudara

<br>

9. 22. **Područje u ethernetskoj mreži unutar kojeg vrijedi pravilo da kad bilo koje dvije stanice istovremeno šalju svoje okvire, dolazi do sudara naziva se:**
 - domena sudara

<br>


9. 10. **Ethernetski komutator šalje primljeni okviri na sve priključke, osim na priključak po kojem je dotični okvir primio:**
 - U slučaju da u tablici komutiranja nema odgovarajuću adresu

<br>

9. 29. **Kada  ethernetski komutator primi okvir za čiju odredišnu MAC-adresu nema  zapis  u  tablici komutiranja, tada komutator:** 
 - prosljeđuje okvir po svim priključcima, osim po priključku po kojem je primio okvir.


9. 11. **Ethernetski komutator dozvoljeno je spojiti na obnavljač pri povezivanju LAN-ova**
 - točno

<br>

9. 13. **Ethernetski komutator nije moguće spojiti s drugim ethernetskim komutatorom jer bi to rezultiralo kolizijom**
 - netočno

<br>

9. 12. **Za upravljanje pristupom prijenosnom mediju kod ethernetskih mreža koristi se metoda prozivanja.**
 - netočno

<br>


9. 20. **Za upravljanje pristupom prijenosnom mediju kod ethernetskih mreža koristi se metoda prozivanja s prioritetima.**
 - netočno

<br>

9. 13. **Područje u ethernetskoj mreži unutar kojeg vrijedi pravilo da kad bilo koje dvije stanice istovremenu šalju svoje okvire, dolazi do sudara naziva se:**
 - domena sudara

<br>

15. 3. **Sudar se u ethernetskoj mreži manifestira kao:**
 - povišen napon

<br>

15. 4. **Što predstavlja tzv. rani sudar u mreži Ethernet?**
 - Situaciju kad stanica otkrije sudar napoveznici za vrijeme slanja svog okvira

<br>


9. 14. **Duljina segmenta kod paričnog etherneta ograničena je na:**
 - 100 metara

<br>

9. 15. **U tablici komutiranja ethernetskog komutatora su spremljeni parovi:**
 - MAC adresa, broj priključaka

<br>

9. 22. **Fizička mrežna topologija najčešće korištena kod izvedbe lokalnih mreža tehnologijom Gigabitnog Etherneta?**
 - zvijezda

<br>


<br>
<br>
<br>

## Slojevi
### Sloj podatkovne poveznice
10. 1. **Koji od navedenih uređaja radi na sloju podatkovne poveznice OSI referentnog modela?**
 - komutator - switch
 - most - bridge	

<br>

10. 2. **Aktivni mrežni uređaj koji radi na sloju podatkovne poveznice je:**
 - komutator - switch

<br>

10. 5. **Kako se naziva postupak kojim se paket višeg sloja referentnog modela OSI pretvara u paket nižeg sloja referentnog modela OSI?**
**Kako se naziva postupak pakiranja paketa višeg sloja OSI referentnog modela u paket nižeg sloja OSI referentnog modela?**
**Kako se naziva postupak kojim se podatkovna jedinica višeg sloja referentnog modela OSI (Open System
Interconnection) pretvara u podatkovnu jedinicu nižeg sloja referentnog modela OSI?**
 - enkapsulacija

<br>
<br>
<br>
<br>

###  Koji sloj OSI / (TCP/IP)
10. 3. **Koji je sloj OSI referentnog modela zadužen za uspostavljanje, upravljanje i raskid veze između aplikacija?**
 - sloj sesije

<br>

10. 4. **Koji sloj OSI referentnog modela pruža neovisnost o razlikama u načinu prikaza podataka?**
 - prezentacijski sloj

<br>

10. 5. **Koji sloj referentnog modela OSI omogućava usmjeravanje jedinica podataka kroz jednu ili više mreža?**
 - mrežni sloj

<br>


10. 6. **Koji sloj OSI referentnog modela je zadužen za sinkronizaciju okvira?**
 - sloj podatkovne poveznice

<br>

10. 7.  **Koji sloj OSI referentnog modela sadrži skup funkcija koje omogućuju korisnicima pristup OSI okružju?**
 - aplikacijski sloj

<br>


10. 8. **Koji sloj referentnog modela je zadužen za pretvorbu podatkovnih paketa u struju bita i obrnuto?**
 - podatkovni sloj

<br>

10. 9. **Koji sloj OSI referentnog modela definira mehaničke i električne karakteristike uređaja za pristup dfizičkom mediju?**
 - fizički sloj

<br>
 10. 10. **Koji sloj OSI referentnog modela ima funkcije koje obavlja ethernetski komutator?**
 - sloj podatkovne poveznice


<br>

10. 12. **Koji sloj OSI referentnog modela omogućuje pouzdan i transparentan prijenos podataka između krajnjih komunikacijskih točaka?**
 - transportni sloj


<br>

10. 11. **Koji sloj TCP/IP obavlja funkcije usmjeravanja IP datagrama?**
 - mrežni sloj



<br>
<br>
<br>
<br>


### Podslojevi
11. 1. **Podsloj upravljanja logičkom poveznicom različit je za različite vrste lokalnih mreža.**
 - netočno

<br>

11. 2. **Podsloj upravljanja logičkom poveznicom jednak je za sve vrste lokalnih mreža.**
 - točno

<br>

11. 3. **Podsloj upravljanja pristupom prijenosnom mediju implementiran je:**
 - hardverski, u mrežnoj kartici

<br>

11. 4. **Podsloj upravljanja pristupom prijenosnom mediju neovisan je o vrsti lokalnih mreža za koju je namijenjen**
 - netočno

<br>

11. 6. **Podsloj upravljanja pristupom prijenosnom mediju jednak je za sve vrste lokalnih mreža.**
 - netočno

<br>


11. 5. **Podsloj upravljanja logičkom poveznicom jednak je za sve vrste lokalnih mreža.**
 - točno

<br>

11. 6. **Uloga podsloja upravljanja logičkim poveznicom je**
 - Onemogućavanje višim protokolima da dijele zajednički medij
 - omogućavanje višim protokolima da dobije zajednički medij

<br>

11. 7. **Podsloj upravljanja logičkom poveznicom ovisi i korištenoj metodi pristupa mediju.**
  - netočno



<br>
<br>
<br>

### Na kojem sloju ... / ... radi na ... sloju
11. 5. **Na kojem sloju OSI referentnog modela su definirane funkcije za upravljanje pogreškama na krajnjim točkama?**
 - transportni sloj

<br>

11. 6. **Na kojem sloju OSI referentnog modela su definirane mehaničke i električne karakteristike uređaja za pristup fizičkom mediju?**
 - na fizičkom sloju

<br>

11. 7. **Koji od navedenih uređaja radi na fizičkom sloju OSI referentnog modela?**
 - parični obnavljač - hub

<br>

11. 8. **Komutator (switch) radi na:**
 - sloju podatkovne poveznice

<br>

11. 9. **Most (bridge) radi na:**
 - sloju podatkovne poveznice

<br>

11. 5. **Parični obnavljač (hub) radi na:**
 - fizičkom sloju

<br>

11. 10. **Usmjeritelj (router) radi na:**
 - mrežnom sloju

<br>

11. 11. **Prolaz(gateway) radi na:**
 - aplikacijskom sloju

<br>

11. 12. **Aktivni mrežni uređaj koji radi na podatkovnom sloju je **
 - most - bridge
 - komutator - switch


<br>
<br>
<br>
<br>

## Protokoli

### CSMA/CD
12. 1. **Slobodan medij se kod CSMA/CD protokola manifestira niskim naponom.**
 - točno

<br>

12. 5. **Slobodan medij se kod CSMA/CD protokola manifestira visokim naponom.**
 - netočno

<br>

12. 2. **Kako stanica otkriva prisutnost signala na mediju kod pristupnog protokola CSMA/CD?**
 - mjerenjem napona na mediju

<br>

12. 3. **Signal zagušenja (jamming signal) kod protokola CSMA/CD šalju samo one stanice koje su slale okvire u trenutku kada je došlo do sudara.**
 - netočno

<br>

12. 4. **Kod CSMA/CD protokola, stanica koja šalje okvir:**
 - Stalno osluškuje medij, kad uoči da je došlo do sudara, prekida slanje i šalje signal zagušenja duljina 32 bita

<br>

12. 9. **Kod CSMA/CD protokola, stanica koja je slala okvir te uočila da je došlo do sudara će:**
 - Prekinuti slanje okvira, poslati signal zagušenja, te pričekati pseudo-slučajno vrijeme pa tek tada pokušati iznova slati okvir

<br>

12. 6. **Kod CSMA/CD protokola, stanica koja se sprema poslati okvir na medij će:**
 - Provjeriti je li medij slobodan, pričekati da istekne vrijeme razmaka između okvira (IFG) te početi slati okvir

<br>

12. 7. **Kod CSMA/CD protokola:**
 - Svaka stanica mjeri napon na mediju, čime otkriva pristustvo nosioca

<br>


12. 5. **CSMA/CD je pristupni protokol sa slučajnim pristupom prijenosnom mediju**
 - točno

<br>

12. 7. **CSMA/CD je primjer decentraliziranog upravljanja pristupom prijenosnom mediju**
 - točno

<br>

12. 8. **Sudar se kod CSMA/CD protokola manifestira promjerom polariteta napona.**
 - netočno


<br>
<br>
<br>
<br>

### ARP
13. 1. **Zahtjevi koje generira ARP prenose se pomoću protokola Ethernet.**
 - točno

<br>

13. 7. **Zahtjevi koje generira ARP prenose se pomoću protokola IP.**
 - netočno


13. 2. **ARP (Address Resolution Protocol) upiti:**
 - usmjeravaju se s obzirom na odredišnu IP adresu

<br>

13. 3. **Protokol ARP povezuje:**
 - IP adrese i Ethernet MAC adrese

<br>

13. 4. **ARP upiti:**
 - ne prolaze kroz usmjeritelja

<br>

13. 5. **U ARP datagramima prenosi se pitanje o MAC adresi koja odgovara poznatoj IP adresi.**
 - točno

<br>

13. 6. **Protokol ARP pronalazi odredišnu MAC adresu koristeći opće razašiljanje na sloju podatkovne poveznice.**
 - točno

<br>

13. 7. **Protokol ARP ispravlja pogreške nastale kod protokola IP**
 - netočno


<br>
<br>
<br>
<br>

###  IP protokol i IP mreža i IP datagrami
14. 1. **Datagrami se u IP mreži usmjeravaju s obzirom na:**
 - odredišnu IP adresu

<br>

14. 2. **Osim odredišne IP adrese, svaki IP datagram mora sadržavati i:**
 - izvorišnu IP adresu

<br>


14. 3. **Tablica usmjeravanja protokola IP koristi se:**
 - samo u usmjerivačima

<br>

14. 4. **Tablica IP usmjeravanja koristi se u **
 - računalima i usmjeriteljima

<br>

14. 5. **Na putu IP datagrama od izvorišta do odredišta pri prolasku kroz usmjeritelje, u zaglavlju IP datagrama:**
 - ne mijenjaju se izvorišna i odredišna IP adresa

<br>

14. 6. **U zaglavlju IP datagrama**
 - nalazi se oktet koji označava protokol kojem se isporučuje datagram

<br>

14. 7. **Tablica usmjeravanja IP datagram koristi se na drugom sloju za usmjeravanje ethernetskih okvira s obzirom na odredišnu MAC adresu.**
 - netočno

<br>

14. 8. **Fragmentacija IP datagrama događa se**
 - kad je duljina datagrama veća od MTU na sloju podatkovne poveznice



<br>
<br>
<br>
<br>
<br>

### TCP
17. 1. **TCP segmenti koji imaju iste izvorišne i odredišne IP adrese te ista izvorišna i odredišna vrata:**
 - pripadaju istoj TCP vezi

<br>

17. 2. **Jedna TCP potvrda može potvrditi**
 - samo jedan TCP segment

<br>

17. 3. **TCP segment može istovremeno sadržavati informacije o potvrdi i nositi korisničke podatke.**
 - točno

<br>

17. 4. **TCP veza se mora uspostaviti**
 - prije slanja prvog okteta korisničkih podataka.

<br>
<br>
<br>
<br>
<br>
<br>

### UDP
18. 1. **Protokol UDP:**
 - omogućava otkrivanje pogreške prilikom transporta paketa putem zaštitne sume zaglavlja.

<br>

18. 2. **Koje od navedenih su karakteristike protokola UDP?**
 - može ga se koristiti za višeodredišno adresiranje - multicast






<br>
<br>
<br>
<br>
<br>
<br>


## Sudari 
15. 1. **Nakon detektiranog sudara, svaka stanica čeka slučajno vrijeme prije nego što ponovno počne slati okvir.**
- točno

<br>

15. 4. **Nakon detektiranog sudara, svaka stanica čeka 9.6 mikrosekundi prije nego što ponovno počne slati okvir.**
 - netočno


15. 2.  **Signal zagušenja (jamming signal) šalju samo one stanice koje su slale u trenutku kad je došlo do sudara.**
 - točno


<br>

15. 3. **Sudar se u ethernetskoj mreži manifestira kao:**
 - povišen napon

<br>


## Nesvrstano

16. 1. **S porastom frekvencije signala,gušenje u kabelu**
 - raste

<br>

16. 2. **Okvire koje primi na jednom priključku, parični obnavljač (hub) prosljeđuje se na**
 - sve ostale priključke

<br>

16. 3. **Uređaj koji obavlja funkcije mrežnog sloja, a ne obavlja funkcije sloja podatkovne poveznice naziva se:**
 - ne postoji takav uređaj

<br>

16. 4. **Četiri računala, parični obnavljač kapaciteta 100 Mbit/s. PC1 šalje podatke na PC2, a PC3 šalje podatke na PC4, drugog prometa nema. Kojom brzinom je moguće slati podatke između PC1 i PC2**
 - ovisi o prometu između PC3 i PC4

<br>

16. 5. **Obavljač kapaciteta 10Mbit/s postiže veće brzine prijenosa nego komutator kapaciteta 10Mbit/s. **
 - netočno

<br>

16. 6. **Usmjeritelj ne smije prosljeđivati okvire poslane na MAC broadcast adresu:**
 - točno

<br>

16. 7. **Korištenjem samo tablice usmjeravanja moguće je promet koji putuje do nekog odredišta raspoređivati na više poveznica u proizvoljnom smjeru.**
 - netočno

<br>

16. 8. **Koji algoritmi se smatraju adaptivnim algoritmima usmjeravanja?**
 - Usmjeravanje prema vektoru udaljenosti i usmjeravanje prema stanju poveznice.

<br>
<br>
<br>
<br>
<br>


