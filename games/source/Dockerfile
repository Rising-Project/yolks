#
# Copyright (c) 2021 Matthew Penner
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.
# gcc g++ lib32gcc-s1 libgcc1 libcurl4-gnutls-dev:i386 libssl1.1:i386 libcurl4:i386 lib32tinfo6 libtinfo6:i386 lib32z1 lib32stdc++6 libncurses5:i386 libcurl3-gnutls:i386 libsdl2-2.0-0:i386

FROM        --platform=$TARGETOS/$TARGETARCH debian:stable-slim

LABEL       author="Katsuki" maintainer="owner@katsuki.digital"

LABEL       org.opencontainers.image.source="https://github.com/rising-project/yolks"
LABEL       org.opencontainers.image.licenses=MIT

ENV         DEBIAN_FRONTEND=noninteractive

RUN         dpkg --add-architecture i386 \
				&& apt update \
				&& apt upgrade -y \
				&& apt-get install -y git \
				&& apt-get install -y tar \
				&& apt-get install -y curl \
				&& apt-get install -y gcc \
				&& apt-get install -y g++ \
				&& apt-get install -y lib32gcc-s1 \
				&& apt-get install -y libgcc1 \
				&& apt-get install -y libcurl4-gnutls-dev:i386 \
				&& apt-get install -y libssl1.1:i386 \
				&& apt-get install -y libcurl4:i386 \
				&& apt-get install -y lib32tinfo6 \
				&& apt-get install -y libtinfo6:i386 \
				&& apt-get install -y lib32z1 \
				&& apt-get install -y lib32stdc++6 \
				&& apt-get install -y libncurses5:i386 \
				&& apt-get install -y libcurl3-gnutls:i386 \
				&& apt-get install -y libsdl2-2.0-0:i386 \
				&& apt-get install -y iproute2 \
				&& apt-get install -y gdb \
				&& apt-get install -y libsdl1.2debian \
				&& apt-get install -y libfontconfig1 \
				&& apt-get install -y telnet \
				&& apt-get install -y net-tools \
				&& apt-get install -y netcat \
				&& apt-get install -y tzdata \
				
				&& apt-get update \
				&& useradd -m -d /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
