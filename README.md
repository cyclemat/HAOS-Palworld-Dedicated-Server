<h1 align="center">🦖 Palworld Dedicated Server (SteamCMD)</h1>
<p align="center">
  <img src="https://img.shields.io/badge/Home%20Assistant-OS-blue?logo=homeassistant">
  <img src="https://img.shields.io/badge/Architecture-amd64-success">
  <img src="https://img.shields.io/badge/SteamCMD-Enabled-informational">
  <img src="https://img.shields.io/badge/Status-Stable-success">
</p>

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

```text
/share/palworld/
├── steam/                # SteamCMD, cache and downloads
├── server/               # Palworld server files
├── config/
│   └── PalWorldSettings.ini   # Main server configuration
├── saves/                # Savegames
└── logs/                 # Server logs
Main configuration file:

text
Code kopieren
/share/palworld/config/PalWorldSettings.ini
⚙️ Configuration
PalWorldSettings.ini
Automatically created on first start

Can be freely edited

Is never overwritten, even during updates

Apply configuration changes
Stop the add-on

Edit PalWorldSettings.ini

Start the add-on again

🌐 Network / Ports
Internal server ports:

Purpose	Port	Protocol
Game Port	8211	UDP
Query Port	27015	UDP

External ports can be configured in the Home Assistant add-on Network section
(e.g. for port forwarding or running multiple servers).

🔄 Updates (SteamCMD)
If enabled in the add-on configuration:

yaml
Code kopieren
update_on_boot: true
On every start or restart:

The Palworld server is automatically updated

The installation is validated (validate)

Configuration and savegames remain untouched

Disable updates
yaml
Code kopieren
update_on_boot: false
💾 Savegames
Savegames are stored at:

text
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

🛠️ Installation (Home Assistant OS)
This add-on is installed as a local Home Assistant add-on via Git.

📌 Prerequisites
Home Assistant OS

SSH or Terminal access enabled

Samba Share (optional, for file editing)

📥 Step 1 – Clone the Repository
bash
Code kopieren
cd /addons/local
git clone https://github.com/<YOUR_GITHUB_USERNAME>/palworld_steamcmd_server.git
⚠️ Make sure the folder name matches the add-on slug.

📦 Step 2 – Refresh the Add-on Store
Open Home Assistant

Go to Settings → Add-ons

Click Add-on Store

Open the ⋮ menu (top right)

Select Check for updates

➡️ The add-on Palworld Dedicated Server (SteamCMD) will now appear under Local Add-ons.

▶️ Step 3 – Install & Start
Open the add-on

Click Install

Start the add-on once to generate default files

Stop the add-on again

⚙️ Step 4 – Configure the Server
text
Code kopieren
/share/palworld/config/PalWorldSettings.ini
Edit the file, save it, then start the add-on again.

🎮 Step 5 – Connect to the Server
Game Port: 8211/UDP

Query Port: 27015/UDP

Make sure ports are forwarded if the server should be reachable from the internet.

🔄 Updating the Add-on
bash
Code kopieren
cd /addons/local/palworld_steamcmd_server
git pull
Refresh the Add-on Store and restart the add-on.

🧠 Notes
Server updates are handled automatically by SteamCMD

Configuration and savegames are stored under /share

Updates will not overwrite your settings

📜 License & Disclaimer
This project is not affiliated with or endorsed by Pocketpair.
Palworld is a trademark of its respective owners.


This project is developed and maintained in my free time.
If it helps you and you like my work, I would be very happy about a small donation via PayPal to support further development.
Paypal: CyCleMat@googlemail.com
