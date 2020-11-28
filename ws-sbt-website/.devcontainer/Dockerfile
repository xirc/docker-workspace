FROM ubuntu

SHELL [ "/bin/bash", "-c" ]

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y \
      build-essential \
      curl \
      git \
      liblzma-dev \
      patch \
      ruby \
      ruby-dev \
      unzip \
      zip \
      zlib1g-dev \
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* \
    # JDK, scala, sbt
    && curl -s "https://get.sdkman.io" | bash \
    && source "$HOME/.sdkman/bin/sdkman-init.sh" \
    && sdk install java \
    && sdk install scala \
    && sdk install sbt \
    # sbt/website
    && gem install \
      nanoc:4.0.2 \
      nokogiri \
      redcarpet

ENV DEBIAN_FRONTEND=dialog