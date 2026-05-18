---
title: Om selvbetjening av Digdirs fellesløsninger
description:  Selvbetjening av Digdirs fellesløsninger

sidebar: main_sidebar
product: Selvbetjening
redirect_from: /selvbetjening_om
---
## Om selvbetjening

Selvbetjening gjør det mulig å administrere Digdirs fellesløsninger uten manuell behandling fra Digdir.

Gjennom selvbetjening kan virksomheter blant annet:

- opprette og administrere klienter
- administrere tilgang til API-er
- automatisere administrasjon gjennom API


## Støttede fellesløsninger

Per i dag kan du selvbetjene følgende fellesløsninger

- ID-porten
- Ansattporten
- Maskinporten


## Grensesnitt for selvbetjening

Vi tilbyr to grensesnitt for selvbetjening. Et via grafisk grensesnitt på Samarbeidsportalen, i tillegg til et API.

### Samarbeidsportalen

Selvbetjening gjennom grafisk grensesnitt i Samarbeidsportalen.

Dette passer for virksomheter som ønsker enkel administrasjon gjennom nettleser.

Funksjonalitet:
- enkel opprettelse og administrasjon av klienter
- autentisering med vanlig brukerinnlogging
- tilgangsstyring via Altinn
- administrasjon uten behov for integrasjon eller API-kall

### Selvbetjening gjennom API for automatisering og integrasjon.

Dette passer for virksomheter som ønsker å automatisere administrasjon eller bygge egne løsninger.

Funksjonalitet:

- automatisering av administrasjon og tilgangsstyring
- integrasjon med interne systemer
- grunnlag for egne selvbetjeningsgrensesnitt
- administrasjon av Maskinporten-API-er programmatisk

For å bruke API-et må virksomheten få utstedt nødvendig klient fra Digdir.

Autentisering skjer med virksomhetssertifikat.

## Miljøer

Selvbetjening er tilgjengelig i både test- og produksjonsmiljø.

| Miljø | URL |
| --- | --- |
| Test | [selvbetjening.test.samarbeid.digdir.no](https://selvbetjening.test.samarbeid.digdir.no) |
| PROD | [selvbetjening.samarbeid.digdir.no](https://selvbetjening.samarbeid.digdir.no) |


## Forutsetninger

For å ta i bruk selvbetjening må:

virksomheten være registrert hos Digdir
nødvendige bruksvilkår være signert
brukeren ha nødvendige roller og tilganger
