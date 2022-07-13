# Truckplanning

De regels van truckplanning.

## Doel truckplanning

Elke dag moeten trips toegewezen worden aan trucks (die bestuurd worden door chauffeurs).

Het doel is om de vervoerscapaciteit van alle trucks zo effectief mogelijk te benutten.

Daarnaast dient er zo goed als mogelijk rekening gehouden te worden met de karakteristieken en voorkeuren van trucks, chauffeurs en klanten.

## Regels, voorkeuren, en karakteristieken

Een dagplanning bestaat uit een set aan dagstaten voor elke chauffeur/vrachtwagen combinatie. Een dagstaat bevat alle ritten die de chauffeur die dag moet rijden.

Een rit is de verplaatsing van een vrachtwagen tussen 2 of meer locaties. Idealiter wordt er een container mee verplaatsd, maar lege en platte ritten komen voor.

Een rit dient te worden uitgevoerd:

* Met een geschikte truck
* Met een geschikt chassis
* Door een geschikte chauffeur
* Wanneer de rit wordt uitgevoerd volgens de afspraken met de klant

Algemene stelregels:

* Wanneer capaciteit in de knel komt gaat regiowerk voor zeehavenwerk
* Vertraging veroorzaakt bij een klant moet zo min mogelijk effect hebben op andere klanten
* Charters gaan niet naar de klant

#### Ritten

Een rit mag worden uitgevoerd wanneer:

* `Tijdvenster`: Elke rit moet binnen het afgesproken tijdvenster op de afgesproken locatie zijn. Dit is een soft-limiet, overschrijdingen vinden plaats. Een roundtrip boeking heeft 4 tijdvensters:
  1. Latest pickup bij de zeehaven of VBL terminal (wanneer de container nog van het schip gelost moet worden)
  2. Afgesproken laad/lostijd bij de klant (afkoppelen of live handling)
  3. Afgesproken laad/lostijd bij de klant (aankoppelen)
  4. Closing bij de zeehaven of VBL terminal (wanneer de container dezelfde dag nog op het schip geladen moet worden)

__Note:__ Er wordt in principe niet gestuurd op deze tijdsvensters, maar op max. departure.

__Note:__ Bij containers die geladen/gelost worden terwijl de chauffeur wacht (live handling) zijn 2 & 3 hetzelfde tijdsvenster.

__Note:__ Bij afgekoppelde containers (import/export) is de afgesproken lostijd (2) leidend, naar aankoppelen (3) wordt niet gekeken. Elke dag vindt er een check plaats om te kijken wat er nog buiten de deur staat. Dit wordt opgehaald wanneer de klant meldt dat de container leeg is, wanneer een chauffeur een nieuwe container komt brengen (volume klanten) of op basis van rangorde (wat staat het langst buiten). Voor kritische export containers wordt wel rekening gehouden met de aankoppeltijd (3), de klant meldt dan wanneer de container klaar staat.

__Note:__ Pickup/closing kan in de het verleden (pickup) of de toekomst (closing) liggen *of* een tijdstip op de dag van uitvoering zijn wanneer een container nog gelost of geladen moet worden van het binnenvaartschip (dit komt echter minimaal voor).

__Note:__ Closing kan vervallen wanneer er een container uit eigen voorraad gebruikt wordt, of wanneer er een container wordt doorgebruikt. CS beheert dit proces. Equipment houdt de voorraad in de gaten.

__Note:__ Tijdvensters voor zeeterminals zijn standaard 00:00 - 23:59 (24/7). Voor RWG geldt dat een container moet worden aagnemeld voor een specifiek tijdvenster. Voor VBL terminals geldt voor externen dat de terminals open zijn van 06:00 - 19:00. Nachtchauffeurs koppelen zelf hun chassis om of zetten in een enkel geval zelf containers in de stack met een reachstacker.

