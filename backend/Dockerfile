# backend/Dockerfile
FROM node:18-alpine AS deps
WORKDIR /app
COPY package*.json ./
RUN npm ci --production

FROM node:18-alpine AS builder
WORKDIR /app
COPY . .
RUN npm ci

FROM node:18-alpine AS runtime
WORKDIR /app
ENV NODE_ENV=production
COPY --from=deps /app/node_modules ./node_modules
COPY --from=builder /app ./
EXPOSE 3000
CMD ["node", "server.js"]
