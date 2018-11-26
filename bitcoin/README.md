useful commands:
```shell
docker build -t allofthecoins:bitcoin ./
docker run --name bitcoin -itd allofthecoins:bitcoin
docker exec -it bitcoin src/bitcoin-cli --version
docker exec -it bitcoin tail /root/.bitcoin/debug.log
```

Runs the bitcoin node, listens of port 8333 on the host, listens for local RPC connections on 8332

```shell
docker run --name bitcoin -itd -p 8333:8333 -p 127.0.0.1:8332:8332 -v bitcoind-data:/root/.bitcoin allofthecoins:bitcoin
```
