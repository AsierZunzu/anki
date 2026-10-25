# Anki Sync Server

Docker image for the official [Anki](https://github.com/ankitects/anki) self-hosted sync server (`anki-sync-server`), built from source on Alpine.

A GitHub Actions workflow builds it weekly against the latest upstream Anki release and publishes multi-arch images (`linux/amd64`, `linux/arm64`) to `ghcr.io/asierzunzu/anki-sync-server`.

## Usage

```sh
docker run -d -p 8080:8080 \
  -e SYNC_USER1=user:password \
  -e PUID=1000 -e PGID=1000 \
  -v ./anki_data:/anki_data \
  ghcr.io/asierzunzu/anki-sync-server:latest
```

Data lives in `/anki_data`; `PUID`/`PGID` set the owner of the files on the volume.
