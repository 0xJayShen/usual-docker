FROM ubuntu:16.04

# Install bitcoind from PPA
RUN apt-get update
RUN apt-get install --yes software-properties-common
RUN add-apt-repository --yes ppa:bitcoin/bitcoin
RUN apt-get update

# install bitcoind (from PPA) and make
RUN apt-get install --yes bitcoind

# copy bitcoin.conf
ADD . /home/bitcoind-testnet

# WORKDIR sets the working directory for any RUN, CMD, ENTRYPOINT, COPY and ADD instructions that follow
WORKDIR /home/bitcoind-testnet

# EXPOSE rpc port for the node to allow outside container access
EXPOSE 12001

ENTRYPOINT ["bitcoind", "-reindex"]