# 1.9: Volumes

```
$ docker run -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service:alpine
```

I had to create an empty `text.log` otherwise the bind mount will autocreate 
an directory called `text.log` which obviously will not work as writeable file.

