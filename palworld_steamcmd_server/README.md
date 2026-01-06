# 🦖 Palworld Dedicated Server (SteamCMD) – Home Assistant Add-on

Dieses Add-on betreibt einen **Palworld Dedicated Server** unter **Home Assistant OS**.  
**SteamCMD, Serverdateien, Konfiguration und Savegames liegen vollständig auf dem Host** unter `/share` und sind jederzeit per **Samba** oder **File Editor** bearbeitbar.

---

## 📁 Verzeichnisstruktur

Alle Daten dieses Add-ons befinden sich unter:

```
/share/palworld/
├── steam/              # SteamCMD, Cache & Downloads
├── server/             # Palworld Serverdateien
├── config/
│   └── PalWorldSettings.ini
├── saves/              # Savegames
└── logs/               # Server-Logs
```

**Wichtige Konfigurationsdatei:**

```
/share/palworld/config/PalWorldSettings.ini
```

---

## ⚙️ Konfiguration

### PalWorldSettings.ini
- Wird beim **ersten Start automatisch erzeugt**
- Kann danach **frei angepasst** werden
- Wird **niemals überschrieben**, auch nicht bei Updates

### Änderungen übernehmen
1. Add-on **stoppen**
2. `PalWorldSettings.ini` bearbeiten
3. Add-on **starten**

---

## 🌐 Netzwerk / Ports

Der Server nutzt intern feste Ports:

| Zweck        | Port  | Protokoll |
|-------------|-------|-----------|
| Game Port   | 8211  | UDP       |
| Query Port | 27015 | UDP       |

**Externe Ports** werden im Add-on unter **„Netzwerk“** konfiguriert  
(z. B. bei Portweiterleitungen oder mehreren Servern).

---

## 🔄 Updates (SteamCMD)

Wenn in der Add-on-Konfiguration folgendes gesetzt ist:

```yaml
update_on_boot: true
```

wird bei **jedem Start oder Neustart**:

- der Palworld Server automatisch aktualisiert
- die Installation validiert (`validate`)
- die Konfiguration und Savegames bleiben unangetastet

### Updates deaktivieren
```yaml
update_on_boot: false
```

---

## 💾 Savegames

Savegames befinden sich unter:

```
/share/palworld/server/Pal/Saved/
```

Sie bleiben erhalten bei:
- Neustarts
- Updates
- Add-on-Neuinstallation

---

## 🛠️ Fehlerbehebung

### Änderungen greifen nicht
- Add-on wurde nicht neu gestartet
- Falsche `PalWorldSettings.ini` bearbeitet

### Neue Palworld-Version bringt neue Optionen
- Neue Optionen einfach manuell in die INI einfügen
- Unbekannte oder veraltete Optionen werden ignoriert

---

## ✅ Vorteile dieses Add-ons

- SteamCMD vollständig auf dem Host
- Volle Kontrolle über Server & Konfiguration
- Keine Home-Assistant-Schema-Limits
- Updatesicher
- Ideal für Samba & File Editor
- Mehrere Server parallel möglich

---

