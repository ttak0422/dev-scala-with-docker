FROM hseeberger/scala-sbt:8u222_1.3.5_2.13.1

ARG USERNAME=dev
ARG USER_UID=1000
ARG USER_GID=$USER_UID

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends apt-utils 2>&1 \
    && apt-get install -y vim \
    && groupadd --gid $USER_GID $USERNAME \
    && useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt-get autoremove -y \
    && apt-get clean -y 

ENV HOME=/home/dev
ENV DEBIAN_FRONTEND=dialog