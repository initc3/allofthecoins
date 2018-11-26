FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install python openssl libssl-dev git python-msgpack python-qt4

RUN git clone https://github.com/Bitmessage/PyBitmessage.git
WORKDIR /PyBitmessage

RUN  python checkdeps.py
RUN  python setup.py install
CMD  /usr/local/bin/pybitmessage