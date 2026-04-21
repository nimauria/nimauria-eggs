# 🏔️ The Lord of the Rings: Return to Moria — Pterodactyl Egg

A fully configured **Pterodactyl egg** for hosting a dedicated server for
**The Lord of the Rings: Return to Moria** using Wine.

This egg installs and runs the official Windows dedicated server build via SteamCMD, with configurable world settings and automatic log streaming.

---

## 📦 Features

* Automated installation via SteamCMD
* Supports **anonymous or authenticated Steam login**
* Runs Windows server build via **Wine**
* Real-time log output in Pterodactyl panel
* Fully configurable world generation & difficulty
* Optional auto-update system
* Optimised `.pteroignore` for faster backups

---

## ⚙️ Requirements

* Pterodactyl Panel (latest recommended)
* Wings node with Docker support
* Network access to Steam servers

**Docker Image:**
`ghcr.io/ptero-eggs/yolks:wine_latest`

---

## 🚀 Installation

1. Import the egg JSON into your Pterodactyl panel
2. Create a new server using this egg
3. Configure environment variables
4. Start the server — installation runs automatically

---

## 🔧 Configuration

The server is configured through `MoriaServerConfig.ini`, automatically updated using environment variables.

### 🌍 Core Settings

| Variable          | Description                       |
| ----------------- | --------------------------------- |
| WORLD_NAME        | Name of the world save            |
| SERVER_PASSWORD   | Optional password for joining     |
| WORLD_TYPE        | campaign or sandbox               |
| DIFFICULTY_PRESET | story, solo, normal, hard, custom |

---

### ⚔️ Custom Difficulty (preset = custom)

| Variable                   | Options            |
| -------------------------- | ------------------ |
| CUSTOM_COMBAT_DIFFICULTY   | verylow → veryhigh |
| CUSTOM_ENEMY_AGGRESSION    | verylow → veryhigh |
| CUSTOM_SURVIVAL_DIFFICULTY | verylow → veryhigh |
| CUSTOM_MINING_DROPS        | verylow → veryhigh |
| CUSTOM_WORLD_DROPS         | verylow → veryhigh |
| CUSTOM_HORDE_FREQUENCY     | verylow → veryhigh |
| CUSTOM_PATROL_FREQUENCY    | verylow → veryhigh |

---

### 🧩 DLC Options

| Variable             | Description                  |
| -------------------- | ---------------------------- |
| OPTIONAL_DLC         | Enable DLC on new worlds     |
| UPGRADE_OPTIONAL_DLC | Apply DLC to existing worlds |

---

### 🔄 Update Control

| Variable    | Description   |
| ----------- | ------------- |
| AUTO_UPDATE | true or false |

---

## 🖥️ Startup Behaviour

```bash
wine ./Moria/Binaries/Win64/MoriaServer-Win64-Shipping.exe -log
```

* Waits for log file creation
* Streams logs to panel
* Falls back gracefully if logs are missing

---

## 📁 File Structure

```
/mnt/server
├── Moria/
├── steamcmd/
├── steamapps/
├── .steam/
└── MoriaServerConfig.ini
```

---

## 🛠️ Installation Details

* Steam App ID: `3349480`
* Forces Windows platform via SteamCMD
* Installs required Steam libraries (`steamclient.so`)
* Wine compatibility via:

  ```
  WINETRICKS_RUN=vcrun2022
  ```

---

## ⚠️ Notes

* Requires Wine (no native Linux server available)
* First startup may take longer due to installation
* World settings apply only when generating a new world

---

## 🐛 Troubleshooting

### Server not starting

* Check console logs
* Ensure port 7777 is open
* Verify Docker image is available

### No logs appearing

* Wait up to 20 seconds for log creation
* Server will still run without log streaming

---

## 📜 License

Provided as-is. Game assets belong to their respective owners.

---

## ✨ Credits

* Author: Nimauria
* Platform: Pterodactyl Panel
