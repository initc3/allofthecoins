FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:bitcoin/bitcoin
RUN apt-get update
RUN apt-get install -y libdb4.8-dev libdb4.8++-dev

RUN git clone https://github.com/particl/particl-core.git
WORKDIR /particl-core
RUN git submodule update --init --recursive

RUN ./autogen.sh
RUN ./configure --disable-tests --disable-bench
RUN make

EXPOSE 8333
VOLUME /root/.particl

ADD particl.conf /root/.particl/particl.conf
CMD ./src/particld -debug