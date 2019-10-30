# Build and Run it Again

`docker build -t webserver .`{{execute}}

`docker run -d -p 8090:80 --name www1 webserver`{{execute}}

Verify the updated output with curl:

`curl localhost:8090`{{execute}}

or access it through: https://[[HOST_SUBDOMAIN]]-8090-[[KATACODA_HOST]].environments.katacoda.com/