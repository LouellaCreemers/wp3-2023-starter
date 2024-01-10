# Werkplekopdracht - Webapplicatie voor Stichting Accessibility

## Opdrachtomschrijving

Als team voeren jullie een project uit voor Stichting Accessibility, waarbij een webapplicatie met een database en een API wordt ontwikkeld. Stichting Accessibility heeft als missie een inclusieve samenleving te bevorderen, waarin alle mensen, met of zonder beperking, gelijkwaardig kunnen participeren. De organisatie streeft naar digitale, fysieke en sociale toegankelijkheid voor iedereen.

Met het oog op het doen van onderzoek naar de huidige toegankelijkheid, en het indienen van verbetervoorstellen, wil Stichting Accessibility een webapplicatie laten ontwikkelen. Deze applicatie is bedoeld om een panel van ongeveer 125 mensen met een beperking samen te brengen met organisaties en bedrijven. Hierin wil Stichting Accessibility een rol nemen als poortwachter, om onderzoeken en ervaringsdeskundigen zorgvuldig geselecteerd bij elkaar te brengen. Omdat het om een kwetsbare doelgroep gaat zal de Stichting Accessibility de gegevens van de ervaringsdeskundigen beheren en alle acties in het proces goedkeuren.

Zowel individuen met een beperking als bedrijven moeten zich kunnen registreren op de site. Gezien de gevoelige aard van de gegevens, is beveiliging van essentieel belang. Daarnaast moeten er nieuwsberichten over aankomende onderzoeken worden geplaatst waar panelleden zich voor kunnen inschrijven. Toegankelijkheid binnen de applicatie is een harde eis: webteksten bijvoorbeeld moeten bondig en eenvoudig moeten zijn.

# Probleemstelling

## Rollen
- **Beheerder (Stichting Accessibility)**: Opdrachtgever en data eigenaar, met verschillende teams  waaronder onderzoekers, usability experts, accessibility experts en data analisten. Via een dashboard willen zij inzicht krijgen in de data van de ervaringsdeskundigen en waar nodig aanpassingen kunnen doen. Zij willen ook nieuwe onderzoeksaanvragen kunnen beoordelen en open stellen voor de deskundigen. 
- **Ervaringsdeskundigen:** Ongeveer 125 mensen die lid zijn van een panel van Stichting Accessibility. Zij voeren een aantal gegevens in. Zij zijn de belangrijkste gebruikers van de webapplicatie, waarvan de persoonlijke gegevens nauwkeurig moeten worden beschermd.
- **Organisaties:** Bedrijven registreren zich en kunnen aan de hand van een API call nieuwe verzoeken voor ervaringsdeskundigen inschieten. 

## Proces
Het proces om ervaringsdeskundigen te werven en te selecteren voor onderzoeken is als volgt:
1. Een *ervaringsdeskundige* meldt zich aan bij Stichting Accessibility. Deze nieuwe gebruiker registreert een uitgebreid profiel met onder andere hun beperking(en), hulpmiddelen, type onderzoek waar ze aan willen deelnemen (telefonisch, op locatie, via internet) en voorkeur voor benadering.   
2. Een *beheerder* van Stichting Accessibility controleert de aanmelding en geeft toegang tot de webapplicatie.
3. Een bedrijf of organisatie wil een onderzoek uitvoeren en meldt dit aan bij Stichting Accessibility. Een *beheerder* neemt hun gegevens aan en registreert het bedrijf. Deze krijgt een API sleutel om onderzoeken te kunnen aanmaken.
4. De *organisatie* maakt een onderzoek aan. Deze krijgt een aantal verwachte attributen zoals omschrijving, soort onderzoek en dergelijk, maar ook een aantal filters. Deze filters kunnen een leeftijd bevatten, type beperking, type onderzoek (telefonisch, op locatie of via internet) en moment van onderzoek. 
5. Een *beheerder* keurt het onderzoek goed en het onderzoek wordt zichtbaar voor de ervaringsdeskundigen die voldoen aan de filters.
6. De *ervaringsdeskundigen* zien bij login welke onderzoeksvragen er open staan op basis van hun voorkeuren en de "filters" van het onderzoek. Zij de details bekijken en zich opgeven voor een onderzoek.
7. Een *beheerder* ziet welke ervaringsdeskundigen interesse aangeven voor een onderzoek en keurt de deelname goed. De beheerder neemt contact op met het bedrijf en geeft de details van de ervaringsdeskundige door. Deze actie vindt buiten de applicatie plaats, maar er moet wel worden geregistreerd dat er contact is opgenomen. 
8. Daarnaast kunnen *organisaties* een API call doen om een lijst van ingeschreven ervaringsdeskundigen op te halen. Eventueel kan de organisatie ook een API call doen om de status van een onderzoek aan te passen en te sluiten. Het is dan niet meer mogelijk voor ervaringsdeskundigen om zich in te schrijven.

