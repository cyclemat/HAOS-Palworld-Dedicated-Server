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

.

🛠️ Installation (Home Assistant OS)

This add-on is installed as a local Home Assistant add-on via Git.

📌 Prerequisites

Home Assistant OS

SSH or Terminal access enabled

Samba Share (optional, for file editing)

📥 Step 1 – Clone the Repository

Open the Home Assistant Terminal / SSH and run:

cd /addons/local
git clone https://github.com/<YOUR_GITHUB_USERNAME>/palworld_steamcmd_server.git


⚠️ Make sure the folder name matches the add-on slug.

📦 Step 2 – Refresh the Add-on Store

Open Home Assistant

Go to Settings → Add-ons

Click “Add-on Store”

Click the ⋮ menu (top right)

Select “Check for updates”

➡️ The add-on Palworld Dedicated Server (SteamCMD) will now appear under Local Add-ons.

▶️ Step 3 – Install & Start

Open the add-on

Click Install

Start the add-on once to generate default files

Stop the add-on again

⚙️ Step 4 – Configure the Server

Edit the configuration file:

/share/palworld/config/PalWorldSettings.ini


(using Samba or the File Editor add-on)

After editing:

Save the file

Start the add-on again

🎮 Step 5 – Connect to the Server

Game Port: 8211/UDP

Query Port: 27015/UDP

Make sure ports are forwarded if the server should be reachable from the internet.

🔄 Updating the Add-on

To update the add-on itself:

cd /addons/local/palworld_steamcmd_server
git pull


Then refresh the Add-on Store again and restart the add-on.

🧠 Notes

Server updates are handled automatically by SteamCMD

Configuration and savegames are stored under /share

Updates will not overwrite your settings

📜 License & Disclaimer
This project is not affiliated with or endorsed by Pocketpair.
Palworld is a trademark of its respective owners.