__Note:__ Tijdvensters op klantlocaties zijn standaard 15 minuten voor tot 15 minuten na de afgesproken laad/los tijd. Sommige klanten hebben een groot tijdvenster, maar willen de containers wel een brokken, bijvoorbeeld: elk uur 2.

Voor het uithalen van import zeecontainers geldt:

* `Documenten`: Wanneer douane-documenten beschikbaar zijn
* `Order bekend`: Wanneer de order en container bij de locatie bekend zijn
* `Fysiek aanwezig`: Wanneer de container fysiek aanwezig is
* `Vrijstelling`: Wanneer de container is vrijgesteldt door de rederij

Voor het wegbrengen van export zeecontainers geldt:

* `Documenten`: Wanneer douane-documenten beschikbaar zijn
* `Order bekend`: Wanneer de order en container bij de locatie is voorgemeldt
* `Geblokkeerd`: Wanneer de container niet geblokkeerd staat
* `FYCO`: Wanneer de container niet is vastgezet voor een fysieke controle van de douane

__Note:__ Bij ECT mogen uitgaande containers zonder documenten worden ingeleverd

Voor alle (ook regio) containers geldt:

* `Gasmeting`: Wanneer de container gasgementen is.

__Note:__ Natuurlijk ventileren is een mogelijkheid, dan wordt de container voor een aantal uur op een gezet en verschuift dus de earliest pickup time (vanaf de achterlandterminal).

* `Stackpositie`: De locatie in de stack bepaalt welke container als eerste vertrekt. Bij Van Berkel bepaalt de planning de stackpositie en wordt daar gedurende de dag niet naar gekeken.

#### Vrachwagens

Een vrachtwagen is geschikt wanneer aan de volgende criteria wordt voldaan:

* `Openbare weg`: Terminal trucks zijn niet toegestaan op de openbare weg en dus alleen geschikt voor trips binnen de grenzen van het industrieterrein.

__Note:__ Welke locaties zijn toegestaan voor transport per terminal-truck staat niet geregistreerd. Planners weten dit uit hun hoofd.

* `Slaapcabine`: Trips met een overnachting zijn alleen geschikt voor vrachtwagens met slaapcabine, bijna alle trucks hebben een slaapcabine, restrictie zit meer aan de kant van de chauffeur.
* `Standairco`: Trips met een overnachting zijn alleen geschikt voor vrachtwagens uitgerust met een standairco.
* `Voorloopas`: LZV-trucks (4x) hebben een voorloop-as, en een aantal oudere trucks. Een oudere truck met een voorloopas kan een hoger gewicht meenemen op een 2-asser chassis (zie chassis).
* `Standplaats`: Elke truck heeft een standplaats. Een truck vertrekt en eindigt op zijn standplaats.
* `Euronorm`: Op sommige locaties moet de motor van de truck voldoen aan een minimale euronorm. Dit staat niet geregistreerd, maar geldt eigenlijk alleen voor Maasvlakte 2 terminals. Een hogere euronorm betekent echter ook een lager verbruik. Trucks met een lager verbruik worden met name ingezet als zeehaven trucks.
* `Hefschotel`: Sommige trucks zijn uitgerust met een hefschotel, die worden ook wel rangeertrucks genoemd. Wanneer een chassis beschikt over vaste poten kan er met een hefschotel zeer snel omgekoppeld worden. Eigenlijk zijn alleen terminal trucks uitgerust met een hefschotel (5% van de vloot). 
* `OBU Duitsland`: On-board unit voor de tolwegen in Duitsland.
* `OBU Belgie`: On-board unit voor de tolwegen rond Antwerpen (boete is €800).
* `ADR uitrusting`: Veiligheidsuitrusting voor het vervoer van gevaarlijke stoffen.
* `Beschikbaar`: Trucks in onderhoud zijn niet beschikbaar.

#### Chassis

Een chassis is geschikt wanneer:

