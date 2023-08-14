FROM node:13.12.0-alpine

RUN mkdir -p /app/client

WORKDIR /app/client

COPY package*.json /app/

RUN npm install

COPY . /app/client

EXPOSE 3000

CMD [ "npm", "start" ]