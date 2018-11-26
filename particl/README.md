useful commands:
```shell
docker build -t allofthecoins:particl ./
docker run --name particl -itd allofthecoins:particl
docker exec -it particl src/particl-cli --version
docker exec -it particl tail /root/.particl/debug.log
docker exec -it particl src/particl-cli getpeerinfo
docker exec -it particl bash
```

Runs the particl node, listens of port 8333 on the host, listens for local RPC connections on 8332

```shell
docker run --name particl -itd -p 8333:8333 -p 127.0.0.1:8332:8332 -v particld-data:/root/.particl allofthecoins:particl
```
