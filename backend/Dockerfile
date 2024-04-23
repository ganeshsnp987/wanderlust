#Stage1*************************************************
FROM node:21 AS backend-builder

#Setup working dir
WORKDIR /app

COPY . .

RUN npm i

#Stage2***************************************************
FROM node:21-slim

WORKDIR /app

#Copy above stage as compressed
COPY --from=backend-builder /app . 

COPY .env.sample .env

#Port
EXPOSE 5000

#App
CMD ["npm", "start"]


