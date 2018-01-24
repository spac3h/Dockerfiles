# Run spotify in a container
#
# docker run -d \
#	-v /tmp/.X11-unix:/tmp/.X11-unix \
#	-e DISPLAY=unix$DISPLAY \
#	--name wavebox \
#	imagename
#
FROM ubuntu
LABEL maintainer "Sergio Cardoso <sergio.cardoso@webhost.pt>"

RUN apt-get update && apt-get install -y \
nginx \
nginx-extras

CMD ["nginx", "-g", "daemon off;"]
