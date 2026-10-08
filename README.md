# UniPop · Déclarations formateurs

Web-App (GitHub Pages, ohne Build-Schritt) mit Mensuel, Trimestriel, Tableau de bord und Formateurs.

## Installation / GitHub Pages

Lade **nur** `index.html`, `README.md` und `.gitignore` in das Repository hoch.

Unter **Settings → Pages → Deploy from a branch → main / root** aktivieren.

**Wichtig:** Die Datei `declarations-unipop-2026-2027.json` enthält personenbezogene Daten und Bearbeitungsstände. **Nicht ins öffentliche GitHub-Repository hochladen!** Sie wird lokal über „Ouvrir…“ in die App geladen.

## Automatische Aktualisierung

- Die App versucht bei jedem Start mit vorhandenem Datenstand, neue UniPop-Formateure aus `https://www.unipop.lu/private/trainings.json` zu laden.
- Bei einem neuen leeren Datenstand startet der Abruf ebenfalls automatisch.
- Während die App offen ist, wird höchstens einmal pro Stunde aktualisiert; bei erneuter Online-Verbindung wird erneut versucht.
- Es werden nur Datensätze mit `organisateur.code === "UNIPOP"` berücksichtigt.
- Bestehende Formateure, Bemerkungen, Monats-/Quartalsstatus und Zuordnungen werden **nicht** überschrieben oder gelöscht.
- Die Anzeige oben meldet Erfolg bzw. Fehler. Bei fehlgeschlagenem Abruf auf die Anzeige klicken, um die vorhandene manuelle JSON-Importfunktion zu verwenden.

### Wichtige technische Grenze

Wenn der UniPop-Server CORS für die GitHub-Pages-Domain nicht erlaubt, kann die Web-App den fremden JSON-Endpunkt nicht direkt lesen. Das lässt sich nicht allein durch JavaScript im Browser beheben. In diesem Fall bleibt der manuelle Import verfügbar. Für eine vollständig automatische Synchronisation auch bei gesperrtem CORS braucht es einen von UniPop freigegebenen CORS-Zugriff oder einen datenschutzkonformen Server-Endpunkt. Die App umgeht keine Zugriffsbeschränkungen.

## Speicherung

- Änderungen werden stets als lokale Browserkopie gesichert.
- Chrome/Edge können eine einmal gewählte Datei direkt automatisch speichern (bei erteilter Berechtigung).
- Firefox lädt beim Klick auf „Enregistrer“ eine JSON-Kopie herunter.
- Datenbestand unbedingt regelmäßig sichern; Browser-Speicher allein ist kein dauerhaftes Backup.
