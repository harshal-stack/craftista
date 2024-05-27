FROM node:16 as bulider
WORKDIR /app
COPY package*.json .
RUN npm install
COPY . .


FROM node:16-alpine
WORKDIR /final_app
COPY --from=bulider /app .
EXPOSE 3000
CMD ["node","app.js"]
