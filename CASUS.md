# Werkplekopdracht - Webapplicatie voor Stichting Accessibility

## Opdrachtomschrijving

Als team voeren jullie een project uit voor Stichting Accessibility, waarbij een webapplicatie met een database en een API wordt ontwikkeld. Stichting Accessibility heeft als missie een inclusieve samenleving te bevorderen, waarin alle mensen, met of zonder beperking, gelijkwaardig kunnen participeren. De organisatie streeft naar digitale, fysieke en sociale toegankelijkheid voor iedereen.

Met het oog op het doen van onderzoek naar de huidige toegankelijkheid, en het indienen van verbetervoorstellen, wil Stichting Accessibility een webapplicatie laten ontwikkelen. Deze applicatie is bedoeld voor een panel van ongeveer 125 mensen met een beperking. De gegevens van de panelleden, inclusief hun beperking, moeten nauwkeurig worden opgeslagen in een database. De webapplicatie moet niet alleen door Stichting Accessibility zelf worden gebruikt voor onderzoek, maar ook toegankelijk zijn voor bedrijven die graag van het panel gebruik willen maken.

Zowel individuen met een beperking als bedrijven moeten zich kunnen registreren op de site. Gezien de gevoelige aard van de gegevens, is beveiliging van essentieel belang. Daarnaast moeten er nieuwsberichten over aankomende onderzoeken worden geplaatst, waar panelleden zich voor kunnen inschrijven. Toegankelijkheid binnen de applicatie is een harde eis, waarbij webteksten bondig en eenvoudig moeten zijn.

## Stakeholders

- **Stichting Accessibility:** Externe opdrachtgever met verschillende teams, waaronder onderzoekers, usability experts, accessibility experts en data analisten.
- **Panelleden met een beperking:** Ongeveer 125 mensen die lid zijn van het panel. Belangrijkste gebruikers van de webapplicatie, waarvan de persoonlijke gegevens nauwkeurig moeten worden beschermd.
- **Bedrijven:** Bedrijven moeten aan de hand van een API call onderzoeken moeten kunnnen inschieten
- **Webontwikkelaars:** De studenten.

## Opdracht
Ontwikkel als team een webapplicatie voor Stichting Accessibility, waarbij alle systeemeisen zijn opgenomen in het ontwerp. Werk samen zodat elk teamlid een gelijke bijdrage kan leveren.

#### Webapplicatie en API

De webapplicatie bestaat deze keer niet uit alleen een backend met een database connectie. Dit blok moe er ook een API bij. De API moet voldoen aan de volgende specificaties:

1. **Registratie en Authenticatie:**
   - Gebruikers moeten zich kunnen registreren op de site, inclusief validatie van ingevoerde gegevens.
   - Inloggen moet veilig en eenvoudig zijn.

2. **Profielbeheer deelnemer:**
   - Het moet mogelijk zijn om profielgegevens bij te werken.
   - Extra informatie over ouders, voogden, of verzorgers moet worden toegevoegd als de deelnemer jonger is dan 18 jaar of een verstandelijke beperking heeft.

3. **Onderzoeksregistratie en -beheer:**
   - Mogelijkheid voor deelnemers om zich in te schrijven voor beschikbare onderzoeken.
   - Deelnemers kunnen alleen onderzoeken kunnen inzien die past bij hun profiel.
   - Beheerders moeten alle onderzoeken moeten inzien.
   - Beheerders moeten in staat zijn onderzoeken toe te voegen, bewerken en verwijderen.
     
#### Technische Vereisten

1. **Technologie Stack:**
   - Maak gebruik van programmeertalen die iedereen in het team kent, gebruik in ieder geval HTML, CSS, Javascript, en REST.

2. **Databases:**
   - Implementeer een veilige databaseopslag voor gebruikersgegevens, onderzoeken, en communicatiegeschiedenis.

3. **API Documentatie:**
   - Zorg voor uitgebreide documentatie van de API, inclusief endpoints.


Naast al deze eisen bevat de webapplicatie heeft twee belangrijke elementen:

1. **De ervaringsdeskundigen portal:** Bevat alle informatie voor een ervaringsdeskundige, inclusief een overzicht van alle beschikbare onderzoeken gebaseerd op hun profiel.
2. **De beheerderportal:** Voor Stichting Accessibility, waar onderzoeken kunnen worden uitgezet, bedrijven aan ervaringsdeskundigen kunnen worden gekoppeld en gegevens van ervaringsdeskundigen kunnen worden beheerd.

#### Ervaringsdeskundigen portal

De profielpagina van een ervaringsdeskundige / deelnemer bevat de volgende velden:

- Voornaam
- Achternaam
- Postcode
- E-mailadres
- Telefoonnummer
- Type beperking (uit een lijst)
- Gebruikte hulpmiddelen
- Aandoening/Ziekte
- Type onderzoek waaraan men wil deelnemen (Interview, Groepsgesprekken, Online onderzoek, Engelstalig onderzoek)
- Voorkeur benadering (Telefonisch, Via portal alleen)
- Toestemming voor commerciële benadering door bedrijven (standaard: ja)
- Beschikbaarheid gedurende de week

Inloggen en registreren moeten mogelijk zijn voor ervaringsdeskundigen.

Indien een deelnemer jonger is dan 18 jaar of een verstandelijke beperking heeft, is extra contact informatie over ouder, voogd of verzorger nodig.

Naast de profielgegevens wordt een overzicht gegeven van onderzoeken waaraan een deelnemer mogelijk kan deelnemen, inclusief titel, korte beschrijving, uitvoerder, datum, locatie, beloning, soort onderzoek en status van reactie.

#### Beheerders portal

Een uitgebreid beheerdersportaal voor Stichting Accessibility, waar de volgende informatie beschikbaar is:

- Lijst van alle ervaringsdeskundigen en hun ingevulde informatie.
- Lijst van lopende onderzoeken met gedetailleerde informatie, inclusief de deelnemers die zich hebben aangemeld
- Lijst van alle bedrijven en de door hen uitgezette onderzoeken.

De lijsten moeten sorteermogelijkheden en filters hebben voor selectie.

## Systeemeisen van Stichting Accessibility

- De site moet WCAG 2.2 - AA compliant zijn.
- Invoervelden moeten ondersteuning bieden voor systeem-gebruikte speech-to-text.
- Bij visuele beperkingen moeten foutmeldingen minstens driemaal terugkomen op de site met passende suggesties.
- Bij verstandelijke beperkingen moeten formuliervelden extra bevestigingen geven bij het invullen.
- Panelleden met gehoorverlies hebben behoefte aan extra visuele stimulatie en kleurrijke ontwerpelementen.

