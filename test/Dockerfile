FROM node:latest

COPY . .

WORKDIR "/app"

RUN npm install --production

EXPOSE 3000

CMD npm test