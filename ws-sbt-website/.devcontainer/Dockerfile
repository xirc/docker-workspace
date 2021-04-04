FROM xirc/sbt-scala

SHELL [ "/bin/bash", "-c" ]

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y \
      liblzma-dev \
      patch \
      ruby \
      ruby-dev \
      zlib1g-dev \
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/* \
    # sbt/website
    && gem install \
      nanoc:4.0.2 \
      nokogiri \
      redcarpet

ENV DEBIAN_FRONTEND=dialog