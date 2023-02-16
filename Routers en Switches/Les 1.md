Twee toetsen, multiple choice. Zwaard is coordinator. Alles op de sheets wordt getoetst, net als de practica stof. Als je nou boeken moet hebben: Computer networds, a top down aproach. 

Cisco CCNA certificaat, industriele certificaten.
CCNA is basis certificaat voor netwerken. 

Volgende week staat in het teken van subnetting, je MOET binair kunnen rekenen met 1 byte. 

# Herhaling
IP over Aviation Carrier protocollen

- Eindapparatuur
	- Apparaten voor de gebruikers
- Netwerkapparatuur
	- Maakt de communicatie mogelijk
Servers zijn in principe eindapparatuur. 

Netwerkt heeft vier basiselementen
- Apparatuur
- Verbindingen
- Data-units
- Regels - protocollen

- WAN
	- Wide Area Network
	- verbindt LAN's
	- WAN's zijn meestal ISP, hoeft niet
- LAN
	- Local Area Network
	- lokaal netwerk

### Netwerken
- Service view
	- Tolerance is  belangrijk
	- Techniche specificaties vanuit klant?
	- Availability
		- Redundancy
			- SPOF's voorkomen
	- Quality of service
		- Prioriteit
			- VIOP krijgt meestal priotiteit, omdat het tijdskrititsch is
	- Security
		- BIV/CIA
- Components View
	- Packtet Tracer werkt hier meestal ook mee
	- Onderdelen van je netwerkt
	- Is niet altijd netjes representaties in hoeveelheden
		- Hoe verder naar beneden, hoe meer apparaten
- Components view
	- Lagen
	- Welke protocollen worden gebruikt
		- Welke afspraken zijn er gemaakt
	- OSI model
		- 7 lagen
		- Elke laag levert een service aan de laag eronder
		- Elke laag praat met de laag op het andere appraat
		- In theorie kan alles met elkaar werken
			- In de praktijk niet, vendor locking
	- TCP/IP of DOD model
		- 4 lagen
		- Zie PowerPoint
	- Encapsulatie en Decapsulatie
		- inpakken data voor transport
		- Headers en Trailers
			- Netwerklaag doet header en trailer
			- De rest doet headers
			- Zie PowerPoint voor namen PDU's 
				- KOMT OP DE TOETS
			- Headers worden weggegooit nadat ze de PDU door een layer is gegaan
	- Lagen
		- Fysiek
			- Over de lijn sturen van data
			- Koper UTP en STP
				- Ethernet Straight Through
				- Ethernet Crossover
					- zend en ontvang lijn wisselen
				- Rollover
					- Is voor console
			- Coax
				- Meestal voor WAN's
			- Bandwith and Throughput
				- Bandwith is theoritsch
					- 4TB schijf in je zak en rennen
				- Throughput is daadwerkelijke snelheid 
		- Adressering, L2 en L3
			- Netwerklaag
				- IP
				- Tussen netwerken
			- Datalink laag
				- MAC
				- Binnen netwerken
					- Broadcast: FF:FF:FF:FF:FF:FF
		- Ethernet L1 en L2
			- Standaard voor internet op L1 en L2
			- Veel verschillende versies IEEE 802.?
			- Preamble voor sync
			- Switch kent alle MAC's van verbonden apparaten
			
- Collision and Broadcast Domains
	- Collisions
		- Poging om twee verschillende signalen op een kabel te sturen
		- In een modern, geswitcht netwerk dit niet mogelijk
			- In een netwerk met een hub kan het nog wel voorkomen
				- Een hub gooit alles gewoon door, zonder logica
				- Maakt het mogelijk netwerk af te tappen
		- Collision domain
			- Elke verbinding in een switch is een apart domain
		- Bij collision
			- CSMA/CD
				- CSMA kijkt of er wat gebeurt op de lijn
				- CD detecteerd collisions
				- Interframe space is de ruimte tussen twee frames
				- Slot time is de maximale tijd voor iets
				- Jam signaal
					- 1010101
					- Informeren over collision
				- Na detectie en jam signal wacht elk apparaat een random tijd
					- Daarna gaan ze weer zenden
	- Broadcast domain
		- Wie ontvangt een broadcast als die uitgezonden wordt
		- Routers breken een broadcast domain op
		- Switches maken het broadcast domain wel groter
		- VLAN's kunnen ook broadcast domains scheiden
	- Bij een volledig geswitched netwerk
		- Full duplex
			- Beide kunnen zowel heen als terug tegelijk praten
		- Half duplex
			- Eentje tegelijkertijd
		

### Routering
- Tussen netwerken communiceren
- Default gateway

### Netwerk testen
ping
	ICMP
	Wordt ook onder water gebruikt
### Arp
Mac adressen vinden
Arp adress table kan je opvragen

### IOT
- Toenemende koppeling van apparaten
	- Je deurbel moet een IP adress hebben


# Cisco IOS
- Cisco's OS
- Voor configuratie van Cisco apparaten
- UNIX based
- Command line interface

- Modussen
	- User executive mode
		- Je kan niks
	- Priiviliged mode
		- Je kan dingen inzien
	- Config mode
		- Configurenen
Boot sequence
- POST
- BIOS
- OS
- start configuratie

? voor opties waar je bent
show ? geeft alle show opties
`show running` geeft je de huidige configuratie 
Zie PP voor meer info

# TCP/UDP
- transport laag zorgt dat data bij de juiste software komt
- UDP werkt zsm, zo min mogelijk overhead
	- checkt ook niet of er iets wordt ontvangen
	- Header
		- Port nummers
		- lengte
		- checksum
	- 
- TCP
	- Bouwt connectie op en controleerd of alles goed aankomt
	- Poort nummers
		- Gereserveerde ports
		- geregistreerde ports
		- vrije ports
	- Data wordt gesegmenteerd als het te groot is om in een keer te sturen
	- Same order delivery
	- Hersturen data die niet goed is aangekomen
	- Flow control
		- Oppropping bij ontvanger of netwerk naar ontvanger
			- Minder verzenden
	- TCP header
		- Ports
		- Sequence nummers
		- Ack nummers
		- Windown voor flow control
		- Checksum voor intergriteit
		- Urgency verklaringen
		- Flex
			- opbouwen, in stand houden en stoppen connectie 
	- Opbouwen TCP connectie
		- Zie Powerpoint voor plaatje
			- dia 102
		- Flow control
			- Op basis van sequentie nummers kunnen packets in de juiste volgorde gezet en kunnen fouten gevonden worden
			- Window size
				- Hoeveel bytes er tegelijk verstuurd worden
				- Ontvanger bepaald

