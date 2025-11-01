# E-Collecting Zielbild «Vertraulich, Barrierefrei, Mehrheitsfähig»


```mermaid

flowchart TD
    Start([Start: Bürger:in entscheidet sich]) --> Install[App installieren & authentifizieren]
    Install --> InitCrypto[Krypto-Initialisierung im Register]
    InitCrypto --> OptIn{Opt-In für<br/>E-Collecting?}
    OptIn -->|Ja| Registered[Registrierung abgeschlossen]
    OptIn -->|Nein| PaperProcess[Papierprozess]
    
    Komitee([Komitee startet Initiative]) --> Launch[Initiative/Referendum lancieren]
    Launch --> GenAuth[Register: Berechtigungen generieren]
    GenAuth --> PubAuth[Board: Berechtigungen veröffentlichen]
    
    Registered --> Wait[Warten auf verfügbare Initiativen]
    PubAuth --> Wait
    Wait --> Select[Volksbegehren zur Unterzeichnung auswählen]
    Select --> Download[Berechtigung downloaden]
    Download --> Sign[Anonyme, beglaubigte Unterschrift erstellen]
    Sign --> Publish[Unterschrift auf Board veröffentlichen]
    
    Publish --> Count{Auszählung}
    Count -->|Amtsstelle| OfficialCount[Offizielle Auszählung]
    Count -->|Öffentlichkeit| PublicVerify[Unabhängige Verifikation]
    
    OfficialCount --> Result[Ergebnis veröffentlichen]
    PublicVerify --> Result
    Result --> End([Ende: Prozess abgeschlossen])
    
    style Start fill:#e3f2fd
    style Komitee fill:#e3f2fd
    style End fill:#c8e6c9
    style OptIn fill:#fff9c4
    style Count fill:#fff9c4
    style Result fill:#c8e6c9
    style PaperProcess fill:#ffccbc

```
vision © is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
