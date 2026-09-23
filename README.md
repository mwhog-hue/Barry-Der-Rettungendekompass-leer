# BARRY – Der Rettungshundekompass

Offline-Anwendung für Organisation, Ausbildung, Trainingsdokumentation und Einsatzunterstützung einer Rettungshundestaffel.

## Diese Version: datenfrei für Testnutzer/Vertrieb

Diese `index.html` enthält **keine** Mitglieder-, Hunde- oder Termindaten Ihrer eigenen Staffel – die Ausbildungsinhalte (DRK-Module, Übungskatalog usw.) sind allgemeines Trainingswissen, keine Staffeldaten. Ein Gerät, auf dem diese Datei zum ersten Mal geöffnet wird, startet automatisch mit genau einem Zugang: Benutzername/Name **Admin**, Passwort **admin** (muss beim ersten Login geändert werden).

Für die Erstbefüllung neuer Nutzer gibt es zwei Wege, die sich kombinieren lassen:
- **Einzeln über die App**: Als Admin unter *Verwaltung → Personen/Hunde* anlegen.
- **Schnellstart per Tabelle**: Unter *Verwaltung → Datensicherung → „Schnellstart: Mitglieder & Hunde aus Tabelle"* eine CSV-Vorlage herunterladen, in Excel/Calc ausfüllen und direkt wieder einlesen – anders als der normale Import werden die Zeilen dabei zum Bestand **hinzugefügt**, nichts wird ersetzt. Alle so angelegten Personen erhalten das Startpasswort `start`.

## Nutzung

- **Im Browser öffnen:** `https://<benutzername>.github.io/<repository>/`
- **Als App installieren:**
  - Android/Chrome: Menü → „App installieren“
  - iPhone/Safari: Teilen → „Zum Home-Bildschirm“
  - Windows (Chrome/Edge): Installationssymbol in der Adressleiste
- Nach dem ersten Öffnen startet BARRY auch ohne Internetverbindung.

## Datenschutz

- Alle Daten bleiben **ausschließlich lokal im Browser des jeweiligen Geräts**.
- Dieses Repository enthält nur die Anwendung selbst, **keine Mitglieder-, Hunde- oder Termindaten**.
- Es gibt keinen automatischen Abgleich zwischen Geräten. Daten werden bewusst per Export/Import übertragen (Verwaltung → Datensicherung).

## Dateien

| Datei | Zweck |
|---|---|
| `index.html` | die komplette Anwendung |
| `manifest.webmanifest` | App-Name, Symbole, Startverhalten |
| `sw.js` | Offline-Start |
| `icon-*.png` | App-Symbole |
| `.nojekyll` | verhindert die Jekyll-Verarbeitung durch GitHub Pages |

## Update auf eine neue Version

1. `index.html` ersetzen.
2. In `sw.js` den Wert `CACHE_VERSION` erhöhen, z. B. `barry-1.8` → `barry-1.9`.
   Ohne diese Änderung zeigen bereits installierte Geräte weiterhin die alte Version.

## Gemeinsamer Datenaustausch

BARRY tauscht Team-Stammdaten im Format „RHS Exchange v2“ mit den eigenständigen Apps aus:
Einsatzprotokoll, RH-Flächensuchassistent, RH-Mantrailing-Assistent, RH-Trümmersuchassistent und Pfotenalltag (nur Empfang).
Der Austausch wird immer bewusst vom Benutzer ausgelöst.
