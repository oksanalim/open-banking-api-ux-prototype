
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


