FROM node:10 AS build
WORKDIR /node
COPY . .
RUN npm install
RUN npm run build

FROM nginx:alpine
COPY --from=build /node/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]






