# TubeSync for Umbrel OS

**TubeSync** is a PVR (personal video recorder) for YouTube, similar to Sonarr but for YouTube. It synchronizes channels and playlists from YouTube to local directories and updates your media server once media is downloaded.

## Key Features

- Synchronizes YouTube channels and playlists
- Updates media servers automatically
- Web interface for managing downloads
- Built-in download client with retry logic

## Installation

TubeSync is designed to be run in a container. The easiest way to install it is using Docker or Docker Compose.

### Docker Compose Example

```yaml
version: '3.7'

services:
  tubesync:
    image: ghcr.io/meeb/tubesync:latest
    container_name: tubesync
    restart: unless-stopped
    ports:
      - 4848:4848
    volumes:
      - /some/directory/tubesync-config:/config
      - /some/directory/tubesync-downloads:/downloads
    environment:
      - TZ=Europe/London
      - PUID=1000
      - PGID=1000