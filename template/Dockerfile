###################### BUILDER ######################
FROM ubuntu:latest AS builder

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

# COPY < File Name > /root/

RUN apt -y update && apt -y upgrade &&\
    apt -y install tzdata \
    locales \
    # < Package > \
    # < Package > \
    # < Package > \
    language-pack-ja-base language-pack-ja locales &&\
    source ~/.bashrc &&\
    locale-gen ja_JP.UTF-8

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

EXPOSE 22
#ENTRYPOINT ["/server-scrypt/main"]
