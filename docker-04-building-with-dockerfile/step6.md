# Try it yourself
Change the following things:

Web content should contain `Docker is awesome!`

`Dockerfile` should an `ENTRYPOINT` with the default argument `-DFOREGROUND`

Validate

```
   docker run -it -p 80:80 -n my-web my-image

   # interactive shell in the container
   # verify hostname and envrionment is the id of the conainer
   hostname
   env
   df

   #check if apache is running
   ps -aufx
```

*Open second terminal*

Verify if you get your HTML text `Docker is awesome!`:

`curl localhost:80`{{execute}}

or access it through: https://[[HOST_SUBDOMAIN]]-80-[[KATACODA_HOST]].environments.katacoda.com/