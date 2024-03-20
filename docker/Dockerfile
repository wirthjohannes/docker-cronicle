FROM node:20-alpine
RUN apk add procps curl
WORKDIR /opt/cronicle
RUN curl -s https://raw.githubusercontent.com/jhuckaby/Cronicle/master/bin/install.js | node
ENV CRONICLE_foreground=1
ENV CRONICLE_echo=1
ENV CRONICLE_color=1
ENV debug_level=1
ENV HOSTNAME=main
RUN node bin/build.js dist && bin/control.sh setup
CMD ["node", "bin/docker-entrypoint.js"]