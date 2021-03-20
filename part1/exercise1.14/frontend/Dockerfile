FROM debian:stable-slim
EXPOSE 5000
WORKDIR /frontend

# install prerequisites
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash
RUN apt install -y nodejs
RUN npm install -g serve

# copy the project to the image
COPY . .

# build
RUN npm install && REACT_APP_BACKEND_URL=http://localhost npm run build

CMD ["serve","-s","-l","5000","build"]
