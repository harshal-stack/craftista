FROM node:16 as bulider
WORKDIR /app
COPY . .
RUN npm install

FROM node:16-alpine
WORKDIR /final_app
COPY --from=bulider /app .
EXPOSE 3000
CMD ["npm","app.js"]
