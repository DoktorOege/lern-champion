# Lern-Champion

Lern-Web-App für das kleine 1×1 sowie Englisch- und Niederländisch-Vokabeln.
Live: https://1x1.kma-online.workers.dev

- `public/index.html` – die App
- `public/vokabeln.js` – alle Vokabel-Lektionen (`["Deutsch", "Fremdsprache"]`, Alternativen mit ` / `)
- `wrangler.jsonc` – Cloudflare-Worker `1x1` (nur statische Dateien)

Jeder Push auf `main` wird über Cloudflare Workers Builds automatisch veröffentlicht.
Nach jeder fertigen Lerneinheit schickt die App eine Zusammenfassung per ntfy.

## Ablauf für neue Vokabeln
Fotos → Eintrag in `public/vokabeln.js` → Push auf `main` → Cloudflare veröffentlicht automatisch.

## Updates in der App
Bei jedem Update `APP_VERSION` in `public/index.html` **und** `version` in `public/version.json` auf denselben neuen Wert setzen
(optional `note` = Text im Banner, z. B. „Neue Vokabeln: Unit 3“, und `VOC_STAND` anpassen).
Die App zeigt dann oben „🆕 … jetzt aktualisieren“.
