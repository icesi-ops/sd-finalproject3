FROM node:8.16.1-alpine
WORKDIR /app
COPY . /app
COPY package.json /app
RUN npm install
EXPOSE 5000
CMD node app.js
