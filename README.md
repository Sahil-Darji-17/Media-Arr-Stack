# 🎬 Self-Hosted Media Server Stack (Docker Desktop, Windows)

This is a fully self-hosted media server stack built using **Docker Desktop on Windows**. It lets you automate movie/TV show downloads, torrenting, metadata management, subtitle fetching, and streaming — all via a beautiful dashboard. Everything runs locally and is accessible via `localhost`.

---

## 📦 Services Included

| Service       | Port  | Purpose                                   |
|--------------|-------|-------------------------------------------|
| **Jellyfin**      | 8096  | Media streaming server                    |
| **Sonarr**        | 8989  | TV show automation                        |
| **Radarr**        | 7878  | Movie automation                          |
| **Transmission**  | 9091  | Torrent client                            |
| **Prowlarr**      | 9696  | Indexer manager                           |
| **Jackett**       | 9117  | Tracker proxy for torrent indexers        |
| **Bazarr**        | 6767  | Subtitles automation                      |
| **Jellyseerr**    | 5055  | Media request manager                     |
| **Flaresolverr**  | 8191  | Bypasses CAPTCHA for indexers             |
| **Homarr**        | 7575  | Beautiful unified dashboard               |

---

## 🖥 System Requirements

- **OS**: Windows 10/11
- **Docker Desktop**: Installed and running  
- **Hardware**:  
  - CPU: Dual-core or better  
  - RAM: 4 GB minimum (8 GB recommended)  
  - Disk: 20+ GB free space  

---



installation Steps:-

1. Install Docker Desktop

    Download from: https://www.docker.com/products/docker-desktop/

    During installation, make sure:

        ✅ Enable WSL 2 backend

        ✅ Use Linux containers (default)

    ⚠️ Reboot if prompted after WSL installation.

2. Clone the Repo

Open PowerShell or Git Bash and run:

git clone https://github.com/yourusername/mediaserver-docker.git
cd mediaserver-docker

3. Create Required Folders

These folders are mounted inside your containers.
Option A: Manual (via File Explorer)

Go to:
C:\Users\YourUsername\Downloads\Mediaserver\

Create these folders:

config/
├─ jellyfin/
├─ sonarr/
├─ radarr/
├─ transmission/
├─ prowlarr/
├─ jackett/
├─ bazarr/
├─ jellyseerr/
├─ homarr/
downloads/
media/
├─ movies/
├─ shows/
icons/

Option B: Auto (PowerShell Script)

Paste this into PowerShell:

$base = "$HOME\Downloads\Mediaserver"
$paths = @(
  "$base\config\jellyfin",
  "$base\config\sonarr",
  "$base\config\radarr",
  "$base\config\transmission",
  "$base\config\prowlarr",
  "$base\config\jackett",
  "$base\config\bazarr",
  "$base\config\jellyseerr",
  "$base\config\homarr",
  "$base\downloads",
  "$base\media\movies",
  "$base\media\shows",
  "$base\icons"
)
foreach ($path in $paths) { New-Item -ItemType Directory -Force -Path $path }

4. Run Docker Compose

Make sure Docker Desktop is running, then in your repo folder:

docker-compose up -d

This will:

    Pull all required images

    Set up containers

    Mount folders to their services

5. Access Your Services
Service	Local URL
Jellyfin	http://localhost:8096
Sonarr	http://localhost:8989
Radarr	http://localhost:7878
Transmission	http://localhost:9091
Prowlarr	http://localhost:9696
Jackett	http://localhost:9117
Bazarr	http://localhost:6767
Jellyseerr	http://localhost:5055
Homarr	http://localhost:7575