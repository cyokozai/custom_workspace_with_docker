###################### RUNTIME ######################
FROM ghcr.io/being24/latex-docker:latest

SHELL ["/bin/bash", "-c"]

WORKDIR /root

ARG lang="C"

ENV DEBIAN_FRONTEND = noninter active
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
    mkdir /root/documents &&\
    locale-gen ${lang}

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

ENV LANG ${lang}
ENV LANGUAGE ${lang}
ENV LC_ALL ${lang}
ENV TZ=Asia/Tokyo
ENV TZ JST-9

EXPOSE 22
#ENTRYPOINT ["/server-scrypt/main"]