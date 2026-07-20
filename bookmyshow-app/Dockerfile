FROM node:18

WORKDIR /app

COPY package*.json ./

RUN npm install --legacy-peer-deps

COPY . .

RUN npm install chokidar@3 watchpack-chokidar2 --legacy-peer-deps

ENV NODE_OPTIONS=--openssl-legacy-provider

EXPOSE 3000

CMD ["npm","start"]
