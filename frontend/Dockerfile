FROM node:22-alpine3.19 as build
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

FROM nginx:alpine as production
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]