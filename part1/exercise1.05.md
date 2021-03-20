# 1.5: Sizes of images

```
$ docker pull devopsdockeruh/simple-web-service:alpine

$ docker images
REPOSITORY                          TAG       IMAGE ID       CREATED       SIZE
devopsdockeruh/simple-web-service   ubuntu    4e3362e907d5   5 days ago    83MB
devopsdockeruh/simple-web-service   alpine    fd312adc88e0   5 days ago    15.7MB

$ docker run -d -it --name looper devopsdockeruh/simple-web-service:alpine

$ docker exec -it looper sh

# tail -f text.log
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```

The Alpine image is much smaller.
