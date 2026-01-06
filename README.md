<h1 align="center">🦖 Palworld Dedicated Server based on (SteamCMD)</h1>

<p align="center">
  A Home Assistant OS add-on to run a fully host-based Palworld Dedicated Server using SteamCMD.
</p>

---

## 🚀 Overview

This add-on runs a **Palworld Dedicated Server** on **Home Assistant OS**.

All data is stored **entirely on the host** under `/share`, including:

- SteamCMD
- Palworld server files
- Configuration
- Savegames

Everything can be managed easily via **Samba** or the **File Editor**.

---

## 📁 Directory Structure

**Main configuration file:**

/share/palworld/config/PalWorldSettings.ini

---

## ⚙️ Configuration

### PalWorldSettings.ini
- Automatically created on **first start**
- Can be **freely edited**
- Is **never overwritten**, even during updates

### Apply changes
1. Stop the add-on
2. Edit `PalWorldSettings.ini`
3. Start the add-on

---

## 🌐 Network / Ports

Internal server ports:

| Purpose     | Port  | Protocol |
|------------|-------|----------|
| Game Port  | 8211  | UDP      |
| Query Port | 27015 | UDP      |

External ports can be configured in the Home Assistant add-on **Network** section  
(e.g. for port forwarding or multiple servers).

---

## 🔄 Updates (SteamCMD)

If enabled:

```yaml
update_on_boot: true
On every start or restart:

The Palworld server is automatically updated

The installation is validated (validate)

Configuration and savegames remain untouched

Disable updates:

update_on_boot: false
💾 Savegames
Savegames are stored at:

swift
Code kopieren
/share/palworld/server/Pal/Saved/
They persist across:

Restarts

Updates

Add-on rebuilds

🛠️ Troubleshooting
Changes do not apply
The add-on was not restarted

The wrong PalWorldSettings.ini file was edited

New Palworld version adds options
Simply add new options manually to the INI file

Unknown or deprecated options are ignored by the server

✅ Why this Add-on?
SteamCMD fully stored on the host

Full control over server & configuration

No Home Assistant schema limitations

Update-safe by design

Perfect for Samba & File Editor

Multiple servers supported

📜 License & Disclaimer
This project is not affiliated with or endorsed by Pocketpair.
Palworld is a trademark of its respective owners.
