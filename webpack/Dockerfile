FROM node:9.7-alpine
LABEL maintainer="Nick Janetakis <nick.janetakis@gmail.com>"

RUN npm install -g yarn

WORKDIR /app/assets

COPY assets/package.json assets/*yarn* ./
RUN yarn install && cp yarn.lock /tmp

COPY . .

RUN chmod +x docker-entrypoint.sh
ENTRYPOINT ["/app/docker-entrypoint.sh"]

CMD ["yarn", "run", "build"]
