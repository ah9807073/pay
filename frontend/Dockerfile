FROM node:14
WORKDIR /app
COPY package*.json ./
RUN npm install react-scripts@4.0.3
COPY . .
RUN npm run build
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
