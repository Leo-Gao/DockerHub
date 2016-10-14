# Start with Node.js base image
FROM node
MAINTAINER Kai Arulkumaran <design@kaixhin.com>

RUN apt-get update -y
RUN apt-get install -y vim
RUN apt-get install -y curl

# Clone FGLab repo and move into it
RUN cd /root && git clone https://github.com/Leo-Gao/FGLab.git && cd FGLab && \
# npm install (with root)
  npm install --unsafe-perm && \
# Create .env with port
  echo "FGLAB_PORT=8080" > .env

RUN npm i mz

# Expose port
EXPOSE 80
EXPOSE 8080
EXPOSE 5080
# Set working directory
WORKDIR /root/FGLab
# Start server
ENTRYPOINT ["node", "lab"]
