###################### BUILDER ######################
FROM ubuntu:latest AS builder

SHELL ["/bin/bash", "-c"]

WORKDIR /root

COPY requirements.txt /root/

#キーボード設定
ENV DEBIAN_FRONTEND = noninter active

#aptアップグレード&設定
RUN apt -y update && apt -y upgrade &&\
    apt -y install tzdata \
    locales \
    language-pack-ja-base language-pack-ja locales \
    python3.10 \
    python3-pip &&\
    pip3 install --upgrade pip &&\
    pip3 install -r requirements.txt &&\
    echo "alias python=python3.10" >> ~/.bashrc &&\
    echo "alias pip=pip3" >> ~/.bashrc &&\
    source ~/.bashrc &&\
    locale-gen ja_JP.UTF-8

#環境変数の設定等
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ=Asia/Tokyo
ENV TZ JST-9
ENV TERM xterm
ENV DISPLAY host.docker.internal:0.0
EXPOSE 22

#コンテナ起動時の実行ファイル
#ENTRYPOINT ["/server-scrypt/main"]