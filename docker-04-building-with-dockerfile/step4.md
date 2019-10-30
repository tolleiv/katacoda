# Build a webapp image

We need to create a `index.html` file in html directory with following content.

`<!DOCTYPE html>
<html>
  <head>
    <title>This is a title</title>
  </head>
  <body>
    <p>Hello world!</p>
  </body>
</html>
`{{copy}}

Enhance our existing `Dockerfile` with following content.

`cat > Dockerfile << EOF
FROM alpine:latest
RUN apk add --update apache2
COPY html /var/www/html
EXPOSE 80
CMD ["/usr/sbin/httpd", "-DFOREGROUND"]
EOF`{{execute}}

Verify the Dockerfile: `cat Dockerfile`{{execute}}
Verify the html file: `cat html/index.html`{{execute}}

The `COPY` instruction copies new files or directories from and adds them to the filesystem of the container at the path