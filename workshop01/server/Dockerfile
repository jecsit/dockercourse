FROM node:latest

ENV DB_USER=root DB_PASSWORD=changeit DB_HOST=nwdb DB_PORT=3306
ENV APP_PORT=3000 APP_ROOT=/app

WORKDIR ${APP_ROOT}

ADD . .

RUN npm install

HEALTHCHECK --interval=30s --timeout=5s --retries=2 --start-period=5s \
   CMD curl -s -f http://localhost:${APP_PORT}/health > /dev/null || exit 1

EXPOSE ${APP_PORT}

ENTRYPOINT [ "node", "main.js" ]
