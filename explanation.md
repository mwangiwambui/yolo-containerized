# 1. choice of base image

I chose alpine as my base image as it small, security-oriented, lightweight 

# 2.Dockerfile directives used in the creation and running of each container
Define base image
FROM node:alpine

Define working directory for the client application
WORKDIR /app/client

Copy package and package-lock.json to the working directory
COPY ./client/package*.json ./


copy rest of the app to the working directory
COPY ./client .

Install dependencies 
RUN npm install

expose port 3000
EXPOSE 3000

Define entry point
CMD [ "npm", "start" ]

Define working directory for the backend application
WORKDIR /app/backend

Copy package and package-lock.json to the working directory
COPY ./backend/package*.json ./


copy rest of the backend to the working directory
./backend .

Install dependencies 
RUN npm install

expose port 5000
EXPOSE 5000

Define entry point
CMD [ "npm", "start" ]

# 3.Docker-compose Networking (Application port allocation and a bridge network implementation) 
The backend application was allocated port 5000, while the fronted application was allocated port 3000.
Both applications use a common network called yolo-app that was defined under the bridge driver.

# 4. Docker-compose volume definition and usage (where necessary).
mongo_db was the volume used to persist the db data once its shut down.

# 5. Git workflow used to achieve the task.
git add . (to stage the changes)
git commit -m '<message>' (to commit the changes and labelling with the appropriate messages)
git push origin master (to push to my forked app repo)

# 6. Good practices such as Docker image tag naming standards for ease of identification of images and containers. 

tagged my image according to semver conventions
- backend image = yomziee/yolo-client:1.0
- client image = yomziee/yolo-backend:1.0
- mongo image = mongo:latest

# 7.Successful running of the applications and if not, debugging measures applied.
failed to connect to mongo server successfully
tried to reconfigure the server.js file with the correct credentials, yet to succeed

# 8. Successfully pushed to all images to dockerhub