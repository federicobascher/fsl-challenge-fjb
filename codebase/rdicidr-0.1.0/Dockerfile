FROM node:15 as builder

WORKDIR codebase/rdicidr-0.1.0

COPY package*.json ./

RUN npm install

COPY ..
 
RUN npm run build

FROM ngnix:alpine

COPY --from=builder /app/build /usr/share/ngnix/html

EXPOSE 80

CMD ["ngnix", "-g", "daemon off;"]

 