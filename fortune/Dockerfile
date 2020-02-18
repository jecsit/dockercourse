FROM node:latest

ENV APP_PORT=3000 MESSAGE="awd def"
ENV APP_ROOT=/app

# create and cd
WORKDIR ${APP_ROOT}

ADD main.js .
ADD package.json .
ADD package-lock.json .
ADD public public
ADD views views

RUN npm install && echo "npm installed"

HEALTHCHECK --interval=30s --timeout=5s --retries=3 --start-period=5s \
    CMD curl -s -f http://localhost:${APP_PORT}/health  > /dev/null || exit 1


EXPOSE  ${APP_PORT}

ENTRYPOINT [ "node", "main.js" ]




