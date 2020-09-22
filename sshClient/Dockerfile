FROM ubuntu:20.04
ARG  BUILD_DATE

LABEL maintainer="JohnTheBoss"
LABEL sourceCode="https://github.com/JohnTheBoss/docker_images/sshClient"
LABEL version="Ubuntu 20.04 with openssh-client & zip | Build Date: ${BUILD_DATE}"


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
    zip \
    openssh-client

CMD ["/bin/bash"]