#Use an existing docker image as a base
FROM node:alpine as builder

#Copy files
WORKDIR /app
COPY ./package.json ./

#Download and install a dependency
#RUN npm config set proxy http://proxy-chain.intel.com:911
#RUN npm config set https-proxy http://proxy-chain.intel.com:911
RUN npm install

#Copy files
COPY . .
RUN npm run build


#Tell the image what to do when it starts
#as a container
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf 
COPY --from=builder /app/build /usr/share/nginx/html