![proces_overzicht.png](docs%2Fimages%2Fproces_overzicht.png)

# Requirements
Ontwikkel als team een webapplicatie voor Stichting Accessibility, waarbij alle systeemeisen zijn opgenomen in het product. Werk samen zodat elk teamlid een gelijke bijdrage kan leveren.

## Webapplicatie en API
Het eindproduct is een web applicatie met een API, bestaande uit drie componenten:
- We verwachten een portal voor ervaringsdeskundigen waar zij hun profiel kunnen inzien en aanpassen, en zich kunnen aanmelden voor onderzoeken.
- Daarnaast verwachten we een portal voor beheerders, waar zij de ervaringsdeskundigen kunnen beheren en nieuwe onderzoeken kunnen goedkeuren of afwijzen. Dit portal moet *real-time* in de browser worden bijgewerkt. Bijvoorbeeld, als een organisatie een nieuw onderzoek aan biedt moet dit direct zichtbaar zijn in het scherm voor de beheerders. 
- Tot slot verwachten we een API, waar bedrijven onderzoeken kunnen aanmaken en ervaringsdeskundigen kunnen ophalen. Deze API mag ook worden uitgebreid met andere functies.  

Alle gegevens dienen te worden opgeslagen in een database. Het ontwerp van de database is aan jullie.

## Functionele Vereisten


### Algemeen
- We verwachten dat de applicatie "WCAG 2.2 - AA" compliant is. Dit betekent dat de applicatie toegankelijk moet zijn voor mensen met een beperking. Specifiek het portaal voor ervaringsdeskundigen moet toegankelijk zijn voor mensen met verschillende beperkingen.
- Bruikbaarheid is een belangrijk aspect van de applicatie. De applicatie moet intuïtief zijn en een duidelijke structuur hebben. Denk bij het zetten van knoppen en HTML elementen uit het oogpunt van de rol van de gebruiker. Toon ook geen zaken die niet relevant zijn voor de huidige rol. 
- Styling is niet het belangrijkste, maar gaat eigenlijk al deels hand-in-hand met de WCAG standaard. De applicatie moet er  verzorgd uitzien. Gebruik bijvoorbeeld Bootstrap om de applicatie een professionele uitstraling te geven.
- Gezien dit een kwetsbare groep betreft is informatiebeveiliging van groot belang. De applicatie moet veilig zijn en de gegevens van de gebruikers moeten goed worden beschermd. Doe de aanname dat hier bij de beoordeling wordt gekeken. Zorg bijvoorbeeld ervoor dat een ervaringsdeskundige niet de gegevens van andere ervaringsdeskundigen kan inzien.

### Portal ervaringsdeskundigen
1. **Registratie en Authenticatie:** 
   - Ervaringsdeskundigen moeten zich kunnen registreren op de site en een profiel kunnen aanmaken. Een minimaal set aan attributen is te vinden in de appendix.  
   - Het profiel moet in het geval van een voogd of toezichthouder ook de contactgegevens van de voogd of toezichthouder bevatten. Een voogd of toezichthouder is verplicht voor ervaringsdeskundigen jonger dan 18 jaar of met een verstandelijke beperking. Gebruik javascript om de juiste velden te tonen en het invullen van een profiel zo eenvoudig mogelijk te maken.
   - Inloggen moet veilig en eenvoudig zijn.
   - Na registratie heeft het account nog géén toegang tot de site. Een beheerder moet het account eerst goedkeuren. Dit moet ook aan de ervaringsdeskundige worden gecommuniceerd door middel van duidelijke uitleg.
   

2. **Profielbeheer ervaringsdeskundigen:**
   - Het moet mogelijk zijn om ná goedkeuring van een account profielgegevens toe te voegen en aan te passen. Hiervoor is geen extra goedkeuring door een beheerder nodig.  


3. **Aanvragen:**
   - Er moet standaard een lijst getoond worden met alle aanvragen van organisaties die qua filters (beperking, leeftijd en beschikbaarheid) van toepassing zijn voor de ervaringsdeskundige én zijn goedgekeurd door een beheerder. 
   - Deze lijst kan als kan de vorm hebben van een verzameling "cards"
   - De ervaringsdeskundige moet de details van een aanvraag kunnen inzien en via een knop zich kunnen inschrijven. 
   - Er moet een optie zijn om onderzoeken te laten zien waarop is ingeschreven
   - Er moet een optie zijn om onderzoeken te laten zien waarop is afgewezen
   - Er moet een optie zijn om onderzoeken te laten zien welke zijn goedgekeurd

