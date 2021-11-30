# docker-scratch

For someone want to solve this:

```console
$ docker run -d \
    -v /bin:/app \
    -w /app
    scratch \
    app

Unable to find image 'scratch:latest' locally
docker: Error response from daemon: 'scratch' is a reserved name.
See 'docker run --help'
```

Now you could do this instead:

```sh
$ docker run -d \
    -v /bin:/app \
    -w /app
    sstc/scratch \
    app
```
