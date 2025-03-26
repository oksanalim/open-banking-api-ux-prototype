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
│   ├── use-case-AIS.md           <- Kontoinformationszugriff (AIS)
│   ├── use-case-PIS.md           <- Zahlungsauslösung (PIS)
│   ├── user-stories.md           <- User Stories (Endnutzer, TPP, Bank)
│   ├── requirements.md           <- API- und UX-Anforderungen
│   ├── api-spec-openapi.yaml     <- Technische OpenAPI-Spezifikation
│   └── standards-comparison.md   <- Vergleich gängiger Standards (NextGenPSD2, OpenWealth, Swiss OB)
|
├── /prototype
│   ├── screens-ais.png
│   └── screens-pis.png
```

---

## Technologien
- **UX-Prototyping**: Axure RP
- **API-Spezifikation**: OpenAPI 3.0 (YAML)
- **Dokumentation**: Markdown

---

## Status
- [x] Mockup-Screens AIS & PIS
- [ ] User Stories
- [ ] API Definition (OpenAPI)
- [ ] Use Cases
- [ ] Standardvergleich
- [ ] README finalisieren

---

## Use Case: Account Information Service (AIS)

### Ziel
Ein Drittanbieter (Third Party Provider, TPP) möchte nach Zustimmung des Kunden auf dessen Kontoinformationen bei einer Bank zugreifen. Dies erfolgt über ein standardisiertes Open-Banking-Interface.

### Beteiligte Akteure
- **Kunde**: Eigentümer des Bankkontos, gibt Zustimmung
- **TPP (Drittanbieter)**: Möchte Kontoinformationen für Finanzanalyse, Budgeting etc. abrufen
- **Bank (ASPSP)**: Authentifiziert den Kunden und stellt die Kontodaten über API bereit

### Ablauf (vereinfachter UX-Flow)
1. Der Kunde wählt innerhalb der TPP-Anwendung „Bankkonto verbinden“
2. Auswahl der Bank (z. B. „Bank AG“)
3. 3. Weiterleitung zur Bank (Redirect mit OAuth2-Flow)
4. Login bei Bank (2-Faktor möglich)
5. Anzeige der Konten, Auswahl und Autorisierung durch den Kunden
6. Rückleitung zur TPP
7. Zugriff auf /accounts-Endpunkt durch TPP

### Sicherheitsmechanismen
- OAuth2 mit Access Tokens
- Konsent-ID und Zeitlimit für Zugriff
- 2FA durch Banksystem bei Authentifizierung

### Relevante API-Calls (gemäß NextGenPSD2 oder Swiss OB)
- `GET /accounts`
- `GET /accounts/{account-id}/transactions`
- `GET /consents/{consent-id}`

---

(Weitere Inhalte folgen als separate Module: User Stories, OpenAPI YAML usw.)