### Portal beheerders
1. **Authenticatie:**
    - Beheerders moeten zich kunnen aanmelden op de site. Nieuwe beheerders kunnen alleen door bestaande beheerders worden aangemaakt. 


2. **Dashboard:** 
   - Het portal van de beheerder toont op het startscherm de volgende informatie:
     - Goed te keuren onderzoeksaanvragen
     - Goed te keuren onderzoek inschrijvingen
     - Goed te keuren nieuwe ervaringsdeskundigen
     
       Deze informatie moet *real-time* worden bijgewerkt, dat wil zeggen dat als bijvoorbeeld een organisatie een nieuw onderzoek aanbiedt dit direct zichtbaar moet zijn in het scherm voor de beheerders.
   - Indien een beheerder iets goedkeurt of afkeurt moet worden bijgehouden wie dit heeft gedaan en wanneer.


3. **Lijsten**
   - Er moet CRUD functionaliteit zijn voor beheerders, onderzoeken, ervaringsdeskundigen en organisaties.

 
### API voor organisaties
1. **Authenticatie:**
   - Organisaties moeten een API sleutel krijgen om onderzoeken te kunnen aanmaken. Deze API sleutel moet worden opgeslagen in de database. 
   - Organisaties moeten nieuwe onderzoeken kunnen aanmaken via een REST API.
   - Organisaties moeten bepaalde velden van onderzoeken kunnen updaten via een REST API: de titel, datum, omschrijving en beloning. De status mag alleen worden aangepast naar "gesloten" en dan ook alleen als de huidige status "goedgekeurd" is. 
   - Organisaties mogen hun eigen onderzoeken opvragen. Daarnaast mogen ze de details van een onderzoek opvragen. Daarin krijgen ze de lijst met de profielinhoud van ingeschreven ervaringsdeskundigen te zien waarvan een beheerder de inschrijving heeft goedgekeurd.
 

## Technische vereisten

### Aanname meldingen
In de casus zijn er veel punten waarop beheerder een goedkeurings of afwijzing doen. Omdat het sturen van e-mail lastig is laten we dit *uit* de requirements. Je mag de aanname doen dat als een beheerder iets goedkeurt of afkeurt hij of zij hier buiten de applicatie actie op onderneemt om de betrokken partijen te informeren. Wel moeten we daarom de contactinformatie van de ervaringsdeskundigen en bedrijven opslaan.


### Technieken
Er is gebruik van een aantal technieken verplicht. Deze zijn:
- Een Python backend met een bekend framework. 
- Een SQL database.  
- Een HTML/CSS/JavaScript frontend. Wij raden gebruik van Bootstrap aan, andere framework zijn ook mogelijk.
- Een REST API om bepaalde data op te halen en te bewerken die succesvol de bijgesloten POSTMAN test cases doorloopt. 
- Gebruik van AJAX om tenminste het dashboard van de *beheerder* dynamisch te maken.

We verwachten van iedere student gebruik van al deze technieken terug te zien in de code. Hou ook rekening met de volgende details:

### Backend
Als backend raden wij Flask aan, maar we willen ook FastAPI of Django als optie aanbieden.

### Database
We verwachten een degelijk databaseontwerp. De applicatie moet gebruik maken van een SQL gebaseerde database. Wij raden SQLite aan, maar MySQL of PostgreSQL zijn ook mogelijk. We verwachten bij oplevering een set met demo data om werking van de applicatie te kunnen testen. 

In tegenstelling tot eerdere opdrachten staat het jullie vrij wel of niet een ORM te gebruiken.

### API
Er moet tenminste voor het aanmelden en volgen van onderzoeksaanvragen een REST API beschikbaar zijn. Eventueel kan de API worden uitgebreid met andere functies als dat handig is. Documenteer de API in een apart bestand op een manier die bruikbaar is voor externe partijen die de API willen gebruiken. Laat in ieder geval zien de method (GET, POST, DELETE, PUT), route, parameters, en een beschrijving van elke endpoint.  

Er is een POSTMAN test bestand bijgesloten waarmee het aanmaken van nieuwe onderzoeken en het ophalen van inschrijvingen van ervaringsdeskundigen kan worden getest. Deze testen moeten succesvol doorlopen.


## Additionele requirements
Er zijn een aantal zaken die als noodzakelijk voor een minimaal product (MVP) worden gezien, maar wel zeer wenselijk zijn.

