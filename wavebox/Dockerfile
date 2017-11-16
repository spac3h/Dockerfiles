# Run spotify in a container
#
# docker run -d \
#	-v /tmp/.X11-unix:/tmp/.X11-unix \
#	-e DISPLAY=unix$DISPLAY \
# --device /dev/snd:/dev/snd \
#	--name wavebox \
#	imagename
#
FROM ubuntu
LABEL maintainer "Sergio Cardoso <sergio.cardoso@webhost.pt>"

RUN apt-get update && apt-get install -y \
wget \
libappindicator1 \
xdg-utils \
libgconf-2-4 \
libxss1 \
libnss3 \
libasound2 \
sudo

RUN mkdir -p /usr/share/applications/

ENV HOME /opt/wavebox/

RUN useradd --create-home --home-dir $HOME wavebox \
&& chown -R wavebox:wavebox $HOME

WORKDIR $HOME

RUN wget https://github.com/wavebox/waveboxapp/releases/download/v3.5.0/Wavebox_3_5_0_linux_x86_64.deb

RUN dpkg -i Wavebox_3_5_0_linux_x86_64.deb 

USER wavebox

ENTRYPOINT ["/opt/wavebox/Wavebox"]
