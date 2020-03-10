FROM ubuntu:16.04
MAINTAINER Nodar Nutsubidze <nodar.nutsubidze@gmail.com>
ENV HOSTNAME packit

# Install packages
RUN apt-get update -y && DEBIAN_FRONTEND=noninteractive apt-get install -qy \
  git \
  mongodb \
  nodejs \
  npm \
  python-pip

# Download git repo
RUN git clone https://github.com/galenmaly/packit.git /var/www/packit

# Move to the directory so we install the libraries in correct folder
RUN cd /var/www/packit && npm install

# Web
EXPOSE 3000

WORKDIR /var/www/packit
CMD ["nodejs", "app.js"]
