# 1.15: Homework

Link to the DockerHub repository:
https://hub.docker.com/r/markusmurto/potatotimer

## Docker build documentation

Cloning the project git repository:
```
$ git clone --depth https://github.com/mtijas/potato-timer.git

$ cd potato-timer
```

Dockerfile:
```
FROM python:3.7-slim-buster
WORKDIR /potaatti

# copy the project to the image
COPY . .

# run the setup and install
RUN python3 ./setup.py build && python3 ./setup.py install

# run the timer with the upstream default config
CMD ["potatotimer","-c","./config.yml"]
```

Building the image:
```
$ docker build . -t potatotimer
```

## Running the container:
```
$ docker run -it markusmurto/potatotimer

# or with your own config
$ docker run -it -v "path/to/your/config.yml:/potaatti/config.yml" markusmurto/potatotimer
```

