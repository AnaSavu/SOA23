FROM node:latest as build

WORKDIR /app

COPY . .

RUN npm install

ENV PUBLIC_URL=/app

RUN npm run build

FROM nginx:latest

COPY --from=build /app/dist/webapp /usr/share/nginx/html