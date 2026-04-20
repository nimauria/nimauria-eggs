# 🌊 Windrose – Dedicated Server (Nimauria Eggs)

Embark on a PvE survival adventure in the Age of Piracy. Fight on land and sea, solo or with friends. Build, craft, and explore a vast open world filled with dark secrets.

Master soulslike combat, command your ship, and plunder unspoken treasures.

Windrose is a co-op pirate survival game featuring exploration, base building, naval combat, and procedurally generated worlds. It supports both self-hosted and dedicated servers, allowing persistent multiplayer experiences.

---

## ⚙️ About This Egg

This egg installs and runs the **Windrose Dedicated Server** using SteamCMD and Wine.

### Features

* Automated installation via SteamCMD
* Windows server support through Wine
* Configurable server settings (JSON-based)
* Invite code system for easy access
* Optional password protection
* Optional Direct IP connection mode
* Optimised backup rules (`.pteroignore`)

---

## ⚠️ Important Notes

* Windrose does **not currently provide a native Linux server build**
* This egg runs the **Windows server via Wine**
* Server configuration is handled via:

  ```
  /home/container/R5/ServerDescription.json
  ```
* World data is stored in:

  ```
  /home/container/R5/Saved
  ```
* Invite code is the default connection method
* Direct IP is optional and may require manual network configuration

---

## 🧠 Server Requirements

| Players | RAM   | Storage   |
| ------- | ----- | --------- |
| 2       | 8 GB  | 32 GB SSD |
| 4       | 12 GB | 32 GB SSD |
| 10      | 16 GB | 32 GB SSD |

> SSD storage is strongly recommended for performance.

---

## 🔌 Connecting to the Server

### Method 1 — Invite Code (Recommended)

* Uses NAT punch-through
* No manual port forwarding required (in most cases)
* Invite code is located in:

  ```
  /home/container/R5/ServerDescription.json
  ```

### Method 2 — Direct Connect

* Connect using:

  ```
  IP:PORT
  ```
* Requires:

  * Port forwarding
  * Firewall configuration
  * Possibly disabling VPN/proxy

---

## 🌐 Server Ports

### Invite Code Mode

* Uses dynamic NAT punch-through (requires UPnP support)

### Direct Connect Mode

* Uses your allocated **Game Port** (default: `7777`)

---

## 🧪 Known Limitations

* No built-in admin commands currently
* Limited server-side control options
* Docker setups may be unreliable
* Performance may degrade with higher player counts
* Networking issues may occur depending on ISP or region

---

## 🚀 Installation Details

This egg:

* Downloads SteamCMD
* Installs Windrose using App ID: `4129620`
* Forces Windows platform install
* Sets up Steam libraries
* Creates backup optimisation rules

---

## 📁 Important Paths

**Server Config**

```
R5/ServerDescription.json
```

**Logs**

```
R5/Saved/Logs/
```

**World Data**

```
R5/Saved/SaveProfiles/
```

---

## 🔧 Key Variables

| Variable                        | Description            |
| ------------------------------- | ---------------------- |
| `SERVER_NAME`                   | Server display name    |
| `INVITE_CODE`                   | Join code (6–32 chars) |
| `MAX_PLAYERS`                   | Max player count       |
| `IS_PASSWORD_PROTECTED`         | Enable password        |
| `SERVER_PASSWORD`               | Server password        |
| `USE_DIRECT_CONNECTION`         | Enable direct IP       |
| `DIRECT_CONNECTION_SERVER_PORT` | Game port              |
| `WORLD_ISLAND_ID`               | World identifier       |

---

## 🧰 Troubleshooting

### Crashes / Illegal Instruction

If running in a VM:

* Set CPU type to:

  * `host`
  * `passthrough`

### Players Can’t Connect

Check:

* Invite code is correct
* Server is running
* VPN/proxy disabled
* UPnP enabled (invite mode)
* Ports forwarded (direct mode)

### Logs Not Appearing

Check:

```
R5/Saved/Logs/R5.log
```

---

## 📦 Backup Optimisation

This egg includes a `.pteroignore` file:

* Excludes unnecessary files
* Keeps essential world + config data
* Improves backup speed and size

---

## 🏗️ Part of Nimauria Eggs

**Nimauria Eggs**
Production-grade Pterodactyl egg collection built for consistency, reliability, and maintainability.

---

## 📜 License

MIT License — see `LICENSE` file.

---

## 💬 Notes

Windrose is in early access and server functionality is still evolving. Expect changes, improvements, and updates o
