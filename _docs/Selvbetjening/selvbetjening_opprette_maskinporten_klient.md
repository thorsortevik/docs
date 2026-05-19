---
title: Opprette Maskinporten-klient
description:  Hvordan opprette Maskinporten-klient

sidebar: selvbetjening_sidebar
product: Selvbetjening
redirect_from: /selvbetjening_opprette_maskinporten_klient
---

Denne siden beskriver hva som skal til for å opprette en klient i Maskinporten.

---
* TOC
{:toc}

## Forutsetninger før du kan opprette klient

For å kunne opprette en klient i Maskinporten må følgende forutsetninger være oppfylt:

1. Du må ha tilgang til miljøet du skal opprette klienten i. Les mer på [Tilgang til selvbetjening](/docs/selvbetjening/selvbetjening_tilgang.html)
2. Du må ha norsk eID på sikkerhetsnivå høyt, for eksempel BankID, Buypass eller Commfides.
3. Du må ha tilgang til scopet som skal brukes av klienten. Dette gjelder ikke åpne scopes.

## Logg inn i rett miljø

Selvbetjeningen er delt inn i flere miljøer, på samme måte som ID-porten, Ansattporten og Maskinporten. Hvis du skal opprette en klient for et testmiljø i ID-porten eller Maskinporten, må du bruke selvbetjeningens testmiljø.

