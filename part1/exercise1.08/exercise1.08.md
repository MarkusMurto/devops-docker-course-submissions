# 1.8: Image for script

Dockerfile:
```
FROM ubuntu:18.04
COPY script.sh .
RUN apt-get update -y && apt-get install -y curl
CMD ./script.sh
```

Commands:
```
$ docker build . -t curler

$ docker run -it curler
Input website
helsinki.fi
Searching...
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```

