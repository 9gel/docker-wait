`docker-wait` is a base image that you can use to create an image that

- blocks until a specified container and port is accepting TCP connection
- perform a task after that

The image is based on alpine:latest so you can take advantage `apk` to install
utilities.

To use:

- use 9gel/docker-wait as the base image `FROM 9gel/docker-wait` or your own fork
- create an entrypoint or command script
- in the script, call `sh /wait` before your command that requires some container to be up
- when you do `docker run` or in your `docker-compose.yml` define the environment variables:
  - `WAIT_ON_LINK` - the linked container to wait on
  - `WAIT_ON_PORT` - the port on that container to wait on

See `docker-compose.yml` and `example/` for an example.
