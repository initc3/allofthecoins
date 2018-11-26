useful commands:
```shell
docker build -t allofthecoins:htmlcoin ./
docker run --name htmlcoin -itd allofthecoins:htmlcoin
docker exec -it htmlcoin src/htmlcoin-cli --version
docker exec -it htmlcoin tail /root/.htmlcoin/debug.log
docker exec -it htmlcoin src/htmlcoin-cli getpeerinfo
docker exec -it htmlcoin bash
```

Runs the htmlcoin node, listens of port 38777 on the host, listens for local RPC connections on 28777

```shell
docker run --name htmlcoin -itd -p 38777:38777 -p 127.0.0.1:28777:28777 -v htmlcoind-data:/root/.htmlcoin allofthecoins:htmlcoin
```
