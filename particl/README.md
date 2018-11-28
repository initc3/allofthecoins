useful commands:
```shell
docker build -t allofthecoins:particl ./
docker run --name particl -itd allofthecoins:particl
docker exec -it particl src/particl-cli --version
docker exec -it particl tail /root/.particl/debug.log
docker exec -it particl src/particl-cli getpeerinfo
docker exec -it particl bash
```

Runs the particl node, listens of port 51738 on the host, listens for local RPC connections on 51735

```shell
docker run --name particl -itd -p 51738:51738 -p 127.0.0.1:51735:51735 -v particld-data:/root/.particl allofthecoins:particl
```
