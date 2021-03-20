# 1.12: Hello, frontend!

Commands:
```
$ git clone --depth 1 https://github.com/docker-hy/material-applications.git

$ cd material-applications/example-frontend/
```

Dockerfile:
```
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
RUN npm install && npm run build

CMD ["serve","-s","-l","5000","build"]
```

Commands:
```
$ docker build . -t example-frontend

$ docker run -it -p 5000 example-frontend
```

