FROM node:alpine as build

WORKDIR /app

ENV PATH /app/node_modules/.bin:$PATH

RUN apk --no-cache add git

RUN git clone "https://github.com/Neography7/questr-front.git" .

ENV VITE_BACKEND_URL=https://api.appquestr.com
ENV VITE_SOCKET_URL=https://socket.appquestr.com

RUN npm install
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/dist /usr/share/nginx/html

RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
# start the nginx web server
CMD ["nginx", "-g", "daemon off;"]