FROM debian:stable-slim
EXPOSE 5000
WORKDIR /frontend

# install prerequisites
RUN apt-get update && apt-get install -y curl git
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash
RUN apt install -y nodejs
RUN npm install -g serve

# clone the project
RUN git clone --depth 1 --filter=blob:none --no-checkout https://github.com/docker-hy/material-applications.git
RUN cd material-applications && git checkout main -- example-frontend

# build
RUN cd material-applications/example-frontend && npm install && npm run build

CMD ["serve","-s","-l","5000","material-applications/example-frontend/build"]
