# 自己打包的镜像，包含Nodejs JDK
FROM jiangchuenjian/openapi-nodejs:1.02 as node

RUN mkdir -p /app
WORKDIR /app

COPY package.json ./
COPY yarn.lock ./

COPY . /app
RUN export NODE_OPTIONS="--max-old-space-size=8192"
RUN yarn install
ARG MODE
RUN yarn build-production

FROM nginx:1.16-alpine
COPY --from=node /app/dist/ /var/www/web/dist
ADD nginx.conf /etc/nginx/nginx.conf

EXPOSE 80
