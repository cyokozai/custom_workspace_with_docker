###################### BUILDER ######################
FROM ghcr.io/typst/typst:latest AS builder

WORKDIR /root

ARG lang="C"
ARG dir="documents"

ENV DEBIAN_FRONTEND = noninter active
ENV TERM xterm
ENV DISPLAY host.docker.internal:0.0

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

RUN apk update &&\
    apk upgrade &&\
    apk add --no-cache tzdata \
        musl-locales \
        font-noto-cjk \
        font-noto-cjk-extra \
        font-noto-emoji \
        setxkbmap &&\
    mkdir /root/${dir}

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

ENV LANG ${lang}
ENV LANGUAGE ${lang}
ENV LC_ALL ${lang}
ENV TZ=Asia/Tokyo
ENV TZ JST-9

EXPOSE 22
