FROM node:14 AS build

WORKDIR /app

COPY . /app
RUN npm ci
RUN npm run build

FROM nginx:1.21.4-alpine

COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80
ENTRYPOINT ["nginx"]
CMD ["-g", "daemon off;"]
