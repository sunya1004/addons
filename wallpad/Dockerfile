ARG BUILD_FROM=ghcr.io/hassio-addons/base/amd64:13.2.0
FROM ${BUILD_FROM}

ENV LANG C.UTF-8

# Copy data for add-on
COPY run.sh /
COPY js /js

# Install requirements for add-on
RUN apk add --no-cache \
  jq \
  npm \
  make \
  gcc \
  g++ \
  python \
  linux-headers \
  udev

COPY package.json /
RUN npm install

CMD [ "/run.sh" ]
