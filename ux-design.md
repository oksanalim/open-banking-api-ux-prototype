## **Axure-Struktur (Seitenübersicht & Komponenten)**

### **AIS – Kontoinformationen freigeben**

---

#### **1. Seite: Bankauswahl (AIS_1_BankAuswahl)**

**Komponenten:**
- Überschrift: „Bankkonto verbinden“
- Textfeld: „Bank suchen“
- Radiobuttons:
  - Bank AG
  - Bank B
  - Bank C
- Weiter-Button

---

#### **2. Seite: Login bei Bank AG (AIS_2_Login)**

**Komponenten:**
- Überschrift: „Melden Sie sich an“
- Textfeld: Benutzername
- Passwortfeld: Passwort
- Link: „Passwort vergessen?“
- Button: „Per SMS-Code“
- Weiter-Button

---

#### **3. Seite: Zustimmung (AIS_3_Zustimmung)**

**Komponenten:**
- Überschrift: „Kontozugriff freigeben“
- Textblock mit Dummy-Daten:
  - Anwendung: Drittanbieter-App
  - IBAN: DE12345678901234
- Buttons: „Zustimmen“ / „Abbrechen“

---

#### **4. Seite: Bestätigung (AIS_4_Bestaetigung)**

**Komponenten:**
- Text: „Ihr Konto wurde erfolgreich verbunden“
- Dummy-Kundennummer
- Button: „Fertig“

---

###  **PIS – Zahlung initiieren**

---

#### **5. Seite: Zahlung eingeben (PIS_1_Eingabe)**

**Komponenten:**
- Textfeld: Empfängername
- Textfeld: Betrag
- Dropdown: Währung (CHF, EUR, …)
- Button: „Weiter“

---

#### **6. Seite: Login (PIS_2_Login)**

**Identisch mit AIS_2_Login** – du kannst Seite duplizieren

---

#### **7. Seite: Zahlung freigeben (PIS_3_Freigabe)**

**Komponenten:**
- Überschrift: „Zahlung freigeben“
- Textblock mit Dummy-Daten:
  - Empfänger: Max Muster
  - IBAN: DE00123455752591000
  - Betrag: 50,00 EUR
- Buttons: „Bestätigen“ / „Abbrechen“

---

#### **8. Seite: Zahlung abgeschlossen (PIS_4_Abschluss)**

**Komponenten:**
- Text: „Ihre Zahlung wurde erfolgreich ausgeführt“
- Button: „Zurück zur Drittanbieter-App“

