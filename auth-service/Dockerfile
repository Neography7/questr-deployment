FROM node:16.19-alpine

WORKDIR /usr/src/app

RUN apk add --no-cache git

RUN git clone "https://github.com/Neography7/questr-auth-srvc.git" .

RUN npm install

ENV NODE_ENV=production
ENV JWT_SECRET=
ENV USER_SERVICE=localhost:5002

EXPOSE 5001

CMD ["npm", "start"]
