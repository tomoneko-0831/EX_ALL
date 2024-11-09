FROM ubuntu:24.04 AS base

RUN apt-get update && apt-get -y upgrade

RUN apt-get install -y make sudo git vim nkf x11-xserver-utils wget unzip curl language-pack-ja-base language-pack-ja ibus-mozc

RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN echo 'export LANG=ja_JP.UTF-8' >> ~/.bashrc

RUN echo 'export LANGUAGE="ja_JP:ja"' >> ~/.bashrc

FROM base AS ex_c_cpp

WORKDIR /

RUN mkdir C Cpp

RUN apt-get update && apt-get -y install build-essential libncurses5-dev libncursesw5-dev


FROM base AS dev_win

WORKDIR /dev_win/

RUN apt-get update && apt-get install -y mingw-w64


FROM base AS ex_java

WORKDIR /Java/

RUN apt-get update && apt-get -y install openjdk-21-jdk


FROM base AS ex_py

WORKDIR /Python

RUN apt-get update && apt-get -y install python3-pip python3-venv


FROM base AS ex_js

WORKDIR /JavaScript

RUN apt-get update && apt-get install -y nodejs npm
