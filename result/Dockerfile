FROM node
WORKDIR /usr/local/app
COPY package-lock.json ./
COPY package.json ./

RUN npm install -g nodemon && npm ci && npm cache clean --force && mv /usr/local/app/node_modules /node_modules

COPY . .

EXPOSE 4000
CMD [ "node","server.js" ]