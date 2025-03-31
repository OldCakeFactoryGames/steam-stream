# Streaming to Steam with a Container

How to use:

1. Install Docker on the host machine
2. Clone this repository
3. If it does not exist create a folder named `/content` on the repository root
3. Put your video in this `/content` folder and name it `video_file.mp4`
4. Open the `steam_token.txt` and place your steam upload token. You can find your upload token
   here: https://steamcommunity.com/broadcast/upload/

The file should then look something like this:
```txt
steam_asdkfjaskdfjsdaklja
```

4. Run `docker-compose -f compose.yaml up` inside the project folder, to verify that the setup works

6. If it works and you see the stream on steam: 
6. `Ctrl + C` to cancel and then run `docker-compose -f compose.yaml up -d`
   to start the service and put it in the background 