FROM mono:slim

RUN apt update \
  && apt -y install iproute2 ca-certificates dnsutils \
  && useradd -m -d /home/container container

USER container
ENV USER=container HOME=/home/container
ENV DEBIAN_FRONTEND noninteractive

WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh
CMD [ "/bin/bash", "/entrypoint.sh" ]