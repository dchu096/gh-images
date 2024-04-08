FROM        debian:trixie-slim

LABEL       author="Daniel" maintainer="danielchu096@gmail.com"

LABEL       org.opencontainers.image.source="https://github.com/dchu096/gh-images"
LABEL       org.opencontainers.image.licenses=MIT

RUN apt update && apt upgrade -y
RUN apt install -y gcc g++ libgcc1 libc++-dev gdb libc6 git wget curl tar zip unzip binutils xz-utils liblzo2-2 cabextract iproute2 net-tools netcat-openbsd
RUN apt install -y libmariadb-dev-compat locales ffmpeg gnupg2 apt-transport-https software-properties-common ca-certificates tzdata
RUN apt install -y liblua5.3 libz-dev rapidjson-dev

USER        container
ENV         USER=container HOME=/home/container
ENV         DEBIAN_FRONTEND noninteractive

WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
