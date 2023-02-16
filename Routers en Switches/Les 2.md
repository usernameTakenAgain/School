# IPv4 adressering 
192.168.0.0/24 is een IP range. Een IPv4 adres is een 32 bit adres, verdeeld over 4 bytes die los uitgeschreven worden. Dat is beter leesbaar dan het volle getal zonder punten. 
Elk deel tussen punten heet een octet.
Elk adres bestaat uit een netwerk deel en uit een hostdeel

```
Een netwerk is een groep hosts die een identiek bitpatroon in het netwerkdeel van hun adressen hebben
```
- Netwerkmasker bepaald welk deel host en welk deel netwerk is. 
	- Extra 32 bit getal
	- Dottet decimal 255.255.0.0 
	- Prefix /16
		- Eerste 16 bits zijn netwerkdeel
	- Wildcard 0.0.255.255
## Adres typen
-  Netwerkadres
	- Is het adres van het hele netwerk zelf
		- Handing voor routers, het maakt dan nog niet uit welk aparaat bedoelt wordt
		- Hostdeel wordt volledig 0
- Hostadres
	- IP adres binnen een netwerk
	- Niks speciaals
	- Alle hostadressen binnen een netwerk hebben hetzelfde netwerkadres
- Broadcast adres
	- In het hostdeel volledig 1
	- Wordt gebruikt om alle apparaten binnen een netwerk tegelijk aan te spreken
## Subnetten
- Classfull Netmaskers
	- Alleen /8 /16 of /24 maskers
		- Class A, B en C
	- /16 opsplitten in 255 * /24
- VLSM - Variable Length SubnetMask
	- prefix hoeft niet /8, 16 of /24 te zijn
	- Goed opletten met rekenen. 
		- Zie Powerpoint'
- Subnetten
	- Opdelen netwerk in meerdere kleinere netwerken
- Supernetten
	- Meerdere kleine netwerken samenvatten in een groot netwerk
	- Het maakt niet uit wat er ter plaatse aan subnetten is, we behandelen het netwerk in zn geheel. 
	- 
- 