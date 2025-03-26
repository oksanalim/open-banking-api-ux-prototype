**Anforderungsdokument – Open Banking API UX-Prototyp (AIS & PIS)**

---

###  1. Funktionale Anforderungen

#### 1.1 **Account Information Service (AIS)**
- Das System muss es ermöglichen, dass Drittanbieter (TPP) mit Einwilligung des Nutzers Zugriff auf Kontoinformationen erhalten.
- Der Endnutzer soll über eine Benutzeroberfläche:
  - eine Bank auswählen,
  - sich authentifizieren,
  - die Datenfreigabe bestätigen.
- Nach Zustimmung muss der Drittanbieter Zugriff auf folgende Daten erhalten:
  - IBAN, Kontoinhaber
  - Kontostand(e)
  - Transaktionshistorie (letzte 90 Tage)

#### 1.2 **Payment Initiation Service (PIS)**
- Der Endnutzer soll eine Zahlung anstoßen können, die über den Drittanbieter an die Bank übermittelt wird.
- Der Endnutzer muss folgende Daten eingeben:
  - Empfängername, IBAN, Betrag, Währung
- Nach Authentifizierung und Bestätigung wird die Zahlung ausgelöst.
- Eine Bestätigung über den Erfolg der Zahlung wird dem Nutzer angezeigt.

---

###  2. Nicht-funktionale Anforderungen

#### 2.1 **Sicherheit**
- Authentifizierung erfolgt mittels Zwei-Faktor-Login (z. B. Passwort + SMS-TAN).
- Autorisierung durch den Nutzer ist Voraussetzung für jede Daten- oder Zahlungstransaktion.
- Alle API-Kommunikation muss über TLS 1.2+ verschlüsselt sein.

#### 2.2 **Benutzerfreundlichkeit (UX)**
- Die Benutzeroberfläche muss intuitiv sein und den Nutzer schrittweise durch den Prozess führen.
- Feedback (Erfolg / Fehler) muss klar, verständlich und zeitnah erfolgen.
- Mobile-First Design wird bevorzugt, responsives Layout erforderlich.

#### 2.3 **Performance**
- Antwortzeit der API-Aufrufe muss unter 1 Sekunde liegen (im Schnitt).
- Login- und Zustimmungsschritte sollen je unter 5 Sekunden dauern (Client-seitig).

#### 2.4 **Kompatibilität**
- Das Frontend muss auf modernen Browsern (Chrome, Firefox, Safari, Edge) funktionieren.
- Die API-Schnittstelle orientiert sich an **OpenAPI 3.0** und **NextGenPSD2**.

#### 2.5 **Standardisierung & Interoperabilität**
- Die API-Spezifikation soll mit gängigen Open-Banking-Standards kompatibel sein:
  - NextGenPSD2 (Berlin Group)
  - Swiss Open Banking
  - OpenWealth (wenn relevant)

---

###  3. Offene Punkte / To-Do

- Noch offen: Implementierung konkreter API-Testfälle mit Postman / Newman
- Optional: Integration eines Mock-Servers zur Simulation von AIS- / PIS-Calls
- Erweiterbar um: Error States, Session Timeouts, Retry-Mechanismen