* `Aantal assen`: Een 2-asser mag maximaal 24T vervoeren, 1-assers worden niet gebruikt, voor een 3-asser is het maximaal gewicht rond de 35T. In combinatie met een voorloopas op de vrachtwagens kan een 2-asser ook 35T vervoeren.
* `Vaste poten`: Chassis met vaste poten zijn sneller wanneer je moet omkoppelen, met name in combinatie met een hefschotel. Alle nieuwe chassis (blinkertjes) hebben draaipoten.
* `Genset`: Trips waarbij actieve reefer koeling benodigd is kunnen alleen worden uitgevoerd met een chassis met een genset. Daarvan zijn er 2, 1 in ITV en 1 in KAT.
* `LZV`: Een LZV-gekeurd chassis kan 3 TEU meenemen, een normaal chassis 2 TEU. Op een LZV chassis kunnen dus maximaal 3 trips in 1 trip gecombineerd worden! Deze chassis hebben speciale bebording. Elke LZV-chauffeur heeft een eigen trekker, dolly (20FT) en 3-asser chassis (40-45FT).

__Note:__ Chassis hebben geen standplaats, maar over het algemeen worden containers opgehaald door een truck met dezelfde standplaats als de truck die de container initieel heeft afgezet. Op die manier blijft de voorraad chassis natuurlijk in balans.

#### Chauffeurs

Een chauffeur is geschikt wanneer:

* `ADR certificaat`: Chauffeur mag met gevaarlijke goederen rijden
* `LZV certificaat`: Chauffeur mag met LZV chassis rijden (3 TEU)
* `Overnachten`: Chauffeur wil wel/niet overnachten. Bij wel gebeurt dit meestal 1-2x per week. Dit is eigenlijk niet wel/niet, maar een %.
* `Locatievoorkeuren`: Chauffeur geeft de voorkeur aan zeehaven, regio, of lokaal werk. Ook dit is een %, zie je met name bij zeehaven/regiowerk.
* `Locatievereisten`: Chauffeur heeft toegangspas mee of klant wil specifieke chauffeur. Bij Bavaria hebben we een aantal jaarpassen voor specifieke chauffeurs, andere chauffeurs moeten zich aanmelden, maar dit is niet echt een "vereiste", aanmelden kan ook. Vroeger waren er ook wel chauffeurs die altijd naar dezelfde klant reden, maar dat komt niet echt meer voor.
* `Handlingsvoorkeuren`: Chauffeur kan/wil snel omkoppelen of geeft de voorkeur aan live handling. Dit deels voorkeur, deels handigheid, en deels lichamelijke conditie.
* `Rijtijdenwet`: Chauffeur heeft voldoende werkuren beschikbaar. Soft limiet, in bijzondere gevallen mogen rijtijden overschreden worden (artikel 12), maar dat is echt voor incidenten, daar wordt niet mee gepland. De chauffeur is in principe de hoofdverantwoordelijke. Rijtijden zijn echter een complexere puzzel dan op het eerste gezicht lijkt, vandaag een chauffeur laten overwerken betekent dat hij morgen pas later kan beginnen vanwege het verplichte aantal rusturen!
* `Werktijden`: Een rit moet worden uitgevoerd binnen de werktijden van een chauffeur.
* `Overwerken`: Chauffeur wil wel/niet overwerken. Zeehavenchauffeurs worden ook wel "elitechauffeurs" genoemd, dit zijn de chauffeurs die veel willen werken en het liefst hun toegestane rijtijd maximaal oprijden. Hier moet je voorzichtig mee zijn, de dagopvolging houdt echt bij wie er aan de beurt is en weet welke chauffeurs je niet hoeft te vragen. Al het overwerk <1 uur noemen we geen overwerk. Vanaf 17:00 is het afschrijftijd, dus als je een chauffeur na 16:30 nog wegstuurt dan weet je dat het overwerk wordt (hij is dan pas na 18:00 terug).
* `Standplaats`: Chauffeurs werken vanaf een vaste locatie.

__Note:__ Veel TT-chauffeurs zijn nog "scholieren", en dus op woensdag vrij.

## Dagopvolging

