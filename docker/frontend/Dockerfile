FROM node:latest

# Create app directory
WORKDIR /app
ADD . /app/

# global install & update
RUN npm i npm && npm i yarn

ENV HOST 0.0.0.0
EXPOSE 3000
