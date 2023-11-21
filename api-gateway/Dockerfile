FROM node:16.19-alpine

WORKDIR /usr/src/app

RUN apk add --no-cache git

RUN git clone "https://github.com/Neography7/questr-gateway.git" .

RUN npm install

ENV NODE_ENV=production
ENV AUTH_SERVICE=localhost:5001
ENV USER_SERVICE=localhost:5002
ENV QUESTION_SERVICE=localhost:5003

EXPOSE 1000 5000

CMD ["npm", "start"]
