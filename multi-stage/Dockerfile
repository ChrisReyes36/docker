FROM node:20-alpine AS dependencies

WORKDIR /app

COPY package.json ./

RUN npm install

FROM node:20-alpine AS builder

WORKDIR /app

COPY --from=dependencies /app/node_modules ./node_modules

COPY . .

RUN npm run test

FROM node:20-alpine AS production-dependencies

WORKDIR /app

COPY package.json ./

RUN npm install --omit=dev

FROM node:20-alpine AS runner

WORKDIR /app

COPY --from=production-dependencies /app/node_modules ./node_modules

COPY app.js ./

COPY tasks/ ./tasks

CMD [ "node", "app.js" ]
