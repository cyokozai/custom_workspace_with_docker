###################### BUILDER ######################
FROM python:3.11 AS builder

SHELL ["/bin/bash", "-c"]

WORKDIR /root

ENV DEBIAN_FRONTEND = noninter active

COPY requirements.txt /root/

RUN pip install --upgrade pip &&\
    pip install -r requirements.txt

###################### RUNTIME ######################
FROM python:3.11-slim

SHELL ["/bin/bash", "-c"]

WORKDIR /root

ARG lang="C"
ARG dir="workdir"

ENV DEBIAN_FRONTEND = noninter active
ENV TERM xterm
ENV DISPLAY host.docker.internal:0.0

COPY --from=builder /usr/local/bin/* /usr/local/bin/*
COPY --from=builder /usr/local/lib/python3.*/site-packages /usr/local/lib/python3.*/site-packages

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

COPY *.py /root/

RUN apt -y update && apt -y upgrade &&\
    apt -y install tzdata \
        locales &&\
    mkdir /root/${dir} &&\
    locale-gen ${lang}

#~~~~~~~~~~~~~~~~~~~~~~ EDIT ~~~~~~~~~~~~~~~~~~~~~~~#

ENV LANG ${lang}
ENV LANGUAGE ${lang}
ENV LC_ALL ${lang}
ENV TZ=Asia/Tokyo
ENV TZ JST-9

EXPOSE 22
