FROM node:14 AS build

WORKDIR /app

# 라이브러리 설치에 필요한 파일만 복사
COPY package.json .
COPY package-lock.json .

# 라이브러리 설치
RUN npm ci

# 소스코드 복사
COPY . /app

# 소스코드 빌드
RUN npm run build

FROM nginx:1.21.4-alpine
COPY nginx.conf /etc/nginx/conf.d/default.conf.template
ENV BACKEND_HOST leafy
ENV BACKEND_PORT 8080

COPY docker-entrypoint.sh /usr/local/bin
RUN chmod +x /usr/local/bin/docker-entrypoint.sh

COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80
ENTRYPOINT ["docker-entrypoint.sh"]
CMD ["nginx", "-g", "daemon off;"]
