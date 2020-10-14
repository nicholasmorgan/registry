# Docker Image which is used as foundation to create
# a custom Docker Image with this Dockerfile
FROM node:12-slim
  
# Copies package.json and package-lock.json to Docker environment
COPY . .
 
# Installs all node packages
RUN yarn install --no-cache --production=true && \
    yarn run build && \
    yarn global add serve
 
# Uses port which is used by the actual application
EXPOSE 3000
 
# Finally runs the application
CMD ["serve", "-s", "build", "-l", "3000"]