# 1.4: Missing dependencies

```
$ docker run -d -it --name looper ubuntu

$ docker exec -d -it looper sh -c 'apt-get -y update'

$ docker exec -d -it looper sh -c 'apt-get install -y curl'

$ docker exec -it looper sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```

