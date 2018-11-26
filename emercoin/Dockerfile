FROM ubuntu:18.04

RUN apt-get update
RUN apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:bitcoin/bitcoin
RUN apt-get update
RUN apt-get install -y libdb4.8-dev libdb4.8++-dev

RUN git clone https://github.com/emercoin/emercoin.git
WORKDIR /emercoin
RUN git checkout cf4ea413bc3587cf81b5f07e05260acd6a21cb2d
RUN git submodule update --init --recursive

RUN ./autogen.sh
RUN ./configure --disable-tests --disable-bench
RUN make

EXPOSE 6661
VOLUME /root/.emercoin

ADD emercoin.conf /root/.emercoin/emercoin.conf
CMD ./src/emercoind -debug