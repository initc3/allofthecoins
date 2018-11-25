FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev
RUN apt-get install -y software-properties-common
RUN add-apt-repository -y ppa:bitcoin/bitcoin
RUN apt-get update
RUN apt-get install -y libdb4.8-dev libdb4.8++-dev

RUN git clone https://github.com/qtumproject/qtum.git
WORKDIR /qtum
RUN git submodule update --init --recursive

RUN ./autogen.sh
RUN ./configure
RUN make -j2

EXPOSE 8333
VOLUME /root/.qtum

ADD qtum.conf /root/.qtum/qtum.conf
CMD ./src/qtumd -debug