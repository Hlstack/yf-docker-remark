FROM node:8.11.1

WORKDIR /app

ADD ./yf-ruiwei-server /app
RUN npm install -g yarn
RUN yarn
EXPOSE 9994
CMD ["yarn", "run", "dev"]
