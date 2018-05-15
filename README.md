# docker-tv-stack

Docker Stack to create private TV Stack like Netflix.

## Stack dependencies

* Docker
* Docker Compose

## Stack details

This stack is write over above softwares:

* qBitTorrent - Torrent controller.
* Jakett - Indexer who get movies and series URIs to download.
* Sonarr - RSS scanner/scheduler to get final files for series.
* radarr - RSS scanner/scheduler to get final movie files.
* Emby - Interface to access videos like *Netflix* and download subtitles.

### What I get with this stack

The simple flow is:
    Sonarr --> Call Jackett as indexer of torrents.
    Sonarr --> Request download to qBitTorrent
    Radarr --> Call Jackett as indexer of torrents.
    Radarr --> Request download to qBitTorrent
    Emby access download folder of torrents movies and series and show to final user.
All need share the same Download volume to access the same videos and work on it workspace.

## How to use

To use this stack, you need to edit docker-compose.yml and reconfigure all Volumes to your folder destinations.
The start volume configurations is on ./volumes folder with initial basic configuration. If you need, you can move this mount structure and mount where you want.

Basic Start:

1. Copy folder 'volume-starter' to 'volume' name.
2. Open folder on console.
3. Run:

```bash
sudo docker-compose up
```

**NOTICE:** You will need to make your settings on final, but here was the basic structure to start with.

## To Subtitles

You need to create an account on some subtitle server like: https://www.opensubtitles.org/pt

## Important information

We don´t aggre with illegal content, than, we sugest you to always use this stack with open content or your personal legal content.
Thanks.