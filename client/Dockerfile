FROM node:18 AS builder

WORKDIR /app

COPY package*.json ./

COPY . .

RUN npm install

FROM node:18-alpine

WORKDIR /app

COPY --from=builder /app .

EXPOSE 5173

ENV HOST = 0.0.0.0

CMD ["npm", "run", "dev", "--", "--host"]
