## 1. Zadaci sa slikom

#### 1. Simbolički su zadane MAC-adrese mrežnih sučelja (MAC-PC1, MAC-PC2, itd.). Mrežni uređaji spojeni su u lokalnu mrežu Ethernet izvedbe 100BASE-T. Tablice usmjeravanja na svim računalima su ispravno podešene. Sva priručna spremišta (engl. caches) su prazna.

![[Pasted image 20210611090609.png]]

1. Ako mrežna maska za IP-podmrežu s računalima PC 1 i PC 2 glasi 255.255.248.0, koja se od sljedećih IP-adresa može pridjeliti mrežnom sučelju u danoj podmreži? (PROVJERENO)
	1. **12.10.88.255**
	2. 12.10.86.20
	3. 12.10.88.0
	4. 12.10.95.255

	> maska 255.255.248.0 -> a.b.c.d 
	> a = 1111 1111
	> b = 1111 1111
	> c = 1111 1000
	> d = 0000 0000
	> zbroji sve nule -> 11
	> znači da je mreža zapravo x.x.x.x/(32-11) -> /21
	> 2^11 = 2048 = 8 * 256 
	> znači da je svakih x.x.8.x nova podmreža
	> tražimo podmrežu u koju spadaju PC 1 i PC 2
	> 12.10.0.0 -> 12.10.7.254  X
	> 12.10.8.0 -> ... X
	> 12.10.80.0 -> 12.10.87.254 X
	> 12.10.88.0 -> 12.10.95.254 -> to je ova
	> iz ponuđenih odgovora :
		> a) ulazi u range
		> b) izvan rangea
		> c) adresa podmreže, ne može biti dodijeljena IP adresa
		> d) adresa broadcasta mreže,  ne može biti dodijeljena IP adresa
	> 

2. Računalo PC1 želi poslati IP datagram s ICMP porukom *Echo Request* računalu PC 2, slijedom čega se šalje ARP-upit. Kako glasi poruka ARP odgovora koji prima računalo PC 1? (PROVJERENO)
	1. **Za IP adresu 12.10.88.21 pripadajuća MAC adresa je MAC-PC2**
> ako želi poslat na PC 2 onda mu treba poveznica IP i MAC adrese od PC 2

3. Kako glasi adresa "sljedećeg skoka" za podrazumijevanu rutu (engl. default route) u tablici usmjeravanja računala PC 1? (PROVJERENO)
	1. **12.10.88.1**
> za sve rute, PC 1 poruke uvijek prvo trebaju ići na Router 1 da bi se mogle dalje proslijediti
> zbog toga je tablica usmjeravanja računala PC 1
> bilo koja mreža/maska 	IP adresa routera 1
> cilj										sljedeći skok
> 0.0.0.0/0							 12.10.88.1

4. Kako glasi adresa "sljedećeg skoka" za podrazumijevanu rutu (engl. default route) u tablici usmjeravanja računala PC 2? (PROVJERENO)
	1. **12.10.88.1**
> za sve rute, PC 2 poruke uvijek prvo trebaju ići na Router 1 da bi se mogle dalje proslijediti
> zbog toga je tablica usmjeravanja računala PC 2
> bilo koja mreža/maska 	IP adresa routera 1
> cilj										sljedeći skok
> 0.0.0.0/0							 12.10.88.1

5. Računalo PC 2 šalje IP-datagram s ICMP-porukom Echo  Request računalu PC 4. Prije  slanja ICMP-poruke računalo PC 2 šalje ARP-upit. Koja računala primaju spomenuti ARP-upit? (NE PROVJERENO)
	1. Računalo PC 1 te usmjeritelji Router 1 i Router 2
> pošto je cache prazan nitko ne zna ničiju adresu
> PC 1 i Router 1 je primaju jer PC 2 šalje request na broadcast adresu
> Router 2 prima request jer Router 1 ne zna IP i MAC adresu od PC 2 pa isto šalje na broadcast adresu request, u ovom slučaju ju samo Router 2 prima jer je jedini povezan u toj podmreži s Routerom 1




## 2. Zadaci s ponuđenim odgovorima
