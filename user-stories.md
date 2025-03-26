# User Stories
- Endnutzer (Bankkunde)
## Story 1 – Kontoinformationen freigeben (AIS):

Als Bankkunde
möchte ich einem Drittanbieter den Zugriff auf meine Kontoinformationen erlauben,
damit ich Finanz-Apps nutzen kann, die meine Kontobewegungen analysieren.

## Akzeptanzkriterien:

Ich kann den Drittanbieter auswählen

Ich werde sicher zu meiner Bank weitergeleitet

Ich kann explizit die Zugriffsrechte bestätigen oder verweigern

Ich werde zurück zum Drittanbieter geführt

## Story 2 – Zahlung initiieren (PIS):

Als Bankkunde
möchte ich über eine Drittanbieter-App Zahlungen von meinem Konto auslösen,
damit ich Rechnungen direkt in einer App begleichen kann.

## Akzeptanzkriterien:

Ich kann Zahlungsdetails eingeben (IBAN, Betrag, Währung)

Ich werde zur Bank weitergeleitet und authentifiziere mich

Ich kann die Zahlung bestätigen oder abbrechen

Ich erhalte eine Transaktionsbestätigung

- Drittanbieter (TPP)
# Story 3 – Zugriff auf Kontoinformationen beantragen:

Als Drittanbieter
möchte ich über eine standardisierte API Kontodaten meiner Nutzer abrufen können,
damit ich Mehrwertdienste wie Budgetplanung oder Multibanking anbieten kann.

## Akzeptanzkriterien:

Ich nutze standardisierte Schnittstellen (z. B. OpenAPI-konform)

Ich leite den Nutzer korrekt zur Bank weiter (Redirect-Flow)

Ich erhalte bei Zustimmung ein gültiges Access Token

Ich kann darüber den /accounts-Endpoint abfragen

## Story 4 – Zahlungsauslösung verarbeiten:

Als Drittanbieter
möchte ich im Auftrag des Nutzers Zahlungen bei seiner Bank auslösen,
damit ich Zahlungsvorgänge direkt in meiner App ermöglichen kann.

## Akzeptanzkriterien:

Ich kann Zahlungsaufträge per API anstossen

Die Bank bestätigt mir den Status (pending / success / failed)

Ich zeige dem User eine nachvollziehbare Statusmeldung an
