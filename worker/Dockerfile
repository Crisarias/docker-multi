#Use an existing docker image as a base
FROM node:alpine

#Copy files
WORKDIR /app
COPY ./package.json ./

#Download and install a dependency
#RUN npm config set proxy http://proxy-chain.intel.com:911
#RUN npm config set https-proxy http://proxy-chain.intel.com:911
RUN npm install

#Copy files
COPY . .


#Tell the image what to do when it starts
#as a container
CMD ["npm", "run", "start"]