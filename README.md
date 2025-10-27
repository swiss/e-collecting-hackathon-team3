# 3) Update_CH

*[Beta E-Collecting](https://beta.ecollecting.ch) Das Pilotprojekt startete im Dezember 2024. Es will das Sammeln von Unterschriften für Volksbegehren digital, sicher und barrierefrei machen – als Ergänzung zum Papier. Dieser Pilot testet eine mögliche Variante von E-Collecting mittels der Beta-ID des Bundes. Hinter dem nicht profitorientierten Projekt stehen der Digital Democracy Hub Schweiz und die Stiftung für direkte Demokratie.*

## Approach

**Kernidee und Ausgangspunkt:**

Am Hackathon möchten wir das [Pilotprojekt](https://beta.ecollecting.ch/de/stimmregister) mit Fokus auf  Stimmregister-Nachweis für anonyme Willensbekundungen weiterentwickeln. 

Unser System ermöglicht das digitale Sammeln von Unterschriften für Volksbegehren unter Nutzung der swiyu E-ID und Blockchain-Technologie. Die Kernprinzipien sind:

-   **Totale Transparenz**: Alle Beteiligten können jederzeit den Sammelstatus auf der öffentlichen Blockchain prüfen
-   **Maximale Sicherheit**: Kryptografische Verankerung statt Handschrift, kombiniert mit Hardware-Security-Modulen in den Gemeinden
-   **Privacy-by-Design**: Anonyme Unterschriften via Nullifier-Konzept -- keine personenbezogenen Daten on-chain
-   **Föderale Souveränität**: Gemeinden behalten ihre autonome Rolle bei der Bescheinigung

## 1. Zielsetzung
E-Collecting ermöglicht es Bürger:innen, mit Hilfe der SSI-basierten **swiyu E-ID App** ihre Stimmberechtigung nachzuweisen und Willensbekundungen **fälschungssicher, anonym und einmalig** für ein konkretes Volksbegehren abzugeben.

---
```mermaid
sequenceDiagram
    actor User as Bürger
    participant Portal as E-Collecting Portal
    participant Addr as Adressservice
    participant Gemeinde as Gemeinde System
    participant Wallet as Swiyu Wallet
    participant Issuer as Generic Issuer (Gemeinde)

    Note over User,Issuer: Phase 1: Adressübermittlung & Gemeindezuordnung
    
    User->>Portal: Möchte Stimmrechtsausweis beantragen
    Portal->>User: Fordert Wohnadresse an
    User->>Portal: Übermittelt Strasse, Hausnummer, PLZ, Ort
    Portal->>Addr: Validiert Adressdaten
    Addr->>Addr: Prüft Adresse & ermittelt BFS-Nummer
    Addr-->>Portal: Gibt BFS-Nummer zurück
    Portal->>Portal: Ermittelt zuständige Gemeinde
    
    Note over User,Issuer: Phase 2: Identifikation & Berechtigung
    
    Portal->>User: Zeigt QR-Code für Identifikation (OID4VP)
    User->>Wallet: Scannt QR-Code mit Swiyu Wallet
    Wallet->>Portal: Öffnet Verification Request
    Portal->>Wallet: Fordert Attribute an (Vorname, Nachname, Geburtsdatum, optional AHV-Nr.)
    User->>Wallet: Gibt Freigabe für Attribute
    Wallet->>Portal: Übermittelt selektierte Attribute (SD-JWT VC)
    Portal->>Gemeinde: Leitet Daten zur Prüfung weiter
    
    Gemeinde->>Gemeinde: Prüft Stimmberechtigung
    Gemeinde->>Gemeinde: Prüft Wohnsitz in Gemeinde
    
    alt Bürger ist stimmberechtigt
        Gemeinde-->>Portal: Berechtigung bestätigt
        
        Note over User,Issuer: Phase 3: Volksbegehren-Auswahl
        
        Portal->>User: Zeigt Liste verfügbarer Volksbegehren
        User->>Portal: Wählt Volksbegehren aus
        
        Note over User,Issuer: Phase 4: Credential-Ausstellung
        
        Portal->>Issuer: Fordert Stimmrechtsausweis-Credential an
        
        
        alt Stimmrechtsausweis ausstellen    
            Issuer->>Issuer: Erstellt Credential mit:<br/>- Nullifier (Bürger+Volksbegehren+Secret)<br/>- Ausstelldatum<br/>- Name Volksbegehren<br/>- Gültig bis (Laufzeit)<br/>- Amtsstelle (BFS-Nummer/DID)
            Issuer->>Issuer: Signiert Credential (ECDSA)
            Issuer->>Portal: Gibt Credential Offer zurück
            Portal->>User: Zeigt QR-Code (OID4VCI)
            User->>Wallet: Scannt QR-Code
            Wallet->>Issuer: Fordert Credential an (Authorization)
            Issuer->>Wallet: Stellt Stimmrechtsausweis aus (SD-JWT VC)
            Wallet->>Wallet: Speichert Credential sicher
            Wallet-->>User: Bestätigt Import des Stimmrechtsausweises
        else Stimmrechtsausweis nicht ausstellen
            Issuer-->>Portal: Anfrage für Stimmrechtsausweis-Credential ablehnen
            Portal-->>User: Zeigt Ablehnungsmeldung
        end


    else Bürger ist nicht stimmberechtigt
        Gemeinde-->>Portal: Berechtigung verweigert
        Portal-->>User: Zeigt Ablehnungsmeldung
    end
```
[Sequenzdigramm](https://github.com/Digital-Democracy-Hub-Schweiz/e-collecting-pilot/blob/main/Konzepte/Stimmrechtsausweis%20Sequenzdiagramm.md) © 2025 by [Digital Democracy Hub](https://digitaldemocracyhub.ch) is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)


## Developer Setup

### Commit Konventionen

Wir verwenden [conventionalcommits](https://www.conventionalcommits.org/en/) für unsere Commit-Nachrichten.

### Prettier & Husky

Folgen Sie der Anleitung für die Installation:

```bash
# Installation
npm install --save-dev husky prettier pretty-quick
npx husky init

# Pre-commit Hook in .husky/pre_commit konfigurieren
npx pretty-quick --staged

# This tells your system: "Hey, this file is a script that can be executed."
chmod +x .husky/pre-commit

# make some changes
git add .
git commit -m "your new message"
git push
```


## Contributing

Please read [CONTRIBUTING.md](/CONTRIBUTING.md) for details on our code of conduct.

## Team Members

- [Sandro Scalco](https://github.com/sansan88) - Digital Democracy Hub Schweiz
- Daniel Graf - Stiftung für direkte Demokratie
- [David Buchmann](https://github.com/dbu/) - Liip AG
- tba
- tba

## License

This software is licensed under a EUPL 1.2 License - see the [LICENSE](LICENSE) file for details. All concepts and documents (markdown files) are licensed under CC BY-SA 4.0.
