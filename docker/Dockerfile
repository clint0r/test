FROM ubuntu:18.04

RUN apt-get update && apt-get -y upgrade \
	&& apt-get install -y git build-essential cpanminus libchi-perl libmojolicious-perl libdatetime-perl libxml-simple-perl libmoo-perl libjson-maybexs-perl libhash-asobject-perl libdata-parsebinary-perl libdigest-crc-perl libcache-perl libtest-longstring-perl libio-pty-perl \
	&& git clone https://github.com/nebulous/infinitude.git /infinitude \ 
    && chmod +x /infinitude/infinitude \
    && cd /infinitude \
    && cpanm Mojolicious::Lite CHI DateTime Try::Tiny Path::Tiny JSON IO::Termios
#COPY ./entrypoint.sh /
COPY https://github.com/clint0r/test/tree/master/docker/entrypoint.sh /
EXPOSE 3000
ENTRYPOINT /entrypoint.sh
