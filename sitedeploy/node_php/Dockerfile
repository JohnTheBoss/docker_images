FROM ubuntu:18.04
LABEL maintainer="JohnTheBoss"

LABEL build_version="SiteDeploy with Node.js: 12x and PHP 7.2x + Composer 1.9x"

ENV DEBIAN_FRONTEND=noninteractive

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

# PHP install and Composer #
RUN ln -fs /usr/share/zoneinfo/Europe/London /etc/localtime && \
    apt-get update && \
    apt-get -y install tzdata && \
    apt install php php7.2-cgi -y && \
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php && \
    mv composer.phar /usr/local/bin/composer && \
    php -r "unlink('composer-setup.php');" && \
    echo "**** PHP Verson: ****" && \
    php -v && \
    echo "**** Composer Version:  ****" && \
    composer -V

# Node.JS Install #
RUN \
    echo "**** Download && Install Node.js  ****" && \
    curl -sL https://deb.nodesource.com/setup_12.x | bash - && \
    apt-get install -y nodejs && \
    echo "**** Node.js Verson: ****" && \
    node -v && \
    echo "**** Update NPM  ****" && \
    npm -g install npm && \
    echo "**** NPM Version:  ****" && \
    npm --version

CMD ["/bin/bash"]
