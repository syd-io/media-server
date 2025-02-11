# 🏠 Self-Hosted Media Server with Docker

This repository contains configurations for a self-hosted media server. It includes popular applications for downloading, managing, and streaming media, all running within Docker containers.

## 🚀 Features

- **VPN Protection**: All traffic is routed through `gluetun` for security.
- **BitTorrent & Usenet Support**: `qBittorrent` and `sabnzbd` for downloading media.
- **Automated Media Management**: `Radarr`, `Sonarr`, `Bazarr` for organizing movies, shows, and subtitles.
- **Indexers & Requests**: `Prowlarr` and `Overseerr` for finding and requesting content.
- **Plex Monitoring**: `Tautulli` for tracking usage stats.
- **UI Dashboard**: `Heimdall` for quick access to services.
- **Log Viewer**: `Dozzle` for monitoring Docker container logs.

## 🏗️ Installation

### 1️⃣ Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- A VPN provider supporting WireGuard/OpenVPN

### 2️⃣ Clone the Repository

```bash
git clone https://github.com/syd-io/media-server.git
cd media-server
```

### 3️⃣ Create an .env File
Copy the sample environment variables:

```bash
cp .env.example .env
```

Edit `.env` to match your setup:

```ini
PUID=1000
PGID=1000
TIMEZONE=Asia/Singapore
WEBUI_PORT_QBITTORRENT=8081
...
```

### 4️⃣ Start the Containers

```bash
docker compose up -d
```

### 5️⃣ Access the Services

Once the containers are running, you can access the services using the following URLs:

| Service       | Description              | URL                  |
|--------------|--------------------------|----------------------|
| **qBittorrent** | BitTorrent client      | http://localhost:8081 |
| **Radarr**     | Movie management       | http://localhost:7878 |
| **Sonarr**     | TV show management     | http://localhost:8989 |
| **Bazarr**     | Subtitle management    | http://localhost:6767 |
| **Heimdall**   | Dashboard for services | http://localhost:80   |
| **Overseerr**  | Media request manager  | http://localhost:5055 |
| **Tautulli**   | Plex monitoring        | http://localhost:8181 |
| **SABnzbd**    | Usenet downloader      | http://localhost:8080 |
| **Prowlarr**   | Indexer manager        | http://localhost:9696 |
| **Flaresolverr** | Captcha resolver    | No Web UI |
| **Recyclarr**  | Sonarr/Radarr sync tool | No Web UI             |
| **Dozzle**     | Docker log viewer      | http://localhost:8080 |

Replace `localhost` with your server's IP if accessing remotely.


## 🔧 Configuration
- Edit service configurations in the configs/ folder.
- Mount your media storage to /data inside containers.

## 🛠️ Maintenance
- View logs: `docker compose logs -f`
- Restart a service: `docker compose restart <service>`
- Stop all services: `docker compose down`

## 📜 License
This project is licensed under the MIT License.
