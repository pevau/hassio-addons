ARG BUILD_FROM
FROM $BUILD_FROM

# Add env
ENV LANG C.UTF-8

# Setup base
#RUN apk add --no-cache git nodejs npm curl wget unzip \
#    && npm set unsafe-perm true \
#    && npm i npm@latest -g 

RUN apk add --no-cache git  curl wget unzip
# Install latest LTS nodejs and npm
RUN apk add --no-cache --repository=https://dl-cdn.alpinelinux.org/alpine/edge/main/ nodejs
RUN apk add --no-cache --repository=https://dl-cdn.alpinelinux.org/alpine/edge/community/ npm
#RUN apk --update nodejs npm
#RUN npm set unsafe-perm true
#RUN npm i npm@latest -g 

WORKDIR /opt/magic_mirror

#RUN git clone --depth 1 -b master https://github.com/MichMich/MagicMirror.git . \
#  && npm install --unsafe-perm

RUN git clone --depth 1 -b master https://github.com/MichMich/MagicMirror.git .

# Copy data
COPY run.sh /
COPY config.js /
USER root
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]



