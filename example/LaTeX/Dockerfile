###################### RUNTIME ######################
FROM ghcr.io/being24/latex-docker:latest

SHELL ["/bin/bash", "-c"]

WORKDIR /home/latex
USER root

ARG lang="ja_JP.UTF-8"
ARG dir="documents"
ARG t2p="/usr/local/bin/"

ENV DEBIAN_FRONTEND = noninter active
ENV TERM xterm
ENV DISPLAY host.docker.internal:0.0

COPY ./tex2pdf ${t2p}

RUN apt -y update &&\
    apt -y upgrade &&\
    apt -y install tzdata \
        locales \
        nano \
        git \
        curl \
        wget \
        unzip &&\
    kanji-config-updmap-sys auto &&\
    kanji-config-updmap-sys status &&\
    # apt-get install texlive-fonts-recommended texlive-fonts-extra　&&\
    mkdir ${dir} &&\
    chmod +x ${t2p}tex2pdf &&\
    export PATH=$PATH:~/bin &&\
    source ~/.bashrc

ENV LANG ${lang}
ENV LANGUAGE ${lang}
ENV LC_ALL ${lang}
ENV TZ=Asia/Tokyo
ENV TZ JST-9
