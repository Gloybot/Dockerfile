FROM alpine:3.8
MAINTAINER oldiy <oldiy@163.com>

WORKDIR /
ENV NPC_VERSION 0.21.0
ENV ARCH arm64
ENV SYSTEM linux

RUN set -x && \
	wget --no-check-certificate https://github.com/ehang-io/nps/releases/download/v${NPC_VERSION}/${SYSTEM}_${ARCH}_client.tar.gz && \ 
	mkdir \npc && \
	mv ${SYSTEM}_${ARCH}_client* /npc && \
	cd /npc && \
	tar xzf ${SYSTEM}_${ARCH}_client.tar.gz && \
	rm -rf *.tar.gz && \
	rm *.conf

ENV SERVERIP 127.0.0.1:8024
ENV VKEY 123

CMD /npc/npc -server=${SERVERIP} -vkey=${VKEY}
