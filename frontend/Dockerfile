FROM node:8.16.1-alpine
WORKDIR /app
COPY . /app
COPY package.json /app
RUN npm install
EXPOSE 8080
CMD node app.js
