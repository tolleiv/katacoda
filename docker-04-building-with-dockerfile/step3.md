# Run an image

Now we have an image created from `Dockerfile`, we'll run it.

`docker run -d -p 8080:80 --name www webserver`{{execute}}

Verify the output with curl:

`curl localhost:8080`{{execute}}

or access it through: https://[[HOST_SUBDOMAIN]]-8080-[[KATACODA_HOST]].environments.katacoda.com/