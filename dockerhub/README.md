# docker-flexget
FlexGet is a multipurpose automation tool for all of your media
Support for torrents, nzbs, podcasts, comics, TV, movies, RSS, HTML, CSV, and more.


## Usage
docker
```
docker create \
  --name=flexget \
  -e PUID=<1000> \
  -e PGID=<1000> \
  -e TZ=<UTC> \
  -e WEBUI_PASSWD=<OPTIONAL> \
  -e LOG_LEVEL=<OPTIONAL> \
  -e LOG_FILE=<OPTIONAL> \
  -e PIP_PKGS=<OPTIONAL> \
  -e APK_PKGS=<OPTIONAL> \
  -v <PATH>:/config \
  -p 5050:5050 \
  winterau/flexget
```
  
  docker-compose
  
```
version: "2"
services:
  flexget:
    image: flexget/flexget
    container_name: flexget
    environment:
      - PUID=<1000>
      - PGID=<1000>
      - TZ=<UTC>
      - WEBUI_PASSWD=<OPTIONAL>
      - LOG_LEVEL=<OPTIONAL> 
      - LOG_FILE=<OPTIONAL> 
      - PIP_PKGS=<OPTIONAL> 
      - APK_PKGS=<OPTIONAL> 
    ports:
      - 5050:5050
    volumes:
      - <PATH>:/config
```

## Parameters 

| Parameter | Use |
| :----: | --- |
| `-e PUID=<1000>` | Sets the User ID for Flexget. Default: 1000 |
| `-e PGID=<1000>` | Sets the Group ID for Flexget. Default: 1000 |
| `-e TZ=<UTC>` | Sets the Timezone. Default: UTC |
| `-e WEBUI_PASSWD=<OPTIONAL>` | Sets the web passwd for Flexget. |
| `-e LOG_LEVEL=<OPTIONAL>` | Sets the Flexget logging level. Default: info |
| `-e LOG_FILE=<OPTIONAL>` | Sets the Flexget log file. Default: flexget.log |
| `-e PIP_PKGS=<OPTIONAL>` | A space separated list of additional pip pkgs to be installed on startup |
| `-e APK_PKGS=<OPTIONAL>` | A space separated list of additional apk pkgs to be installed on startup |
| `-v <PATH>:/config` | Config directory for Flexget |
| `-p 5050:5050` | Port for the Flexget webui |