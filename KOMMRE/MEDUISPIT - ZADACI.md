**NOTE FROM THE AUTHOR:**
*Nemojte uzeti ovu skriptu zdravo za gotovo. Neke zadatke sam sama rješavala i nisu provjereni. Also ovim putem želim napisati da ako netko nauči nešto krivo iz ove skripte i sj\*\*\* zadatak na ispitu, nisam kriva. Tko vam kriv što niste išli provjerit negdje da ja nisam luda. :D* 
*also, ovo je napravljeno u markdown editoru koji mi je default za sve, zato je editing off jer nemam pageve.*

1. **U mreži na slici koristi se usmjeravanje prema vektoru udaljenosti, gdje je cilj stvoriti tablicu usmjeravanja čvorova G na temelju poznatih kašnjenja. Vektori udaljenosti (kašnjenje) koje je čvor G primio od svojih susjeda dani su tablicom. Također je navedeno kašnjenje koje je izmjereno od čvora G do njegovih susjeda. Dovršite tablicu usmjeravanja čvora G uzevši u obzir poznate vrijednosti.**
![[Pasted image 20210417120505.png]]
- na svaki redak vektora kašnjenja dodaj pripadajuću vrijednost kašnjenja G do X, uzmi najmanji broj dobiveni, zapiši ga i zapiši sučelje kod kojeg je taj broj najmanji
- npr. 
A - B = 4 + 4 = 8
A - E = 16 + 7 = 23
A - J = 9 + 2 = 11
min je A - B = 8
- za ostale čvorove: 
za taj isti čvor X koji se traži = X | 0 | -
za čvorove za koje je određeno kašnjenje = Y | (X do Y) | Y

<br>

 2. **Temeljem predloženog plana, svakom mrežnom sučelju dodijelite IP - adresu i označite ju uz odgovarajuće sučelje.**
![[Pasted image 20210417121234.png]]
- sučelja oko komutatora nemaju IP adresu (e0, e1, e2, e3, e4, e5)
- sve što izlazi iz lijeve strane usmjeritelja dodijeliti neku adresu iz istog raspona, npr. iz raspona (10.0.0.1 -> 10.0.63.254)
	- ethA 10.0.1.1
	- ethB 10.0.1.2
	- ethC 10.0.1.3
	- eth1 10.0.1.4
- sve što izlazi s desne strane usmjeritelja dodijeli adresu iz drugog raspona (172.16.0.1 -> 172.16.15.254)
	- eth2 172.16.1.1
	- ethD 172.16.1.2

<br>

3. **Na slici je prikazan dvosmjerni protokol za kanal sa smetnjama. Prikazana su prva dva okvira u komunikaciji između sustava A i sustava B. **
 ![[Pasted image 20210417122738.png]]
 
<br>

3. 1.  **Označite sadržaj sljedeća tri prikazana okvira.**
 - (0, 1, A2)
 - (1, 1, B1)
 - (0, 0, B2)
 - ajmo redom
 - nakon što B pošalje zadnju raspisanu poruku iz skice A je na potezu
 - A je već prije bio poslao neki okvir pa sad neće poslati ništa (0, -, A-) jer treba biti iterativno, šalji ne šalji
 - A je također primio ispravan okvir 1 od B-a (0, 1, A-)
 - now, correct me if I'm wrong, ali ili je ovaj treći dio proizvoljan ili se mijenja (povećava) s promjenom vremenske kontrole tako da je pun odgovor (0, 1, A2)
 - next please
 - B je malo poludio jer mu nije ništa stiglo od A, a završio mu je jedan okvir vremenske kontrole, pa pošto nije ništa dobio u međuvremenu, ponavlja okvir koji je i zadnji put poslao (1, 1, B1)
 - okvir koji je poslao A je u međuvremenu došao do B i on mu odgovara
 - šalje okvir 0, jer je zadnji put slao okvir 1 (iterativno, get it?) (0, -, B-)
 - zadnji ispravan okvir koji je dobio je 0 koji mu je poslao A (0, 0, B-)
 - pa ajmo uvećati podatke od B za 1 s obzirom da je ovo novi okvir (0, 0, B2)
 - NOTE: ovo su moja dva centa objašnjavanja zadatka, rješenje je provjereno kao što vidite 

<br>


