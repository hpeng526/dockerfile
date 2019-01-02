FROM nginx:1.15.8-alpine

LABEL maintainer="hpeng526 <hpeng526@gmail.com>"

ENV VERSION     1.0.0
ENV DOWNLOAD    https://github.com/mayswind/AriaNg/releases/download/${VERSION}/AriaNg-${VERSION}.zip

RUN apk upgrade --update \
    && apk add --no-cache --update curl unzip \
    && curl -sSLO ${DOWNLOAD} \
    && unzip -d /app AriaNg-${VERSION}.zip \
    && mv /app/* /usr/share/nginx/html \
    && rm -f AriaNg-${VERSION}.zip

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]