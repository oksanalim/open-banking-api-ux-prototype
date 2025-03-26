## Use Case: PIS - Zahlungsauslösung

### Beschreibung
Ein Drittanbieter initiiert eine Zahlung im Namen des Endnutzers. Die Bank des Nutzers übernimmt die Ausführung der Transaktion nach expliziter Zustimmung des Nutzers. Dieser Prozess ist in der EU durch PSD2 geregelt und basiert auf standardisierten Schnittstellen.

### Beteiligte Akteure
- **Endnutzer**: Gibt die Zahlungsdetails ein und autorisiert die Zahlung
- **TPP (Drittanbieter)**: Erfasst die Zahlungsdaten und initiiert die Zahlung
- **Bank AG (ASPSP)**: Authentifiziert den Endnutzer und führt die Zahlung aus

### Ablauf (vereinfacht)
1. Nutzer gibt im TPP-Frontend die Zahlungsdaten ein (Empfänger, Betrag, IBAN)
2. Auswahl der Bank AG und Weiterleitung zur Authentifizierung
3. Login und 2-Faktor-Authentifizierung
4. Darstellung der Zahlungsdetails und Einholung der Zustimmung ("Zahlung bestätigen")
5. Bank AG prüft und führt Zahlung aus
6. Rückmeldung an TPP über Ausführungsstatus

### Beispiel-Endpunkt (POST)
```
POST /payments
Body:
{
  "debtorAccount": {
    "iban": "CH9300762011623852957"
  },
  "creditorAccount": {
    "iban": "CH5604835012345678009"
  },
  "amount": {
    "currency": "CHF",
    "amount": "250.00"
  },
  "creditorName": "Muster AG",
  "remittanceInformation": "Rechnung 10324"
}
```
