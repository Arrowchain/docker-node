# Run an Arrow node with docker

build:
```sh-session
docker build -t arw .
```

start arrow with the data directory mapped to a local directory:
```sh-session
docker run -d -v ~/.arrow:/root/.arrow --net=host --name=arw arw
```

tail the debug logs:
```sh-session
tail -n 50 -f ~/.arrow/debug.log
```

arrow-cli example:
```sh-session
docker exec -it arw arrow-cli --conf=/arrow-conf/arrow.conf getinfo
```


### note
if you don't have docker rootless set up, you'll likely have to prefix commands with `sudo`.
