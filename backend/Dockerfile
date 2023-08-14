FROM node:19.9.0-alpine

RUN mkdir -p /yolo/backend

WORKDIR /yolo/backend

COPY package*.json /app/

RUN npm install

COPY . /app/backend

CMD [ "npm", "start" ]