Mogelijke veranderingen:

* Vertraging/versnelling: Bij afhandelen of onderweg. Chauffeur geeft dit door via Whatsapp (kan via Data2Track automatisch gedetecteerd worden). Planner checkt of dit gevolgen heeft voor de opvolgende rit.

* Nieuwe order: Lege containers worden op eigen initiatief van chauffeurs meegenomen. Customer Service (CS) neemt ad hoc orders aan in overleg met de planner.

* Orderannulering: Klanten kunnen last minute orders annuleren, planners kunnen ze doorschuiven naar een andere dag.

* Wijziging tijdvenster: Klant wil de container op een ander tijdstip of het tijdvenster verandert door een update in de aankomsttijd van het zeeschip.

* Afkeuring container: Gasmeting is afgekeurd, documenten zijn niet orde, boeking onbekend bij de klant, container zelf is afgekeurd...

* Verandering herkomst/bestemming rit: Container gaat niet rechtstreeks naar de klant maar eerst naar ITV/KAT/OSS (vanaf de zeehaven is dit eigenlijk standaard, niemand wil zijn container eind van de dag hebben). Dit komt met name voor bij doorgebruikers, dan rij je rechtstreeks van klant naar klant, of haal je een container uit voorraad op een andere terminal.

* Uitval vrachtwagen/chauffeur: Chauffeur is ziek of vrachtwagen stuk.

* Chauffeur gaat over zijn rijtijd heen: Chauffeur meldt (verwachte) overschrijding.


## Taken

Belangrijkste taken planner.

1. Is er voldoende capaciteit beschikbaar?

Maak een planning en verhelp knelpunten:

* Werktijden chauffeurs
* Tijdsvensters/levertijden bij de klant/zeehaven
* Directe zeehavenritten via de terminal laten lopen
* Herverdelen capaciteit regio/zeehaven/terminal
* Bijschakelen charters + externe chauffeurs

Vraag: Hoeveel restcapaciteit is noodzakelijk?

2. Ben ik in controle?

* Chauffeurs op tijd begonnen aan eerste ritten?
* Zijn er vertragingen of versnellingen?
* Zijn er problemen met boekingen?
* Zijn er nieuwe orders of annuleringen?
* Zijn er wijzigingen in tijdsslots?

3. Kan het efficienter?

* Verwacht ik lege containers mee te kunnen nemen?
* Kan ik zeehavenritten combineren met voorwerk?
* Kan ik ritten overnemen uit de bargeplanning?
* Kan ik voorwerk doen voor de rest van de week?
* Zijn er transferritten?

4. Doet iedereen wat hij moet doen?

* Juiste chauffeur op de juiste ritten?
* Staat er niemand te wachten?

## Constraints

De belangrijkste constraints waar de Squid planner mee moet rekenen:

* Alle ritten hebben tijdvensters, ritten dienen _zoveel als mogelijk_ te worden uitgevoerd binnen die tijdvensters
* Er is afhankelijkheid tussen ritten, het uitvoeren van een bepaalde rit limiteert de mogelijke vervolgritten
* Ritten van en naar terminals (zeehaven/inland) kunnen gecombineerd worden door meerdere containers op 1 chassis te plaatsen
* Containers kunnen op meerdere inlandterminals worden ingeleverd
* Auto's hebben restricties: gebiedstoegang, gewicht, standplaats,...
* Chauffeurs hebben voorkeuren: zeehaven/regio/terminalwerk, overnachtingen, overwerk, ...
* Chauffeurs hebben restricties: rijtijdenwet, LZV, gevaarlijke goederen, ...
* Chauffeurs hebben kwaliteiten: snelheid omkoppelen, ...

## Uitdagingen

* De truckendoos modelleren, bijvoorbeeld: 1 chauffeur met 2 auto's
* Vooruitkijken naar de rest van de week voor het combinaties en het uitvoeren van voorwerk
* Communicatie met barge/terminalplanning
* Omgaan met continue verandering