FROM node:16.18-alpine
WORKDIR /backend
COPY ["package.json", "package-lock.json", "./"]
RUN npm install
COPY . .
EXPOSE 5000
CMD [ "node", "server.js"]



