# Build a webapp image

We need to create a `index.html` file in html directory with following content.

<pre class="file" data-filename="html/index.html" data-target="replace">&#x3C;!DOCTYPE html&#x3E;
&#x3C;html&#x3E;
  &#x3C;head&#x3E;
    &#x3C;title&#x3E;This is a title&#x3C;/title&#x3E;
  &#x3C;/head&#x3E;
  &#x3C;body&#x3E;
    &#x3C;p&#x3E;Hello world!&#x3C;/p&#x3E;
  &#x3C;/body&#x3E;
&#x3C;/html&#x3E;
</pre>

Enhance our existing `Dockerfile` with following content.

`cat > Dockerfile << EOF
FROM alpine:latest
RUN apk add --update apache2
COPY html /var/www/localhost/htdocs
EXPOSE 80
CMD ["/usr/sbin/httpd", "-DFOREGROUND"]
EOF`{{execute}}

Verify the Dockerfile: `cat Dockerfile`{{execute}}
Verify the html file: `cat html/index.html`{{execute}}

The `COPY` instruction copies new files or directories from and adds them to the filesystem of the container at the path