3. 2. **Koja je veličina kliznog prozora u prethodnom primjeru? Kako bi se mogla poboljšati efikasnost danog protokola?**
 - vel. kliznog prozora = 2
 - treba produljiti vrijeme vremenske kontrole

<br>

4. **Želimo prenijeti 9910 okteta podataka na poveznici od točke A do točke B koje su međusobno udaljene 600 kilometara. Maksimalna veličina okvira je 2118 okteta, pri čemu je veličina polja podataka u okviru 2100 okteta. Komunikacijska infrastruktura preko koje se odvija komunikacija uključuje prijenosni medij s propusnosti 8 Mbit/s i brzinom propagacije od 2*10^8 m/s. Koliko ukupno (u sekundama) traje prijenos podataka između točaka A i B? Napomena: traži se točna vrijednost (bez zaokruživanja) te u slučaju pisanja decimalnog broja možete koristiti točku ili zarez.**
- ((9910 okteta + 5 zaglavlja x 18 okteta) x 8 bitova ) / (8 x 1024^2 brzina) + 600 000 metara / (2x 10^8 s) = 0.012536
- broj bitova / brzina bit/s + udaljenost / propagacijsko kašnjenje


<br>

5. **Prilikom primjene protokola "stani i čekaj", koliko će predajnik najmanje čekati na potvrdu odaslanog okvira veličine 100 kbit, uz brzinu prijenosa 100 Mbit/s i propagacijsko kašnjenje od 2ms između lokacija na kojima su smješteni izvorište i odredište okvira? Prilikom izračuna zanemarite veličinu potvrde.**
- 100 / 100 000 (ms) + 2ms + 0ms + 2ms = 5ms

<br>

6. ** Simbolički su zadane MAC-adrese mrežnih sučelja (MAC-PC1, MAC-PC2, itd.). Mrežni uređaji spojeni su u lokalnu mrežu Ethernet izvedbe 100BASE-T. Tablice usmjeravanja na svim računalima su statičke (tj. nema prethodne komunikacije između usmjeritelja) te su ispravno podešene. Podrazumijevani iznos parametra TTL za sva računala jednak je 64. Sva priručna spremišta (engl. cache) su prazna.** ( ova slika se odnosi ne sve 6.x zadatke ovdje)

![[Pasted image 20210417134133.png]]

6. 1. **U mreži prikazanoj na gornjoj slici, računalo PC 2 provjerava dostupnost računala PC 3 korištenjem naredbe ping. Pomoću alata Wireshark pokrenuto je snimanje prometa na sučelju eth1 usmjeritelja Router 2. Koja će biti izvorišna i odredišna MAC adresa snimljenog okvira kojim se prenosi poruka Echo Reply?**
- Izvorišna MAC-PC-3, odredišna MAC-R2-1.

6. 2. **U mreži prikazanoj na Slici 1, računalo PC 1 provjerava dostupnost računala PC 3 korištenjem naredbe ping. Pomoću alata Wireshark pokrenuto je snimanje prometa na sučelju eth0 usmjeritelja Router2. Kojaće biti izvorišna i odredišna MAC adresa snimljenog okvira kojim se prenosi poruka Echo Reply?**
- Izvorišna MAC-R2-0, odredišna MAC-R1-1

6. 3. **U mreži prikazanoj na Slici 1, računalo PC 1 šalje poruku računalu PC2. Hoće li u nekom trenutku komunikacija između ta dva računala ići preko usmjeritelja?**
 - ne

