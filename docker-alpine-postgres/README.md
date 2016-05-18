# PostgreSQL docker image based on Alpine Linux

Based on the following image, except with su-exec and using standard postgres (not edge)

   [Click here to see it's DockerHub homepage](https://hub.docker.com/r/kiasaki/alpine-postgres/)

# Usage

Read the README from kiasaki's repo for details.  Here's the condensed version if everything goes as planned:

1. Create a new named volume
```
$ docker volume create --name newpgdata
```
2. Build the image (or use 'make build')
```
docker build -t alpine-postgres --rm=true .
```
3. Run the image
```
docker run -p 5432:5432 -v newpgdata:/var/lib/postgresql/data -e POSTGRES_PASSWORD=mysecretpassword alpine-postgres
```
3. OR Run the image as a daemon
```
docker run -d -p 5432:5432 -v newpgdata:/var/lib/postgresql/data -e POSTGRES_PASSWORD=mysecretpassword alpine-postgres
```

See kiasaki's readme for details on linking containers

# License

MIT. See `LICENSE` file.
