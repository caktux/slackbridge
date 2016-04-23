Docker container for [discord-irc](https://github.com/reactiflux/discord-irc)
===

### Installation
```
git clone https://github.com/billimek/discordbridge
```

### Configuration

Copy `config.json.sample` to `config.json` and edit to your liking.

### Building and running

Build the docker container and run it with:

```
cd discordbridge/docker
docker build -t discordbridge .
docker run -d -t discordbridge
```

Enjoy :)
