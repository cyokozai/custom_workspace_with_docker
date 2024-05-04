FROM ubuntu:latest AS builder

SHELL ["/bin/bash", "-c"]

ARG lang="C"
ARG dir="workdir"

ENV DEBIAN_FRONTEND = noninter active
ENV TERM xterm
ENV DISPLAY host.docker.internal:0.0

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

COPY kotlininstaller.sh /root/

RUN apt -y update && apt -y upgrade &&\
    apt -y install tzdata \
        locales \
        curl \
        zip \
        unzip &&\
    bash kotlininstaller.sh &&\
    rm -rf kotlininstaller.sh &&\
    mkdir /root/${dir} &&\
    locale-gen ${lang}

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

ENV LANG ${lang}
ENV LANGUAGE ${lang}
ENV LC_ALL ${lang}
ENV TZ=Asia/Tokyo
ENV TZ JST-9

EXPOSE 22
