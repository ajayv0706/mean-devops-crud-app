# frontend/Dockerfile
FROM node:18-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
# try both common build commands; one of them will run
RUN npm run build -- --prod || npm run build

FROM nginx:stable-alpine as runtime
# NOTE: adjust 'frontend' below if your dist folder name is different (see step 4)
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html
COPY nginx-static.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
