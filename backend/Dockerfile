FROM node:19.9.0-alpine

RUN mkdir -p /yolo/backend

WORKDIR /yolo/backend

COPY package*.json /yolo/backend/

RUN npm install

COPY . /yolo/backend/

EXPOSE 5000

CMD [ "npm", "start" ]