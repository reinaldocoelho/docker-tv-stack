# docker-tv-stack

Docker Stack to create private TV Stack like Netflix.

## Stack details

This stack is write over above softwares:

* qBitTorrent - Torrent controller.
* Sonarr - RSS scanner/scheduler to get final files.
* Emby - Interface to access videos like *Netflix*

### What I get with this stack

The simple flow is:
    Sonnar --> Call Jackett as indexer of torrents.
    Sonnar --> Request download to qBitTorrent
    Emby access download folder of torrents.
All need share the same Download volume to access the same videos and work on it workspace.

## How to use

To use this stack, you need to edit docker-compose.yml and reconfigure all Volumes to your folder destinations.
The start volume configurations is on ./volumes folder with initial basic configuration. If you need, you can move this mount structure and mount where you want.



## To Subtitles

You need to create an account on some subtitle server like: https://www.opensubtitles.org/pt