FROM ubuntu:16.04

RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y python-pip
RUN apt-get install -y openssl libssl-dev git python-msgpack python-qt4
RUN pip install setuptools

RUN git clone https://github.com/Bitmessage/PyBitmessage.git
WORKDIR /PyBitmessage

RUN python setup.py install --user
RUN ~/.local/bin/pybitmessage
RUN  python checkdeps.py