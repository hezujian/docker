FROM ${DockerImageLabel}

EXPOSE 80

WORKDIR /usr/src/app

COPY ./ /usr/src/app/

RUN rm -rf node_modules package-lock.json \
    && npm install --registry=https://registry.npm.taobao.org \
    && npm run build \
    && rm -rf /usr/share/nginx/html/* \
    && mv ./dist/* /usr/share/nginx/html \
    && rm -rf *

CMD ["nginx", "-g", "daemon off;"]