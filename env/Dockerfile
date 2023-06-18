FROM nvidia/cuda:11.6.2-devel-ubuntu20.04

RUN mkdir /app
RUN mkdir /app/mnt
WORKDIR /app

RUN apt update
RUN apt install -y wget
RUN apt install -y git
RUN apt install -y vim
RUN apt install -y tmux

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y tzdata
RUN apt-get install -y software-properties-common

RUN add-apt-repository -y ppa:hvr/ghc \
 && apt-get update \
 && apt-get install -y curl netbase pkg-config wget

RUN curl -sSL https://get.haskellstack.org/ | sh

RUN wget https://apt.llvm.org/llvm.sh
RUN chmod +x llvm.sh
RUN ./llvm.sh 12

ENTRYPOINT ["tail", "-f", "/dev/null"]

