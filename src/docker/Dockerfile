FROM ubuntu:16.04

RUN apt-get update
RUN apt-get install -y sudo && \
    apt-get install -y wget && \
    apt-get install -y openjdk-8-jdk && \
    apt-get install -y libgtk2.0-0 libcanberra-gtk-module && \
    apt-get install -y git
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /var/cache/*

RUN echo 'Downloading IntelliJ...' && \
    wget https://download.jetbrains.com/idea/ideaIC-2018.2.4.tar.gz -O /tmp/intellij.tar.gz && \
    echo 'Installing IntelliJ' && \
    tar -xf /tmp/intellij.tar.gz -C /opt && rm /tmp/intellij.tar.gz

ADD run /usr/local/bin/intellij

RUN chmod +x /usr/local/bin/intellij 

ENV HOME /home/root
WORKDIR /home/root
ENTRYPOINT /usr/local/bin/intellij
