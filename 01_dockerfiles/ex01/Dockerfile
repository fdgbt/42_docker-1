FROM debian

# CONFIG CONTAINER
RUN apt-get update && apt-get upgrade -y && apt-get install -y wget bzip2

# CONFIG TEAMSPEAK
ENV VERSION=3.4.0
ENV TS3SERVER_LICENSE=accept

# CONFIG PORT
EXPOSE 9987/udp
EXPOSE 30033
EXPOSE 10011
EXPOSE 41144

# Create teamspeak user
RUN adduser --disabled-login --gecos GECOS teamspeak

# Download and unpack teamspeak server
WORKDIR /home/teamspeak
RUN wget http://dl.4players.de/ts/releases/3.4.0/teamspeak3-server_linux_amd64-3.4.0.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.4.0.tar.bz2 && rm teamspeak3-server_linux_amd64-3.4.0.tar.bz2

# Launch ts3 server at starting
CMD ["/home/teamspeak/teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh"]
