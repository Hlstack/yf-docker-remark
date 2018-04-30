FROM node:8.11.1

WORKDIR /code
RUN npm install -g yarn
RUN npm install -g nodemon
ADD ./fpm-plugin-mysql /code

EXPOSE 9999
RUN ["yarn"]
CMD ["nodemon", "dev/dev.babel.js"]
