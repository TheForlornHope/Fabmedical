FROM node:alpine AS base
RUN apk -U add curl
WORKDIR /usr/src/app
EXPOSE 3001

FROM node:argon AS build
WORKDIR /usr/src/app

# Install app dependencies
COPY package.json /usr/src/app/
RUN npm install

#bundle app source
COPY . /usr/src/app

FROM base AS final
WORKDIR /urs/src/app
COPY --from=build /usr/src/app .
CMD [ "npm, 'start' ]
