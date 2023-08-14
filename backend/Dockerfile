FROM node:19.9.0-alpine

RUN mkdir -p /yolo/backend

WORKDIR /yolo/backend

COPY package*.json /yolo/backend/

RUN npm install

COPY . /yolo/backend/

CMD [ "npm", "start" ]