# FROM node:lts-alpine

# # install simple http server for serving static content
# RUN npm install -g http-server

# # make the 'app' folder the current working directory
# WORKDIR /app

# # copy both 'package.json' and 'package-lock.json' (if available)
# COPY package*.json ./

# # install project dependencies
# RUN npm install

# # copy project files and folders to the current working directory (i.e. 'app' folder)
# COPY . .

# # build app for production with minification
# RUN npm run build

# EXPOSE 8080
# CMD [ "http-server", "dist" ]



FROM node:10 as build

WORKDIR /app

COPY package*.json ./

RUN npm install

# COPY . .

# RUN npm run build

EXPOSE 8080

CMD ["npm", "run", "serve"]

# STEP 2

# FROM nginx:1.19.0-alpine AS prod-stage
# COPY --from=build /app/dist /usr/share/nginx/html
# EXPOSE 80
# CMD ["nginx","-g","daemon off;"]