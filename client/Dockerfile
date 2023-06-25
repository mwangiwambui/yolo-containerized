# Get the base node image
FROM node:16.1-alpine

LABEL maintainer="Wambui Mwangi <naomi.wambui@student.moringaschool.com>"

RUN mkdir -p /app/client/

WORKDIR /app/client/

COPY package*.json /app/client/

# Install dependencies
RUN npm install --omit=dev

COPY . /app/client/

CMD ["npm","start"]