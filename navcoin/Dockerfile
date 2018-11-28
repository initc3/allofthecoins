FROM ubuntu:14.04

RUN apt-get update
RUN apt-get -y install build-essential libcurl3-dev libunbound-dev libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:bitcoin/bitcoin
RUN apt-get update
RUN apt-get install -y libdb4.8-dev libdb4.8++-dev
RUN apt-get install -y git cmake libboost-all-dev

RUN git clone https://github.com/NLnetLabs/unbound.git
WORKDIR /unbound
RUN ./configure && make && make install
WORKDIR ../

RUN git clone https://github.com/NAVCoin/navcoin-core.git
WORKDIR /navcoin-core
RUN git checkout 0225ba53f866cff8c71198f453627c24153c9f36
WORKDIR /navcoin-core

RUN ./autogen.sh
RUN ./configure --enable-debug
RUN make

EXPOSE 18886
VOLUME /root/.navcoin

ADD navcoin.conf /root/.navcoin/navcoin.conf
CMD ./src/navcoind -debug