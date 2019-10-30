# Build it !

We can build a docker image by executing `docker build -t webserver .`{{execute}} .

The docker build command builds an image from a `Dockerfile` and a context. The build’s context is the files at a specified location PATH or URL. The PATH is a directory on your local filesystem. The URL is a Git repository location.

The Docker daemon runs the instructions in the Dockerfile one-by-one, committing the result of each instruction to a new image if necessary, before finally outputting the ID of your new image.

View the stored images on your host:

`docker images`{{execute}}