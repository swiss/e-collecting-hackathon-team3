# E-Collecting Zielbild «Vertraulich, Barrierefrei, Mehrheitsfähig»


```mermaid
---
config:
  layout: dagre
---
flowchart TD
 subgraph col1["Benutzer:in"]
        A["Bürger:in entscheidet sich<br>für E-Collecting"]
        n1["Installation der App<br>Authentifizierung der Benutzer:in<br>Initialisierung der Krypto<br>Opt-In für E-Collecting<br>Opt-Out für Papierprozess"]
        n8["Benutzer:in wählt<br>Volksbegehren zur<br>Unterzeichnung aus"]
        n16["Download der Berechtigung<br>für Willensbekundung und<br>Verwendung zur Unterschrift"]
        n9["Download der Berechtigung<br>für Willensbekundung und<br>Verwendung zur Unterschrift"]
  end
 subgraph col2["Stimmrechtsregister"]
        n2["Initialisierung der Krypto<br>Opt-In für E-Collecting<br>Opt-Out für Papierprozess"]
        n6["Generierung der Berechtigungen<br>für Willensbekundung<br>(Pro Begehren und Individuum)"]
  end
 subgraph col3["Komitee"]
        D["Lancierung Initiative<br>Ergreifung Referendum"]
  end
 subgraph col4["Öffentliches Board"]
        n7["Veröffentlichung der<br>Berechtigungen für<br>Willensbekundung"]
        n10["Veröffentlichung der<br>anonymen, beglaubigten<br>Unterschrift"]
  end
 subgraph col5["Amtsstelle"]
        n12["Auszählen der Stimmen<br>aus dem Board"]
  end
 subgraph col6["Öffentlichkeit / Individuen"]
        n14["Auszählen der Stimmen<br>aus dem Board"]
  end
    A --> n1
    n1 --> n2
    D --> n6
    n6 --> n7
    n7 --> n16
    n8 --> n16
    n16 --> n9
    n9 --> n10
    n10 --> n12 & n14


```
vision © is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)







```mermaid
---
config:
  theme: redux
  layout: fixed
---
flowchart TD
    A["Bürger:in entscheidet sich für E-Collecting"] --> n1["Installation der App<br>Authentifizierung der Benutzer:in<br>Initialisierung der Krypto<br>Opt-In für E-Collecting"]
    n1 --> n2["Initialisierung der Krypto<br>Opt-In für E-Collecting"]
    n6["Generierung der Berechtigungen für Willensbekundung<br>(Täglich, pro Individuum)"] --> n7["Veröffentlichung der Berechtigungen für Willensbekundung"]
    n7 --> n16["Download der Berechtigung für Willensbekundung, Verwendung zur Unterschrift und Zuweisung zu Komitee (freiwillig)"]
    n10["Veröffentlichung der anonymen, beglaubigten Willensbekundung (Beweis)"] --> n12["Zählen der Unterschriften aus dem Board"] & n14@{ label: "Zählen der <span style=\"padding-left:\">Unterschriften</span> aus dem Board" } & n19@{ label: "Auszählen der <span style=\"padding-left:\">Unterschriften</span> aus dem Board und Feststellen Zusstanekommen/Nicht-Zustandekommen" } & n20["Prüfen der Unterschrift auf dem Board"]
    n8["Benutzer:in wählt Volksbegehren zur Unterzeichnung aus"] --> n16
    n17["Lancierung Initiative<br>Ergreifung Referendum"] --> n18["Prüfung der Volksbegehren"]
    n18 --> D["Veröffentlichung der Volksbegehren"]
    D --> n8
    n16 --> n10
    n2 --> n6
    n3["Benutzer:in"]
    n4["Stimmrechtsregister"]
    n5["Öffentliches Board <br>"]
    n11["Amtsstelle <br>"]
    n13["Öffentlichkeit / Idividuen"]
    n15["Komitee"]
    A@{ shape: rect}
    n1@{ shape: rect}
    n2@{ shape: rect}
    n6@{ shape: rect}
    n7@{ shape: rect}
    n16@{ shape: rect}
    n10@{ shape: rect}
    n12@{ shape: rect}
    n14@{ shape: rect}
    n19@{ shape: rect}
    n20@{ shape: rect}
    n8@{ shape: rect}
    n17@{ shape: rect}
    n18@{ shape: rect}
    n3@{ shape: text}
    n4@{ shape: text}
    n5@{ shape: text}
    n11@{ shape: text}
    n13@{ shape: text}
    n15@{ shape: text}
    style n3 color:#000000
    style n4 color:#000000
    style n5 color:#000000
    style n11 color:#000000
    style n13 color:#000000
    style n15 color:#000000
```
vision © is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
