FROM ubuntu

SHELL [ "/bin/bash", "-c" ]

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get autoremove

# Install basic development tools
RUN apt-get install -y build-essential git

# Install jdk, scala, sbt
RUN apt-get install -y curl unzip zip && \
    curl -s "https://get.sdkman.io" | bash && \
    source "$HOME/.sdkman/bin/sdkman-init.sh" && \
    sdk install java && \
    sdk install scala && \
    sdk install sbt

# Install requirements for sbt/website
RUN apt-get install -y ruby ruby-dev patch zlib1g-dev liblzma-dev && \
    gem install nanoc:4.0.2 redcarpet nokogiri
