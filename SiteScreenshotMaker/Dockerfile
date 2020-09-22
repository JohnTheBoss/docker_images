FROM johntheboss/sitedeploy:node12
ARG  BUILD_DATE

LABEL maintainer="JohnTheBoss"
LABEL sourceCode="https://github.com/JohnTheBoss/docker_images/SiteScreenshotMaker"
LABEL version="SiteScreenshotMaker with Node.js 12 | Build Date: ${BUILD_DATE}"

# Update and Install #
RUN \
    echo "**** install packages ****" && \
    apt-get update -qq &&  \
    apt-get install -qq -y \
    libgconf-2-4 \ 
    fonts-ipafont-gothic \
    fonts-wqy-zenhei \
    fonts-thai-tlwg \
    fonts-kacst \
    fonts-freefont-ttf > /dev/null && \
	echo "**** DONE! ****"

# Install Chrome Unstable #
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add - \
    && sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google.list' \
    && apt-get update -qq \
    && apt-get install -qq -y google-chrome-unstable \
      --no-install-recommends > /dev/null\
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /src/*.deb

CMD ["/bin/bash"]
