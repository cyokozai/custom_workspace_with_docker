###################### BUILDER ######################
FROM ghcr.io/being24/latex-docker:latest AS builder

SHELL ["/bin/bash", "-c"]

WORKDIR /root

# Environment variables
ENV DEBIAN_FRONTEND = noninter active
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ=Asia/Tokyo
ENV TZ JST-9
ENV TERM xterm
ENV DISPLAY host.docker.internal:0.0

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

RUN apt -y update &&\
    apt -y upgrade &&\
    ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone &&\
    apt -y install tzdata \
        locales \
        nano \
        git \
        curl \
        wget \
        unzip &&\
    kanji-config-updmap-sys auto &&\
    kanji-config-updmap-sys status &&\
    mkdir /root/documents

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

EXPOSE 22
#ENTRYPOINT ["/server-scrypt/main"]