# Stage 1: Build the application
FROM node:14 as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Stage 2: Create the production image
FROM nginx:alpine
COPY --from=build /app/out /usr/share/nginx/html
EXPOSE 80
