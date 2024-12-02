FROM node:20 
LABEL name=myapp 
ARG APP_DIR=/app 
WORKDIR ${APP_DIR}

ADD main.js .
ADD package.json . 
ADD public public
ADD views views

RUN npm ci --progress=false

ENV APP_PORT=3000
ENV INSTANCE_NAME='day01app'
ENV INSTANCE_HASH='nus'

EXPOSE ${APP_PORT}

ENTRYPOINT node main.js ${APP_PORT}
