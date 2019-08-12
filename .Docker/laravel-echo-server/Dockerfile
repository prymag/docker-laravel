FROM node:12.8.0-alpine

WORKDIR /app
COPY package.json /app
RUN npm install

ENTRYPOINT ["/app/node_modules/.bin/laravel-echo-server", "start"]