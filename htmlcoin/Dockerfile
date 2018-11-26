FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:bitcoin/bitcoin
RUN apt-get update
RUN apt-get install -y libdb4.8-dev libdb4.8++-dev

RUN git clone https://github.com/HTMLCOIN/htmlcoin
WORKDIR /htmlcoin
RUN git submodule update --init --recursive

RUN ./autogen.sh
RUN ./configure --disable-tests --disable-bench
RUN make

EXPOSE 38777
VOLUME /root/.htmlcoin

ADD htmlcoin.conf /root/.htmlcoin/htmlcoin.conf
CMD ./src/htmlcoind -debug