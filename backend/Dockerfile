# Get the base node image
FROM node:14-alpine

LABEL maintainer="Wambui Mwangi <naomi.wambui@student.moringaschool.com>"

RUN mkdir -p /app
# Set the working directory to /backend
WORKDIR /app

# Copy all files to the working directory
COPY package*.json /app/

# Install dependencies
RUN npm install

COPY . /app/

CMD ["npm","start"]