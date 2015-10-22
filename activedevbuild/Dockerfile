FROM debian:wheezy
MAINTAINER Justin Grayston

ENV METEORD_DIR /opt/meteord
ENV WORK_DIR /var/www/
ENV METEOR_PORT 3000
ENV DB_NAME meteor
ENV MONGO_URL mongodb://localhost:3001/$DB_NAME

COPY scripts $METEORD_DIR

# Set up requirements (node, phantomjs etc)
RUN bash $METEORD_DIR/init.sh
# Install meteor
RUN bash $METEORD_DIR/lib/install_meteor.sh

WORKDIR $WORK_DIR

EXPOSE $METEOR_PORT