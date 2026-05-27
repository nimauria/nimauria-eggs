Uptime Kuma Egg

A custom Pterodactyl egg for deploying and managing Uptime Kuma through Nimauria Hosting.


---

Features

Automatic installation of Uptime Kuma from the official Git repository

Supports Node.js 20 and Node.js 22 yolks

Automatic update support during startup

Uses system and Wings timezone configuration

Clean process handling using exec

Simplified deployment and maintenance

Persistent Uptime Kuma data storage

Compatible with standard Pterodactyl allocations and networking

Designed for long-term maintainability and clean deployments



---

Official Repository

Official Uptime Kuma repository:

https://github.com/louislam/uptime-kuma


---

Supported Docker Images

ghcr.io/ptero-eggs/yolks:nodejs_22
ghcr.io/ptero-eggs/yolks:nodejs_20


---

Startup Command

export TZ="${TZ:-Europe/London}"; export NODE_ENV="{{NODE_ENV}}"; cd /home/container; if [[ -d .git ]] && [[ "{{AUTO_UPDATE}}" == "true" ]]; then npm run setup; fi; exec /usr/local/bin/node /home/container/{{JS_FILE}} --port={{SERVER_PORT}}


---

Variables

Auto Update

Automatically updates Uptime Kuma during startup.

Variable	Default

AUTO_UPDATE	true



---

Node Environment

Sets the Node.js runtime environment.

Variable	Default

NODE_ENV	production



---

Git Repository

Repository used for installation.

Variable	Default

GIT_ADDRESS	https://github.com/louislam/uptime-kuma



---

Server JS File

Main startup file.

Variable	Default

JS_FILE	server/server.js



---

Notes

Timezone handling is inherited from the host and Wings configuration.

Existing Uptime Kuma data can be preserved during egg migration by backing up the data/ directory.

Recommended for self-hosted monitoring, service status pages, and internal infrastructure monitoring.

Designed for compatibility with modern Pterodactyl Wings deployments.



---

Nimauria Hosting

https://hosting.nimauria.co.uk


---

Created By

Nimauria Hosting
