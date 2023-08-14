FROM node:19.9.0-alpine

RUN mkdir -p /app

WORKDIR /app

COPY package*.json /app/

RUN npm install

COPY . /app/

CMD [ "npm", "start" ]