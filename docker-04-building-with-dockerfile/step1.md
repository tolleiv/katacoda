# Write Dockerfile
In this step we shall create Dockerfile.

Create a Dockerfile with following content in current directory. `cat > Dockerfile << EOF
FROM alpine:latest
RUN apk add --update apache2
EXPOSE 80
CMD ["/usr/bin/httpd", "-DFOREGROUND"]
EOF`{{execute}}

Verify the file: `cat Dockerfile`{{execute}}

Above Dockerfile content describes a `Alpine Linux` Docker image with Apache web server installed.

`FROM` indicates the base image for our build
Each `RUN` line will be executed by Docker during the build
Our `RUN` commands must be non-interactive. (You can‘t provide input to Docker during the build.)

The `EXPOSE` instruction informs Docker that the container listens on the specified network ports at runtime.

Here the `CMD` provides the defaults for the executing container.