# Get the base node image
FROM node:13-alpine

LABEL maintainer="Wambui Mwangi <naomi.wambui@student.moringaschool.com>"

RUN mkdir -p /app/client/

WORKDIR /app/client/

COPY package*.json /app/client/

# Install dependencies
RUN npm install

COPY . /app/client/

EXPOSE 3000

CMD ["npm","start"]