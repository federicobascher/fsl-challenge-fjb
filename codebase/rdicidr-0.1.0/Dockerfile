FROM node:15 as builder

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .
 
RUN npm run build

FROM nginx:alpine

COPY --from=builder /app/build /usr/share/ngnix/html

EXPOSE 80

CMD ["ngnix", "-g", "daemon off;"]

 