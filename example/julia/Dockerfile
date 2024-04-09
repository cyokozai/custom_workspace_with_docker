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

COPY requirements.txt, rye_installer.sh, *.py /root/

RUN apt -y update && apt -y upgrade &&\
    apt -y install tzdata \
    locales \
    wget \
    tar \
    language-pack-ja-base language-pack-ja locales &&\
    wget https://julialang-s3.julialang.org/bin/linux/x64/1.7/julia-1.7.0-linux-x86_64.tar.gz &&\
    tar zxvf julia-1.7.0-linux-x86_64.tar.gz -C /usr --strip-components 1 &&\
    rm julia-1.7.0-linux-x86_64.tar.gz &&\
    echo "alias newalias='julia'" >> ~/.bashrc &&\
    source ~/.bashrc &&\
    locale-gen ja_JP.UTF-8

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

EXPOSE 22
#ENTRYPOINT ["/server-scrypt/main"]
