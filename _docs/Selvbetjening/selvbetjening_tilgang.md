---
title: Tilgang til selvbetjening
description:  Tilgang til selvbetjening

sidebar: selvbetjening_sidebar
product: Selvbetjening
redirect_from: /selvbetjening_tilgang
---

Denne siden beskriver hvordan man får tilang til grensesnittene for selvbetjening.

---
* TOC
{:toc}

## Innlogging

Selvbetjeningen er beskyttet av Ansattporten i både test- og prodmiljøet.

For å logge inn, kan du gå rett til nettadressen i det miljøet du vil selvbetjene.

| Miljø | URL |
| --- | --- |
| Test | [selvbetjening.test.samarbeid.digdir.no](https://selvbetjening.test.samarbeid.digdir.no) |
| PROD | [selvbetjening.samarbeid.digdir.no](https://selvbetjening.samarbeid.digdir.no) |

## Tilgang i testmiljø

I testmiljøet finnes det to måter å bruke selvbetjeningen på.

### Representere virksomhet

For å representere en ekte virksomhet må brukeren ha nødvendige rettigheter i Altinn for virksomheten.

### Innlogging uten representasjon

Brukere kan også logge inn uten å representere en virksomhet.

Brukeren kobles da til et syntetisk organisasjonsnummer som kan brukes til testing og utprøving. Man kan fritt bytte syntetisk organisasjonsnummer etter innlogging.


## Tilgang i produksjonsmiljø

I produksjonsmiljø må brukeren representere en virksomhet.

Tilgang styres gjennom Altinn og må delegeres av en person med nødvendige rettigheter i virksomheten.

Om du mangler rettigheter når du logger inn, vil du få mulighet til å be om tilgang.

## Be om tilgang

Brukere som logger inn uten nødvendige rettigheter vil få mulighet til å be om tilgang direkte i løsningen.

Forespørselen sendes til personer i virksomheten som kan delegere nødvendige rettigheter i Altinn.

## Altinn-rettigheter

Følgende Altinn-rettigheter brukes for selvbetjening:

|**Rettighet**|**Funksjon**|
| - | - |
| Selvbetjening av APIer i ID-porten/Maskinporten | Gir tilgang til å administrasjon og tilgangsstyring av scopes for API-tilbydere i både test- og produksjonsmiljø |
| Selvbetjening av integrasjoner i ID-porten/Maskinporten | Gir tilgang til å opprette, endre og slette klienter og integrasjoner mot KRR, ID-porten og Maskinporten i både test- og produksjonsmiljø |
| Selvbetjening for leverandører i ID-porten/Maskinporten*| Åpner opp feltet "For en kunde" slik at leverandører kan opprette klienter kunder sine organisajonsnummer i både test- og produksjonsmiljø |
| Selvbetjening for testing i ID-porten/Maskinporten | Gir tilgang til administrasjon av klienter og scopes kun i testmiljøet |

*NB! Selvbetjening for leverandører krever "Selvbetjening av integrasjoner..." i tillegg.

## Tilgang til API

Selvbetjenings-API-et brukes for automatisering og integrasjon.

For å bruke API-et må virksomheten:
- få utstedt nødvendig klient fra Digdir
- bruke virksomhetssertifikat for autentisering

Ta kontakt med servicedesk@digdir.no for tilgang til API-et.


## Ofte stillte spørsmål

### Støtter selvbetjeningen utelandske brukere?

Per nå kan ikke personer uten Norsk eID på nivå høyt selvbetjene via denne løsningen. De må ta kontakt på servicedesk@digdir.no for hjelp til klientoppsett.

### Jeg får ikke opp virksomheten jeg ønsker å representere i innloggingsvinduet

Ansattporten lister bare ut de virksomhetene du har rettighet til å representere. Sjekk at du har fått rettigheten i Altinn.

### Jeg har sendt inn forespørsel om tilgang via selvbetjeningen, hva nå?

Forespørselen legges til godkjenning hos virksomheten i Altinn. Noen med rettigheter på vegne av virksomheten må godkjenne forespørselen.