| Miljø | URL |
| --- | --- |
| Test | [selvbetjening.test.samarbeid.digdir.no](https://selvbetjening.test.samarbeid.digdir.no) |
| PROD | [selvbetjening.samarbeid.digdir.no](https://selvbetjening.samarbeid.digdir.no) |

<h2 id="opprette-klient">Opprette klient</h2>

<ol>
  <li>Etter innlogging, gå til <code>Klienter</code></li>
  <li>Trykk på <code>Legg til klient</code></li>
  <li>Velg <code>Maskinporten</code></li>
</ol>

<p align="center">
  <img
    src="{{site.baseurl}}/assets/knapp_maskinporten.png"
    style="
      width:100%;
      max-width:700px;
      border:1px solid #dcdcdc;
      border-radius:8px;
    "
  >
  <br>
  <em>Velg "Maskinporten"</em>
</p>

<ol start="4">
  <li>
    Fyll ut påkrevde felter.
    (Se <a href="#feltforklaring---maskinporten">feltforklaring</a>)
  </li>
</ol>

<p align="center">
  <img
    src="{{site.baseurl}}/assets/skjema_maskinporten.png"
    style="
      width:100%;
      max-width:700px;
      border:1px solid #dcdcdc;
      border-radius:8px;
    "
  >
  <br>
  <em>Fyll ut klientdetaljer</em>
</p>

<ol start="5">
  <li>Trykk på <code>Legg til scope</code></li>
  <li>
    Søk opp og legg til de scopene du vil benytte og trykk på
    <code>Fullfør</code>.
  </li>
  <li>Trykk på <code>Lagre endringer</code> for å lagre klienten.</li>
  <li>Klienten er nå opprettet.</li>
</ol>

## Registrere nøkkel eller sertifikat på klient

Maskinporten støtter autentisering med:
- virksomhetssertifikat via `x5c`
- registrert nøkkel via `kid`

Les mer om dette i dokumentasjonen for [JWT grant](https://docs.digdir.no/docs/Maskinporten/maskinporten_protocol_jwtgrant.html#grant-structure).

For klienter som kun skal kunne autentiseres med bestemte nøkler eller sertifikater, kan dette administreres under fanen `Nøkler`.

> NB! Nøkler registrert fra virksomhetssertifikat har maksimal levetid på 1 år, selv om sertifikatet har lengre gyldighetstid.
>
> Nøkkelen må derfor fornyes før den utløper.

### Eksempel på offentlig del av virksomhetssertifikat

1. Få eksportert ut den offentlige nøkkelen av virksomhetssertifikatet i PEM-format
2. Gå til inn på ønsket klient og fanen 'Nøkler'
3. Trykk på '+ Legg til'
4. Lim inn PEM-formatert sertifikat og trykk 'Lagre'

Eksempel på gyldig PEM av en offentlig del av et virksomhetssertifikat.

```
-----BEGIN PUBLIC KEY-----
MIIBojANBgkqhkiG9w0BAQEFAAOCAY8AMIIBigKCAYEAwGAGTEkkeWVac30+/Z2z
k/5pgFQzvmudPg225dqq8zijQEZ2A+C3CjGm3+HgOaJ71F3LMirPvG0/lw5Y/WqJ
XGBTrbdUju2Syt4poxSdUzf+3mVKhFXSWHBex7+4gKn7ybWKWaJpSNgse+CDhG3H
c1c/kFoE8W9M9lOsa75ZX+n55Pga7+lkiANg/9ZqdkQARBdnPmwUB5o7rfQfUYeq
PckFGS7qSedNTuptTI34KMItIdWGb2KIJ56RvERfkXnXwt+u0KdcWsKwbbH1X3Kw
lSdJsz10Zn9+S01vn57IpxniePuuON6c/G8dslgelPTkGbtZYeVs7rEAIB02jNbF
751KEQXGE21X7ni34KJPr9V3M8F7+6rwjP/S0noml5MJu0lZjvE3M4VKbSyrsOS5
bxM6lTwklGgcU8rv2r/BPSzsd6YdJ8ZC1gLHLz7gS9unSQMUEfgQxg/H4trpedkX
IFmh486x6nBuVKxTqA3PzRwWDQ0PT+pbNGUPCli+KJpnAgMBAAE=
-----END PUBLIC KEY-----

```

### Eksempel på å registrere nøkkel

1. Offentlig nøkkel, i PEM-format, må konverteres til JWK ved hjelp av JWK Creator eller lignende, før den kan bli lagt på klienten.
2. Gå til inn på ønsket klient og fanen 'Nøkler'
3. Trykk på '+ Legg til'
4. Lim inn JWK og trykk på 'Lagre'.

Eksempel på gyldig JWK:

```
    {
      "kty": "RSA",
      "e": "AQAB",
      "use": "sig",
      "kid": "min_egen_nokkel",
      "alg": "RS256",
      "n": "lGc-dGnl9l9pCSb6eW5Mf23Aiss09q7Mxre9q9dazSiN9IjQJmkWDySpoYW3g_rSX2a74cg_q3iTSM0Co9iJ0LQp8gjoIi9I8syi6anBKK6fISr1adZbsGGrM1-zMRRNVsJ811snTdkbgx8ZxVRJM4F6D2KwL3TEnv0CRRVtphO0sRmimKBVVBdawPYQC64SQDvARy6xIlPhD-Da2n2Cl6vRQbVns7dYD8-C2TeYGgB_tAsrVSorx9GF5cZ-hlNHfIgg2qQYZzaljyfOWPPG5rybp9bAWg9vFllUFd_Y6vvZ0tqVfAyj67nFz_w4Rxy-MdRgERKHJcq81GkmVzq5fQ"
    }

```

## Legge til scope

Scopes kan legges til både under opprettelse av klienten og i etterkant. For å legge til et scope på en eksisterende klient, gå til fanen 'Scopes' og trykk på '+ Legg til'.

## Fjerne scope fra klient

For å fjerne et scope fra en klient, gå til fanen 'Scopes' og trykk på søppelkasse-ikonet til høyre for scope-navnet.

## Feltforklaring - Maskinporten

| Feltnavn | Forklaring |
| --- | --- |
| Visningsnavn | Brukes kun som visningsnavn i selvbetjeningen og har ingen teknisk betydning i Maskinporten. |
| Beskrivelse | Fritekstfelt der man kan gi litt mer detaljer om hva klienten brukes til. Spesielt nyttig for større organisasjoner der flere har tilgang til løsningen |
| Applikasjonstype | 'application_type' i henhold til [OAuth kap 2.1](https://tools.ietf.org/html/rfc6749#section-2.1). Denne er automatisk satt til 'web' for Maskinporten, og kan ikke endres |
| Autentiseringsmetode | 'token_endpoint_auth_method' er automatisk satt til 'private_key_jwt' for Maskinporten og kan ikke endres |
| Tillatte grant types | 'grant_types' Denne er automatisk satt til 'urn:ietf:params:oauth:grant-type:jwt-bearer' for Maskinporten og kan ikke endres |
| Access token levetid | Angir hvor lenge access token skal være gyldig. Dersom API-tilbyder har satt en maksimal levetid for scopet, vil denne grensen brukes selv om høyere verdi angis her. |
| Nøkler | I fanen 'Nøkler' listes alle registrerte nøkler på klienten, samt levetiden for desse |
| Scopes | I fanen 'Scopes' kan man legge til, og fjerne scopes som skal registreres på klienten |
| Historikk | I fanen 'Historikk' ser man endringslogg for klienten |


## Ofte stilte spørsmål

### Jeg finner ikke scopet jeg leter etter

Det kan være flere grunner til at et scope ikke vises i listen. Her er noen eksempler:

- Virksomheten din har ikke tilgang. Kontakt API-tilbyder for å be om tilgang.
- Virksomheten har fått tilgang i et annet miljø enn det du er logget inn i.
- Scopet ligger allerede på klienten
- Scopet støtter ikke den klienttypen du har opprettet. For eksempel om API-tilbyder har bestemt at et scope kun kan brukes av ID-porten, så vil ikke scopet vises når du oppretter en Maskinporten-klient.
- Det er benyttet et filter i "legg til scope" flyten. Vi anbefaler å ikke hake bort noen av filterne.
