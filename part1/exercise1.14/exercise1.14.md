# 1.14: Environment

frontend Dockerfile:
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
RUN npm install && REACT_APP_BACKEND_URL=http://localhost npm run build

CMD ["serve","-s","-l","5000","build"]
```

backend Dockerfile:
```
FROM debian:stable-slim
EXPOSE 8080
WORKDIR /backend

# install prerequisites
RUN apt-get update && apt-get install -y curl
RUN rm -rf /usr/local/go && curl -sL https://golang.org/dl/go1.15.10.linux-amd64.tar.gz | tar -C /usr/local -xzf -
ENV PATH=$PATH:/usr/local/go/bin

# copy the project to the image
COPY . .

# build the project
RUN go build

ENV REQUEST_ORIGIN=http://localhost:5000
CMD ["./server"]
```

Commands:
```
$ docker run -it -p 80:8080 example-backend

$ docker run -it -p 5000:5000 example-frontend
```

