#Docker file by RahulSaini :)
FROM node:18-alpine AS artifact
WORKDIR /app
COPY package*.json .
RUN npm install
COPY . .
RUN npm run build
#Second stage of image creation
FROM nginx:alpine
COPY --from=artifact /app/dist /usr/share/nginx/html/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
#Docker file end here 
