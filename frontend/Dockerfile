### STAGE 1: Build ###
FROM node:lts-alpine AS build

WORKDIR /var/frontend

COPY package.json ./
COPY yarn.lock ./

CMD ["yarn"]

COPY . .

CMD ["yarn", "build"]

EXPOSE 8080

