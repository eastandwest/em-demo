FROM ubuntu:16.04
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -
RUN apt-get install -y nodejs
RUN apt-get install -y build-essential
RUN npm install -g pm2
ADD cxc-demo.tar /
WORKDIR cxc-demo
RUN npm install --production
COPY server_conf.yaml conf/server_conf.yaml
COPY monitor_conf.yaml conf/monitor_conf.yaml
CMD ["pm2-docker", "index.js"]