6. 4. 1.  *Simbolički su zadane MAC-adrese mrežnih sučelja (MAC-PC1,  MAC-PC2,  itd.).  Mrežni uređaji spojeni su u lokalnu mrežu Ethernet izvedbe 100BASE-T. Tablice usmjeravanja na svim računalima su ispravno podešene. Podrazumijevani iznos parametra TTL za sva računala jednak je 64. Sva priručna spremišta (engl. cache) su prazna. ( Ovo se odnosi ne sve 6.4.x zadatke u ovoj zbirci.* **U mreži na Slici  3, korisnik računala PC  1 želi saznati kojim čvorovima će paketi upućeni prema računalu PC  4 najvjerojatnije proći. Međutim, na računalu PC  1 nije  dostupan  alat traceroute, koji služi u ovu svrhu. Napišite niz ping naredbi kojima bi se moglo doći do željene informacije o ostvarenom putu, te IP adrese čvorova na putu, dobivene kao rezultat izvođenja tih ping naredbi.**
 - logika iza rješavanja, pingamo PC4 i polako dižemo TTL za svaku naredbu, tako svaki put dobijemo još jedan čvor koji je uključen u rutu do PC4 
```bash
ping -m 1 12.11.216.21
// dobijemo poruku od 12.10.88.1


ping -m 2 12.11.216.21
// dobijemo poruku od 12.11.91.2


ping -m 3 12.11.216.21
// dobijemo poruku od 12.11.216.21
```

6. 4. 2. **Pomoću alata Wireshark pokrenuto je snimanje prometa na sučelju eth1 usmjeritelja Router1. Računalo PC  2 šalje IP-datagram računalu PC  4. Koja je izvorišna MAC adresa, a koja je odredišna MAC adresa snimljenog okvira koji u sebi prenosi taj IP-datagram? Koja je izvorišna IP adresa, a koja odredišna  IP  adresa  u  zaglavlju  IP-datagrama  koji  se  nalazi unutar snimljenog okvira?** **Koja  je  vrijednost polja  TTL  (engl.  time  to live) u  zaglavlju snimljenog  IP-datagrama?  Na kojem mrežnom čvoru se prvi puta smanjila vrijednost TTL-a?**
 - izvorišna MAC adresa		  = MAC-R1-1  // adresa sučelja koje šalje
 - odredišna MAC adresa		= MAC-R2-0 // adresa sučelja koje prima
 - izvorišna IP adresa			= 12.10.88.21 // adresa PC2
 - odredišna IP adresa  		= 12.11.216.21 // adresa PC4
 - vrijednost TTL, po defaultu je na početku TTL = 64, umanjuje se za jedan nakon što prođe R1 TTL = 63 ( note: nemoj zaboravit da gledamo wireshark na eth1 od R1)

6. 4. 3. **Pomoću  alata  Wireshark  pokrenuto  je  snimanje  prometa  na  sučelju eth0 usmjeritelja Router1. Računalo PC 1 provjerava   dostupnost   (ping)  računala PC 2,  tako  što  šalje pripadajuću ICMP-poruku Echo  Request prema računalu PC 2. Nakon što je računalo PC 1 uspješno primilo ICMP-poruku Echo  Reply, računalo PC 4 provjerava dostupnost računala  PC 2 na isti način, slanjem ICMP-poruke Echo  Request, na koju uspješno primi pripadajući odgovor.** 
		- **Navedite vrstu  ICMP-poruke,  izvorišne i odredišne IP-adrese  i  TTL IP-datagrama koji prenose ICMP poruke snimljene alatom Wireshark, kronološkim redoslijedom**
		- NOTE: nisam sigurna vidi li eth0 ARP broadcastove 
		- R1 ne vidi komunikaciju između PC1 i PC2 jer pretpostavljam da PC1 zna gdje se nalazi PC2 i ne treba slat ARP broadcast koji bi R1 vidio, zato su prva dva retka tablice prazna jer eth0 na R1 ne vidi Echo Request i Echo Reply od PC1 i PC2
		- zatim kad PC4 pinga PC2, pretpostavljam isto, ARP broadcast who has ... nije potreban, correct me if I'm wrong
		- Echo ping request, šalje PC4, prima PC2, TTL je 62, jer je request prošao dva rutera ergo smanjio se za 2
		- Echo ping reply, šalje PC2, prima PC4, TTL je 64, jer reply na eth0 od R1 još nije prošao nijedan ruter

| ICMP poruka         	| Izvorišna IP 	| Odredišna IP 	| TTL 	|
|---------------------	|--------------	|--------------	|-----	|
| -                   	| -            	| -            	| -   	|
| -                   	| -            	| -            	| -   	|
| Echo (ping) request 	| 12.11.216.21 	| 12.10.88.21  	| 62  	|
| Echo (ping) reply   	| 12.10.88.21  	| 12.11.216.21 	| 64  	|

		

<br>

7. **Ako  je  duljina  ICMP-poruke ovijeneu  IP-datagram  jednaka  1100  okteta,  a  duljina  zaglavlja pripadajućeg IP-datagrama jednaka 20 okteta, tada će u polju Total  LengthIP-zaglavlja  biti zapisana vrijednost**
- 1100 okteta podataka + 20 okteta zaglavlja = 1120 okteta

<br>

8. **Raspon IP adresa podmreže zadan je sa 192.168.10.128/28. Koliko ukupno IP adresa postoji u tom rasponu?**
 - 2^(32-28) = 2^4 = 16 


<br>

9. **500 GB podataka prenosi se između računalnih centara u Zagreba i Beču. Komunikacijska infrastruktura preko koje se odvija komunikacija uključuje bakrene veze između Zagreba i Ljubljane duljine 115 km s propusnosti od 1 Gbit/s i brzinom propagacije signala 2,3·10^8m/s, te optička vlakna između Ljubljane i Beča duljine 280km  s  propusnosti  od  10  Gbit/s  i brzinom propagacije svjetlosti od 2·10^8m/s. Zanemare li se vremena obrade na putu, koliko ukupno traje prijenos podataka između računalnih centara?**
 -  500 x 1024^3 / (1024^3) + 500 x 1024^3 /(10 x 1024^3) +
   115 000 / (2,3 x 10^8) + 280 000 / (2 x 10^8) = 550,0019 s 
- broj bitova / brzina bit/s + udaljenost / propagacijsko kašnjenje

(nisam sigurna da je ovo točno, ovo su moja dva centa iz v=s/t formule :D )

<br>

10. **Radite u poduzeću Mreže d.o.o. i zadatak Vam je dizajnirati mrežu za cijelo poduzeće. Topologija mreže zadana je slikom.  Vaš je zadatak jasno popuniti tablicu uređaja i njihovih sučelja s pripadajućim vrijednostima. IP adrese podmreža A, B i C zadane su, dok su sve ostale podmreže proizvoljne:
podmreža A: 10.0.0.128/28, 
podmreža B: 10.0.0.160/28, 
podmreža C: 10.0.0.224/28
NAPOMENA: Za polja koja nisu primjenjiva upišite crticu (-).**

- 1. korak 
- u sva polja koja su sučelja switcheva staviti -
- oni nemaju IP adresu
- u sva polja routera, osim Router 2 eth3 što je zadano, u podrazumijevanog usmjeritelja staviti -, oni nemaju podrazumijevanog usmjeritelja

| Uređaj (sučelje) 	|   IP adresa  	| IP adresa podrazumijevanog usmjeritelja 	|
|:----------------:	|:------------:	|-----------------------------------------	|
| Router 2 - eth3  	| 161.53.19.72 	| 161.53.19.1                             	|
| Router 1 - eth0  	|              	| -                                       	|
| Switch 1 - e0    	| -            	| -                                       	|
| Switch 1 - e1    	| -            	| -                                       	|
| Switch 1 - e2    	| -            	| -                                       	|
| PC 1             	|              	|                                         	|
| Server 1         	|              	|                                         	|
| Router 1 - eth1  	|              	| -                                       	|
| Router 2 - eth0  	|              	| -                                       	|
| Router 2 - eth1  	|              	| -                                       	|
| PC 2             	|              	|                                         	|
| Router 2 - eth2  	|              	| -                                       	|
| Router 3 - eth1  	|              	| -                                       	|
| Router 3 - eth0  	|              	| -                                       	|
| Switch 2 - e0    	| -            	| -                                       	|
| Switch 2 - e1    	| -            	| -                                       	|
| Server 2         	|              	|                                         	|

- 2. korak
- podmreža A
- range je od 10.0.0.129 -> 10.0.0.142
- Routeru 1 eth0 (sučelje koje ide do podmreže A), PC1 i serveru 1, postaviti IP adresu na neku iz ovog rangea (ne mora ići po redu kao ovdje u primjeru)
- postaviti podrazumijevane adrese od PC1 i Servera 1 na IP adresu od sučelja eth0 na Routeru 1

| Uređaj (sučelje) 	|   IP adresa  	| IP adresa podrazumijevanog usmjeritelja 	|
|:----------------:	|:------------:	|-----------------------------------------	|
| Router 2 - eth3  	| 161.53.19.72 	| 161.53.19.1                             	|
| Router 1 - eth0  	| 10.0.0.129   	| -                                       	|
| Switch 1 - e0    	| -            	| -                                       	|
| Switch 1 - e1    	| -            	| -                                       	|
| Switch 1 - e2    	| -            	| -                                       	|
| PC 1             	| 10.0.0.130   	| 10.0.0.129                              	|
| Server 1         	| 10.0.0.131   	| 10.0.0.129                              	|
| Router 1 - eth1  	|              	| -                                       	|
| Router 2 - eth0  	|              	| -                                       	|
| Router 2 - eth1  	|              	| -                                       	|
| PC 2             	|              	|                                         	|
| Router 2 - eth2  	|              	| -                                       	|
| Router 3 - eth1  	|              	| -                                       	|
| Router 3 - eth0  	|              	| -                                       	|
| Switch 2 - e0    	| -            	| -                                       	|
| Switch 2 - e1    	| -            	| -                                       	|
| Server 2         	|              	|                                         	|

- 3. korak
- podmreža B
- range je od 10.0.0.161 -> 10.0.0.174
- postaviti eth1 od Routera 2 koji gleda na podmrežu B i PC2 na IP adrese iz ovog rangea (ne mora ići po redu kao ovdje u primjeru)
- postaviti defaultnu adresu od PC2 na eth1 od Routera 2

| Uređaj (sučelje) 	|   IP adresa  	| IP adresa podrazumijevanog usmjeritelja 	|
|:----------------:	|:------------:	|-----------------------------------------	|
| Router 2 - eth3  	| 161.53.19.72 	| 161.53.19.1                             	|
| Router 1 - eth0  	| 10.0.0.129   	| -                                       	|
| Switch 1 - e0    	| -            	| -                                       	|
| Switch 1 - e1    	| -            	| -                                       	|
| Switch 1 - e2    	| -            	| -                                       	|
| PC 1             	| 10.0.0.130   	| 10.0.0.129                              	|
| Server 1         	| 10.0.0.131   	| 10.0.0.129                              	|
| Router 1 - eth1  	|              	| -                                       	|
| Router 2 - eth0  	|              	| -                                       	|
| Router 2 - eth1  	| 10.0.0.161   	| -                                       	|
| PC 2             	| 10.0.0.162   	| 10.0.0.161                              	|
| Router 2 - eth2  	|              	| -                                       	|
| Router 3 - eth1  	|              	| -                                       	|
| Router 3 - eth0  	|              	| -                                       	|
| Switch 2 - e0    	| -            	| -                                       	|
| Switch 2 - e1    	| -            	| -                                       	|
| Server 2         	|              	|                                         	|

- 4. korak
- podmreža C
- range je 10.0.0.225 -> 10.0.0.238
- postaviti eth0 od Routera 3 i Server 2 na neku IP adresu iz ovog rangea (ne mora ići po redu kao ovdje u primjeru)
- postaviti defaultnu adresu od Servera 2 na IP adresu eth0 sučelja od Routera 2

| Uređaj (sučelje) 	|   IP adresa  	| IP adresa podrazumijevanog usmjeritelja 	|
|:----------------:	|:------------:	|-----------------------------------------	|
| Router 2 - eth3  	| 161.53.19.72 	| 161.53.19.1                             	|
| Router 1 - eth0  	| 10.0.0.129   	| -                                       	|
| Switch 1 - e0    	| -            	| -                                       	|
| Switch 1 - e1    	| -            	| -                                       	|
| Switch 1 - e2    	| -            	| -                                       	|
| PC 1             	| 10.0.0.130   	| 10.0.0.129                              	|
| Server 1         	| 10.0.0.131   	| 10.0.0.129                              	|
| Router 1 - eth1  	|              	| -                                       	|
| Router 2 - eth0  	|              	| -                                       	|
| Router 2 - eth1  	| 10.0.0.161   	| -                                       	|
| PC 2             	| 10.0.0.162   	| 10.0.0.161                              	|
| Router 2 - eth2  	|              	| -                                       	|
| Router 3 - eth1  	|              	| -                                       	|
| Router 3 - eth0  	| 10.0.0.225   	| -                                       	|
| Switch 2 - e0    	| -            	| -                                       	|
| Switch 2 - e1    	| -            	| -                                       	|
| Server 2         	| 10.0.0.226   	| 10.0.0.225                              	|

- 5. korak 
- sučelja između dva routera, prvo ćemo gledati sučelja između routera 1 i routera 2
- praksa je staviti takva sučelja u podmrežu 10.0.0.0/najveći broj moguć, tako da pokrijemo max broj adresa, piše u zadatku da su ostale podmreže proizvoljne pa možete i nešto drugo staviti, ovo je samo stereotip/standard u pravim mrežama I guess, ovako se ne gube IP adrese u prazno (don't take them if you don't need them)
- vidimo da ih je kod nas ostalo 2 (gledamo samo sučelja između routera 1 i routera 2, to je jedna podmreža), što znači da maska mora biti 30 (2^(32-30) - 2 = 2)
- IP range = 10.0.0.1 -> 10.0.0.2
- isto radimo za sučelja između routera 2 i routera 3
- uzimamo prvi sljedeći blok IP adresa, a to je 10.0.0.4/30
- IP range je tada = 10.0.0.5 -> 10.0.0.6
- PS ako te bune ove adrese i blokovi i rangevi pogledaj [ovaj IP calc](http://jodies.de/ipcalc?host=10.0.0.0&mask1=30&mask2=), play a little bit pa ćeš skužit poantu, explanation je ovdje [[MEDUISPIT - ZADACI#IP adrese rangevi maske]]
- also u ovom koraku je bitno napisati masku mreže s obzirom da smo sami birali 

| Uređaj (sučelje) 	|   IP adresa  	| IP adresa podrazumijevanog usmjeritelja 	|
|:----------------:	|:------------:	|-----------------------------------------	|
| Router 2 - eth3  	| 161.53.19.72 	| 161.53.19.1                             	|
| Router 1 - eth0  	| 10.0.0.129   	| -                                       	|
| Switch 1 - e0    	| -            	| -                                       	|
| Switch 1 - e1    	| -            	| -                                       	|
| Switch 1 - e2    	| -            	| -                                       	|
| PC 1             	| 10.0.0.130   	| 10.0.0.129                              	|
| Server 1         	| 10.0.0.131   	| 10.0.0.129                              	|
| Router 1 - eth1  	| 10.0.0.1/30  	| -                                       	|
| Router 2 - eth0  	| 10.0.0.2/30  	| -                                       	|
| Router 2 - eth1  	| 10.0.0.161   	| -                                       	|
| PC 2             	| 10.0.0.162   	| 10.0.0.161                              	|
| Router 2 - eth2  	| 10.0.0.5/30  	| -                                       	|
| Router 3 - eth1  	| 10.0.0.6/30  	| -                                       	|
| Router 3 - eth0  	| 10.0.0.225   	| -                                       	|
| Switch 2 - e0    	| -            	| -                                       	|
| Switch 2 - e1    	| -            	| -                                       	|
| Server 2         	| 10.0.0.226   	| 10.0.0.225                              	|

- that's all folks

<br>

11. **Računalo PC  1 provjerava dostupnost računala PC  2 putem  naredbe ping.  Pri  tome,  IP-datagram  koji  prenosi  ICMP-poruku Echo  Request od PC  1 do PC  2 ima zadanu veličinu od 1300 okteta, a jednaku veličinu ima i pripadajući IP-datagram koji prenosi ICMP-poruku Echo Reply od PC 2 do PC 1. Na slici su navedeni iznosi MTU-a (engl. Maximum Transmission Unit) na  svakom  segmentu  puta  od PC  1 do PC  2. Pokrenuto je snimanje prometa pomoću alata Wireshark na sljedećim mrežnim sučeljima: na sučelju eth0 računala PC  1, na sučelju eth1 usmjeritelja R2 i na sučelju eth0 računala PC 2. U prikazu datagrama (ispod)simbolički su prikazani dijelovi datagrama relevantni za zadatak: zastavica MF–More  Fragments,  polje Offset–mjesto fragmenta,te podatkovno  polje IP-datagrama.**

<br>

11. 1. **IP-datagram koji u sebi nosi ICMP-poruku Echo Request poslanu s PC 1 na PC 2 snimljenje na  mrežnom  sučelju eth0 računala PC  1.  Na  jednak  način  prikažite  sve  IP-datagrame snimljene na mrežnom sučelju eth1 usmjeritelja R2 tijekom prolaska ICMP-poruke Echo Request na putu prema PC 2.**
![[Pasted image 20210418140722.png]]
- da bi IP datagram došao do PC2, on se na Routeru 1 fragmentira
- u Routeru 2 se ne događa fragmentacija jer će paketi biti manji od MTU-a
- isto vrijedi za Router 3
- u Routeru 2, MTU je 576 okteta, mi imamo podatke veličine 1280 okteta, u tih 576 okteta mora biti 20 okteta IP zaglavlja, što ostavlja 556 okteta za podatke, ali to mora biti djelijvo s 8, pa max možemo poslat 552 okteta podataka u jednom fragmentu
- prvi paket i drugi paket 552 (mora biti djeljivo s 8) okteta podataka + 20 okteta zaglavlja = 572 okteta
- treći paket ima još 1280 - 2 x 552 okteta podataka = 176 okteta podataka + 20 okteta zaglavlja = 196 okteta sveukupno
- idemo redom raditi pakete
- prvi paket, MF = 1 jer slijedi još paketa ovo nije zadnji
- offset je 0 jer je prvi paket podaci su s početka originalnog paketa (offset je koristan za spajanje podataka kad dođu na odredište), podaci se nalaze u prvih 552 okteta

| MF 	| Offset 	| DATA =  	|
|----	|--------	|---------	|
| 1  	| 0      	| 1 - 552  	|

- drugi paket
- MF je 1, ovo nije zadnji fragment
- offset je 552/8=69, jer je ovo drugi blok podataka iz originalnog datagrama, a počinje od 553. mjesta
- data je u sljedećih 552 okteta

| MF 	| Offset 	| DATA =  	|
|----	|--------	|---------	|
| 1  	| 69    	| 553 - 1104|

- treći paket
- MF je 0, ovo je zadnji fragment, offset je 1104/8=138 jer je to zadnji dio originalnog datagrama
- podaci su zapisani u zadnjih 196 okteta

| MF 	| Offset 	| DATA =  	|
|----	|--------	|---------	|
| 0  	| 138   	|1105 - 1280|


<br>

11. 2. ** IP-datagram  koji  u  sebi  nosi  ICMP-poruku Echo Reply(odgovor) snimljen je na mrežnom sučelju eth0 računala PC  2.  Na  jednak  način  prikažite  sve  IP-datagrame  snimljene  na mrežnom sučelju eth1 usmjeritelja R2 tijekom prolaska ICMP-poruke Echo  Reply na  putu prema PC 1**
 - MTU između R2 i R3 je 1280, što je evidentno veće od ukupnih 1300 okteta koje šalje PC2
 - datagram dijelimo na 2 fragmenta
 - 1. fragment 1260 okteta podataka but to nije djeljivo s 8, pa je 1256 podataka + 20 okteta zaglavlja = 1276 okteta
 - 2. fragment 1280-1256=24 okteta podataka + 20 okteta zaglavlja
 - 1. fragment = MF 1, slijedi još jedan fragment, Offset je 0 jer podatke uzimamo s početka datagrama, podaci se nalaze na prvih 1256 okteta

| MF 	| Offset 	| DATA =   	|
|----	|--------	|----------	|
| 1  	| 0      	| 1 - 1256 	|

- 2. fragment = MF je 0, ovo je zadnji fragment, offset je 1256/8 jer uzimamo zadnjih 24 okteta podataka iz originalnog datagrama, podaci se nalaze na zadnjih 24 bitova

| MF 	| Offset 	| DATA =  	|
|----	|--------	|---------	|
| 0  	| 157   	| 1257 - 1280	|

<br>


<br>
<br>
<br>
<br>
<br>

### IP adrese, rangevi, maske
**Što to znači da se uzima raspon adresa 0.0.0.0/8?**
- /8 znači da basically ima 232-8 - 2 mogućnosti u tom rangeu za dodijelit IP adresu  
u prijevodu to znaci da 0.0.0.0/8 ima range IP adresa od  
0.0.0.1 -> 0.255.255.254  
u svakom dijelu od ove 4 stavke može bit 256 različitih brojeva (0 -> 255)  
232-8 - 2 je jako velik broj i pokriva po redu sve mogućnosti od 0.0.0.1 do 0.255.255.254  
razlog zasto je - 2 je, jer je jedna oznaka mreže (0.0.0.0), a jedna je adresa za broadcastanje, što je zadnja adresa u rangeu 0.255.255.255

- vidi [http://jodies.de/ipcalc?host=0.0.0.0&mask1=8&mask2=](http://jodies.de/ipcalc?host=0.0.0.0&mask1=8&mask2=)  
i hope i was clear