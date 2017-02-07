FROM ubuntu:16.04
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get install -y nodejs
RUN apt-get install -y build-essential
RUN npm install -g pm2
RUN npm install -g peer
CMD ["peerjs", "--port", "9000", "--key", "peerjs"]
