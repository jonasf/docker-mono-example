# Mono
#
# VERSION               0.1

FROM	ubuntu:13.10

MAINTAINER	Jonas Fredriksson

RUN		apt-get install sudo
RUN     sudo apt-get update
RUN     sudo DEBIAN_FRONTEND=noninteractive apt-get install -y -q software-properties-common
RUN     sudo add-apt-repository ppa:directhex/monoxide -y
RUN     sudo apt-get update
RUN     sudo DEBIAN_FRONTEND=noninteractive apt-get install -y -q mono-devel

ADD     . /MonoDockerTest

RUN     mcs /MonoDockerTest/Program.cs
CMD     ["mono", "/MonoDockerTest/Program.exe"]