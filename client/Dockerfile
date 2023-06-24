# Get the base node image
FROM node:16.1-alpine

LABEL maintainer="Wambui Mwangi <naomi.wambui@student.moringaschool.com>"

RUN mkdir -p /app

WORKDIR /app

COPY package*.json /app/

# Install dependencies
RUN npm ci

COPY . /app/

CMD ["npm","start"]