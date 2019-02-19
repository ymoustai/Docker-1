FROM debian

RUN apt-get update -y && apt-get upgrade -y 
RUN apt-get install curl -y 
RUN apt-get install bzip2 -y 
RUN curl -O http://dl.4players.de/ts/releases/3.5.1/teamspeak3-server_linux_amd64-3.5.1.tar.bz2
RUN bzip2 -d teamspeak3-server_linux_amd64-3.5.1.tar.bz2
RUN tar -xf teamspeak3-server_linux_amd64-3.5.1.tar

# 9987 default voice
# 10011 server query
# 30033 file transport

EXPOSE 9987/udp
EXPOSE 10011
EXPOSE 30033

ENV TS3SERVER_LICENSE accept

CMD ["sh", "./teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh"]
