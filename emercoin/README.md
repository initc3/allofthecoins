useful commands:
```shell
docker build -t allofthecoins:emercoin ./
docker run --name emercoin -itd allofthecoins:emercoin
docker exec -it emercoin src/emercoin-cli --version
docker exec -it emercoin tail /root/.emercoin/debug.log
docker exec -it emercoin src/emercoin-cli getpeerinfo
docker exec -it emercoin bash
```

Runs the emercoin node, listens of port 6661 on the host, listens for local RPC connections on 6662

```shell
docker run --name emercoin -itd -p 6661:6661 -p 127.0.0.1:6662:6662 -v emercoind-data:/root/.emercoin allofthecoins:emercoin
```
