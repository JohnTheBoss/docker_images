FROM ubuntu:20.04
ARG  BUILD_DATE
ARG NODE_VERSION

LABEL maintainer="JohnTheBoss"
LABEL sourceCode="https://github.com/JohnTheBoss/docker_images/sitedeploy"
LABEL build_version="SiteDeploy with Node.js: ${NODE_VERSION}x | Build Date: ${BUILD_DATE}"

# Update System #
RUN \
    echo "**** update system ****" && \
    apt-get update && \
    apt-get full-upgrade -y

# Update and Install #
RUN \
    echo "**** install packages ****" && \
    apt-get update && \
    apt-get install -y \
    git \
    zip \
    openssh-client \
    lftp \
    curl \
    wget \
    build-essential \
    autoconf \
    automake \
    libtool \
    nasm \
    make \
    pkg-config \
    libpng-dev \
    rsync

# Node.JS Install #
RUN \
    echo "**** Download && Install Node.js  ****" && \
    curl -sL https://deb.nodesource.com/setup_${NODE_VERSION}.x | bash - && \
    apt-get install -y nodejs && \
    echo "**** Node.js Verson: ****" && \
    node -v && \
    echo "**** Update NPM  ****" && \
    npm -g install npm && \
    echo "**** NPM Version:  ****" && \
    npm --version

CMD ["/bin/bash"]