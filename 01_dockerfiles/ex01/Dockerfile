## docker build -t ex01 . ## while in the ex01 directory 
## ▶ docker run --rm -it -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01
FROM debian

LABEL maintainer="saolivei@student.42.us.org"


RUN dpkg --add-architecture i386; apt-get update; apt-get install -y wget bzip2 \
	&& wget https://files.teamspeak-services.com/releases/server/3.7.1/teamspeak3-server_linux_amd64-3.7.1.tar.bz2 \
	&& tar xvf teamspeak3-server_linux_amd64-3.7.1.tar.bz2 \
	&& cd teamspeak3-server_linux_amd64 \
	&& touch .ts3server_license_accepted \
	&& apt-get purge -y bzip2 wget \
  	&& apt-get autoremove -y

ENV TS3SERVER_LICENSE accept

EXPOSE 9987/udp 10011 30033 41144

CMD  sh teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh
