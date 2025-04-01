FROM node:22.9.0 AS frontend
WORKDIR /front-end
COPY front-end/ .
WORKDIR front-end/
RUN npm install && npm run build

FROM nginx:alpine
WORKDIR /
COPY --from=frontend /front-end/build /build
COPY ssl/ /ssl
COPY nginx.conf /etc/nginx/nginx.conf
#

