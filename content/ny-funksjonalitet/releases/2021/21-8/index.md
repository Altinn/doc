---
title: 21.8
description: Endring i paralell signering og nedlasting av delegeringer p� fil. Mindre endringer og feilrettinger
weight: 130
type: releasenote
releasenote_info: Release 21.8. Produksjonssettes 25. august 2021
---

**Dette er en kommende endring. Gjeldende endring ligger [her](../21-7).**

**Vi minner ogs� om endringer i [Altinn 3.0.](https://github.com/Altinn/altinn-studio/releases)**

## Endringer i Portal

### Nedlasting av delegeringer p� fil

Det er lagt til mulighet til � laste ned delegeringer p� fil det lagres som CSV filer og legges inn i en ZIP fil for � samle det i en nedlasting. For organisasjoner med mange underenheter og delegeringer har det lenge v�rt et �nske � kunne hente ut en total oversikt over hvem som har hvilke roller/rettigheter p� virksomheten, inkludert tilknyttede organisasjonsledd og underenheter.
Form�let med dette er enklere � ha kontroll hvem som har tilgang til hva i Altinn p� tvers av hoved og underenheter.
Funksjonaliteten har s�rlig v�rt etterspurt av kommuner. Tidligere har det kun v�rt mulig � bestille denne typen oversikter som manuelle kj�ringer.

Hvis uthenting av data tar for lang tid vil sp�rringen bli stoppet av sikkerhets�rsaker og virksomheten blir bedt om � bestille oversikten p� epost. Oversikten vil kun inneholde direkte-delegeringer og ikke rettigheter man f�r fordi man har en rolle i en virksomhet som har mottatt en rettighet.

Funksjonalitet for � laste ned oversikt over delegeringer p� fil finner man i Profil for virksomheten under �Andre med rettigheter�.

![Funksjonalitet for � laste ned delegeringer p� fil](lasteDelegeringer1.png " ")

Det genereres 2 filer; en med oversikt over roller og en med oversikt over rettigheter inkludert rettigheter for kun et enkelt element (videresending). I filene vil man ogs� kunne se hvem som har delegert roller/rettigheter og n�r dette skjedde der denne informasjonen er tilgjengelig.

![Excel-filer med oversikt over roller og rettigheter](lasteDelegeringer2.png " ")

CSV filene benytter semikolon (;) som skilletegn mellom celler slik at �pning i Excel krever at brukeren har satt opp Excel slik at det er dette skilletegnet og ikke komma (,) som benyttes. Dersom komma tolkes som skilletegn kan det gi problemer n�r data inneholder komma.


### Endring i plattform-delen for MVA kvittering

Endring i plattform-delen for MVA kvittering MVA modulen som genererer betalingsinformasjon som skal vises p� kvitteringssiden er endret slik at hvis man sender inn et skjema med Meldingstype �Korrigert melding� s� skal man f� samme bel�p i betalingsinformasjonen p� kvitteringssiden som det st�r i skjemadelen p� kvitteringen.

## Endringer i Autorisasjon

### Endring i parallellsignering

For � kunne signere et skjema som benytter parallell signering m�tte man tidligere enten ha rollen PASIG direkte for avgiveren eller s� m� man ha en n�kkelrolle for avgiveren. Dette er n� endret slik at man ogs� kan signere hvis man har en rolle som arver PASIG rollen, uansett om dette er en n�kkelrolle eller ikke.
Dette gj�r at de som kun har rollen KNUF for et NUF n� kan signere et skjema som benytter parallell signering. Liste over alle roller fra Enhetsregisteret som kan utf�re en paralellsignering p� vegne av virksomhet som skal signere finnes [her](https://www.altinn.no/nn/hjelp/skjema/alle-altinn-roller/parallell-signering/).

## Endringer i REST

### Implementere API for � opprette virksomhetsbrukere

Implementerte et API for � opprette, endre og slette virksomhetsbrukere, der tokens brukes i stedet for virksomhetssertifikat. Alle APIene krever tokenet altinn:enterpriseusers.read for GET, altinn:enterpriseusers.write for POST/PUT/DELETE. Brukerne blir opprettet uten thumbprint for virksomhetssertifikat, s� de kan ikke logge inn i portalen som en vanlig virksomhetsbruker.

### St�tte for virksomhetsbrukertoken fra 3.0 i sluttbruker REST API
 
Gj�re det mulig � kaller operasjoner som krever maskinporten-token med virksomhetsbruker-token

I release 21.7 ble det �pnet for st�tte for virksomhetsbrukertoken fra 3.0 i sluttbruker REST API.
N� �pnes det ogs� for at virksomhetsbrukertoken kan brukes mot andre virksomhetsautentiserte APIer, som ellers ikke krever brukerautentisering. Dette inkluderer:

- /api/consentrequests
- /api/delegationsrequests
- /api/authorization/token
- /api/serviceowner/*

Brukerautentiseringen av en virksomhetsbruker som da ogs� ligger i tokenet blir da bare ignorert av disse operasjonene, og oppf�re seg tilsvarende som om man benytter et vanlig Maskinporten-token utvekslet til AltinnToken.

### HAL-lenke til rolerequirements fra metadata
 
Det er tre forskjellige lenker for de forskjellige tjenestetypene

Correspondence, FormTask, Lookup, Broker, Link og Collaboration:[]( https://www.altinn.no/api/metadata/rolerequirements?serviceCode=&lt;SC&gt;&amp;serviceEditionCode=&lt;SEC>)
DelegationScheme: []( https://www.altinn.no/api/metadata/rolerequirements?serviceCode=AppId%3A&lt;appid>)
AltinnApp:[]( https://www.altinn.no/api/metadata/rolerequirements/?app=&lt;AltinnAppId>)

### Fjerne innlesing av Preferert Kontaktadresse fra Folkeregisteret

Folkeregisteret vil fjerne Preferert Kontaktadresse fra og med 16. oktober. Fram til n� har dette v�rt hovedkilden til adressene i Altinn. Basert p� statistikk fra Skatteetaten vil dette kunne for�rsake en endring i adressekilde for opptil 37.000 personer.
Vi vil ikke gjennomf�re en komplett re-innlesing av personer som f�lge av denne endringen, s� en persons adresse vil bare bli oppdatert ved neste hendelse mottatt fra Folkeregisteret. Personer som blir oppdatert etter 21.8 vil f� registrert adresse fra f�rste gyldige adresse fra f�lgende kilder:

- postadresse
- oppholdsadresse
- bostedsadresse
- postadresse i utlandet

## Endringer i TUL

### Ny Logo i TUL
Lagt til ny digitaliseringsdirektoratet logo i tjeneste utviklings plattformen.


## Diverse feilrettinger

### KoFuVi kontaktinformasjon for virksomheter tilgjengelig for alle med tilgang til virksomheten

Det har blitt funnet og utbedret en svakhet hvor alle som har tilgang til en virksomhet i sin avgiverliste kunne f� uthentet KoFuVi kontaktinformasjon for virksomheten ved � navigere til url: /ui/ContactSettings/Enterprise/ etter � ha valgt virksomheten som avgiver i portalen.
For � kunne f� tilgang til KoFuVi informasjon for en virksomhet skal det kreves tilgang til systemressursen EntityProfileAdministration, som det n� ogs� er lagt inn autorisasjonssjekk for p� dette endepunktet.

### Omvendt rekkef�lge p� navn i aksjeselskap ved utlisting til Excel fil

Det har blitt funnet og utbedret en svakhet med CSV-fil eksport funksjonaliteten i �S�k p� flere akt�rer�. CSV-fil eksporten benyttet ikke fullstendig navn p� virksomhet fra enhetsregisteret, samtidig som at organisasjonsnummer eller maskert f�dselsnummer for eier av meldingsboks-elementene manglet. OBS: Vi minner om at personnummer delen av f�dselsnummer er maskert med ***** selv om det er innlogget brukers eget f�dselsnummer. Dette for � minske faren for at SSN kan komme p� avveie.

### Valideringsfeil i respons body for feil org. nr./SSN eller navn ved opprettelse av samtykkeforesp�rsler i REST API

Det har blitt utbedret en svakhet i REST API grensesnitt for opprettelse av samtykkeforesp�rsler. 
Dersom input parameterne OfferedBy og OfferedByName eller RequiredDelegator og RequiredDelegatorName inneholder ett organisasjonsnummer eller f�dselsnummer som Altinn ikke har kjennskap til, evt. om oppgitt navn ikke stemmer med personen eller virksomhetens registrerte navn i enhetsregisteret eller folkeregisteret, f�r man i dag bare HttpStatusCode 400 og en Reason-Phrase med forklaring.
Reason-Phrase er det mange som ikke har ett forhold til i sine implementasjoner og vi har f�tt flere henvendelser hvor feil SSN eller feilregistrerte navn er �rsak til at man ikke f�r gjennomf�rt samtykkeprosessen.

Grensesnittet blir n� utbedret til � gi tilsvarende feilmelding i respons body som andre valideringsfeil p� samtykkeforesp�rselen:

> [
>    {
>        "ErrorCode": "40332",
>        "ErrorMessage": "01010112345 is either not a valid organization number or social security number, or the provided name; Nordmann does not match the person or organizations registered name."
>    }
> ]

### Tilgangsstyrer for privatperson fikk tilgang til avgivere og rettigheter personen har mottatt av andre

Tilgangsstyrer for en privatperson kunne f� tilgang til avgivere og informasjon om roller og rettigheter delegert fra andre til brukeren man car tilgangsstyrer for, gjennom operasjoner laget for det nye �Rettigheter virksomheten har hos andre� panelet. For � bruke disse operasjonene m� brukeren n� representere en virksomhet.

### Visning av lese- og skriveikoner var forskjellig i kvitteringssiden og andre med rettigheter panelet

Endret visning av ikoner i andre med rettigheter panelet s� det vises likt som i kvitteringssiden. Hvis brukeren har les eller les-arkiv vises leseikonet, og hvis han har skriv eller slett-arkiv vises skriveikonet.

### Samtykkepanel krasjer ikke lenger n�r IDPorten er nede

Feilen er rettet. Dette gj�r at man n� kan �pne samtykkepanelet uten at man f�r en 400 bad request feilmelding.

### NotificationIcon for samtykkeforesp�rsel vises ikke p� foresp�rselen i full-vindu-modus

F�r var utropstegn-ikonene i samtykkene synlige kun i mobilvisning. S� snart man forst�rret vinduet forsvant ikonet. Denne feilrettingen legger til utropstegn-ikonet ved siden av �Behandle foresp�rsel�-teksten.

### AuthorizeAccess f�r NULLReference for Sluttbrukersystem med Lokale roller

Metoden AuthorizationDecisionPoint.AuthorizeAccess som brukes blant annet av SubmitFormTask hadde en bug der den som en del av en sjekk gjorde en aksjon p� en property som er NULL for Lokale Roller. Lokale roller er definert av brukeren selv, og er relativt sjeldne, noe som kan forklare hvorfor denne bug ikke har v�rt synlig tidligere, da aktuell kode ikke har v�rt endret p� flere �r.

Siden aktuell sjekk kun skal agere p� eksterne roller, s� legges det p� en ekstra sjekk p� RoleType.RoleSource = External f�r man pr�ver � hente ut RoleTypeCode. Denne verdien er alltid satt, og man unng�r derfor � f� NULLReference.

### Forbedret h�ndtering av ukjente adresser

Persondokumenter med postadresser som inneholdt data av typen ukjent adresse eller vegadresser med kun postnummer og poststed ble ikke lest inn korrekt. Dette f�rte til feil innlesing for noen f� personer fra folkeregisteret. Dette har blitt utbedret og f�rer ikke lenger til feil, men personene vil fortsatt ikke v�re registrert med adresser, siden disse er tomme.

### Spr�k for CAPTCHA valideringsmelding

Det er rettet en gammel feil som gj�r at man ikke lenger f�r et tilfeldig spr�k for valideringsmelding fra CAPTCHA.

### Sharepoint 2019 endringer uten egen branch

Det er gjort tilpasninger som gj�r at man ikke trenger en egen kodebranch for Sharepoint 2019.
