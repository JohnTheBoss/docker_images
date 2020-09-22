FROM openjdk:13-buster
ARG  BUILD_DATE

LABEL maintainer="JohnTheBoss"
LABEL sourceCode="https://github.com/JohnTheBoss/docker_images/openjdk13_withAntJ4"
LABEL build_version="OpenJDK 13 Debian with Ant & junit4 | Build Date: ${BUILD_DATE}"

RUN apt-get update -yqq
RUN apt-get install -yqq ant junit4

CMD ["jshell"]
