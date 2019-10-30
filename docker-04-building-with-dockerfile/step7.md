# Parameterize builds

The `ARG` instruction defines a variable that users can pass at build-time to the builder with the `docker build` command using the `--build-arg <varname>=<value>` flag.

Enhance our existing `Dockerfile` with following content.

`cat > Dockerfile << EOF
FROM alpine:latest
RUN apk add --update apache2
COPY html /var/www/html
EXPOSE 80
ARG DATA
RUN echo $DATA > /var/www/html/data.txt
CMD ["/usr/bin/httpd", "-DFOREGROUND"]
EOF`{{execute}}

Build it with the argument:

`docker build -t webserver --build-arg DATA="Hello Data!" .`{{execute}}

And run it to check the results:

`docker run -d -p 8070:80 --name www2 webserver`{{execute}}

Verify the updated output with curl:

`curl localhost:8070/data.txt`{{execute}}

or access it through: https://[[HOST_SUBDOMAIN]]-8070-[[KATACODA_HOST]].environments.katacoda.com/data.txt