FROM sharelatex/sharelatex
ARG  BUILD_DATE

LABEL maintainer="JohnTheBoss"
LABEL sourceCode="https://github.com/JohnTheBoss/docker_images/sharelatex-full/hu"
LABEL build_version="Sharelatex Full Package - HUN Mirror | Build Date: ${BUILD_DATE}"

RUN wget http://mirror.ctan.org/systems/texlive/tlnet/update-tlmgr-latest.sh && sh update-tlmgr-latest.sh
RUN tlmgr option repository https://mirror.szerverem.hu/ctan/systems/texlive/tlnet/
RUN tlmgr install scheme-full
