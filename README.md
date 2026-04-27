# CQ Regulatory Viewer — Akeneo Custom Component

Eine Akeneo Custom Component, die direkt auf der Produktseite die **regulatorische Dokumentation** aus dem CQ Regulatory DMS anzeigt. Sie gibt Produktteams und Einkäufern einen sofortigen Überblick über Freigabestatus, INCI-Deklaration, CPNP-Notifizierung und alle zugehörigen Dokumente — ohne das PIM zu verlassen.

---

## Was die Extension macht

- Zeigt **Freigabestatus** und regulatorische Kennzeichnungen (CPNP notifiziert, Schreibgeschützt, etc.)
- **Rezeptur & INCI-Deklaration** mit Hervorhebung der Funktionswirkstoffe
- **Freigabekette** mit allen Schritten (Rohstoff-Compliance, Safety Assessment, CPNP, etc.)
- **Dokumentenliste** (Safety Assessment Report, Stabilitätsprüfung, LUCID, etc.)
- **Tests & Studien** (SPF, dermatologische Verträglichkeit, Wirksamkeit)
- Live-Sync-Indikator zur Anzeige der letzten Synchronisation mit CQ

---

## Einrichtung in Akeneo PIM

### 1. GitHub Pages aktivieren (einmalig)

1. Dieses Repository öffnen → **Settings** → **Pages**
2. Unter *Branch* → `main` auswählen → **Save**
3. Nach 1–2 Minuten ist die Extension erreichbar unter:
   ```
   https://arkadius-skupien.github.io/cura-cq-cc/
   ```

### 2. Custom Component in Akeneo anlegen

1. Im PIM: **Einstellungen → Custom Apps / Extensions → Neu**
2. Folgende URL eintragen:

   ```
   https://arkadius-skupien.github.io/cura-cq-cc/?sku={{product_identifier}}&productName={{product_label}}
   ```

3. Speichern — die Extension erscheint nun auf jeder Produktseite.

> **Hinweis:** `{{product_identifier}}` und `{{product_label}}` sind Platzhalter, die Akeneo beim Öffnen automatisch befüllt.

---

## URL-Parameter

| Parameter | Pflicht | Beschreibung |
|---|---|---|
| `sku` | Empfohlen | Produkt-Identifier (SKU), z. B. `JW-81211018` |
| `product_identifier` | Alternativ zu `sku` | Alias für `sku` |
| `productName` | Empfohlen | Produktbezeichnung, z. B. `Vitamin C+ Fluid LSF 50` |

Ohne Parameter zeigt die Extension Demo-Daten für das Beispielprodukt `JW-81211018`.

---

## Lokale Vorschau

Einfach `index.html` im Browser öffnen. Mit Parametern testen:
```
index.html?sku=MEIN-SKU&productName=Mein+Produktname
```

---

## Technische Details

- **Keine Build-Tools** — eine einzige `index.html`, keine externen Abhängigkeiten
- **Kein PIM-API-Zugriff** — Daten werden aus dem CQ Regulatory DMS synchronisiert (in dieser Version als Demo dargestellt)
- **Kompatibel mit:** Akeneo PIM Growth, Additional, Enterprise (alle Versionen mit Custom Components)
- **Sprache:** Deutsch (DE)
