# BootForge-Katalog

Der Distro-Katalog für [BootForge](https://github.com/xHellPhoenix/bootforge). Die App lädt beim Start

```
https://raw.githubusercontent.com/xHellPhoenix/bootforge-catalog/main/catalog.json
```

(nur über HTTPS). Ist das nicht möglich, nutzt sie den zuletzt geladenen Katalog aus dem Cache und
im Notfall die in die App eingebaute Kopie.

| Datei | Inhalt |
|---|---|
| `catalog.json` | Der Katalog: Distros, Varianten, wie die neueste Version gefunden wird, Prüfsummen, GPG-Schlüssel |
| `catalog.schema.json` | JSON-Schema (generiert aus dem App-Code, **nicht von Hand ändern**) |
| `FORMAT.md` | Beschreibung des Formats |

## Einen Eintrag ändern

1. `catalog.json` bearbeiten. Editoren wie VS Code prüfen dabei automatisch gegen das Schema.
2. Regeln beachten: nur HTTPS, jede Variante braucht eine Prüfsumme, GPG-Fingerprints nur aus
   offiziellen Quellen des Herstellers (siehe `FORMAT.md`).
3. `updated` auf das heutige Datum setzen.

> Ein fehlerhafter Katalog wird von der App komplett abgelehnt; sie fällt dann auf Cache bzw.
> eingebaute Kopie zurück. Kaputt machen kann man mit einem Tippfehler also nichts, aber die
> Änderung kommt auch nicht an.
