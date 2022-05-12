# Spelregels truckplanning

De regels van truckplanning.

## Doel truckplanning

Elke dag moeten trips toegewezen worden aan trucks (die bestuurd worden door chauffeurs).

Het doel is om de vervoerscapaciteit van alle trucks zo effectief mogelijk te benutten.

In andere woorden: Het doel is om zoveel mogelijk beladen ritten uit te voeren in de beschikbare tijd, zonder dat er regels worden overtreden.

## De regels van de dagplanning

### Trip regels

Een trip is de verplaatsing van een truck tussen 2 of meer locaties. Idealiter verplaatsen we ook een container, maar soms is niet het geval.

Een trip dient te worden uitgevoerd:

* Met een geschikte truck
* Met een geschikt chassis
* Door een geschikte chauffeur
* Wanneer aan de boekingsvoorwaarden is voldaan

#### Truck regels

Een vrachtwagen is geschikt wanneer aan de volgende criteria wordt voldaan:

* `Openbare weg`: Terminal trucks zijn niet toegestaan op de openbare weg en dus alleen geschikt voor trips binnen de grenzen van het industrieterrein.
* `Slaapcabine`: Trips met een overnachting zijn alleen geschikt voor vrachtwagens met slaapcabine.
* `Voorloopas`: ??
* `Genset`: Trips met actieve reefer koeling zijn alleen geschikt wanneer de vrachtwagen een genset heeft.
* `Standplaats`: Elke truck heeft een standplaats. Een truck vertrekt en eindigt op zijn standplaats.
* `Euronorm`: Op sommige locaties moet de motor van de truck voldoen aan een minimale euronorm.
* `Beschikbaar`: Trucks in onderhoud zijn niet beschikbaar.

#### Chassis regels

Een chassis is geschikt wanneer:

* `Aantal assen`: Een 2-asser mag maximaal 18T vervoeren, andere as-aantallen??
* `Vaste poten`: Chassis met vaste poten zijn sneller wanneer je moet omkoppelen??
* `Standplaats`: Idealiter keren chassis weer terug op hun standplaats??
* `LZV`: Een LZV chassis kan 3 TEU meenemen, een normaal chassis 2 TEU. Op een LZV chassis kunnen dus maximaal 3 trips in 1 trip gecombineerd worden!

#### Chauffeur regels

Een chauffeur is geschikt wanneer:

* `Certificaat gevaarlijke goederen`: Chauffeur mag met gevaarlijke goederen rijden
* `LZV certificaat`: Chauffeur mag met LZV chassis rijden
* `Overnachten`: Chauffeur wil wel/niet overnachten
* `Locatievoorkeuren`: Chauffeur geeft de voorkeur aan zeehaven, regio, of lokaal werk
* `Locatievereisten`: Chauffeur heeft toegangspas mee of klant wil specifieke chauffeur
* `Handlingsvoorkeuren`: Chauffeur kan/wil snel omkoppelen of geeft de voorkeur aan live handling
* `Rijtijdenwet`: Chauffeur heeft voldoende werkuren beschikbaar. Soft limiet, in bijzondere gevallen mogen rijtijden overschreden worden (artikel 12).
* `Werktijden`: Order valt binnen werktijden chauffeur
* `Overwerken`: Chauffeur wil wel/niet overwerken

#### Boeking regels

Een boeking mag worden uitgevoerd wanneer:

* `Tijdvenster`: Elke rit moet binnen het afgesproken tijdvenster op de afgesproken locatie zijn. Dit is een soft-limiet, overschrijdingen vinden plaats. Een roundtrip boeking heeft 4 tijdvensters:
  1. Latest pickup bij de zeehaven
  2. Afgesproken laad/lostijd bij de klant
  3. Afgesproken laad/lostijd bij de klant
  4. Closing bij de zeehaven

__Note:__ Bij containers die geladen/gelost worden terwijl de chauffeur wacht zijn 2 & 3 hetzelfde tijdsvenster.
__Note:__ Pickup/closing kan afhankelijk zijn van het moment dat een container gelost/geladen wordt van het binnenvaartschip
__Note:__ Pickup/closing kan vervallen wanneer er een container uit eigen voorraad gebruikt wordt, of wanneer er een container wordt doorgebruikt
__Note:__ Tijdvensters voor terminals zijn standaard 00:00 - 23:59
__Note:__ Tijdvensters op klantlocaties zijn standaard 15 minuten voor tot 15 minuten na de afgesproken laad/los tijd.

* `Documenten`: Wanneer douane-documenten beschikbaar zijn
* `Order bekend`: Wanneer de order en container bij de locatie bekend zijn
* `Fysiek aanwezig`: Wanneer de container fysiek aanwezig is
* `Vrijstelling`: Wanneer de container meegenomen mag worden

__Note__: Bovenstaande geldt voor zeehavenritten
__Note__: Bij ECT mogen uitgaande containers zonder documenten worden ingeleverd
__Note__: Bij regioritten wordt er door de klant gecommuniceerd wanneer een container opgehaald kan worden

* `Stackpositie`: De locatie in de stack bepaalt welke container als eerste vertrekt.

## Dagopvolging

Mogelijke veranderingen:

* Vertraging/versnelling: Bij afhandelen of onderweg. Chauffeur geeft dit door via Whatsapp (kan via Data2Track automatisch gedetecteerd worden). Planner checkt of dit gevolgen heeft voor de opvolgende rit.

* Nieuwe order: Lege containers worden op eigen initiatief van chauffeurs meegenomen. Customer Service (CS) neemt ad hoc orders aan in overleg met de planner.

* Orderannulering: Klanten kunnen last minute orders annuleren, planners kunnen ze doorschuiven naar een andere dag.

* Wijziging tijdvenster: Klant wil de container op een ander tijdstip.

* Afkeuring container: Gasmeting is afgekeurd, documenten zijn niet orde, boeking onbekend bij de klant, ...

* Verandering herkomst/bestemming rit: Container gaat niet rechtstreeks naar de klant maar eerst naar ITV/KAT/OSS.

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

* Chauffeurs op tijd begonnen aan eerte ritten?
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
