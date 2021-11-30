# docker-scratch

For someone want to solve this:

```console
$ docker run -d \
    -v /path/to/target:/app \
    -w /app
    scratch \
    ./main

Unable to find image 'scratch:latest' locally
docker: Error response from daemon: 'scratch' is a reserved name.
See 'docker run --help'
```

Now you could do this instead:

```sh
$ docker run -d \
    -v /path/to/target:/app \
    -w /app
    sstc/scratch \
    ./main
```
