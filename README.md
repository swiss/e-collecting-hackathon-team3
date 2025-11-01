# 3) Update_CH

Pitch : [Google Drive](https://docs.google.com/presentation/d/1nnjI3S2vm0zWIGJR33QyXo3_bb9VwULtzKTLTMF0CZo/edit?usp=sharing) / [Github](https://github.com/swiss/e-collecting-hackathon-team3/blob/main/Hackathon%20Team%203.pdf)



Ausgangslage: *[Beta E-Collecting](https://beta.ecollecting.ch) Das Pilotprojekt startete im Dezember 2024. Es will das Sammeln von Unterschriften für Volksbegehren vertraulich, barrierefrei und mehrheitsfähig machen – als Ergänzung zum Papier. Dieser Pilot testet eine mögliche Variante von E-Collecting mittels der Beta-ID des Bundes. Hinter dem nicht profitorientierten Projekt stehen der Digital Democracy Hub Schweiz und die Stiftung für direkte Demokratie.*

## Kernidee und Ausgangspunkt

Am Hackathon wollen wir das [Pilotprojekt](https://beta.ecollecting.ch/de/stimmregister) mit Fokus auf Vertraulichkeit ausbauen.

Unser System ermöglicht das digitale Sammeln von Unterschriften für Volksbegehren unter Nutzung der swiyu E-ID zur Authentisierung. Die Kernprinzipien sind:

-   **Totale Transparenz**: Alle Beteiligten können jederzeit den Sammelstatus auf dem öffentlichen Board prüfen
-   **Maximale Sicherheit**: Kryptografische Verankerung statt Handschrift
-   **Privacy-by-Design**: Anonyme Unterschriften via «Berechtigungen zur Willensbekundung» und der Veröffentlichung von anonymen Beweisen.
-   **Föderale Souveränität**: Gemeinden behalten ihre autonome Rolle bei der Bescheinigung resp. dem Führen des Stimmregisters

## 1. Zielsetzung für den Hackathon

| Topic | Titel | Beschreibung |
| -- | --- | ------- |
| [**Topic 1**](https://github.com/swiss/e-collecting-hackathon-team3/issues/4) | Vom Unterstützungswillen zur Unterstützungsbekundung | Benutzer:in wählt Volksbegehren in App aus und leistet Unterschrift. Strassensammlung mit QR-Code, der auf App und Begehren verweist. Online-Sammlung per URL. |
| [**Topic 2**](https://github.com/swiss/e-collecting-hackathon-team3/issues/5) | Zugang zu aktuellen Informationen über die eingereichten Unterstützungsbekundungen | In öffentlichem Board können geleistete Willensbekundungen (Beweise) gezählt werden. Durch Verwendung des selben Credential-Paares (zur Unterschrift durch Gemeinde und Person) lassen sich doppelte Unterschriften ausschliessen. Beweise lassen sich auf die generierende Amtstelle (der Berechgigung) zurückführen. Die Informationen stehen allen öffentlich zur Verfügung. Das Stimmgeheimnis ist technisch gewährleistet (siehe Topic 7). Durch die gleichwertige Nutzung eigener Geräte ist die Anonymität und Barrierefreiheit auch für Menschen mit Behinderung gewährleistet. |
| [**Topic 3**](https://github.com/swiss/e-collecting-hackathon-team3/issues/3) | Zuschreibung der Unterstützungsbekundungen an Komitees und Sammelunternehmen | Bei der Wahrnehmung der «Berechtigung zur Willensbekundung» (für ein Referendum; Beweis) kann dieser einem Komitee zugewiesen werden. Diese Information wird auch veröffentlicht. |
| [**Topic 4**](https://github.com/swiss/e-collecting-hackathon-team3/issues/7) | Unterbreitung von Argumenten der Komitees via E-Collecting | Jedes Komitee gibt bei Ergreifen des Referendumg oder der Lancierung einer Initiative einen definierten Text zum Volksbegehren an. Dieser wird nach der Pürfung im öffentlichen Board veröffentlicht und bei der Unterzeichnung angezeigt. |
| [**Topic 5**](https://github.com/swiss/e-collecting-hackathon-team3/issues/8) | Ausschluss unrechtmässiger Unterstützungsbekundungen | Durch Verwendung von «Berechtigungen zur Willensbekundung», die auf dem Stimmregister basieren. Durch Opt-In zum digitalen Unterzeichnen wird ein Opt-Out für papierbasierte Unterschriften ausgelöst. Dies gewährleistet, dass pro Volksbegehren nur eine digitale oder handschriftliche Unterschrift eingereicht werden kann. Durch mathematische Beweise ist die Überprüfbarkeit (auch für gerichtliche Belange) gewährleistet. |
| [**Topic 6**](https://github.com/swiss/e-collecting-hackathon-team3/issues/9) | Verhinderung unterschlagener Unterstützungsbekundungen | Durch die Veröffentlichung der Willensbekundung und die Möglichkeit zur Prüfung der Willensbekundung im Board (sowie der Nachzählung) ist eine vollständige Erfassung aller Willensbekundungen gewärhleistet. |
| [**Topic 7**](https://github.com/swiss/e-collecting-hackathon-team3/issues/10) | Wahrung des Stimmgeheimnisses | Privacy-by-Design durch Ausstellung von «Berechtigungen zur Willensbekundung», die anonym wahrgenommen werden können (entspricht Stufe 2 im Whitepaper, erweiterbar auf Stufe 3 durch Veröffentlichung aller Berechtigungen einer Gemeinde zu einem Begehren in einer Datei resp. Verwendung eines Mixnets). |
| [**Topic 8**](https://github.com/swiss/e-collecting-hackathon-team3/issues/11) | Integration mit dem papierbasierten Prozess | Beide Prozesse funktionieren parallel. Ausschluss von doppelten Unterschriften durch Verwendung des selben Credential-Paares (zur Unterschrift durch Gemeinde und Person). Damit wird eine doppelte Unterschrift nur einmal gezählt. |
| [**Topic 9**](https://github.com/swiss/e-collecting-hackathon-team3/issues/12) | Erleichterte Einführung für Gemeinden mit Effizienzgewinn; auf der Grundlage von bestehender Infrastruktur und bestehenden Prozessen | Wegfallen der Beglaubigung für geleistete digitale Willensbekundungen. Digitaler Prozess setzt auf bestehendem Stimmregister auf (keine zusätzliche zentralisierung der Stimmregister nötig; werden aber unterstützt). Nur zusätzliche Software/Erweiterung für Initialisierung der Kryptographie und Erstellung/Veröffentlichung der «Berechtigungen für Willensbekundung» nötig. Im einfachsten Fall (Fast Track) kann mit Import/Export gearbeitet werden. |
| [**Topic 10**](https://github.com/swiss/e-collecting-hackathon-team3/issues/13) | E-Collecting für alle föderalen Ebenen | Kann problemlos und individuell pro Gemeinde, Kanton oder Bund eingeführt werden. Allenfalls sogar pro Begehren. |

### Flussdiagramm 

<img src="https://github.com/swiss/e-collecting-hackathon-team3/blob/main/vision/diagram.png" />


### Schlusspräsentation

[Schlusspräsentation als PDF](docs/schlusspraesentation.pdf)

## Team Members

- [Sandro Scalco](https://github.com/sansan88) - Digital Democracy Hub Schweiz
- Daniel Graf - Stiftung für direkte Demokratie
- [David Buchmann](https://github.com/dbu/) - Liip AG
- [Maximilian Rietschel](https://github.com/romtecmax)
- [Erik Schönenberger](https://github.com/datenreisen)
- Lucian Butera

## License

This software is licensed under a EUPL 1.2 License - see the [LICENSE](LICENSE) file for details. All concepts and documents (markdown files) are licensed under CC BY-SA 4.0.
