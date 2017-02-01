FROM ubuntu:16.04
RUN apt-get update
RUN apt-get -y upgrade
RUN apt-get -y install mosquitto
EXPOSE 1883
ENTRYPOINT ["mosquitto"]
