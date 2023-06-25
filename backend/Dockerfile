# Get the base node image
FROM node:14-alpine

LABEL maintainer="Wambui Mwangi <naomi.wambui@student.moringaschool.com>"

RUN mkdir -p /app/backend/
# Set the working directory to /backend
WORKDIR /app/backend/

# Copy all files to the working directory
COPY package*.json /app/backend/

# Install dependencies
RUN npm install

COPY . /app/backend/

CMD ["npm","start"]

