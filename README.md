Dockerized GHCJS Compiler
=========================

This repository aims to provide useful Docker images to build a GHCJS application.

* Dockerfiles: https://github.com/y-taka-23/docker-stack-ghcjs
* Images: https://hub.docker.com/r/ytaka23/stack-ghcjs/

So far the images are built by not AUTOMATED BUILD but manual work.
It because building GHCJS compiler consumes so large amount of resources (time/RAM)
that we cannnot accomplish the build within the Docker Hub's limit.

Example
-------

Let's build a simple "Hello World" application in GHCJS.

```console
git clone https://github.com/y-taka-23/docker-stack-ghcjs
cd docker-stack-ghcjs/example
docker build --tag stack-ghcjs-example .
```

The Dockerfile builds JavaScript files and deploys them into an Nginx image.
Note that, the GHCJS images are terribly huge (around 10 GB,) so it takes a long time to pull them.

```console
docker run -d -p 8080:80 stack-ghcjs-example
```

Open [http://localhost:8080](http://localhost:8080),
and you can see `putStrLn` in Haskell is compiled to `console.log()` in JavaScript.

Todo: screenshot here.
