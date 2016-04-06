FROM ubuntu:wily

ENV DEBIAN_FRONTEND noninteractive

# Usual update / upgrade
#RUN apt-get update && apt-get upgrade -y && apt-get dist-upgrade -y
RUN apt-get update && apt-get upgrade -y

# Install requirements
RUN apt-get install -y curl supervisor

# Install nodejs
RUN curl -sL https://deb.nodesource.com/setup_5.x | bash -
RUN apt-get install --fix-missing -y nodejs

# Get discord-irc
#RUN npm install -g react@0.13.3
RUN npm install -g discord-irc-billimek
#RUN npm install -g https://github.com/billimek/discord-irc
#ADD discordirc-0.4.3.tgz /discordirc-0.4.3.tgz
#RUN npm install -g /discordirc-0.4.3.tgz --verbose

# Add configurations
ADD config.json discord-irc/config.json

# Add supervisor configs
ADD supervisord.conf supervisord.conf

CMD ["-n", "-c", "/supervisord.conf"]
ENTRYPOINT ["/usr/bin/supervisord"]
