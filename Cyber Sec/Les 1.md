# Cyber Security
Anders dan informatiebeveiliging. 
BIV/CIA
Letterlijk security essentials
Proactief is iets wat je van te voren moet doen, verzekering of backup
Defence in depth en zo


1. Isolatie
	1. Alles wat niet migelijk is schakel je uit
2.  compartimenten
	1. Beschermde processen worden apart van andere processen gedraait, zodat ze niet bij het beschermde process kan,
3. Beperkign
	1. Alleen de minimale rechten aan users geven
4. Volledigheid
	1. Beveiliging geld zonder uitzonderingen 
5. Functiescheiding
	1. Verschillende personen voeren delen van het process uit, zodat meer mensen ergens naar kijken en geen elkele persoon het hele process kan uitvoeren. 
6. Veilige defaults
	1. Alleen dingen doorlaten die zeker weten veilig zijn
7. Ergonomie 
	1. KISS
	2. Verkleinen van kans op gebruikers fouten door systemen zo simpel mogelijk te houden
8. Open ontwerp
	1. De beveiliging hangt niet af van de geheimhouding van het ontwerp. 
9. Redudantie 
	1. Meervoudige uitvoeren kritische systemen
10. Diversiteit
	1. Meerdere maatregelen toepasssen die net anders zijn, zodat het uitvallen van een maatregel niet het einde van de beveiliging is. 
	2. Defense in depth
11. Onderhoudt
	1. Regelmatig onderhouden van alle systemen, dingen die niet onderhouden wordt. Dingen die niet automatisch worden geupdate worden onveilig
12. Registratie
	1. Alle relevante events in een systeem worden netje gelogt.

Kill chain
- Recon
- Exploitation
- Privilege escalation
- persistance

# Cryptografie
- P = Plaintext
- C = cyphertext
- Ek = encryptie algoritme
- Dk = decryptie algoritme
- k = key

Dk = Ek^-1

## Predigitale systemen
- Stenografie 
	- Het verbergen van boodschappen in andere boodschappen
- Transpositie 
	- Verwisselen volgorde symbolen
	- Tekst om een stok binden
- Substitutie - Ceasar
	- Ceasar Chipher
	- Letters op dezelfde volgorde, andere letter
	- Sleutelruimte is erg klein
- S-box
	- Ook substitutie
	- Niet gelijkmatige substitutie, elke letter wordt een andere willekeurige letter
- Vigenere
	- Meerdere Ceasar cyphers worden gecombineerd
		- Elke letter krijgt een andere substitutie
	- poly-alfabetisch
- Enigma
	- Ook een soort substitutie
	- Werkt met schijven
	- Elke letter draait schijven, waardoor een nieuwe combinatie wordt gekozen
- Vernam
	- Viginere met een key length gelijk aan de plain text lengh
	- Sleutel is vaak te groot om veilig over te brengen, waardoor je de alsnog andere encryptie nodig hebt om de key aan de overkant nodig hebt. 


### Kerckhoffs's Law
De veiligheid van een systeem mag niet afhangen van de geheimhouding van het systeem. Het enige wat je geheim mag houden is de sleutel. 
- Ook omdat het systeem door verschillende partijen implemented worden. 
Security by obscurity - Je systeem verborgen houden. Ook als het eerst verborgen systeem openbaar wordt moet het veilig blijven. 
A5 codering bij GSM telefonie is een voorbeeld. Reversed in een half jaar. 

### Cryptoanalyse
Voorkennis is belangrijk voor het aanvallen van een cryptografisch systeem.

Frequentie-analyse is een methode die je kan doen als je geen voorkennis hebt. 

- Known plain text attack
	- Met een stukje bekende plain text attack 
- Chosen plain text attack
	- Je kiest de plain text die je al weet
	- Differentiele cryptoanalise
- Brute force attack
	- Alle sleutels proberen
	- Rekenkracht enorm belangrijk
- Algorithim/Protocol breaking
	- Kwetsbaarheid in het algoritme vinden
- Side channel attacks
	- Implementatie van het algoritme aanvallen

### Onkraakbaar: One Time Pad
-  XOR
	- digtiale versie van Vernam met vergelijkbare eigenschappen
	- Elk bitje van de plaintext wordt XOR met een bit uit een random file
	- Random file wordt slechts een keer gebruikt en is even groot als de plaintext

## Moderne cryptografie 
- Vanaf WW2
- Computational Secrecy
	- Veiligheid door nodige rekenkracht om te kraken hoog te maken
	- Bij normaal gebruik ken je de sleutel, algoritme is snel
	- bv EAS

	- Algoritme niet geheim
	- Voldoende grote sleutel
	- Confusion
		- Ingewikkelde relatie tussen key en cipher text
			- Verandering van 1 bit in de sleutel leidt tot verandering van gemiddeld 50% van de cipher text bits
	- Diffusion
		- Ingewikkelde relatie tussen plain en cipher text
			- Elke verandering van plaintext leidt weer tot gemiddeld 50% verandering van cipher text
- DES
	- Data Encryption Standard
		- Bedacht door de US Feds in 1976
			- Hulp van NSA
	- Gebruikt subkeys uit pseudo random gen voor elke ronde van encryptie
	- Gebruikt S-boxes voor maximale confusion
	- 16 rondes van encrytie

	- Tabellen waren optimaal veilig, kwamen ze in de jaren 90 achter
	- DES was wel gevoelig voor brute force met DES chips
		- NSA kon dat waarschijnlijk al eerder
- EAS
	- Advanced Encryption Standard
	- Om EAS te maken werd een wedstrijd uitgeschreven
		- Twee belgen, Deamen en Rijnen - Rijndael
	- Op dit moment belangrijkste standaard voor cryptografie 

	- Sleutel is te kiezen
		- 128, 196 of 256 bit 
			- Exponentiële groei met bit in de sleutel
	- Datablok is altijd 128 bit
	- Byte georiënteerd
		- Makkelijk in software te implementeren
	- Geen Feitsel functie 
		- Dus geen XOR maar tabel
	- 14 rondes
		- 16 byte input
		- Stap 1: 1e substitutie tabel
		- Stap 2: Shift Rows; bytewise permutatie
			- Draagt bij aan diffusie 
			- Zie Powerpoint voor plaatje
		- Stap 3: Mix Collunm
			- Lineare matrixvermenigvuldiging per kolom van 4 bytes
			- Again, Powerpoint voor plaatje
			- Over meerdere rondes zorgt dit ervoor dat 1 byte de hele kolom beïnvloed 
		- Stap 4: Key addition; bitwise XOR met key 
		- Zie PowerPoint voor plaatje volledig process
		- Eerste ronde worden de eerste stappen niet gedaan, heeft geen zin. Aan het einde wordt de matrix overgeslagen, heeft geen effect en kost veel tijd

		- Key lengh wordt gehalveerd door quantum computers, maar nog steeds veilig
		- Side channel attacks zijn een probleem voor AES
			- Cache brute force maakt gebruik van cache timing
				- Door speciale AES instructies werkt dit niet
			- Meten stroomverbruik in mastercards 
			- Sleutel onderscheppen. 
			- AES in ECB mode laat plaatjes nog steeds zichtbaar omdat pixels hetzelfde zijn. 