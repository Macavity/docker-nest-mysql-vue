### STAGE 1: Build ###
FROM node:lts-alpine AS build

WORKDIR /var/frontend

COPY . .

# Prepare for build
RUN ["yarn"]
RUN ["yarn", "build"]

# Prepare nginx
FROM nginx

RUN rm /etc/nginx/conf.d/default.conf

COPY docker/nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build /var/frontend /usr/share/nginx/html

# Start nginx
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
