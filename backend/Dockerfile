
FROM node:13-alpine

LABEL maintainer="Simon Okello <simon.okello@studentmoringaschool.com>"

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 5000

CMD ["npm", "start"]