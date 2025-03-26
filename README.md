# Projekt: Open Banking API UX-Prototyp

## Ziel
Dieses Projekt demonstriert anhand zweier konkreter Anwendungsfälle (AIS und PIS) die Anforderungen, UX-Flows und API-Spezifikationen einer Open-Banking-Schnittstelle im Schweizer Kontext.

---

## Projektstruktur

```
open-banking-api-ux-prototype/
|
├── README.md                     <- Projektbeschreibung und Einstieg
├── /docs
│   ├─ use-case-AIS.md           <- Kontoinformationszugriff (AIS)
│   ├─ use-case-PIS.md           <- Zahlungsauslösung (PIS)
│   ├─ user-stories.md           <- User Stories (Endnutzer, TPP, Bank)
│   ├─ requirements.md           <- API- und UX-Anforderungen
│   ├─ api-spec-openapi.yaml     <- Technische OpenAPI-Spezifikation
│   └─ standards-comparison.md   <- Vergleich gängiger Standards (NextGenPSD2, OpenWealth, Swiss OB)
|
├── /prototype
│   ├─ screens-ais.png
│   └─ screens-pis.png
```

---

## Technologien
- **UX-Prototyping**: Axure RP
- **API-Spezifikation**: OpenAPI 3.0 (YAML)
- **Dokumentation**: Markdown

---

## Use Case: AIS - Kontoinformationszugriff

### Beschreibung
Ein Drittanbieter (Third Party Provider, TPP) möchte im Rahmen eines Open-Banking-Prozesses nach Zustimmung des Endnutzers auf dessen Kontoinformationen bei der Bank AG zugreifen. Der Zugriff erfolgt über eine standardisierte API gemäß NextGenPSD2 oder Swiss Open Banking.

### Beteiligte Akteure
- **Endnutzer**: Gibt die Zustimmung zur Freigabe der Kontoinformationen
- **TPP (Drittanbieter)**: Initiiert den Zugriff und verarbeitet die Daten
- **Bank AG (ASPSP)**: Authentifiziert den Endnutzer und stellt die Daten über API bereit

### Ablauf (vereinfacht)
1. Der Nutzer wählt im TPP-Frontend die gewünschte Bank (Bank AG)
2. Weiterleitung zur Authentifizierung bei der Bank AG
3. Login (2-Faktor, z. B. Passwort + SMS-Code)
4. Darstellung der beantragten Berechtigungen (z. B. Zugriff auf Kontostand, Transaktionshistorie)
5. Nutzer stimmt zu ("Zustimmen")
6. Weiterleitung zurück an den TPP mit Autorisierungstoken
7. TPP ruft Kontoinformationen per API ab

### Beispiel-Endpunkte (GET)
```
GET /accounts
GET /accounts/{accountId}/transactions
```

---

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

---

## Status
- [x] Mockup-Screens AIS & PIS
- [x] Use Case AIS
- [x] Use Case PIS
- [ ] User Stories
- [ ] API Definition (OpenAPI)
- [ ] Standardvergleich
- [ ] README finalisieren
