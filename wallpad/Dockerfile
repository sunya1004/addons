ARG BUILD_FROM=alpine:3.18
FROM ${BUILD_FROM}

ENV LANG=C.UTF-8

# Copy data for add-on
COPY run.sh /
COPY js /js

# Install requirements for add-on
RUN apk add --no-cache \
  bash \
  jq \
  npm \
  make \
  gcc \
  g++ \
  python3 \
  linux-headers \
  udev

COPY package.json /
RUN npm install

CMD [ "/run.sh" ]
