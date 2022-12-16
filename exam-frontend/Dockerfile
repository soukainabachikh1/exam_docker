#build environment
FROM node:12-alpine as build
WORKDIR /frontend-app
COPY ./package.json /frontend-app/package.json
COPY ./package-lock.json /frontend-app/package-lock.json
RUN npm install 
COPY . .
RUN npm run build

#production environment
FROM nginx:stable-alpine
COPY --from=build /frontend-app/build /usr/share/nginx/html
COPY ./nginx/nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]