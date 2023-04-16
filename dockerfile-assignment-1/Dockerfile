# use this empty Dockerfile to build your assignment

# NOTE: The instructions are now in the README.md file in this directory.

#Use node official image with alpine 6.x branch
FROM node:6-alpine

#install tini
RUN apk add --no-cache tini

#create working directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

#Copy in pacakge.kson file
COPY package.json package.json

#Install depedencies and clean up cache
RUN npm install --production \
    && npm cache clean --force

#Copy all files from current directory into the image
COPY . .

#Open port 80
EXPOSE 80

#Run cmd
CMD ["/sbin/tini", "--", "node", "./bin/www"]
