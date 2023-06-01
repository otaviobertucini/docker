FROM node:18-alpine as build

WORKDIR /home/app

COPY ./package.json ./
RUN npm install
COPY . .

CMD ["npm", "run", "build"]

FROM nginx as run
COPY --from=build /home/app/dist /usr/share/nginx/html