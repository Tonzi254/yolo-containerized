FROM node:13.12.0-alpine

RUN mkdir -p /yolo/client

WORKDIR /yolo/client

COPY package*.json /app/

RUN npm install

COPY . /yolo/client

EXPOSE 3000

CMD [ "npm", "start" ]