### Proces en UI verbeteringen
- Een ervaringsdeskundige zou zelf zijn account moeten kunnen verwijderen, met opgaaf van reden. In dat geval moet het account een aparte status krijgen en mag het niet langer getoond worden. 
- Als filters hebben we nu leeftijd, type beperking en type onderzoek. Een filter waarin een ervaringsdeskundige een periode van beschikbaarheid kan aangeven is ook wenselijk, waarbij dus alleen onderzoeken worden getoond met een startdatum binnen de periode van beschikbaarheid.
- Een ervaringsdeskundige moet zich kunnen uitschrijven voor een onderzoek. De beheerder moet dit kunnen zien en de uitschrijving kunnen goedkeuren en zo buiten de applicatie om de organisatie kunnen informeren.
- Als een ervaringsdeskundige inlogt zouden we graag nieuw aangemaakte onderzoeken willen tonen die voldoen aan de filters van de ervaringsdeskundige.

### Eigen portal organisaties
Er zou ook een portal moeten komen voor organisaties. Hierin kunnen zij ook buiten de API om onderzoeken aanmaken en de status van onderzoeken inzien. Van belang is dat ze hierbij bij het opgeven van een onderzoek bij het instellen van de filters dynamisch kunnen zien hoeveel (alleen het aantal) ervaringsdeskundigen er zijn die voldoen aan de filters. Zo kunnen ze zelf de filters aanpassen om een grotere groep ervaringsdeskundigen te bereiken.
 
### E-mail notificatie
E-mails versturen is in verband met problemen met spam lastig. Maar dit is wel hoe de organisatie nu werkt. Het zou daarom welkom zijn om alsnog de moeite te nemen om e-mails te versturen. Dit kan bijvoorbeeld met een externe dienst als [Mailersend](https://developers.mailersend.com/guides/sdk/sending-emails-with-mailersend-and-python.html#install-mailersend-sdk). 

# Appendix

## Gegevens ervaringsdeskundigen
De profielpagina van een ervaringsdeskundige / ervaringsdeskundige bevat de volgende velden. Een aantal daarvan zijn gemarkeerd als "filterveld" - dit zijn de attributen waar naar gekeken moet worden als een onderzoek wordt aangeboden:

| Attribuut                              | Type       | Toelichting                                                        |
|----------------------------------------|------------|--------------------------------------------------------------------|
| Voornaam                               | String     |                                                                    |
| Achternaam                             | String     |                                                                    |
| Postcode                               | String     |                                                                    |
| Geslacht                               | String     |                                                                    |  
| E-mailadres                            | String     |                                                                    |
| Telefoonnummer                         | String     |                                                                    |
| Geboortedatum                          | Date       |  Filterveld.                                                                 |
| Type beperking                         | Verwijzing | Keuze uit een lijst, meerdere mogelijk. Filterveld.                |
| Gebruikte hulpmiddelen                 | Tekstveld  |                                                                    |
| Bijzonderheden                         | Tesktveld  |                                                                    |
| Toezichthouder                         | Boolean    | Standaard: Nee                                                     |
| Naam voogd of toezichthouder           | String     | Indien toezichthouder                                              |
| E-mailadres voogd of toezichthouder    | String     | Indien toezichthouder                                              |
| Telefoonnummer voogd of toezichthouder | String     | Indien toezichthouder                                              |
|                                        | String     |                                                                    |
| Voorkeur benadering                    | Keuze      | Keuze uit telefonisch of email                                     |
| Type onderzoek                         | Keuze      | Meerdere mogelijk. Keuze uit telefonisch, internet of op locatie.  Filterveld. |
| Bijzonderheden beschikbaarheid         | Tekstveld  |                                                                    |

## Gegevens onderzoek
Een aantal gegevens van een onderzoek zijn gemarkeerd als "filterveld" - dit zijn de attributen waarop wordt bepaald wanneer het onderzoekn aan een ervaringsdeskundige wordt getoond:

| Attribuut              | Type       | Toelichting                                             |
|------------------------|------------|---------------------------------------------------------|
| Titel                  | String     |                                                         |
| Status                 | Verwijzing | Keuze uit nieuw, goedgekeurd, afgekeurd, gesloten       |
| Beschikbaar            | Boolean    | Geeft aan of er nog is in te schrijven op dit onderzoek |
| Beschrijving           | String     |                                                         |
| Datum vanaf            | Date       |                                                         |
| Datum tot              | Date       |                                                         |
 | Type onderzoek         | Verwijzing | Keuze uit op locatie, telefonisch, online.  Filterveld. |
| Locatie                | String     | Indien op locatie                                       |
 | Met beloning           | Boolean    |                                                         |
| Beloning               | Tekstveld  | Indien "met beloning"                                   |
| Doelgroep leeftijd van | Number     | Filterveld.                                             |
| Doelgroep leeftijd tot | Number     | Filterveld.                                             |
 | Doelgroep beperking    | Verwijzing | Keuze uit een lijst, meerdere mogelijk.  Filterveld.    |
