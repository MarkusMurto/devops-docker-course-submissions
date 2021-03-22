# 1.16: Heroku

Link to the released heroku app: https://murtotest-heroku-example.herokuapp.com/

Commands:
```
$ docker pull devopsdockeruh/heroku-example

$ heroku login
$ docker tag devopsdockeruh/heroku-example registry.heroku.com/murtotest-heroku-example/web
$ heroku container:login

$ docker push registry.heroku.com/murtotest-heroku-example/web

$ heroku container:release web -a murtotest-heroku-example
```

