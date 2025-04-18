
[[Open Container Initiative]]


## Login

Authenticate with docker hub.
```
docker login
```


## Building image

Use -t to tag the image

```
docker image build -t [username]/[name:tag] .

docker build -t terryjmitchell/gsd:ctr2025 .
```

- username:  Docker Hub ID
- name: repo
- tag: image version


## List Images

```
docker image ls
```


## Delete Image

```
docker image rm [username]/[name:tag]

docker image rm terryjmitchell/gsd:ctr2025
```


## Push Image

```
docker image push [username]/[name:tag]

docker image push terryjmitchell/gsd:ctr2025
```


### Build and Push Image

```
docker buildx build --platform linux/arm64/v8,linux/amd64 --push --tag terryjmitchell/gsd:ctr2025 .
```


## Run Container

```
docker container run -d --name web -p 8000:8080 terryjmitchell/gsd:ctr2025
```

- `-d` flag runs container in background detached from terminal, good for web server, background processor

### Interactive

```
docker container run -it --name test alpine
```

- starts container and switches terminal to interactive ssh session
- `exit` will exit ssh and also stop container because no more work
- `ctrl+p+q` will exit but leave container running
## Stop Container

```
docker container stop web
```


## Start Container

```
docker container start web
```

## List Containers

```
docker container ls
docker container ls -a
```


## Delete Container
Needs to be stopped first

```
docker container rm web
```

Can force removal
```
docker container rm web -f
```



## Learning To Do

[Docker Deep Dive](https://app.pluralsight.com/library/courses/docker-deep-dive-2023)


