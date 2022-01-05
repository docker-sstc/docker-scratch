# docker-scratch

For someone want to solve this:

```console
$ docker run --rm \
    -v /path/to/target:/app \
    -w /app
    scratch \
    ./main

Unable to find image 'scratch:latest' locally
docker: Error response from daemon: 'scratch' is a reserved name.
See 'docker run --help'
```

Now you could do this instead:

```bash
docker run --rm \
    -v /path/to/target:/app \
    -w /app
    sstc/scratch \
    ./main
```

## Timezone for Golang

```bash
docker run --rm \
    -v /usr/share/zoneinfo:/usr/share/zoneinfo:ro \
    -e TZ=Asia/Taipei \
    -v /path/to/target/main:/app/main \
    -w /app
    sstc/scratch \
    ./main
```

## Cross compiling

```bash
# go
CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build main.go

# rust
cargo build --target x86_64-unknown-linux-musl --release
```
