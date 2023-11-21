FROM node:16.19-alpine

WORKDIR /usr/src/app

RUN apk add --no-cache git

RUN git clone "https://github.com/Neography7/questr-user-srvc.git" .

RUN npm install

ENV NODE_ENV=production

ENV S3_ACCESS_KEY=
ENV S3_SECRET_KEY=
ENV S3_REGION=
ENV S3_BUCKET=

ENV MONGODB_URL=mongodb://localhost:27017/questr_users

EXPOSE 5002

CMD ["npm", "start"]