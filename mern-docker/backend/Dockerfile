FROM node:20-alpine

RUN addgroup app && adduser -S -G app app

# create /app and give it to the app user so it can write here
RUN mkdir /app && chown app:app /app
WORKDIR /app

USER app

COPY --chown=app:app package*.json ./

RUN npm install

COPY --chown=app:app . .

EXPOSE 8000

CMD npm start