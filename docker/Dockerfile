FROM node

ENV DEBIAN_FRONTEND noninteractive

# Usual update and install
RUN apt-get update && apt-get install -y supervisor

# Get slack-irc
RUN npm install -g slack-irc

# Add configurations
ADD config.json slack-irc/config.json

# Add supervisor configs
ADD supervisord.conf supervisord.conf

CMD ["-n", "-c", "/supervisord.conf"]
ENTRYPOINT ["/usr/bin/supervisord"]
