useful commands:
```shell
docker build -t allofthecoins:navcoin ./
docker run --name navcoin -itd allofthecoins:navcoin
docker exec -it navcoin src/navcoin-cli --version
docker exec -it navcoin tail /root/.navcoin/debug.log
docker exec -it navcoin src/navcoin-cli getpeerinfo
docker exec -it navcoin bash
```

Runs the navcoin node, listens of port 18886 on the host, listens for local RPC connections on 44446

```shell
docker run --name navcoin -itd -p 18886:18886 -p 127.0.0.1:44446:44446 -v navcoind-data:/root/.navcoin allofthecoins:navcoin
```
