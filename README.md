# Streaming to Steam with a Container

How to use:

1. Install Docker on the host machine
2. Clone this repository
3. put your video in the `/content` folder and name it `video_file.mp4`
4. Open the `compose.yaml` and place your steam upload token. You can find your upload token
   here: https://steamcommunity.com/broadcast/upload/

```yaml
version: '3'

services:
  stream:
    image: linuxserver/ffmpeg
    environment:
      - steam_token=steam_1394u901324u03294123 #<- will look something like this
    volumes:
      - .:/code
    entrypoint: bash /code/steam-stream.sh /code/content/video_file.mp4 $(steam_token)
    restart: unless-stopped
```

4. Run `docker-compose -f compose.yaml up` to verify that the setup works

6. If it works and you see the stream on steam: 
6. `Ctrl + C` to cancel and then run `docker-compose -f compose.yaml up -d`
   to start the service and put it in the background 