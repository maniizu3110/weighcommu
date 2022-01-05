FROM node:16-alpine3.12
WORKDIR '/app'
COPY ./package.json ./
COPY ./yarn.lock ./
COPY ./nuxt.config.js ./
ENV HOST=0.0.0.0

RUN yarn install
COPY . .
RUN yarn build
CMD ["yarn","start"]