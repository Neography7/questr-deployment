FROM node:16.19-alpine

WORKDIR /usr/src/app

RUN apk add --no-cache git 

RUN git clone "https://github.com/Neography7/questr-question-srvc.git" .

RUN npm install

ENV NODE_ENV=production
ENV USER_SERVICE=localhost:5002
ENV MONGODB_URL=mongodb://localhost:27017/questr_questions

EXPOSE 5003

CMD ["npm", "start"]